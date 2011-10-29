# coco-mode for xyzzy

CoffeeScriptの方言[Coco](http://satyr.github.com/coco/)用メジャーモード

## インストール
- NetInstallerよりインストール
  [package.l](http://youz.github.com/xyzzy/package.l) を登録し、パッケージ`*scrape*`よりインストールして下さい。
- 手動インストール
  ページ上部Downloadリンクよりソース一式をダウンロードし、アーカイブ内の
  coco-mode.lを`*load-path*`に配置してください。


## node.js と Cocoのインストール
ソースのコンパイル、実行、インタラクティブ実行を行うにはnode.jsとCocoの
インストールが必要です。

- [node.js](http://nodejs.org/)
- [Coco](https://github.com/satyr/Coco)

## .xyzzy設定例

   (require "coco-mode")
   (setq coco:*command-path* "c:/path/to/node.exe c:/path/to/coco/lib/command.js"
         coco:*compiled-buffer-mode* 'jscript-mode)
   (push '("\\.co\\(ffee\\)?$" . ed:coco-mode) *auto-mode-alist*)

- `coco:*command-path*` -> cocoのコマンドライン実行用パス
- `coco:*compiled-buffer-mode*` -> コンパイル結果のJavaScriptソース表示用バッファのメジャーモード

## キーバインド

- C-c l -- list-function (関数一覧表示)
- C-c r -- evaluate-buffer (バッファ全体の内容をCocoで実行し、結果を表示)
- C-c R -- evaluate-region (リージョンの内容をCocoで実行し、結果を表示)
- C-c c -- compile-buffer (バッファ全体の内容をJavaScriptにコンパイルし、結果を表示)
- C-c C -- compile-region (リージョンの内容をJavaScriptにコンパイルし、結果を表示)
- C-c i -- repl (CoffeeScriptのreplを起動)
- C-c I -- rcpl (CoffeeScriptインタラクティブコンパイラを起動)
- C-c C-x r -- evaluate-buffer-in-repl (バッファ全体の内容をrepl上で評価)
- C-c C-x C-r -- evaluate-buffer-in-repl (リージョンの内容をrepl上で評価)
- C-c C-x c -- compile-buffer-in-rcpl (バッファ全体の内容をrcpl上で評価)
- C-c C-x C-c -- compile-region-in-rcpl (リージョンの内容をrcpl上で評価)
- TAB -- indent-or-dabbrev-expand

### repl バッファ用キーバインド
- C-j -- 改行
- TAB -- indent-or-dabbrev-expand

他は`*shell-mode-map*`と同じ

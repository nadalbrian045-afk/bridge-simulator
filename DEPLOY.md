# GitHub Pages 公開手順（チーム共有用URLを作る）

フラッシュ暗算アプリでやったのと同じ方式です。`index.html` を1枚置くだけなので簡単です。

## 方法1：ブラウザだけで完結（一番簡単）

1. GitHubにログインし、右上の「+」→「New repository」
2. リポジトリ名を入力（例：`bridge-simulator`）、Public を選択して「Create repository」
3. 作成後の画面で「uploading an existing file」リンクをクリック
4. この `index.html` をドラッグ＆ドロップ →「Commit changes」
5. リポジトリの「Settings」→左メニュー「Pages」
6. 「Branch」を `main` / `/(root)` にして「Save」
7. 数分待つと `https://<ユーザー名>.github.io/bridge-simulator/` で公開される
8. このURLをチームに送れば全員がPC・スマホで開ける

## 方法2：コマンドライン（Claude Code / ターミナル）

```bash
cd bridge-project
git init
git add index.html
git commit -m "Add bridge simulator"
git branch -M main
git remote add origin https://github.com/<ユーザー名>/bridge-simulator.git
git push -u origin main
```

その後、GitHubのリポジトリ Settings → Pages で `main` / root を選んで Save。

## 更新したいとき

`index.html` を差し替えて再度アップロード（またはgit push）すれば、
同じURLのまま内容が更新されます。

## 注意
- リポジトリを Public にしないと GitHub Pages は使えません（無料プランの場合）。
- 公開URLは誰でもアクセスできます。コンテスト前に手の内を広く見せたくない場合は、
  URLを知っている人だけに共有する運用にするか、方法として単一HTMLファイルを
  直接メンバーに配る方法（index.htmlをそのまま送る）でもOKです。

# GARNET RESIDENCE 京都辰巳 更新進捗管理

不動産事業部内で更新進捗（4部屋 × 10項目）を共有するための静的ページです。
金額・滞納等の詳細情報は載せていません（進捗ステータスのみ）。

## セットアップ手順（GitHubアカウントをお持ちの方が実施）

### 1. リポジトリを作成
1. https://github.com/new を開く
2. Repository name（例: `garnet-tatsumi-renewal`）を入力
3. Public を選択
4. 「Create repository」をクリック

### 2. ファイルをアップロード
1. 作成したリポジトリのページで「uploading an existing file」をクリック
2. この3ファイル（`index.html`, `data.json`, `README.md`）をドラッグ＆ドロップ
3. 「Commit changes」をクリック
   - コマンドライン（git）を使える方は、`git init` して `git remote add origin ...` → `git push` でも構いません。

### 3. GitHub Pagesを有効化
1. リポジトリの「Settings」→ 左メニューの「Pages」
2. 「Build and deployment」の Source を「Deploy from a branch」に設定
3. Branch を `main` / `/ (root)` に設定して「Save」
4. 数分待つと、ページ上部に公開URL（`https://ユーザー名.github.io/リポジトリ名/`）が表示されます

このURLを不動産事業部メンバー3名に共有すれば、誰でも閲覧できます（GitHubアカウント不要）。

## 進捗を更新する方法（編集モード）

閲覧だけなら誰でもURLを開くだけでOKです。ステータスを更新したい場合のみ、以下が必要です。

1. ページ右上の「編集モードにする」をクリック
2. GitHubの Personal Access Token を求められるので入力
   - トークンの作り方: GitHubの Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token
   - Repository access は「Only select repositories」でこのリポジトリのみを選択
   - Permissions は「Contents: Read and write」のみ付与
   - 有効期限はなるべく短く設定することを推奨します
3. 入力したトークンはその端末のブラウザ内（localStorage）にのみ保存され、他の人やClaudeには送信されません
4. 各項目のバッジをクリックすると 未着手 → 進行中 → 完了 → 対象外 の順に切り替わり、自動的にリポジトリの `data.json` にコミットされます

編集は基本的にGitHubアカウントを持つ方（作成者）が行い、他のメンバーは閲覧のみ、という運用が最もシンプルです。他のメンバーもGitHubアカウントを作成し、コラボレーターとして招待すれば同様に編集できます。

## 注意点

- Publicリポジトリのため、このURLと`data.json`の中身（部屋番号・進捗ステータスのみ）は誰でも閲覧可能です
- 金額・滞納トラブル等の情報は意図的にこのページには含めていません。それらは引き続きチャット内のトラッカーで管理してください
- Personal Access Tokenは絶対にリポジトリのファイルやチャットに貼り付けないでください

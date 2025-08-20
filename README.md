# fastapi-starter

1. 仮想環境の作り方（Windows, PowerShell）

python -m venv .venv
. .\.venv\Scripts\Activate.ps1
deactivate   # 終了

2. ライブラリのインストールと保存

pip install fastapi "uvicorn[standard]"
pip freeze > requirements.txt

3. FastAPI の起動

uvicorn app.main:app --reload

4. Git 操作（基本5つ）

git clone <URL>   # 初回のみ
git pull          # 最新を取得
git add .         # 変更を追加
git commit -m "メッセージ"
git push          # GitHubへ反映

5. よくあるトラブルと解決

Author identity unknown →
git config --global user.name "YourName"
git config --global user.email "you@example.com"
PowerShellで仮想環境有効化できない →
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned




## 開発環境の準備（Windows, PowerShell）

1. clone
```powershell
git clone https://github.com/<team>/<repo>.git
cd <repo>

venv作成 & 有効化
python -m venv .venv
. .\.venv\Scripts\Activate.ps1


依存ライブラリ
pip install -r requirements.txt

サーバ起動
uvicorn app.main:app --reload

Gitの使い方（最低限）
作業前：git pull
作業後：git add . → git commit -m "メッセージ" → git push


---

✅ まとめ  
- **共有するなら README.md** に書く  
- **自分専用なら MEMO.md / OneNote / 紙**  
- 内容は「仮想環境」「pip」「FastAPI起動」「Gitの流れ」の4セット  

---

👉 質問です：  
このメモは **チーム全員に共有する想定（README.md）** にしたいですか？  
それとも **まずは自分用（MEMO.mdやノート）** に残すイメージですか？




## Git 初期セットアップ & 運用ルール

### 1. 初回セットアップ（PCごとに一度だけ）

1. Git インストール確認  
```powershell
git --version
ユーザー情報を設定（GitHubアカウントと同じメール推奨）

powershell
コードをコピーする
git config --global user.name "YourName"
git config --global user.email "you@example.com"
2. リポジトリの取得（clone）
チームのリポジトリを最初に手元にコピーします：

powershell
コードをコピーする
git clone https://github.com/<team>/<repo>.git
cd <repo>
⚠️ clone は「最初の1回だけ」。
2回目以降は pull で最新化します。

3. 開発の基本ワークフロー
(1) 作業前に最新化
powershell
コードをコピーする
git pull
(2) 作業（編集・ファイル追加など）
(3) 変更をステージ
powershell
コードをコピーする
git add .
(4) コミット（ローカル履歴を作成）
powershell
コードをコピーする
git commit -m "feat: 機能追加の説明"
(5) プッシュ（GitHubへ共有）
powershell
コードをコピーする
git push
4. よくある注意点
ライブラリを追加したら必ず requirements.txt を更新

powershell
コードをコピーする
pip freeze > requirements.txt
git add requirements.txt
git commit -m "chore: update dependencies"
git push
GitHubから取得したい時

powershell
コードをコピーする
git pull
無視するファイルは .gitignore に記載済み

.venv/, __pycache__/, app.db, .env, .idea/ など

✅ まとめ

clone は最初の1回

pull → 作業 → add → commit → push の流れを繰り返す

ライブラリ追加時は requirements.txt を更新して push

yaml
コードをコピーする

---

これを README.md に貼っておけば、**初めて参加する人でも「環境の作り方」と「Gitの流れ」が一目で分かる**状態になります。  

👉 質問です：README に「仮想環境の立ち上げ手順（venv）」も一緒に書きますか？  
（Gitだけでなく、clone直後に `python -m venv .venv` から始められるようにすると完璧です）

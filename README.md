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

# 概要
Dev Containers を用いた Zenn 記事作成用環境のテンプレートです。  
使い方は Zenn にて紹介しています。  
[解説記事](https://zenn.dev/trifolium/articles/5e7cd43586b68a)   

下記では最低限の使用方法のみ記載しています。  

# セットアップ
SSH の設定をローカルにて行います。  

```powershell:PowerShell
# SSHエージェントサービスを自動起動に設定
Set-Service ssh-agent -StartupType Automatic
# SSHエージェントサービスを開始
Start-Service ssh-agent
# 登録されている秘密鍵を確認
ssh-add -l
# .ssh 直下にある秘密鍵を登録（例: ~/.ssh/id_ed25519）
ssh-add
# 特定の秘密鍵を指定して登録する場合
ssh-add ~/.ssh/GitHub/id_ed25519
```

本テンプレートをローカルにダウンロードします。  

GitHub レポジトリを作成し、Zenn との連携を行います。  
[Zenn 公式記事 アカウントにGitHubリポジトリを連携してZennのコンテンツを管理する](https://zenn.dev/zenn/articles/connect-to-github)  

VSCode で記事執筆用のディレクトリを開き、コマンドパレットから `Rebuild Container Without Cache and Reopen in Container` を選択します。  
※拡張機能を Active にするために、初回はコンテナに入りなおすことを推奨します。  

コンテナ内で Zenn CLI の初期化処理をします。  

```:sh
npx zenn init
```

これでセットアップ完了です。  

# Zenn CLI

* [📘 How to use](https://zenn.dev/zenn/articles/zenn-cli-guide)    

# チートシート

```
# 記事作成
# slug_name ^[a-z0-9_-]{12,50}$
npx zenn new:article --slug name
```

```
# ブラウザでのプレビュー
npx zenn preview
```

ブラウザでのプレビュー  
[localhost:8000](localhost:8000)  

`Ctrl + Alt + V` で画像を貼り付け  

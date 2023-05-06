# DockerHub

DockerHubにコンテナイメージを置く手順。

Local -> DockerHub

1. イメージを作成する。
2. タグをつける。 `nerdctl tag app USERNAME/app:latest`
3. ログインする。 `nerdctl login (enter github username & password)`
4. プッシュする。 `nerdctl push USERNAME/app:latest`

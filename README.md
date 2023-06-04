# FE + FB + Keycloak

## Github Workflow

GitHub -> Artifact Registry

- front-end-app
- back-end-app
- keycloak

## CI&CD

TODO!()

## クラスタへのデプロイ手順

### 1. デプロイ対象をコンテナレジストリに登録する

1. FE
2. BE
3. Keycloak

各デプロイ対象をコンテナ化してコンテナレジストリに登録する。
Google CloudのArtifact Registryに登録する。

### 2. クラスタとリソースを作成する

いずれかのクラスタ環境が必要。
ローカルの開発用として「Rancer Desktop(k3s)」を使用」を使用する。

必要なリソース(アプリ用とKeycloak用でそれぞれ必要):

- namespace
- service
- deployments

### 3. 必要なセットアップ

1. Rancher Desktop
2. helmfile
3.

#### 3-1. Rancher Desktop

##### cluster(k3s)

クラスタは「rncher-desktop」を開発用として使用。
そのほかのリソースは作成する。
設定不要。
kubectlを使用。

##### containderd

Rancher Destktopに同梱されている。
設定不要。
nerdctlを使用。

##### helm

Rancher Destktopに同梱されている。
設定不要。
helmコマンドを使用。

#### 3-2. helmfile

helmfileはhomebrewでインストールが必要。
設定不要。
helmfileコマンドを使用。

#### 各種CLI

1. kubectl
2. nerdctl
3. gcloud

``` shell
helm upgrade --install keycloak codecentric/keycloakx -f values.yaml --namespace keycloak

helm upgrade keycloak codecentric/keycloakx -f values.yaml --namespace keycloak

helmfile -f helmfile-keycloak.yaml apply

helmfile -f helmfile-keycloak.yaml destroy

cat 278c9edda242a0c7efeea80804b5164f43421015 | docker login -u _json_key --password-stdin https://us-west1-a-docker.pkg.dev

WARNING! Your password will be stored unencrypted in /home/<USERNAME>/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
```

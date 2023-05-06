# Artifact Registry

未完成
Google Cloud Artifact Registryにコンテナイメージを置く場合の手順。

1. レジストリを作成する。
2. 認証を構成する。

   ``` shell
   # Cloud Shell
   gcloud auth configure-docker us-west1-docker.pkg.dev
   ```

3. tag付けする。

    ``` shell
    docker tag \
        TARGET_IMAGE:TAG \
        REGION_NAME-docker.pkg.dev/PROJECT_ID/REPOGITRY_NAME/IN_REPOGITRY_IMAGE_NAME:0.1


    ```

4. gcloudを認証する。ローカルターミナルからgcloudを使用する前に必要。

    ``` shell
    gcloud auth login
    ```

5. pushする

    ``` shell
    docker push \
        REGION_NAME-docker.pkg.dev/PROJECT_ID/REPOGITRY_NAME/IN_REPOGITRY_IMAGE_NAME:0.1

    docker push \
        us-west1-docker.pkg.dev/long-axle-323211/keycloak/keycloak-dev:18
    ```

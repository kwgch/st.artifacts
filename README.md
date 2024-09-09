# st.artifacts

## github codespacesでの動かし方

- AWS Webコンソールでbedrockの `Claude 3 Haiku` を有効化しておく
    - Amazon Bedrock -> メニュー（画面左上の3本線）の下のほうにある Bedrock configurations / モデルアクセス をクリック ->  ベースモデル / Anthropic / Claude 3 Haiku の「リクエスト可能」をクリック -> 「モデルアクセスをリクエスト」をクリック
- github上で「.」押してcodespacesを起動
- メニュー（画面左上の3本線） -> ターミナル -> 新しいターミナル -> 「Github Codespaces で作業を続ける」をクリック -> 2-core • 8GB RAM • 32GB を選択
- ターミナルが使えるようになるのを待つ
- 下記コマンドを実行してAWS CLIをインストール
    ```
    $ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
    $ unzip awscliv2.zip
    $ sudo ./aws/install
    ```
- AWS CLIの設定
    ```
    $ aws configure 
    AWS Access Key ID [None]: xxxx
    AWS Secret Access Key [None]: xxxxxx
    Default region name [None]: ap-northeast-1
    Default output format [None]: json
    ```
- poetryのインストール
    ```
    $ curl -sSL https://install.python-poetry.org | python3 -
    ```
- パッケージのインストール
    ```
    $ poetry install --no-directory
    ```
- streamlitの起動
    ```
    $ python -m streamlit run app.py
    ```
- 「ポート 8501 で実行されているアプリケーション は使用可能です。 」のpopupが画面右下に現れるので、「ブラウザで開く」をクリック
- プロンプト例
    - HTMLでログイン画面をつくって
    - HTMLとJavaScriptでブロック崩しゲームを作って
- 使い終わったら
  - https://github.com/codespaces を開く
  - 画面下の一覧から、使っていたcodespacesの右側の「...」をクリック -> `delete` を選択

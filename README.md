# ルートユーザーをMFAで保護する
1. 「セキュリティ認証情報」→「MFAを割り当てる」をクリックする。
2. デバイス名を入力する欄が表示されるので、自分のスマホに送られてくる認証コードがルートユーザーであることがすぐにわかるようなデバイス名する。
3. MFAデバイスを選択する欄で「認証アプリケーション」を選択する。
4. QRコードをGoogle Authenticatorで読み込むと認証コードが表示されるので、その異なる認証コードを二つ入力する。

# BillingをIAM ユーザーで閲覧できるようにする
1. マネジメントコンソールにあるルートユーザー名から「アカウント」をクリックする。
2. 下にスクロールすると「IAMユーザ/ロールによる請求情報へのアクセス」があるので「IAMアクセスのアクティブ化」にチェックを入れて「更新」をクリックする。
3. サイドバーから「ポリシー」を選択して、「ポリシーを作成」をクリックする。
4. 検索欄に「Billing」を記述して、それを選択する。
5. 今回は要件が閲覧だけですので「読み取り」にチェックを入れて、「次へ」をクリックする。
6. 任意のポリシー名を入力し、「ポリシーの作成」をクリックする。

# AdministratorAccess権限のIAM ユーザーを作成する
1. ルートユーザーでログインし、画面の上の検索欄から「IAM」と検索する。
2. サイドバーの「ユーザー」をクリックする。
3. 任意のユーザー名を入力し、「AWS マネジメントコンソールへのユーザーアクセスを提供する 」→「IAM ユーザーを作成します」→「自動生成されたパスワード」→「ユーザーは次回のサインイン時に新しいパスワードを作成する必要があります」→「次へ」をクリックする。
4. 今回は既存のIAMユーザー/グループがないので「ポリシーを直接アタッチする」を選択する。
5. 検索欄に「AdministratorAccess」で検索し、チェックを入れて「次へ」をクリックする。
6. これまでに記入した内容に間違いがないことを確認し、「ユーザーの作成」をクリックする。
7. CSVファイルをダウンロードする。次回からこのIAMユーザーを利用するために必要となる認証情報が書かれている。

# Cloud9を作成する
1. サービスメニューから「Cloud9」と検索し、「環境を作成」をクリックする。
2. 任意の名前を記入して、今回は学習用にEC2を作成するだけなので一番スペックの低い「t2.micro」を選択する。
3. その他の項目で変更点がなければ「作成」をクリックする。

# Cloud9でのプログラム作成から実行まで
1. 「New File」をクリックし、任意のファイル名を記述します。
2. そのファイルにコードを書き、「Run」を押す。

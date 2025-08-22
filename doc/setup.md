# Microsoft 365 GraphAPI を使用する準備

## Entra 管理センター で App Registraion (アプリの登録) を行う

[Microsoft Entra管理センター](https://entra.microsoft.com/) を開き、**アプリの登録** をクリックします
![](setup01.png)

**アプリの登録** 画面で、**+ 新規登録** をクリックします
![](setup02.png)

アプリ名(識別しやすいものを設定、ここでは *M365GraphAPIApp*)を入力し、**この組織ディレクトリーのみ含まれるアカウント (シングルテナント)** が選択されていることを確認して、**[登録]** をクリックします
![](setup03.png)

## アプリのアクセス許可を設定する

**アプリの登録** 画面から、**[すべてのアプリケーション]** タブを選択し、作成したアプリ (ここでは *M365GraphAPIApp*) をクリックします
![](setup04.png)

アプリの概要が表示されます。表示されている **アプリケーションId(クライアントId)** と **ディレクトリId(テナントId)** を控えておきます
![](setup05.png)

アプリ概要画面の左バナーから **アプリのアクセス許可** をクリックして **API のアクセス許可** 画面を表示します。**+ アクセス許可の追加** をクリックします
![](setup06.png)

**API アクセス許可の要求** バナーで **Microsoft Graph** をクリックします
![](setup07.png)

**委任されるアクセス許可** をクリックして選択します。検索バナーを使って **Files.Read** を探し (*Files* の **v** をクリックして開き、*Files.Read* を表示させます)、チェックボックスをオン **✓** にします
![](setup08.png)

同様に以下のスコープを検索して、チェックボックスをオンにします;
- Mail.Read, Calendars.Read, Chat.Read, Channel.ReadBasic.All, ChannelMessage.Read.All, Team.ReadBasic.All

チェックが終わったら、**[アクセス許可の追加]** をクリックします
![](setup09.png)

*構成されたアクセス許可* に追加したアクセス許可が含まれていることを確認します。**[** xxx(※テナント名) **に管理者の合意を与えます]** が表示されている場合は、クリックします。**[管理者の合意の確認を与えます]** というメッセージが表示されるので **[はい]** をクリックします。(※ **[** xxx(※テナント名) **に管理者の合意を与えます]** と表示されない場合は、そのまま次に進みます)
![](setup10.png)

*構成されたアクセス許可* の状態が **✓** xxx(※テナント名) **に付与されました** と表示されていればOKです
![](setup11.png)

## アプリのパブリッククライアントフローを許可する

アプリ概要画面の左バナーから **Authentication** をクリックして **Authentication** 画面を表示します。**Switch to the old experience** をクリックします
![](setup12.png)

*パブリッククライアントフローを許可する* を **はい** に設定、**[保存]** をクリックします
![](setup13.png)


## RestAPI でアクセスするときにパブリッククライアントフローを使う

実行すると、以下のようなメッセージが表示されるので、クリックして、https://microsoft.com/devicelogin を開きます
```
To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code XXXXXXXXX to authenticate.

```

表示されたコードを入力して、次に進みます
![](setup21.png)

サインインします
![](setup22.png)

アプリ名を確認して、次に進みます
![](setup23.png)

ブラウザーを使ったサインインは完了です
![](setup24.png)

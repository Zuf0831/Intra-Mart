<h1 align="center">Intra Mart</h1>

<p align="center">
  <img src="media/Logo.png" alt="images" width="500"/>
</p>

### EN Version
NTT DATA Intramart's digital process automation platform integrates various corporate business systems onto a unified platform, 
enabling IT investment efficiency and the optimization/standardization of business processes.


### JP Version
株式会社NTTデータ イントラマートが提供する、企業内の様々な業務システムを同一のプラットフォーム上に集約し、
IT投資の効率化と業務プロセスの最適化・標準化を実現するためのデジタルプロセスオートメーションプラットフォーム。

<h1 align="center">✨ Disclaimer ✨</h1>

- For more details about Intra-Mart, please refer to the official Intra-Mart website.
- この情報はIntra-Martに関する作成されたので、不明点があったら、Intra-Martの正式サイトをご覧ください。
##### リンク : `https://www.intra-mart.jp/`.


<h1 align="center">📖 Requirements 📖</h1>

- [Java 8](#java-8)
- [Resin](#resin)
- [PostgreSQL 16.9 (17以下) - Compatible Version](#postgresql)
- [Juggling](#juggling)
- [EBuilder](#ebuilder)
- [Notepad++ ・ VSCode](#notepad-vscode)
- [STMP 4 Dev](#stmp-4-dev)


<h1 align="center">💻 Installation 💻</h1>

⭐⭐⭐⭐⭐⭐
## Java 8
⭐⭐⭐⭐⭐⭐

> **Note:** If you want a free version, you can download OpenJDK from [Link Here](https://www.openlogic.com/openjdk-downloads)

> **ノート:** 無料版をご利用になりたい場合は、OpenJDKをダウンロードいただけます [ここにクリック](https://www.openlogic.com/openjdk-downloads)

<p align="left">
  <img src="media/Java/Filter.png" alt="images" width="500"/>
</p>

* Filter data to 8 version and download newest version (.msi)
* Java８バージョンを検索、最新のバージョンの方が良い (.msi)

<p align="left">
  <img src="media/Java/version.png" alt="images" width="500"/>
</p>

> **Note:** If Show nothing Need to check the **Environment variables**

> **ノート:** Javaバージョン確認の結果が見つからなかったら、**環境変数** 確認が必要

<p align="left">
  <img src="media/Java/path.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/Java/Environment.png" alt="images" width="800"/>
</p>


⭐⭐⭐⭐⭐⭐
## Resin
⭐⭐⭐⭐⭐⭐

> **Download Resin from the link below** 

> **Resinをダウンロードするため、以下のリンクをご覧ください** 

##### リンク : [Resin Download](https://download.intra-mart.jp/library/).

<p align="left">
  <img src="media/Resin/Link.png" alt="images" width="500"/>
</p>

> **Input License Key** 

> **ライセンスキーを入力** 

<p align="left">
  <img src="media/Resin/License.png" alt="images" width="800"/>
</p>

> **Filter Category to Resin** 

> **カテゴリのところにResinを入力** 

<p align="left">
  <img src="media/Resin/Filter.png" alt="images" width="800"/>
</p>


> **Extract Resin, Make sure to put it to C Drive** 

> **Resinを抽出し、Cドライブへ配置する必要があります。** 

<p align="left">
  <img src="media/Resin/Extract.png" alt="images" width="800"/>
</p>

> **Go to conf folder and edit resin.properties (Please ensure that Uncommented and Commented sections are same)** 

> **conf/resin.properties を編集（コメントアウト状態に注意）** 

<p align="left">
  <img src="media/Resin/pathConf.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Resin/properties.png" alt="images" width="800"/>
</p>


> **To Connect PostgreSQL Database to Resin (Intra-Mart), Need to download JDBC** 

> **PostgreSQL接続にはJDBCドライバが必要です** 

##### リンク : [JDBC Download](https://jdbc.postgresql.org/download/).

<p align="left">
  <img src="media/Resin/JDBC.png" alt="images" width="600"/>
</p>

> **Move the JDBC file to the lib folder inside the Resin folder.** 

> **ダウンロード後、libフォルダの中に移動** 

<p align="left">
  <img src="media/Resin/pgJDBC.png" alt="images" width="1000"/>
</p>


> **Create lib-backup folder, (CTRL + X ) file that showed in green line** 

> **lib-backupフォルダを作成し、緑色ファイルは　(CTRL + X )を押し、作成されたフォルダに移動** 

<p align="left">
  <img src="media/Resin/removejar.png" alt="images" width="1000"/>
</p>



> **Setup Resin as Local Service, The Password is your own device password** 

> **Resin　はローカルサービスとして設定が必要, パスワードは自分のパソコンのパスワード** 

<p align="left">
  <img src="media/Resin/resinsetup.png" alt="images" width="1000"/>
</p>

> **After that you can check in (Task Manager > Services)** 

> **確認方法: タスクマネージャー > サービス** 

<p align="left">
  <img src="media/Resin/taskmanager.png" alt="images" width="700"/>
</p>


⭐⭐⭐⭐⭐⭐
## PostgreSQL
⭐⭐⭐⭐⭐⭐

> **Download PostgreSQL from the link below** 

> **PostgreSQLをダウンロードするため、以下のリンクをご覧ください** 

##### リンク : [PostgreSQL Download](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads).

> **For now Compatible version is 16.9** 

> **現在、１７以下のバージョンがおすすめ** 

<p align="left">
  <img src="media/PostgreSQL/Potral.png" alt="images" width="700"/>
</p>

> **If you got Ps1 Error, Follow Guide Below** 
,If not you can go to PostgreSQL Setup [PostgreSQL Setup](#postgresql-setup)

> **PS1 エラーが発生したら、次のガイドをご覧ください、** 
なかったらPostgreSQL Setupに移動　[PostgreSQL Setup](#postgresql-setup)
<p align="left">
  <img src="media/PostgreSQL/Errorps1.png" alt="images" width="700"/>
</p>

> **Open Powershell as Admin** 

> **PowerShellを検索、管理者として実行** 

<p align="left">
  <img src="media/PostgreSQL/PowershellAdmin.png" alt="images" width="700"/>
</p>

> **Copy and Paste Command Below to PowerShell** 

> **コピペ以下のコマンド、PowerShellに入力** 

```sh
mkdir C:\TempPG
set TEMP=C:\TempPG
set TMP=C:\TempPG
```

> **Move PostgreSQL.exe file to the path (C:\TempPG), and then setup variable environment (Don't Forget to create a backup)** 

> **PostgreSQL.exe ファイルを指定パス (C:\TempPG) に移動, 環境変数設定も必要 (バックアップの作成を忘れずに！)** 

<p align="left">
  <img src="media/PostgreSQL/MoveData.png" alt="images" width="700"/>
</p>

> **Execute PostgreSQL.exe as Admin** 

> **PostgreSQL.exe ファイルは管理者として実行** 

<p align="left">
  <img src="media/PostgreSQL/MovetoTemp.png" alt="images" width="700"/>
</p>

#### PostgreSQL Setup

<p align="left">
  <img src="media/PostgreSQL/setup1.png" alt="images" width="300"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/setup2.png" alt="images" width="300"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/setup3.png" alt="images" width="300"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/setup4.png" alt="images" width="300"/>
</p>

> **You can choose a password that you want, for example, (123).** 

> **パスワードは自由に入力、例として今回は（123）を入力** 

<p align="left">
  <img src="media/PostgreSQL/setup5.png" alt="images" width="300"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/setup6.png" alt="images" width="300"/>
</p>

> **For the Locale, you can setup general locale (English, United States)** 

> **エラーを避けるため、ローカル設定は (English, United States)を入力した方が良い** 

<p align="left">
  <img src="media/PostgreSQL/setup7.png" alt="images" width="300"/>
</p>

> **For the last part, if the pop up appears you can ignore it and press cancel** 

> **インストールした後で、以下の画面が表示したら、無視しても良い** 

<p align="left">
  <img src="media/PostgreSQL/setup8.png" alt="images" width="300"/>
</p>


### Create Database

> **Search PgAdmin and Run as Admin** 

> **PgAdmin を検索、管理者として実行** 

<p align="left">
  <img src="media/PostgreSQL/pgadmin.png" alt="images" width="500"/>
</p>


> **Input password that you already created before** 

> **先の決定されたパスワードを入力** 

<p align="left">
  <img src="media/PostgreSQL/DBPassword.png" alt="images" width="500"/>
</p>


> **Create New imart Role For Intra-Mart Development** 

> **Intra-Mart開発のため、imartロールが必要** 

<p align="left">
  <img src="media/PostgreSQL/CreateRole.png" alt="images" width="300"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/role1.png" alt="images" width="300"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/role2.png" alt="images" width="300"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/role3.png" alt="images" width="300"/>
</p>

> **Create New Database For Intra-Mart Development** 

> **Intra-Mart開発のため、新しいデータベースが必要** 

<p align="left">
  <img src="media/PostgreSQL/CreateDB.png" alt="images" width="300"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/databaseCreate.png" alt="images" width="300"/>
</p>



⭐⭐⭐⭐⭐⭐
## Juggling
⭐⭐⭐⭐⭐⭐

> **Download Juggling from the link below** 

> **Jugglingをダウンロードするため、以下のリンクをご覧ください** 

##### リンク : [Juggling Download](https://download.intra-mart.jp/library/).

<p align="left">
  <img src="media/Resin/Link.png" alt="images" width="500"/>
</p>

> **Input License Key** 

> **ライセンスキーを入力** 

<p align="left">
  <img src="media/Resin/License.png" alt="images" width="800"/>
</p>

> **Search Juggling using (CTRL + F) feature** 

> **キーボードで(CTRL + F)を押し、Jugglingを入力** 

<p align="left">
  <img src="media/Juggling/filter.png" alt="images" width="500"/>
</p>



#### Juggling Setup

<p align="left">
  <img src="media/Juggling/setup1.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup2.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup3.png" alt="images" width="500"/>
</p>
<p align="left">
  <img src="media/Juggling/setup4.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup5.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup6.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup7.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup8.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup9.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup10.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup11.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup12.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup13.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup14.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup15.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup152.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup16.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup17.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup18.png" alt="images" width="500"/>
</p>








⭐⭐⭐⭐⭐⭐
## EBuilder
⭐⭐⭐⭐⭐⭐



⭐⭐⭐⭐⭐⭐
### STMP 4 Dev
⭐⭐⭐⭐⭐⭐
<h1 align="center">Intra Mart</h1>

<p align="center">
  <img src="media/Logo.png" alt="images" width="500"/>
</p>

### EN Version

<p align="left">
NTT DATA Intramart's digital process automation platform integrates various corporate business systems onto a unified platform, <br> enabling IT investment efficiency and the optimization/standardization of business processes.
</p>



### JP Version
<p align="left">
株式会社NTTデータ イントラマートが提供する、企業内の様々な業務システムを同一のプラットフォーム上に集約し、<br>
IT投資の効率化と業務プロセスの最適化・標準化を実現するためのデジタルプロセスオートメーションプラットフォーム。
</p>



<h1 align="center">✨ Disclaimer (免責事項)✨</h1>

- For more details about Intra-Mart, please refer to the official Intra-Mart website.
- この情報はIntra-Martに関する作成されたので、不明点があったら、Intra-Martの正式サイトをご覧ください。
##### リンク : `https://www.intra-mart.jp/`.


<h1 align="center">📖 Requirements (要件項目)📖</h1>

- Java 8
- Notepad++ ・ VSCode
- Resin
- PostgreSQL 16.9 (17以下) - Compatible Version
- Juggling
- EBuilder
- SMTP 4 Dev
- SQL Express DB

(Optional)
- NET Framework3.5.(Windows 8 / Windows8.1)


<h1 align="center">📖 Documentation (ドキュメント)📖</h1>

Please follow the steps below (以下の手順に従ってください).

1. [Program Install](#install-section)
2. [Tenant Setup](Tenant_Setup/tenant.md)
3. [Workflow Setup](workflow_setup/workflow.md)
4. [Source Code Setup](scode_setup/scode.md)
5. [CRUD Setup](db_setup/database.md)

<h4 align="left">📖 Feature (機能)📖</h4>

1. [Table](feature/table.md)
2. [Attachment](feature/attachment.md)
3. [Jobnet](feature/jobnet.md)
4. [Mail](feature/mail.md)


<h1 align="center">⏭️ Details (目次) ⏭️</h1>

1. [Java Install](#java-8)
2. [Notepad++ ・ VSCode Download](#notepad-vscode)
3. [Resin Install](#resin)
    - [JDBC Download](#jdbc-download)
4. [PostgreSQL Install](#postgresql)
    - [Fix getlocal.ps1 Error](#handle-ps1-error)
    - [PostgreSQL Setup](#postgresql-setup)
    - [Create Database](#create-database)
5. [Juggling](#juggling)
    - [Execute Warfile](#execute-warfile)
    - [Fix Bean Error](#bean-error)
    - [Checkpoint Deploy](#checkpoint-deploy)
5. [EBuilder Install](#ebuilder)
    - [Create Ebuilder Project](#create-ebuilder-project)
    - [Create Server Ebuilder](#create-server-ebuilder)
6. [SMTP 4 Dev Download](#smtp-4-dev)


<h1 align="center">💻 Installation 💻</h1>

###### Install Section

⭐⭐⭐⭐⭐⭐
## Java 8
⭐⭐⭐⭐⭐⭐

> **Note:** If you want a free version, you can download from OpenJDK.

> **ノート:** 無料版をご利用になりたい場合は、OpenJDKをダウンロードいただけます。

##### リンク : [OpenJDK Download](https://www.openlogic.com/openjdk-downloads).


<p align="left">
  <img src="media/Java/Filter.png" alt="images" width="500"/>
</p>

* Filter data to 8 version and download newest version (.msi)
* Java８バージョンを検索、最新のバージョンの方が良い (.msi)

<p align="left">
  <img src="media/Java/version.png" alt="images" width="500"/>
</p>

> **Note:** If Show nothing Need to check the **Environment variables**

> **ノート:** Javaバージョン確認の結果が見つからなかったら、**環境変数** 確認が必要。

<p align="left">
  <img src="media/Java/path.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/Java/Environment.png" alt="images" width="800"/>
</p>

⭐⭐⭐⭐⭐⭐
## Notepad VsCode
⭐⭐⭐⭐⭐⭐

> **Download Notepad++ from the link below** 

> **Notepad++をダウンロードするため、以下のリンクをご覧ください** 

##### リンク : [Notepad++ Download](https://notepad-plus-plus.org/).


<p align="left">
  <img src="media/Editor/notepad.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/Editor/notepad2.png" alt="images" width="500"/>
</p>

> **Download VSCode from the link below** 

> **VSCodeをダウンロードするため、以下のリンクをご覧ください** 

##### リンク : [VSCode Download](https://code.visualstudio.com/).

<p align="left">
  <img src="media/Editor/vscode.png" alt="images" width="500"/>
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

#### JDBC Download

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

### Handle PS1 Error

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
  <img src="media/PostgreSQL/setup1.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/Setup2.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/Setup3.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/Setup4.png" alt="images" width="500"/>
</p>

> **You can choose a password that you want, for example, (123).** 

> **パスワードは自由に入力、例として今回は（123）を入力** 

<p align="left">
  <img src="media/PostgreSQL/Setup5.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/Setup6.png" alt="images" width="500"/>
</p>

> **For the Locale, you can setup general locale (English, United States)** 

> **エラーを避けるため、ローカル設定は (English, United States)を入力した方が良い** 

<p align="left">
  <img src="media/PostgreSQL/Setup7.png" alt="images" width="500"/>
</p>

> **For the last part, if the pop up appears you can ignore it and press cancel** 

> **インストールした後で、以下の画面が表示したら、無視しても良い** 

<p align="left">
  <img src="media/PostgreSQL/Setup8.png" alt="images" width="500"/>
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
  <img src="media/PostgreSQL/CreateRole.png" alt="images" width="500"/>
</p>

> **General > Name** 

```sh
 imart
```

<p align="left">
  <img src="media/PostgreSQL/role1.png" alt="images" width="500"/>
</p>

> **Definition > Password パスワード** 

```sh
 imart
```

<p align="left">
  <img src="media/PostgreSQL/role2.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/role3.png" alt="images" width="500"/>
</p>

> **Create New Database For Intra-Mart Development** 

> **Intra-Mart開発のため、新しいデータベースが必要** 

<p align="left">
  <img src="media/PostgreSQL/CreateDB.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/PostgreSQL/databaseCreate.png" alt="images" width="500"/>
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

> **Uncomment base URL and create your own URL name (For now we only run it on localhost)** 

> **エンドポイント名を自由に作成し、ベースURLからコメント解除されていない部分を削除（現在はlocalhostでのみ実行する）** 

<p align="left">
  <img src="media/Juggling/setup10.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup11.png" alt="images" width="500"/>
</p>

> **Ensure created database in PostgreSQL are same** 

> **前回の作成したデータベース名、確認が必要** 

<p align="left">
  <img src="media/Juggling/setup12.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup13.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/Juggling/setup14.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup15.png" alt="images" width="500"/>
</p>


> **Make sure the file name in this section matches the URL name you previously created.** 

> **以前に作成したURL名と一致するように、このセクションのファイル名を確認してください。** 


<p align="left">
  <img src="media/Juggling/setup152.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/Juggling/setup16.png" alt="images" width="500"/>
</p>

> **For the language you can choose what you want** 

> **言語について自由に選択出来る** 

<p align="left">
  <img src="media/Juggling/setup17.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Juggling/setup18.png" alt="images" width="500"/>
</p>



⭐⭐⭐⭐⭐⭐
### Execute Warfile
⭐⭐⭐⭐⭐⭐

> **We need to create a new resin folder because (1 Project 1 Resin Folder) and move all data from resin-main folder to new resin folder** 

> **新しい resin フォルダを作成し（1プロジェクト＝1 Resinフォルダのルールに従い）、resin-main フォルダ内の全データを新しい resin フォルダに移動してください** 


<p align="left">
  <img src="media/Warfile/setup1.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/Warfile/setup2.png" alt="images" width="500"/>
</p>

> **Run Resin.exe as Admin** 

> **Resin.exe ファイルは管理者として実行** 

<p align="left">
  <img src="media/Warfile/setup3.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="media/Warfile/setup4.png" alt="images" width="500"/>
</p>

> **In Command Prompt you need to copy path your resin folder（Need to add 'cd' command）** 

> **コマンドプロンプトの中にResinフォルダのパースをコピペ（ｃｄコマンド忘れないように）** 

<p align="left">
  <img src="media/Warfile/setup5.png" alt="images" width="800"/>
</p>

> **Add 'resin deploy' + (your warfile path) / (file.war)** 

> **'resin deploy (warfileフォルダパース) / (WARファイル)'を入力してください。** 

<p align="left">
  <img src="media/Warfile/setup6.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="media/Warfile/setup62.png" alt="images" width="1000"/>
</p>

> **If you got Bean Error, you need to follow guide below** 
 if not just go to [Checkpoint Deploy](#checkpoint-deploy)

> **Beanエラーが発生したら、以下のガイドをご覧ください。**
なかったらCheckpoint Deployに移動 [Checkpoint Deploy](#checkpoint-deploy)


#### Bean Error

<p align="left">
  <img src="media/Warfile/ErrorBean.png" alt="images" width="1000"/>
</p>

> **Find (applicationContext-im_tgfw_common.xml) file inside deployed warfile** 

> **デプロイされたWarfileフォルダの中に(applicationContext-im_tgfw_common.xml)ファイルを探さないといけない。** 

<p align="left">
  <img src="media/Warfile/ErrorBean22.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="media/Warfile/ErrorBean2.png" alt="images" width="1000"/>
</p>

> **Change Dozzer Setting with code below** 

> **Dozzer設定された部分に対して変更が必要** 

> **Before Edit, 編集前** 
```sh
<bean class="org.dozer.spring.DozerBeanMapperFactoryBean">
  <property name="mappingFiles" value="classpath*:/META-INF/dozer/**/*-mapping.xml" />
</bean>
```

> **After Edit, 編集後** 
```sh
<bean class="com.github.dozermapper.spring.DozerBeanMapperFactoryBean">
  <property name="mappingFiles" value="classpath*:/META-INF/dozer/**/*-mapping.xml" />
</bean>
```

<p align="left">
  <img src="media/Warfile/ErrorBean3.png" alt="images" width="1000"/>
</p>


> **RESTART Resin.exe (Stop ⇒ Start)** 

> **Resin.exe再起動が必要  (Stop ⇒ Start)** 

<p align="left">
  <img src="media/Warfile/ErrorBean223.png" alt="images" width="400"/>
</p>

🚩🚩🚩
#### Checkpoint Deploy
🚩🚩🚩

<p align="left">
  <img src="media/Warfile/setup7.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="media/Warfile/setup8.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/Warfile/setup9.png" alt="images" width="800"/>
</p>



⭐⭐⭐⭐⭐⭐
## EBuilder
⭐⭐⭐⭐⭐⭐

> **Download EBuilder from the link below** 

> **EBuilderをダウンロードするため、以下のリンクをご覧ください** 

##### リンク : [EBuilder Download](https://download.intra-mart.jp/library/).

<p align="left">
  <img src="media/Resin/Link.png" alt="images" width="500"/>
</p>

> **Input License Key** 

> **ライセンスキーを入力** 

<p align="left">
  <img src="media/Resin/License.png" alt="images" width="800"/>
</p>

> **Search ebuilder using (CTRL + F) feature** 

> **キーボードで(CTRL + F)を押し、ebuilderを入力** 

<p align="left">
  <img src="media/EBuilder/setup1.png" alt="images" width="800"/>
</p>


> **Extract EBuilder, Make sure to put it to C Drive, and then modify ebuilder.ini file** 

> **EBuilderを抽出し、Cドライブへ配置し、ebuilder.iniファイル編集が必要** 

<p align="left">
  <img src="media/EBuilder/setup2.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup3.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup4.png" alt="images" width="500"/>
</p>

> **For the language you can choose what you want** 

> **言語について自由に選択出来る** 

<p align="left">
  <img src="media/EBuilder/setup5.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup6.png" alt="images" width="500"/>
</p>

> **Input URL (URL入力)** 

```sh
 http://www.intra-mart.jp/eclipse/update/site/eBuilder/8.0.x/
```

<p align="left">
  <img src="media/EBuilder/setup7.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup8.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup9.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup10.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup11.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup12.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/setup13.png" alt="images" width="500"/>
</p>

> **General ⇒　Editor ⇒　Text/Editor (Show Whitespace Charaters)** 

<p align="left">
  <img src="media/EBuilder/setup14.png" alt="images" width="500"/>
</p>

> **General ⇒　Show Heap Status** 

<p align="left">
  <img src="media/EBuilder/setup15.png" alt="images" width="500"/>
</p>

> **Ebuilder ⇒　Input Ebuilder License** 

<p align="left">
  <img src="media/EBuilder/setup16.png" alt="images" width="500"/>
</p>

> **And then Apply(終わったら適用ボータン押しが必要)** 

🚩🚩🚩🚩🚩🚩
#### Create Ebuilder Project
🚩🚩🚩🚩🚩🚩

<p align="left">
  <img src="media/EBuilder/project1.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/project2.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/project3.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/project4.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/project5.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/project6.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/project7.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="media/EBuilder/project8.png" alt="images" width="500"/>
</p>


🚩🚩🚩🚩🚩🚩
#### Create Server Ebuilder
🚩🚩🚩🚩🚩🚩

<p align="left">
  <img src="media/EBuilder/move1.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/EBuilder/move2.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/EBuilder/move3.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/EBuilder/move4.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/EBuilder/move5.png" alt="images" width="800"/>
</p>



⭐⭐⭐⭐⭐⭐
### SMTP 4 Dev
⭐⭐⭐⭐⭐⭐

> **Download SMTP4Dev from the link below** 

> **SMTP4Devをダウンロードするため、以下のリンクをご覧ください** 

##### リンク : [SMTP4Dev Download](https://github.com/rnwood/smtp4dev).

<p align="left">
  <img src="media/smtp/try1.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="media/smtp/try2.png" alt="images" width="800"/>
</p>

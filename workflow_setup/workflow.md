<h1 align="center">Intra Mart</h1>

⬅️
[Back to README 戻る](../README.md)


<h2 align="left">⭐Worfkflow Setup⭐</h2>


Please follow the steps below (以下の手順に従ってください).

ユーザー登録　⇒　コンテンツ定義　⇒　ルート定義　⇒　フロー定義

1. [User Register](#user-register)
2. [Content Definition](#content-definition)
     - [Screen Register](#screen-register)
     - [User Program](#user-program)
3. [Route Definition](#route-definition)
4. [Flow Definition](#flow-definition)


<h3 align="center">📖 User Register (ユーザー登録)📖</h3>

##### User Register

> **Before create User we need to create public group** 

> **ユーザー登録前にパブリックグループの作成が必要** 

> **Tenant Management ⇒　Common Master ⇒　(User / Public Group)**

<p align="left">
  <img src="images/user1.png" alt="images" width="500"/>
</p>

> **Create New Public Group** 

> **パブリックグループの作成** 

<p align="left">
  <img src="images/user2.png" alt="images" width="500"/>
</p>

> **Input Public Group name** 

> **パブリックグループ名を記入** 

<p align="left">
  <img src="images/user3.png" alt="images" width="1000"/>
</p>

> **Create New User** 

> **ユーザーアカウントの登録** 

<p align="left">
  <img src="images/user4.png" alt="images" width="800"/>
</p>

> **Input username (Usercode) for the account** 

> **ユーザーアカウントのユーザーコードを記入** 

<p align="left">
  <img src="images/user5.png" alt="images" width="800"/>
</p>


<p align="left">
  <img src="images/user6.png" alt="images" width="800"/>
</p>

> **Input password and dont forget to give check for the License** 

> **パスワードを記入、ライセンスのところにチェックマークを付けてください** 

<p align="left">
  <img src="images/user7.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/route8.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/user8.png" alt="images" width="800"/>
</p>

> **Public Group** 

<p align="left">
  <img src="images/user9.png" alt="images" width="1000"/>
</p>

> **Search public group that created before** 

> **作成されたパブリックグループを検索** 

<p align="left">
  <img src="images/user10.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/user11.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/user12.png" alt="images" width="1000"/>
</p>


> **Ensure Tenant's Account Role, Public Group** 

> **Tenantアカウントを確認、（ロール、パブリックグループ）** 

<p align="left">
  <img src="images/user13.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/user14.png" alt="images" width="800"/>
</p>




<h3 align="center">📖 Content Definition (コンテンツ定義)📖</h3>

##### Content Definition

<p align="left">
  <img src="images/content1.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/content2.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/content3.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/content4.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/content5.png" alt="images" width="500"/>
</p>


##### Screen Register

> **For this part, we'll use (path_test) for the URL path, you can adjust it to whatever you want.** 

> **今回、パースは(path_test)を使用してます、自由に記入してください** 

<p align="left">
  <img src="images/applyScreen.png" alt="images" width="500"/>
</p>


<p align="left">
  <img src="images/ApproveScreebbbbbn.png" alt="images" width="500"/>
</p>


<p align="left">
  <img src="images/confirmScreen.png" alt="images" width="500"/>
</p>


<p align="left">
  <img src="images/reApply.png" alt="images" width="500"/>
</p>


<p align="left">
  <img src="images/confirmScreen.png" alt="images" width="500"/>
</p>


<p align="left">
  <img src="images/DetailProcess.png" alt="images" width="500"/>
</p>


<p align="left">
  <img src="images/referenceDetail.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/confirmDetail.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/content6.png" alt="images" width="1000"/>
</p>


##### User Program

<p align="left">
  <img src="images/content7.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/content8.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/content9.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/content10.png" alt="images" width="500"/>
</p>


<h3 align="center">📖 Route Definition (ルート定義)📖</h3>

##### Route Definition


<p align="left">
  <img src="images/route1.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/route2.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/route3.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/route4.png" alt="images" width="500"/>
</p>

> **For this part, we'll use simple route, You can drag and drop node on the left** 

> **今回、シンプルなルートを作成し、左側のノードをドラッグドロップしてください** 

<p align="left">
  <img src="images/route5.png" alt="images" width="800"/>
</p>

> **We need to assign user for the Apply Node and Approve Node** 

> **申請ノードと承認ノードはユーザー登録が必要** 

<p align="left">
  <img src="images/route6.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/route7.png" alt="images" width="500"/>
</p>


<p align="left">
  <img src="images/route9.png" alt="images" width="800"/>
</p>

> **Approve Node** 

<p align="left">
  <img src="images/route10.png" alt="images" width="900"/>
</p>

<p align="left">
  <img src="images/route11.png" alt="images" width="800"/>
</p>



<h3 align="center">📖 Flow Definition (フロー定義)📖</h3>

##### Flow Definition


<p align="left">
  <img src="images/flow1.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/flow2.png" alt="images" width="500"/>
</p>

<p align="left">
  <img src="images/flow3.png" alt="images" width="500"/>
</p>

> **Find Content and Route that you created before** 

> **先ほど、作成されたコンテンツとルートを検索してください** 

<p align="left">
  <img src="images/flow4.png" alt="images" width="1000"/>
</p>

> **For this part(Sample_Workflow) you can create source code to show screen** 

> **(Sample_Workflow)の画面を表示するため、ソースコードが必要。** 

➡️
[Source Code Setup ソースコード作成](../scode_setup/scode.md)

<p align="left">
  <img src="images/flow5.png" alt="images" width="1000"/>
</p>

⬅️
[Back to README 戻る](../README.md)


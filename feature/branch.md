<h1 align="center">Intra Mart</h1>

⬅️
[Back 戻る](../README.md)


<h2 align="left">⭐Branch Setup⭐</h2>


<h1 align="center">⏭️ Details (目次) ⏭️</h1>

    
1. [Create Route](#create-route-set-branch)
2. [Create Matter Property](#create-matter-property)
3. [Create Rule](#create-rule)
4. [Set the rule in Content Definition](#define-the-rule-inside-the-content-definition)
5. [Set the rule in Flow Definition](#define-the-rule-inside-the-flow-definition)
6. [MatterProperty Function](#matterproperty-source-code) 
    - [Source Code](#source-code)
7. [Testing Branch](#testing-branch)
    - [True Condition](#testing-true-condition)
    - [False Condition](#testing-false-condition)
   


<h3 align="center">🚩Create Route（ジョブネット作成）🚩</h3>

### Create Route (Set Branch)

<p align="left">
  <img src="images/branch/branch_1.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_2.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_3.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_4.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_5.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_6.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_7.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_8.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_9.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_10.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_11.png" alt="images" width="1000"/>
</p>

### Create Matter Property

<p align="left">
  <img src="images/branch/branch_12.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_13.png" alt="images" width="1000"/>
</p>


<p align="left">
  <img src="images/branch/numericorstring.png" alt="images" width="600"/>
</p>

> **For the type, select whether to compare character/string data or numeric data.** 

> **タイプでは、文字列（キャラクター）データまたは数値データの比較を選択できます。** 


<p align="left">
  <img src="images/branch/branch_14.png" alt="images" width="1000"/>
</p>

### Create Rule

<p align="left">
  <img src="images/branch/branch_15.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_16.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_17.png" alt="images" width="1000"/>
</p>

#### For more details about "COMPARE", please check the documentation below.
#### 「COMPARE/比較」の詳細については、以下のドキュメントをご確認ください。
#### Documentation : [Click Here](https://document.intra-mart.jp/library/iap/public/im_workflow/im_workflow_administrator_guide/texts/basic_guide/basic_guide_5.html)

<p align="left">
  <img src="images/branch/branch_18.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_19.png" alt="images" width="1000"/>
</p>

### Define The Rule inside the Content Definition

<p align="left">
  <img src="images/branch/branch_20.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_21.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_22.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_23.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_24.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_25.png" alt="images" width="1000"/>
</p>

### Define The Rule inside the Flow Definition

<p align="left">
  <img src="images/branch/branch_26.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_27.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_28.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_29.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_30.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_31.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_32.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_33.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_34.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_35.png" alt="images" width="1000"/>
</p>


#### Source Code 

#### Call the function to create the matter property during Apply (ActionProcess).
#### 申請（ActionProcess）内でMatterプロパティを作成する関数を呼び出します。

<p align="left">
  <img src="images/branch/branch_36.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/branch_37.png" alt="images" width="1000"/>
</p>



##### MatterProperty Source Code

```sh
private final void createMatterProperty(final String userDataId, final String matterPropertyKey, final String matterPropertyValue) throws WorkflowException {
        final UserMatterPropertyModel matterPropertyModel = new UserMatterPropertyModel();
        matterPropertyModel.setUserDataId(userDataId);
        matterPropertyModel.setMatterPropertyKey(matterPropertyKey);
        matterPropertyModel.setMatterPropertyValue(matterPropertyValue);

        UserActvMatterPropertyValue property;
        property = new UserActvMatterPropertyValue();
        final UserMatterPropertyModel[] matterProperty = new UserMatterPropertyModel[1];
        matterProperty[0] = matterPropertyModel;
        property.createMatterProperty(matterProperty);
    }

private final void updateMatterProperty(final String userDataId, final String matterPropertyKey, final String matterPropertyValue) throws WorkflowException {
    final UserMatterPropertyModel matterPropertyModel = new UserMatterPropertyModel();
    matterPropertyModel.setUserDataId(userDataId);
    matterPropertyModel.setMatterPropertyKey(matterPropertyKey);
    matterPropertyModel.setMatterPropertyValue(matterPropertyValue);

    UserActvMatterPropertyValue property;
    property = new UserActvMatterPropertyValue();
    final UserMatterPropertyModel[] matterProperty = new UserMatterPropertyModel[1];
    matterProperty[0] = matterPropertyModel;
    property.updateMatterProperty(matterProperty);
}

private final void deleteMatterProperty(final String userDataId, final String matterPropertyKey) throws WorkflowException {
    final UserMatterPropertyModel matterPropertyModel = new UserMatterPropertyModel();
    matterPropertyModel.setUserDataId(userDataId);
    matterPropertyModel.setMatterPropertyKey(matterPropertyKey);

    UserActvMatterPropertyValue property;
    property = new UserActvMatterPropertyValue();
    final UserMatterPropertyModel[] matterProperty = new UserMatterPropertyModel[1];
    matterProperty[0] = matterPropertyModel;
    property.deleteMatterProperty(matterProperty);
}

```

<h3 align="center">🚩Testing Branch（Branchのテスト）🚩</h3>

# Testing Branch

### Testing TRUE Condition


<p align="left">
  <img src="images/branch/test_1.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/test_2.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/test_3.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/test_4.png" alt="images" width="1000"/>
</p>

### Testing FALSE Condition

<p align="left">
  <img src="images/branch/test_5.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/branch/test_6.png" alt="images" width="1000"/>
</p>

⬅️
[Back to README 戻る](../README.md)


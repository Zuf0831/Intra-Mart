<h1 align="center">Intra Mart</h1>

⬅️
[Back 戻る](../README.md)


<h2 align="left">⭐Database Setup⭐</h2>



Need to Follow Step Bellow (以下の流れ手順にご覧ください。)

<h4 align="left">📖 Design (デザイン) </h4>
Create Screen
画面作成 

<h4 align="left">📖 Apply Action Process （申請処理）</h4>
Create Table　⇒　Create Model ⇒ Create Repository ⇒ Create Service Action 

テーブル作成 ⇒ モデル作成 ⇒ リポジトリ作成 ⇒ サービスアクション作成

<h4 align="left">📖 Process Data　（データ処理）</h4>
Get Data ⇒　Show data

データ取得 ⇒ データ表示

<h4 align="left">📖 Matter End Process　（案件終了処理）</h4>

Create Service MatterEnd ⇒ Update Database

案件終了サービス作成 ⇒ データベース更新



1. [Design](#design)
    - [Apply JSP Sample Code](#sample-code-1)
    - [Diagram](#diagram)
    - [Flow Chart](#flow-chart)
    
2. [Apply Action Process](#apply-action-process)
    - [Create Database](#create-database)
    - [Create Model](#create-model)
    - [Create Repository](#create-repository)
    - [Create Action Service](#create-service)
        - [ActionProcessServiceImpl.java](#sample-code-2)
    - [Apply Testing](#apply-testing)

3. [Process Data](#process-data)
    

3. [Matter End Process](#matter-end)
    
    


<h3 align="center">🚩Design (デザイン)🚩</h3>

##### Design


> **First you need to create views (JSP) and set some input form** 

> **JSPファイルを作成、入力フォームを作成が必要** 

> **For example we create 3 input forms** 

> **例として、今回は３つの入力フォームを作成** 

<p align="left">
  <img src="images/baseinput.png" alt="images" width="800"/>
</p>


<p align="left">
  <img src="images/sample.png" alt="images" width="1000"/>
</p>

#### Sample Code 1

> **Apply.jsp** 


```sh

<%@ page contentType="text/html; charset=utf-8" pageEncoding="utf-8"%>
<%@ taglib prefix="imui" uri="http://www.intra-mart.co.jp/taglib/imui"%>
<%@ taglib prefix="imart" uri="http://www.intra-mart.co.jp/taglib/core/standard"%>
<%@ taglib prefix="workflow" uri="http://www.intra-mart.co.jp/taglib/imw/workflow"%>
<%@ taglib prefix="form"   uri="http://www.springframework.org/tags/form"%>
<%@ taglib prefix="spring" uri="http://www.springframework.org/tags"%>
<%@ taglib prefix="f" uri="http://terasoluna.org/functions"%>
<%@ taglib prefix="c" uri="http://java.sun.com/jstl/core"%>
<%@ taglib prefix="im" uri="http://www.intra-mart.co.jp/taglib/im-tenant"%>

<%@ page import="java.util.List"%>
<%@ page import="java.util.ArrayList"%>
<%@ page import="java.util.Map"%>
<%@ page import="java.util.HashMap"%>

<imui:head>
	<title>Sample Workflow</title>
	<workflow:workflowOpenPageCsjs />
	
	<link href="ui/css/select2.min.css" rel="stylesheet" />
    <script src="ui/js/select2.min.js" type="text/javascript"></script>
    <script src="ui/js/jquery.validate.js" type="text/javascript"></script>
	
	
	
	<script type="text/javascript">
		

        $(function(){
           

            $('#openPage').click(function() {
   
            	
            	workflowOpenPage('${f:h(ApplyForm.imwPageType)}');
            	
                
            });  
        });   
	</script>
	

	
	<!-- CSS Scripts -->
    <style type="text/css">
        
    </style>
</imui:head>

<workflow:workflowUserContentsAuth imwApplyBaseDate='${f:h(ApplyForm.imwApplyBaseDate)}'
            imwAuthUserCode = '${f:h(ApplyForm.imwAuthUserCode)}'
            imwFlowId='${f:h(ApplyForm.imwFlowId)}'
            imwNodeId ='${f:h(ApplyForm.imwNodeId)}'
            imwPageType = '${f:h(ApplyForm.imwPageType)}'
            imwSystemMatterId='${f:h(ApplyForm.imwSystemMatterId)}'
            imwUserDataId='${f:h(ApplyForm.imwUserDataId)}'/>
            

<div class="imui-title-small-window">
	<h1>Workflow</h1>
</div>
<div class="imui-toolbar-wrap">
 	<div class="imui-toolbar-inner">
		<ul class="imui-list-toolbar">
			<li>
				<a href="javascript:void(0);" id="back">
					<span class="im-ui-icon-common-16-back"></span>
				</a>
			</li>
		</ul>
	</div>
</div>

<imui:tabs selected="0">
<imui:tabItem title="Workflow" >
	<div class="imui-form-container">
		<workflow:workflowOpenPage name="workflowOpenPageForm"
				id="workflowOpenPageForm"
				method="POST"
				target="_top"
				imwUserDataId="${f:h(ApplyForm.imwUserDataId)}"
				imwSystemMatterId="${f:h(ApplyForm.imwSystemMatterId)}"
				imwAuthUserCode="${f:h(ApplyForm.imwAuthUserCode)}"
				imwApplyBaseDate="${f:h(ApplyForm.imwApplyBaseDate)}"
				imwNodeId="${f:h(ApplyForm.imwNodeId)}"
				imwFlowId="${f:h(ApplyForm.imwFlowId)}"
				imwCallOriginalParams="${f:h(ApplyForm.imwCallOriginalParams)}"
				imwNextScriptPath="${f:h(ApplyForm.imwCallOriginalPagePath)}">	
				
		  		<header class="imui-chapter-title">
					<h2>Input Form</h2>
				</header>
				
				<table class="imui-form tab_header">
					<tbody>
						<tr>
							<th width="250">
								<label class="imui-required" style="margin-left:20px">Name</label>
							</th>
							<td>
								<input type="text" id="f_name" name="f_name" placeholder="Name.." style="height:20px" size="50">
								
							</td>
						</tr>
              
	                    <tr>
                    		<th>
	                            <label class="imui-required" style="margin-left:20px">Age</label>
	                        </th>
	                        <td>
	                            <div class="">
									<input type="number" id="f_age" name="f_age" min="0" max="500" placeholder="0">                              
	                            </div>
	                        </td>
	                            
	                    </tr>
	                    
	                    <tr>
	                    	<th width="250">
								<label style="margin-left : 20px">Notes</label>
							</th>
	                        <td>
	                            <div class="form-group">
	                                <textarea rows="3" 
	                                            cols="40" 
	                                            name="f_note" 
	                                            id="f_note" 
	                                            class=""
	                                            style="margin-left: 5px;"></textarea>
	                            </div>
	                        </td>
	                    </tr>
					</tbody>
				</table>
				
		</workflow:workflowOpenPage>
		
		
		
	</div>
	
</imui:tabItem>
</imui:tabs>


		
<!-- Button Default -->
<div class="imui-operation-parts">
	<imart:decision case="0" value="${f:h(ApplyForm.imwPageType)}">	
		<input type="button" value='Apply' id="openPage" name="openPage" class="imui-large-button"
			escapeXml="true" escapeJs="false" />
	</imart:decision>
	<imart:decision case="3" value="${f:h(ApplyForm.imwPageType)}">
		<input type="button" value='Re-Apply' id="openPage" name="openPage" class="imui-large-button"
			escapeXml="true" escapeJs="false" />
	</imart:decision>
	
</div>

<form name="backForm" id="backForm" method="POST" action="${f:h(ApplyForm.imwCallOriginalPagePath)}">
    <input type="hidden" name=imwCallOriginalParams value="${f:h(ApplyForm.imwCallOriginalParams)}" />
</form>

```


> **From the screen we have flow database like diagram below** 

> **画面作成した後、データベースのイメージが以下の図に表示される** 

##### Diagram

<p align="left">
  <img src="images/umlDiagram.png" alt="images" width="800"/>
</p>

##### Flow Chart

> **処理フロー図** 

<p align="left">
  <img src="images/flowchart.png" alt="images" width="1000"/>
</p>



<h3 align="center">🚩Apply Action Process （申請処理）🚩</h3>

### Apply Action Process

##### Create Database

> **Open PostgreSQL to create table in database that already created** 

> **PostgreSQLでの作成されたDBを開き、テーブルを作成** 

<p align="left">
  <img src="images/db1.png" alt="images" width="700"/>
</p>


> **Scroll to the bottom and you will get your own created table** 

> **作成されたテーブルは下にスクロールしてください** 

<p align="left">
  <img src="images/db2.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db3.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db4.png" alt="images" width="700"/>
</p>


<p align="left">
  <img src="images/db4.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db5.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db6.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db7.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db8.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db9.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db10.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/db11.png" alt="images" width="700"/>
</p>



#### Create Model

<p align="left">
  <img src="images/model1.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/model2.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/model3.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/model4.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/model5.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/model6.png" alt="images" width="700"/>
</p>


#### Create Repository

<p align="left">
  <img src="images/repo1.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/repo2.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/repo3.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/repo4.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/repo5.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/repo6.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/repo7.png" alt="images" width="700"/>
</p>

#### Create Service

<p align="left">
  <img src="images/service1.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/service2.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/service3.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/service4.png" alt="images" width="1000"/>
</p>


#### Sample Code 2

> **ActionProcessServiceImpl.java** 

```sh


import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.ArrayList;
import java.util.Collection;
import java.util.Collections;
import java.util.Date;
import java.util.List;
import java.util.Map;

import jp.co.intra_mart.common.aid.jdk.java.util.LocaleUtil;
import jp.co.intra_mart.foundation.security.message.MessageManager;
import jp.co.intra_mart.foundation.workflow.application.general.UserActvMatterPropertyValue;
import jp.co.intra_mart.foundation.workflow.application.model.HorizontalAndVerticalNodeConfigModel;
import jp.co.intra_mart.foundation.workflow.application.model.UserMatterPropertyModel;
import jp.co.intra_mart.foundation.workflow.exception.WorkflowException;
import jp.co.intra_mart.foundation.workflow.exception.WorkflowExternalException;
import jp.co.intra_mart.foundation.workflow.plugin.process.action.ActionProcessParameter;
import jp.co.intra_mart.foundation.workflow.util.WorkflowNumberingManager;

import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Propagation;
import org.springframework.transaction.annotation.Transactional;


//Import all package
import wf.path_test.general.*;
import wf.path_test.general.app.*;
import wf.path_test.general.data.*;
import wf.path_test.general.domain.model.*;
import wf.path_test.general.domain.repository.*;
import wf.path_test.general.domain.service.*;


@Service
@Transactional(propagation = Propagation.MANDATORY)
public class ActionProcessServiceImpl implements ActionProcessService {
	@Override
    public final String apply(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    String number = null;
        try {
        	
        	//Repository
        	
        	
        	
        	//Model to Entity
        	
        	
        	
            number = WorkflowNumberingManager.getNumber();
        } catch (final WorkflowException e) {
            throw new WorkflowExternalException(MessageManager.getInstance().getMessage(LocaleUtil.toLocale(parameter.getLocaleId()), "SAMPLE.IMW.ERR.003"));
            
        }

        return number;
    }

	
	private String getEntityListString(List<String> input_form, int i) {
		try {
			//System.out.println("Input data :" + input_form.get(i));
			return input_form.get(i);
		} catch (Exception e) {
			return "";
		}
	}
	
	private String getEntityUserParameter(final Map<String, Object> userParameter, String input_form) {
		try {
			return userParameter.get(input_form).toString();
		} catch (Exception e) {
			return "";
		}
	}
	


	private String getEntity_TryCatch_UserParameter(final Map<String, Object> userParameter, String input_form) {
    	try {
			return userParameter.get(input_form).toString();
		}catch(Exception e) {
			return "";
		}
	}

	@Override
    public final String applyFromTempSave(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
        String number = null;
        try {
            number = WorkflowNumberingManager.getNumber();
        } catch (final WorkflowException e) {
            throw new WorkflowExternalException(MessageManager.getInstance().getMessage(LocaleUtil.toLocale(parameter.getLocaleId()), "SAMPLE.IMW.ERR.003"));
        }
        return number;
    }

    @Override
    public final String applyFromUnapply(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
        String number = null;
        try {
            number = WorkflowNumberingManager.getNumber();
        } catch (final WorkflowException e) {
            throw new WorkflowExternalException(MessageManager.getInstance().getMessage(LocaleUtil.toLocale(parameter.getLocaleId()), "SAMPLE.IMW.ERR.003"));
        }
        return number;
    }
    

    @Override
    public void approve(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk approve");
    }

    @Override
    public final void approveEnd(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk approve end");
    }

    @Override
    public final void deny(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk deny");
    }

    @Override
    public final void discontinue(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk discontinue");
    }

    @Override
    public final void matterHandle(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk matterHandle");
    }

    @Override
    public final void pullBack(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk pullBack");
    }

    @Override
    public final String reapply(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk reapply");

        return null;
    }

    @Override
    public final void reserve(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk reserve");
    }

    @Override
    public final void reserveCancel(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk reserveCancel");
    }

    @Override
    public final void sendBack(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk sendBack");
    }

    @Override
    public final void sendBackToPullBack(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk sendBackToPullBack");
    }

    @Override
    public final void tempSaveCreate(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk tempSaveCreate");
    }

    @Override
    public final void tempSaveDelete(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk tempSaveDelete");
    }

    @Override
    public final void tempSaveUpdate(final ActionProcessParameter parameter, final Map<String, Object> userParameter) throws Exception {
    System.out.println("masuk tempSaveUpdate");
    }

    private void outputLog(final ActionProcessParameter parameter) {
        System.out.println("LoginGroupId        : " + parameter.getLoginGroupId());
        System.out.println("LocaleId            : " + parameter.getLocaleId());
        if (parameter.getTargetLocales() != null) {
            System.out.print("TargetLocales       : ");
            for (final String str : parameter.getTargetLocales()) {
                System.out.print(str + " ");
            }
            System.out.println();
        } else {
            System.out.println("TargetLocales       : ");
        }
        System.out.println("ContentsId          : " + parameter.getContentsId());
        System.out.println("ContentsVersionId   : " + parameter.getContentsVersionId());
        System.out.println("RouteId             : " + parameter.getRouteId());
        System.out.println("RouteVersionId      : " + parameter.getRouteVersionId());
        System.out.println("FlowId              : " + parameter.getFlowId());
        System.out.println("FlowVersionId       : " + parameter.getFlowVersionId());
        System.out.println("ApplyBaseDate       : " + parameter.getApplyBaseDate());
        System.out.println("ProcessDate         : " + parameter.getProcessDate());
        System.out.println("SystemMatterId      : " + parameter.getSystemMatterId());
        System.out.println("UserDataId          : " + parameter.getUserDataId());
        System.out.println("MatterName          : " + parameter.getMatterName());
        System.out.println("MatterNumber        : " + parameter.getMatterNumber());
        System.out.println("PriorityLevel       : " + parameter.getPriorityLevel());
        System.out.println("Parameter           : " + parameter.getParameter());
        System.out.println("ActFlag             : " + parameter.getActFlag());
        System.out.println("NodeId              : " + parameter.getNodeId());
        if (parameter.getNextNodeIds() != null) {
            System.out.print("NextNodeIds         : ");
            for (final String str : parameter.getNextNodeIds()) {
                System.out.print(str + " ");
            }
            System.out.println();
        } else {
            System.out.println("NextNodeIds         : ");
        }
        System.out.println("AuthUserCd          : " + parameter.getAuthUserCd());
        System.out.println("ExecUserCd          : " + parameter.getExecUserCd());
        System.out.println("ResultStatus        : " + parameter.getResultStatus());
        System.out.println("AuthCompanyCode     : " + parameter.getAuthCompanyCode());
        System.out.println("AuthOrgzSetCode     : " + parameter.getAuthOrgzSetCode());
        System.out.println("AuthOrgzCode        : " + parameter.getAuthOrgzCode());
        System.out.println("ProcessComment      : " + parameter.getProcessComment());
        System.out.println("LumpProcessFlag     : " + parameter.getLumpProcessFlag());
        System.out.println("AutoProcessFlag     : " + parameter.getAutoProcessFlag());
    }
}


```


<p align="left">
  <img src="images/service5.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/service6.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/service7.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/service8.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/service9.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/service10.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/service11.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/service12.png" alt="images" width="1000"/>
</p>



<h3 align="center">🚩🚩Apply Testing (申請テスト)🚩🚩</h3>

###### Apply Testing

<p align="left">
  <img src="images/apply1.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/apply2.png" alt="images" width="700"/>
</p>

<p align="left">
  <img src="images/apply3.png" alt="images" width="1000"/>
</p>

<p align="left">
  <img src="images/apply4.png" alt="images" width="1000"/>
</p>



<h3 align="center">🚩🚩Process(Get Data) (処理プロセス)🚩🚩</h3>

##### Process Data

<h3 align="center">🚩🚩MatterEndProcess (案件終了)🚩🚩</h3>

##### Matter End


⬅️
[Back to README 戻る](../README.md)

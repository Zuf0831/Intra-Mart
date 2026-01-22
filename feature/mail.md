<h1 align="center">Intra Mart</h1>

⬅️
[Back 戻る](../README.md)


<h2 align="left">⭐Mail Setup⭐</h2>

> **Before create the Mail Function, Ensure you already have SMTP4Dev installed** 

> **開発する為、SMTP4Devアプリが必要** 


##### Example Mail Flow Design

<p align="center">
  <img src="images/mail/design1.png" alt="images" width="1000"/>
</p>


<p align="center">
  <img src="images/mail/design2.png" alt="images" width="1000"/>
</p>


<h1 align="center">⏭️ Details (目次) ⏭️</h1>

### ⚠️Disclaimer ⚠️
<p>
    In this documentation, we will create a simple custom mail notification. The trigger will use the Job function, and you can see the flow in the Flow Design.
If a custom mail is not necessary, you can skip the following steps after completing the first step.
</p>

<p>
    本ドキュメントでは、シンプルなカスタムメール通知を作成します。
    トリガーにはジョブ機能を使用し、フローデザインでその流れを確認できます。
    カスタムメールが不要な場合は、最初のステップ完了後、以降の手順をスキップしてください。
</p>

1. [Setup Mail Notification](#setup-notification)
2. [Modify Database](#edit-action-process-service-impl)
3. [Modify Jobnet Source Code](#modify-source-code)
    - [Send Mail Function Source Code](#send-mail-function-service)
4. [Test Mail Function](#testing-area)
5. [Reference Source Code](#sample-source-code)
    - [Standard + Extended Mail Function](#extend-mail-function)
    - [Mime Mail Function](#mime-mail-function)

<h3 align="center">🚩Setup Notification（メール通知設定）🚩</h3>

#### Setup Notification

> **Enable the Email Function in the Content Settings** 

> **コンテンツ設定でメール機能を有効にする** 

<p align="left">
  <img src="images/mailsetup/mailsetup1.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup2.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup3.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup4.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup5.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup6.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup7.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup8.png" alt="images" width="800"/>
</p>

> **Configure Email for Users Related to the Workflow** 

> **ワークフロー関連ユーザーのメール設定** 

<p align="left">
  <img src="images/mailsetup/mailsetup9.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup10.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mailsetup/mailsetup11.png" alt="images" width="800"/>
</p>

> **Verify email notifications via SMTP (e.g., when a user submits a request, the receiver receives an email notification).** 

> **SMTPメール通知の動作確認（ユーザーが申請すると、受信者に通知メールが送信されます）** 


<p align="left">
  <img src="images/mailsetup/mailsetup12.png" alt="images" width="800"/>
</p>

<h2 align="left">🚩Customize Mail Notification🚩</h2>

<h3 align="center">🚩Modify Database（データベース編集）🚩</h3>

##### Edit Action Process Service Impl

<p align="left">
  <img src="images/mail/db1.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/db2.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/db3.png" alt="images" width="800"/>
</p>

> **Update Source Code Apply Action Process** 

> **Apply Action Processソースコードの編集が必要** 

<p align="left">
  <img src="images/mail/db4.png" alt="images" width="800"/>
</p>

> **Update Source Code Matter End Process** 

> **MaterEndProcessソースコードの編集が必要** 

<p align="left">
  <img src="images/mail/db5.png" alt="images" width="800"/>
</p>



<h3 align="center">🚩Modify Jobnet Source Code（ジョブネットソースコード編集）🚩</h3>

#### Modify Source Code

<p align="left">
  <img src="images/mail/mail1.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/mail2.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/mail3.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/mail4.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/mail5.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/mail6.png" alt="images" width="800"/>
</p>


##### Send Mail Function Service

> **Send Mail Source Code** 

> **メール送信ソースコード** 

```sh
public void send_email(String matterId, String mail, ImartForm FormClassRows) throws Exception {
		
		
		
    //set Data
    String matterID = FormClassRows.getF_system_matter_id();
    String name = FormClassRows.getF_name();
    String age = FormClassRows.getF_age();
    String note = FormClassRows.getF_note();
    
    //Set Mail
    StandardMail create_mail = new StandardMail();
    create_mail.setFrom("mailTesting@yahoo.jp", "Email Notification");
    create_mail.setSubject(" [Test Mail]");
    create_mail.setText("Dear Mr./Mrs./Ms.,\r\n" + 
            "\r\n" + 
            "Application with Matter Number " + matterID + " has been Apply. Here the cover of Applicant document. \r\n" +
            "\r\n" + 
            "\r\n" +
            "Customer Information*  \r\n" + 
            "___________________________________________________ \r\n\r\n" + 
            "| Customer Name 		: " + name + "\r\n" + 
            "| Customer Age 		: " +  age + "\r\n" + 
            "| Customer Notes 		: " +  note + "\r\n" + 
            "___________________________________________________ \r\n\r\n" +
            "\r\n" + 
            "\r\n" +
            "Best Regards,\r\n" + 
            "Testing Team\r\n");
    create_mail.addTo(mail);
    
    //Execute Mail
    try {
        JavaMailSender sender = new JavaMailSender(create_mail);
        sender.send();
        //Update mail_status in HeaderDB
        HeaderRepository HeaderDB = new HeaderRepository();
        HeaderModel rows_header = HeaderDB.selectDataHeader(matterId, "system_matter_id").iterator().next();
        rows_header.setMail_status("2");
        HeaderDB.updateDataHeader(rows_header);
    } catch (MailSenderException var30) {
        //Update mail_status in HeaderDB
        HeaderRepository HeaderDB = new HeaderRepository();
        HeaderModel rows_header = HeaderDB.selectDataHeader(matterId, "system_matter_id").iterator().next();
        rows_header.setMail_status("99");
        HeaderDB.updateDataHeader(rows_header);
        
        var30.printStackTrace();
        throw new MailSenderException ("Error in sendEmailWithAttachment()", var30);
    }
}
```

⬅️
[Back 戻る](../README.md)


<h3 align="center">🚩Testing Mail Function（メール機能テスト）🚩</h3>

#### Testing Area

> **To Test the Mail Function, Ensure you already have SMTP4Dev installed** 

> **テストする為、SMTP4Devアプリが必要** 

<p align="left">
  <img src="images/mail/testing1.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/testing2.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/testing3.png" alt="images" width="800"/>
</p>

<p align="left">
  <img src="images/mail/testing4.png" alt="images" width="800"/>
</p>


<h3 align="center">🚩Sample Source Code（メール機能の参考ソースコード）🚩</h3>

##### Sample Source Code

### ⚠️Disclaimer ⚠️
<p>
    This sample source code returns a simple HTML message and includes an attached file (e.g., PDF, Txt, Excel, etc.).
</p>

<p>
    このサンプルソースコードでは、シンプルなHTMLメッセージを返し、PDFやExcelなどの添付ファイルも送信します。
</p>

#### Extend Mail Function

```sh
private StandardMail createMail_extended() throws MailSenderException, IOException {
    ExtendedMail mail = new ExtendedMail();

    mail.setFrom("tenant@marimo.com");
    mail.setSubject("Test Subject Email");

    mail.addTo("test1@gmail.com");
    mail.addCc("testcc1@gmail.com");

    mail.addHeader("Content-Type", "text/html; charset=UTF-8");
    mail.setText("");

    mail.setHTML("<html><body style='font-family:arial; font-size:14px; line-height: 1.6;'>" +
        "Dear Sir/Madam, " +
        "
Here we would like to request your kind <b><u>approval</u></b> for Application with matter number " + 001234 +
        "
Detail matter information: " +
        "

<table border='0'>" +
        "<tr><td width='200px'>Flow Name</td><td>:</td><td> Lorem Ipsum 1 </td>" +
        "<tr><td>Matter Number</td><td>:</td><td> Lorem Ipsum 2 </td>" +
        "<tr><td>Matter Name</td><td>:</td><td> Lorem Ipsum 3 </td>" +
        "<tr><td>Applicant Name</td><td>:</td><td> Lorem Ipsum 4 </td>" +
        "<tr><td>Application Date</td><td>:</td><td> Lorem Ipsum 5 </td>" +
        "<tr><td>Priority</td><td>:</td><td> Lorem Ipsum 6 </td>" +
        "</table>
" +
        "Please <a href='#'>click here</a> to process the application." +
        "
Thank you." +
        "
" +
        "
" +
        "Best Regards, 
" +
        "
" +
        "<i>Note: This email is auto generated by System</i>" +
                "</body></html>");

    String pdfFile = "test_pdf.txt";
    PublicStorage storage = new PublicStorage("marimo_training/" + pdfFile);

    mail.addAttachmentStorage(pdfFile, storage);

    return mail;
  }
```


### Mime Mail Function

##### Result

<p align="left">
  <img src="images/mail/mimefunction.png" alt="images" width="800"/>
</p>

##### Source Code
```sh
public static void sendEmailUsingMimeFunction(String systemMatter, String[] Emails, MarimoContractForm MarimoContractFormClassRows) throws Exception {
    ApprovalContractHeaderRepository ApprovalContractHeaderDB = new ApprovalContractHeaderRepository();
    ApprovalContractHeaderModel rows_header = ApprovalContractHeaderDB.selectDataMarimoContractHeader(systemMatter, "system_matter_id").iterator().next();
    rows_header.setIs_mail_sent("1");
    ApprovalContractHeaderDB.updateDataMarimoContractHeader(rows_header);
    String MATTER_NM = MarimoContractFormClassRows.getF_system_matter_id();
    String Company_Name = MarimoContractFormClassRows.getF_company_name();
    String Customer_Name = MarimoContractFormClassRows.getF_customer_name();
    String Contract_Type = MarimoContractFormClassRows.getF_contract_type();
    String Contract_No = MarimoContractFormClassRows.getF_contract_no();
    String Contract_Title = MarimoContractFormClassRows.getF_contract_title();
    String Term_start = MarimoContractFormClassRows.getF_term_date_start();
    String Term_end = MarimoContractFormClassRows.getF_term_date_end();
    String PIC_C_JTitle = MarimoContractFormClassRows.getF_pic_customer_job();
    String PIC_C_NM = MarimoContractFormClassRows.getF_pic_customer_name();
    String PIC_C_Phone = MarimoContractFormClassRows.getF_pic_customer_phone();
    String PIC_C_Email = MarimoContractFormClassRows.getF_pic_customer_email();
    String PIC_YK_JTitle = MarimoContractFormClassRows.getF_pic_ykkap_job();
    String PIC_YK_NM = MarimoContractFormClassRows.getF_pic_ykkap_name();
    String DummyLink = "https://streamable.com/lf027o";
    String host = "smtp.example.com";
    String port = "587";
    String username = "email@example.com";
    String password = "dummypassword";
    String mail = MarimoContractFormClassRows.getF_pic_customer_email();
    Properties props = new Properties();
    System.setProperty("mail.smtp.host", "localhost");
    System.setProperty("mail.smtp.port", "25");
    System.setProperty("mail.smtp.auth", "false");
    Session session = Session.getDefaultInstance(System.getProperties());
    MimeMessage marimoMail = new MimeMessage(session);
    marimoMail.setFrom((Address)new InternetAddress(username));
    marimoMail.setFrom((Address)new InternetAddress("MarimoTeam@gmail.com"));
    for (int i = 0; i < Emails.length; i++) {
      String user_email = Emails[i];
      marimoMail.addRecipient(Message.RecipientType.TO, (Address)new InternetAddress(user_email));
    } 
    marimoMail.setSubject("Test Email from Intra-Mart");
    MimeBodyPart htmlpart = new MimeBodyPart();
    String htmlContent = "<span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Dear Sir/ Madam,
</span>
<span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Here we would like to request your kind <span style=\"text-decoration: underline;\"><strong>approval</strong></span> for Application with matter number " + 
      MATTER_NM + ".
</span>
" + 
      "<span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Customer Information:</span>

\r\n" + 
      "<table style=\"height: 108px; width: 100%; border-collapse: collapse;\" border=\"1\">\r\n" + 
      "<tbody>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Company Name</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + Company_Name + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Customer Name </span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + Customer_Name + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "</tbody>\r\n" + 
      "</table>\r\n

" + 

      "<span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Contract Information:</span>

\r\n" + 
      "<table style=\"height: 108px; width: 100%; border-collapse: collapse;\" border=\"1\">\r\n" + 
      "<tbody>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Contract Type</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + Contract_Type + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr>\r\n" + 
      "<td style=\"width: 25.9017%;\"><span style=\"font-family: arial, helvetica, sans-serif;\">Contract No</span><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">
</span></td>\r\n" + 
      "<td style=\"width: 1.2924%;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:
</span></td>\r\n" + 
      "<td style=\"width: 72.8059%;\"><span style=\"font-size: 14px; font-family: arial, helvetica, sans-serif;\">" + Contract_No + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Contract Title</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + Contract_Title + " </span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Contract From</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + Term_start + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Contract End</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + Term_end + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "</tbody>\r\n" + 
      "</table>\r\n

" + 

      "<span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">PIC of Contract (Customer) Information:</span>

\r\n" + 
      "<table style=\"height: 108px; width: 100%; border-collapse: collapse;\" border=\"1\">\r\n" + 
      "<tbody>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Job Title</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + PIC_C_JTitle + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr>\r\n" + 
      "<td style=\"width: 25.9017%;\"><span style=\"font-family: arial, helvetica, sans-serif;\">Name</span><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">
</span></td>\r\n" + 
      "<td style=\"width: 1.2924%;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:
</span></td>\r\n" + 
      "<td style=\"width: 72.8059%;\"><span style=\"font-size: 14px; font-family: arial, helvetica, sans-serif;\">" + PIC_C_NM + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Phone</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + PIC_C_Phone + " </span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Email</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + PIC_C_Email + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "</tbody>\r\n" + 
      "</table>\r\n

" + 

      "<span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">PIC of Contract (Marimo) Information:</span>

\r\n" + 
      "<table style=\"height: 108px; width: 100%; border-collapse: collapse;\" border=\"1\">\r\n" + 
      "<tbody>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Job Title</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + PIC_YK_JTitle + " </span></td>\r\n" + 
      "</tr>\r\n" + 
      "<tr style=\"height: 18px;\">\r\n" + 
      "<td style=\"width: 25.9017%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">Name</span></td>\r\n" + 
      "<td style=\"width: 1.2924%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">:</span></td>\r\n" + 
      "<td style=\"width: 72.8059%; height: 18px;\"><span style=\"font-family: arial, helvetica, sans-serif; font-size: 14px;\">" + PIC_YK_NM + "</span></td>\r\n" + 
      "</tr>\r\n" + 
      "</tbody>\r\n" + 
      "</table>\r\n

" + 

      "
<span style='font-family: arial, helvetica, sans-serif; font-size: 14px;'>Please <a href='" + DummyLink + "'>click here</a>  to process the application.</span>
" + 
      "<span style='font-family: arial, helvetica, sans-serif; font-size: 14px;'>Thank you.</span>

" + 
      "<span style='font-family: arial, helvetica, sans-serif; font-size: 14px;'>Best Regards,</span>
" + 
      "<span style='font-family: arial, helvetica, sans-serif; font-size: 14px;'>Marimo Team</span>

" + 
      "<span style='font-family: arial, helvetica, sans-serif; font-size: 14px;'>Note: This email is auto generated by System</span>\r\n";
    htmlpart.setContent(htmlContent, "text/html; charset=utf-8");
    ApprovalContractInfoAttachmentRepository Attach_Repo = new ApprovalContractInfoAttachmentRepository();
    List<ApprovalContractInfoAttachmentModel> entityInfoAttachment = new ArrayList<>();
    entityInfoAttachment = new ArrayList<>(Attach_Repo.readTempInfoFile(MATTER_NM, "system_matter_id"));
    MimeMultipart mimeMultipart = new MimeMultipart();
    mimeMultipart.addBodyPart((BodyPart)htmlpart);
    for (int j = 0; j < entityInfoAttachment.size(); j++) {
      ApprovalContractInfoAttachmentModel model = entityInfoAttachment.get(j);
      String System_id = model.getSystem_matter_id();
      String File_name = model.getFile_name();
      String File_path = model.getFile_path();
      String File_Real_name = model.getFile_real_name();
      String fileDecode = URLDecoder.decode(File_path.toString(), "UTF-8");
      PublicStorage filedet = new PublicStorage(fileDecode);
      String Data_File = filedet.read();
      if (filedet.length() == 0L) {
        System.err.println("File is empty: " + File_Real_name);
      } else {
        MimeBodyPart attachment = new MimeBodyPart();
        ByteArrayDataSource byteArrayDataSource = new ByteArrayDataSource(Data_File, "application/octet-stream");
        attachment.setDataHandler(new DataHandler((DataSource)byteArrayDataSource));
        attachment.setFileName(File_name);
        mimeMultipart.addBodyPart((BodyPart)attachment);
      } 
    } 
    marimoMail.setContent((Multipart)mimeMultipart);
    Transport.send((Message)marimoMail);
    System.out.println("Email sent successfully.");
  }
```
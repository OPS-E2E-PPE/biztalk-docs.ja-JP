---
title: "WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inserting data, using a channel
- WCF channel model, performing an Insert operation
- how to, perform an insert operation using a channel
- channel programming, performing an insert operation
- performing an insert operation, using a channel
ms.assetid: 85c44507-0166-42ef-a908-6098f7a683fc
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540cd06f15ae95dba41636418be273a78c39f447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="4e1b7-102">WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-102">Run an Insert Operation in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="4e1b7-103">このセクションでは、チャネルを使用して Oracle データベースにレコードを挿入する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-103">This section shows how to insert a record into an Oracle database by using a channel.</span></span> <span data-ttu-id="4e1b7-104">メッセージを送信するときに、メッセージ本文とメッセージのアクションの両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-104">You must specify both a message body and a message action when you send a message.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="4e1b7-105">挿入メッセージ</span><span class="sxs-lookup"><span data-stu-id="4e1b7-105">The Insert Message</span></span>  
 <span data-ttu-id="4e1b7-106">次の XML は、人事で挿入操作のメッセージ本文を示しています。EMPLOYEES テーブル。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-106">The following XML shows a message body for an Insert operation on the HR.EMPLOYEES table.</span></span> <span data-ttu-id="4e1b7-107">レコード セットは、1 人の従業員レコードで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-107">The record set consists of a single employee record.</span></span> <span data-ttu-id="4e1b7-108">挿入メッセージのスキーマの詳細については、次を参照してください。 [、基本的な Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-108">For more information about the schema of an Insert message, see [Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span> <span data-ttu-id="4e1b7-109">これは、この例で使用される Employee_Insert.xml ファイルの内容です。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-109">This is the contents of the Employee_Insert.xml file used in the example.</span></span>  
  
```  
\<!-- New namespace: http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES -->  
<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES">  
    \<RECORDSET xmlns:i="http://www.w3.org/2001/XMLSchema-instance">  
        <EMPLOYEESRECORDINSERT>  
            <EMPLOYEE_ID>0</EMPLOYEE_ID>  
            <FIRST_NAME>Anton</FIRST_NAME>  
            <LAST_NAME>Kirilov</LAST_NAME>  
            <EMAIL></EMAIL>  
            <PHONE_NUMBER>555-0198</PHONE_NUMBER>  
            <HIRE_DATE>2007-03-01T00:00:00.0000000</HIRE_DATE>  
            <JOB_ID>FI_ACCOUNT</JOB_ID>  
            <SALARY>5000</SALARY>  
            <COMMISSION_PCT>0.15</COMMISSION_PCT>  
            <MANAGER_ID>108</MANAGER_ID>  
            <DEPARTMENT_ID>100</DEPARTMENT_ID>  
       </EMPLOYEESRECORDINSERT>  
    </RECORDSET>  
</Insert>  
```  
  
## <a name="specifying-the-message-action"></a><span data-ttu-id="4e1b7-110">メッセージのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-110">Specifying the Message Action</span></span>  
 <span data-ttu-id="4e1b7-111">SOAP メッセージを送信するときに、メッセージのアクションを指定する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-111">You must specify a message action when you send a SOAP message to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="4e1b7-112">次の例のように、メッセージを作成するときに、メッセージのアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-112">You can specify the message action when you create the message as in the following example.</span></span>  
  
```  
Message messageIn2 = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES/Insert", readerIn2);  
```  
  
 <span data-ttu-id="4e1b7-113">この例では、「/HR/テーブル/従業員/挿入」のメッセージ アクションが指定されている、人事部で挿入操作します。実行するのには、EMPLOYEES テーブルです。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-113">The message action in this example, "/HR/Table/EMPLOYEES/Insert", specifies that an Insert operation on the HR.EMPLOYEES table is to be performed</span></span>  
  
## <a name="sending-the-insert-message"></a><span data-ttu-id="4e1b7-114">挿入のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-114">Sending the Insert Message</span></span>  
 <span data-ttu-id="4e1b7-115">この例では、チャネル経由での Oracle テーブルに対する挿入操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-115">This example shows how to perform an Insert operation on an Oracle table over a channel.</span></span> <span data-ttu-id="4e1b7-116">コードによって公開される SQLEXECUTE 操作を使用して、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle シーケンスの次の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-116">The code uses the SQLEXECUTE operation exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to return the next value of an Oracle SEQUENCE.</span></span> <span data-ttu-id="4e1b7-117">この値は、EMPLOYEE_ID レコードのフィールドに、挿入書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-117">This value is then written to the EMPLOYEE_ID field in the Insert record.</span></span> <span data-ttu-id="4e1b7-118">このパターンでは、自動生成された主キー値を持つデータベースに行を挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-118">This pattern enables you to insert rows into databases that have an auto-generated primary key value.</span></span> <span data-ttu-id="4e1b7-119">詳細については、SQLEXECUTE 操作を呼び出してチャネル経由で、次を参照してください。 [WCF チャネル モデルを使用して、SQLEXECUTE 操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e1b7-119">For more information about invoking the SQLEXECUTE operation over a channel, see [Run a SQLEXECUTE Operation by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Xml;  
using System.IO;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
using Microsoft.ServiceModel.Adapters;  
using Microsoft.Adapters.OracleDB;  
  
namespace OracleDMLChannel  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create Endpoint  
            EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
  
            // Create Binding  
            OracleDBBinding binding = new OracleDBBinding();  
  
            // Create Channel Factory  
            ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
            factory.Credentials.UserName.UserName = "HR";  
            factory.Credentials.UserName.Password = "TIGER";  
            factory.Open();  
  
            // Create Request Channel  
            IRequestChannel channel = factory.CreateChannel();  
            channel.Open();  
  
            // Send Request  
            System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create("SQLExecute.xml");  
  
            Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
            Message messageOut = channel.Request(messageIn);  
  
            // Get Response XML  
            XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
            // Get Employee ID  
            string id = null;  
            XmlDocument doc = new XmlDocument();  
            doc.Load(readerOut);  
            XmlNodeList list = doc.GetElementsByTagName("ColumnValue");  
            if (list.Count > 0) id = list[0].InnerXml;  
  
            // Compose Insert XML  
            XmlDocument insertDoc = new XmlDocument();  
            insertDoc.Load("Employee_Insert.xml");  
  
            // Change Employee ID  
            XmlNodeList empidList = insertDoc.GetElementsByTagName("EMPLOYEE_ID");  
            XmlNode empidNode = empidList[0];  
            empidNode.InnerXml = id;  
  
            // Change email  
            XmlNodeList emailList = insertDoc.GetElementsByTagName("EMAIL");  
            XmlNode emailNode = emailList[0];  
            emailNode.InnerXml = "scotty" + id + "@microsoft.com";  
  
            // Change date  
            XmlNodeList dateList = insertDoc.GetElementsByTagName("HIRE_DATE");  
            XmlNode dateNode = dateList[0];  
            dateNode.InnerXml = "2007-03-01T00:00:00.0000000";  
  
            StringReader strReader = new StringReader(insertDoc.InnerXml);  
            XmlReader readerIn2 = XmlReader.Create(strReader);  
  
            // Send XML  
            Message messageIn2 = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES/Insert ", readerIn2);  
            Message messageOut2 = channel.Request(messageIn2);  
  
            // Close the messages  
            messageOut.Close();  
            messageOut2.Close();  
  
            channel.Close();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e1b7-120">参照</span><span class="sxs-lookup"><span data-stu-id="4e1b7-120">See Also</span></span>  
 <span data-ttu-id="4e1b7-121">[WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) </span><span class="sxs-lookup"><span data-stu-id="4e1b7-121">[Develop Oracle Database applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) </span></span>  
 <span data-ttu-id="4e1b7-122">[Oracle データベースを使用して、チャネルを作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="4e1b7-122">[Create a channel using Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) </span></span>  
 <span data-ttu-id="4e1b7-123">[WCF チャネル モデルを使用して、SQLEXECUTE 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md) </span><span class="sxs-lookup"><span data-stu-id="4e1b7-123">[Run a SQLEXECUTE Operation by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md) </span></span>  
 [<span data-ttu-id="4e1b7-124">WCF チャネル モデルを使用して Oracle データベース内の関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="4e1b7-124">Invoke a Function in Oracle Database Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)
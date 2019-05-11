---
title: 手順 3 b:Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 115c908f-777b-4c51-85ea-71d639b01775
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 332a444cc2be3851f366e31360068372eb06fb2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392623"
---
# <a name="step-3b-retrieve-opportunity-details-from-salesforce-using-the-wcf-webhttp-adapter"></a><span data-ttu-id="c9e8f-102">手順 3 b:Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-102">Step 3b: Retrieve Opportunity Details from Salesforce using the WCF-WebHttp Adapter</span></span>
<span data-ttu-id="c9e8f-103">このセクションで、オーケストレーションを受信した営業案件通知を処理して、通知から営業案件名を抽出するを使用して Salesforce に送信する要求クエリを作成するを強化します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-103">In this section, we’ll enhance the orchestration to process the incoming opportunity notification, extract the opportunity name from the notification, and use that to create a request query to send to Salesforce.</span></span> <span data-ttu-id="c9e8f-104">これには、営業案件に関連付けられている製品に関する特定の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-104">This retrieves specific details about the products associated with the opportunity.</span></span> <span data-ttu-id="c9e8f-105">Salesforce からクエリ応答の受信に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-105">The query response from Salesforce is received back into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c9e8f-106">これを実現するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-106">To achieve this, we’ll perform the following steps:</span></span>  
  
-   <span data-ttu-id="c9e8f-107">Salesforce にクエリ メッセージを送信するスキーマとメッセージ変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-107">Create a schema and message variables to send a query message to Salesforce.</span></span>  
  
-   <span data-ttu-id="c9e8f-108">営業案件に関連付けられている製品の詳細を取得するクエリを作成するための営業案件通知からの値を使用するマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-108">Create a map to use the values from the opportunity notification for creating a query to retrieve product details associated with the opportunity.</span></span>  
  
-   <span data-ttu-id="c9e8f-109">Salesforce からクエリ応答を受信するスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-109">Create a schema to receive a query response from Salesforce.</span></span>  
  
-   <span data-ttu-id="c9e8f-110">要求および応答スキーマにメッセージ変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-110">Create message variables for the request and response schemas.</span></span>  
  
## <a name="create-schema-and-message-variables-to-send-query-messages-to-salesforce"></a><span data-ttu-id="c9e8f-111">Salesforce にクエリ メッセージを送信するには、スキーマとメッセージ変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-111">Create Schema and Message Variables to Send Query Messages to Salesforce</span></span>  
 <span data-ttu-id="c9e8f-112">Salesforce から営業案件通知から利用できる情報を使用して製品の詳細を取得、Salesforce にクエリを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-112">To retrieve product details from Salesforce by using the information available through an Opportunity notification, we need to send a query to Salesforce.</span></span> <span data-ttu-id="c9e8f-113">クエリは、XML メッセージとして Salesforce に送信されます。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-113">The query is sent to Salesforce as an XML message.</span></span> <span data-ttu-id="c9e8f-114">そのため、次の手順で要求メッセージのスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-114">So, in the following procedure we create a schema for the request message.</span></span> <span data-ttu-id="c9e8f-115">以降の手順は営業案件の製品の詳細を取得するためのクエリを作成するには、このスキーマで営業案件通知スキーマをマップします。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-115">In the subsequent procedure, we will map the opportunity notification schema with this schema to construct a query for retrieving product details for the opportunity.</span></span>  
  
#### <a name="to-create-a-schema-for-sending-query-request"></a><span data-ttu-id="c9e8f-116">クエリ要求を送信するためのスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="c9e8f-116">To create a schema for sending query request</span></span>  
  
1. <span data-ttu-id="c9e8f-117">新しいスキーマを追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-117">Add a new schema to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="c9e8f-118">「`QueryRequest.xsd`」という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-118">Name it `QueryRequest.xsd`.</span></span>  
  
2. <span data-ttu-id="c9e8f-119">ルート ノードの名前を変更`QueryRequest`します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-119">Rename the root node to `QueryRequest`.</span></span> <span data-ttu-id="c9e8f-120">QueryRequest レコードの下の子フィールド要素を追加し、名前`Query`します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-120">Add a child field element under the QueryRequest record and name it `Query`.</span></span>  
  
3. <span data-ttu-id="c9e8f-121">昇格、**クエリ**オーケストレーション内で使用できるように、スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-121">Promote the **Query** element in the schema so that it is available for use within the orchestration.</span></span> <span data-ttu-id="c9e8f-122">後の手順では、クエリ文字列を割り当てる、昇格させたこの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-122">In the later steps we will use this promoted element to assign the query string.</span></span>  
  
    <span data-ttu-id="c9e8f-123">右クリックし、**クエリ**要素を指す**昇格**、 をクリックし、**クイック昇格**します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-123">Right-click the **Query** element, point to **Promote**, and then click **Quick Promotions**.</span></span> <span data-ttu-id="c9e8f-124">これは、結果、作成、 **PropertySchema.xsd**でスキーマを**クエリ**要素。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-124">This results in creating a **PropertySchema.xsd** schema with a **Query** element.</span></span> <span data-ttu-id="c9e8f-125">PropertySchema の名前空間に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-125">Note the namespace for the PropertySchema.</span></span> <span data-ttu-id="c9e8f-126">必要があります、今後、このセクションの手順で物理ポートを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-126">You will need this in the future steps while configuring the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4. <span data-ttu-id="c9e8f-127">すべての変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-127">Save all changes.</span></span>  
  
## <a name="map-the-opportunity-notification-schema-to-the-query-schema"></a><span data-ttu-id="c9e8f-128">営業案件通知スキーマをクエリ スキーマにマップします。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-128">Map the Opportunity Notification Schema to the Query Schema</span></span>  
 <span data-ttu-id="c9e8f-129">営業案件に関連付けられている製品の詳細を取得するには、Salesforce に次のようなクエリを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-129">To retrieve the product details associated with the opportunity, we need to send a query similar to the following to Salesforce:</span></span>  
  
```  
SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '<opportunity_name>'  
```  
  
 <span data-ttu-id="c9e8f-130">私たちの前の手順で、クエリ メッセージのスキーマを既に作成しています。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-130">In the previous procedure we already created the schema of the query message.</span></span> <span data-ttu-id="c9e8f-131">この手順では、クエリ要求スキーマに、営業案件通知スキーマをマップし、functoid を使用して、このクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-131">In this procedure, we map the opportunity notification schema to the query request schema and use functoids to construct this query.</span></span> <span data-ttu-id="c9e8f-132">このクエリは値として渡される、**クエリ**内の要素、 **QueryRequest.xsd**スキーマ。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-132">This query will be passed as a value to the **Query** element in the **QueryRequest.xsd** schema.</span></span>  
  
#### <a name="to-map-the-opportunity-notification"></a><span data-ttu-id="c9e8f-133">営業案件通知をマップするには</span><span class="sxs-lookup"><span data-stu-id="c9e8f-133">To map the opportunity notification</span></span>  
  
1. <span data-ttu-id="c9e8f-134">マップを追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-134">Add a map to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="c9e8f-135">マップの名前を`Notification_QueryRequest.btm`します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-135">Name the map `Notification_QueryRequest.btm`.</span></span>  
  
2. <span data-ttu-id="c9e8f-136">送信元スキーマを設定**NotificationService_soap_sforce_com_2005_09_outbound.xsd**します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-136">Set the source schema to **NotificationService_soap_sforce_com_2005_09_outbound.xsd**.</span></span> <span data-ttu-id="c9e8f-137">送信先スキーマを設定**QueryRequest**.xsd。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-137">Set the destination schema to **QueryRequest**.xsd.</span></span>  
  
3. <span data-ttu-id="c9e8f-138">追加、**文字列連結**functoid をマッピング画面。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-138">Add a **String Concatenate** functoid to the mapping surface.</span></span> <span data-ttu-id="c9e8f-139">開く、**文字列連結 Functoid の構成** ダイアログ ボックスし、次のように入力値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-139">Open the **Configure String Concatenate Functoid** dialog box and specify the input values as follows:</span></span>  
  
   |||  
   |-|-|  
   |<span data-ttu-id="c9e8f-140">Input [0]</span><span class="sxs-lookup"><span data-stu-id="c9e8f-140">Input[0]</span></span>|<span data-ttu-id="c9e8f-141">SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '</span><span class="sxs-lookup"><span data-stu-id="c9e8f-141">SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '</span></span>|  
   |<span data-ttu-id="c9e8f-142">Input [1]</span><span class="sxs-lookup"><span data-stu-id="c9e8f-142">Input[1]</span></span>|<span data-ttu-id="c9e8f-143">ソース スキーマの Name 要素を名前の要素の値を 2 番目の入力として使用する functoid に接続します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-143">Connect the Name element in the source schema to the functoid to use the value of the Name element as the second input.</span></span>|  
   |<span data-ttu-id="c9e8f-144">[2] の入力</span><span class="sxs-lookup"><span data-stu-id="c9e8f-144">Input[2]</span></span>|<span data-ttu-id="c9e8f-145">'**に注意してください。** 最後の入力値に対してのみ単一引用符 (') を指定します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-145">' **Note:**  For the last input value, specify only a closing single quote (').</span></span>|  
  
    <span data-ttu-id="c9e8f-146">次のスクリーン ショットの構成を示しています、**文字列連結**functoid。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-146">The following screenshot depicts the configuration for the **String Concatenate** functoid.</span></span>  
  
    <span data-ttu-id="c9e8f-147">![文字列連結 functoid の構成](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")</span><span class="sxs-lookup"><span data-stu-id="c9e8f-147">![Configure String Concatenate functoid](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")</span></span>  
  
    <span data-ttu-id="c9e8f-148">次の 3 つの入力パラメーターが連結された場合は、Salesforce に送信するに必要なクエリが形成されます。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-148">When the three input parameters are concatenated, it will form the required query to be sent to Salesforce.</span></span>  
  
4. <span data-ttu-id="c9e8f-149">次のスクリーン ショットに示すように、文字列連結 functoid を送信先スキーマ内のクエリの要素に接続します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-149">Connect the String Concatenate functoid to the Query element in the destination schema, as shown in the following screenshot.</span></span>  
  
    <span data-ttu-id="c9e8f-150">![通知応答をクエリ スキーマにマップする](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")</span><span class="sxs-lookup"><span data-stu-id="c9e8f-150">![Map notification response to query schema](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")</span></span>  
  
5. <span data-ttu-id="c9e8f-151">マップに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-151">Save changes to the map.</span></span>  
  
## <a name="creating-schema-to-receive-the-query-response-message"></a><span data-ttu-id="c9e8f-152">クエリの応答メッセージを受信するスキーマの作成</span><span class="sxs-lookup"><span data-stu-id="c9e8f-152">Creating Schema to Receive the Query Response Message</span></span>  
 <span data-ttu-id="c9e8f-153">このセクションでは、Salesforce からクエリ応答メッセージを受信するスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-153">In this section, we create the schema to receive the query response message from Salesforce.</span></span> <span data-ttu-id="c9e8f-154">このセクションで、クエリの応答のスキーマを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-154">In this section, we manually create the schema for the query response.</span></span>  
  
#### <a name="to-create-a-schema-to-receive-the-query-response"></a><span data-ttu-id="c9e8f-155">クエリの応答を受信するスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="c9e8f-155">To create a schema to receive the query response</span></span>  
  
1. <span data-ttu-id="c9e8f-156">新しいスキーマを追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトし、名前を付けます`QueryResult.xsd`します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-156">Add a new schema to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project and name it `QueryResult.xsd`.</span></span>  
  
2. <span data-ttu-id="c9e8f-157">Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017)オブジェクトは Salesforce から受信したクエリの応答を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-157">The Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017) object depicts the query response received from Salesforce.</span></span> <span data-ttu-id="c9e8f-158">そのため、ように、次のスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-158">So, we’ll build a schema to depict the following:</span></span>  
  
   ```  
   <?xml version="1.0" encoding="utf-16" ?>  
   - <xs:schema xmlns="http://BtsSalesforceIntegration.QueryResult" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://BtsSalesforceIntegration.QueryResult" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
     - <xs:element name="QueryResult">  
       - <xs:complexType>  
         - <xs:sequence>  
           <xs:element name="done" type="xs:string" />  
           - <xs:sequence>  
             - <xs:element name="records">  
               - <xs:complexType>  
                 - <xs:sequence>  
                   <xs:element name="Id" type="xs:string" />  
                   <xs:element name="Amount" type="xs:string" />  
                   <xs:element name="Name" type="xs:string" />  
                   - <xs:sequence>  
                     - <xs:element name="OpportunityLineItems">  
                       - <xs:complexType>  
                         - <xs:sequence>  
                           <xs:element name="done" type="xs:string" />  
                           - <xs:sequence minOccurs="1" maxOccurs="unbounded">  
                             - <xs:element name="records">  
                               - <xs:complexType>  
                                 - <xs:sequence>  
                                   <xs:element name="Quantity" type="xs:string" />  
                                   <xs:element name="ListPrice" type="xs:string" />  
                                   - <xs:element name="PricebookEntry">  
                                     - <xs:complexType>  
                                       - <xs:sequence>  
                                         <xs:element name="UnitPrice" type="xs:string" />  
                                         <xs:element name="Name" type="xs:string" />  
                                       </xs:sequence>  
                                       <xs:attribute name="type" type="xs:string" />  
                                       <xs:attribute name="url" type="xs:string" />  
                                     </xs:complexType>  
                                   </xs:element>  
                                 </xs:sequence>  
                                 <xs:attribute name="type" type="xs:string" />  
                                 <xs:attribute name="url" type="xs:string" />  
                               </xs:complexType>  
                             </xs:element>  
                           </xs:sequence>  
                           <xs:element name="totalSize" type="xs:string" />  
                         </xs:sequence>  
                       </xs:complexType>  
                     </xs:element>  
                   </xs:sequence>  
                 </xs:sequence>  
                 <xs:attribute name="type" type="xs:string" />  
                 <xs:attribute name="url" type="xs:string" />  
               </xs:complexType>  
             </xs:element>  
           </xs:sequence>  
           <xs:element name="totalSize" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
     </xs:element>  
   </xs:schema>  
   ```  
  
    <span data-ttu-id="c9e8f-159">スキーマの構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-159">The schema structure should look like the following:</span></span>  
  
    <span data-ttu-id="c9e8f-160">![Salesforce からクエリ応答のスキーマ](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")</span><span class="sxs-lookup"><span data-stu-id="c9e8f-160">![Schema for query response from Salesforce](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")</span></span>  
  
3. <span data-ttu-id="c9e8f-161">スキーマの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-161">Save changes to the schema.</span></span>  
  
## <a name="create-message-variables-for-queryrequest-and-queryresult-schemas"></a><span data-ttu-id="c9e8f-162">QueryRequest および QueryResult スキーマのメッセージ変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-162">Create Message Variables for QueryRequest and QueryResult Schemas</span></span>  
 <span data-ttu-id="c9e8f-163">QueryRequest および QueryResult スキーマを作成した後は、2 つのメッセージ型を表すオーケストレーションで、2 つのメッセージ変数を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-163">After you have created the QueryRequest and QueryResult schemas, you must create two message variables in the orchestration to represent the two message types.</span></span>  
  
#### <a name="to-create-message-variables"></a><span data-ttu-id="c9e8f-164">メッセージ変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="c9e8f-164">To create message variables</span></span>  
  
1.  <span data-ttu-id="c9e8f-165">開く、 **NotificationService.odx**オーケストレーション、オーケストレーション ビューで 2 つの新しいメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-165">Open the **NotificationService.odx** orchestration and in the orchestration view, add two new messages.</span></span> <span data-ttu-id="c9e8f-166">メッセージの名前は設定`QueryRequestMsg`と`QueryResultMsg`します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-166">Set the message names as `QueryRequestMsg` and `QueryResultMsg`.</span></span>  
  
2.  <span data-ttu-id="c9e8f-167">メッセージの種類を設定**QueryRequestMsg**として**BtsSalesforceIntegration.QueryRequest**します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-167">Set the message type for **QueryRequestMsg** as **BtsSalesforceIntegration.QueryRequest**.</span></span>  
  
3.  <span data-ttu-id="c9e8f-168">メッセージの種類を設定**QueryResultMsg**として**BtsSalesforceIntegration.QueryResult**します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-168">Set the message type for **QueryResultMsg** as **BtsSalesforceIntegration.QueryResult**.</span></span>  
  
4.  <span data-ttu-id="c9e8f-169">オーケストレーションに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-169">Save changes to the orchestration.</span></span>  
  
## <a name="update-the-orchestration-to-send-message-to-salesforce-and-receive-a-response"></a><span data-ttu-id="c9e8f-170">Salesforce にメッセージを送信し、応答を受信するオーケストレーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-170">Update the Orchestration to Send Message to Salesforce and Receive a Response</span></span>  
 <span data-ttu-id="c9e8f-171">トピックの[手順 3 a:BizTalk Server に Salesforce の営業案件通知を受信](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)、Salesforce から営業案件通知を受け取るし、受信確認を送信するオーケストレーションを構築しました。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-171">In the topic [Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md), we built the orchestration that receives opportunity notifications from Salesforce and sends an acknowledgement.</span></span> <span data-ttu-id="c9e8f-172">この手順では、営業案件に関連する製品の詳細を取得し、応答を受信する Salesforce にクエリ要求を送信するには、このオーケストレーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-172">In this step, we build on this orchestration to send a query request to Salesforce to get product details related to the opportunity and receive a response.</span></span> <span data-ttu-id="c9e8f-173">この手順では、スキーマ (QueryRequest.xsd と QueryResult.xsd) および使用するメッセージ変数 (QueryRequestMsg と QueryResultMsg) を既に作成しましたがいます。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-173">We have already created the schemas (QueryRequest.xsd and QueryResult.xsd) and the message variables (QueryRequestMsg and QueryResultMsg) that we’ll use in this step.</span></span>  
  
#### <a name="to-send-a-query-request-to-salesforce-and-receive-a-response"></a><span data-ttu-id="c9e8f-174">Salesforce にクエリ要求を送信し、応答を受信するには</span><span class="sxs-lookup"><span data-stu-id="c9e8f-174">To send a query request to Salesforce and receive a response</span></span>  
  
1. <span data-ttu-id="c9e8f-175">後のメッセージの構築図形を追加、 **SendNotificationAck**図形。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-175">Add a Construct Message shape after the **SendNotificationAck** shape.</span></span> <span data-ttu-id="c9e8f-176">図形の名前を設定`ConstructQuery`設定と、**構築メッセージ**プロパティを**QueryRequestMsg**します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-176">Set the name of the shape to `ConstructQuery` and set the **Messages Constructed** property to **QueryRequestMsg**.</span></span>  
  
2. <span data-ttu-id="c9e8f-177">内で、 **ConstructQuery**図形を追加、**変換**図形。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-177">Within the **ConstructQuery** shape, add a **Transform** shape.</span></span> <span data-ttu-id="c9e8f-178">変換の構成 ダイアログ ボックスを開くための変換図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-178">Double-click the Transform shape to open the Transform Configuration dialog box.</span></span> <span data-ttu-id="c9e8f-179">ダイアログ ボックスで、選択、**既存のマップ**、オプションをドロップダウン リストから選択して**BtsSalesforceIntegration.Notification_QueryRequest**します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-179">In the dialog box, select the **Existing Map** option, and then from the drop-down select **BtsSalesforceIntegration.Notification_QueryRequest**.</span></span> <span data-ttu-id="c9e8f-180">設定**ソース**に**NotificaitonMessage**、**先**に**QueryRequestMsg**、順にクリックします**OK**.</span><span class="sxs-lookup"><span data-stu-id="c9e8f-180">Set **Source** to **NotificaitonMessage**, **Destination** to **QueryRequestMsg**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="c9e8f-181">内で、 **ConstructQuery**図形、変換図形の後にメッセージの割り当て図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-181">Within the **ConstructQuery** shape, after the Transform shape, add a Message Assignment shape.</span></span> <span data-ttu-id="c9e8f-182">メッセージの割り当て図形をダブルクリックし、次の式を追加します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-182">Double-click the Message Assignment shape and add the following expression:</span></span>  
  
   ```  
   QueryRequestMsg(BtsSalesforceIntegration.PropertySchema.Query) = QueryRequestMsg.Query;  
   ```  
  
    <span data-ttu-id="c9e8f-183">これによりの値を渡して、**クエリ**内の要素、 **QueryRequestMsg**スキーマの昇格要素**クエリ**プロパティ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-183">By doing this, we pass on the value of the **Query** element in the **QueryRequestMsg** schema to the promoted element **Query** in the property schema.</span></span> <span data-ttu-id="c9e8f-184">Wcf-webhttp ポートを構成するときに要求メッセージにクエリの値を動的に渡すをこの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-184">While configuring the WCF-WebHttp port, we’ll use this element to dynamically pass on the query value to the request message.</span></span>  
  
4. <span data-ttu-id="c9e8f-185">後に、 **ConstructQuery**図形を送信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-185">After the **ConstructQuery** shape, add a Send shape.</span></span> <span data-ttu-id="c9e8f-186">図形の名前は`SendQueryRequest`としてメッセージの種類を設定および**QueryRequestMsg**します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-186">Name the shape `SendQueryRequest` and set the message type as **QueryRequestMsg**.</span></span>  
  
5. <span data-ttu-id="c9e8f-187">送信図形の後に受信図形を追加し、名前`ReceiveQueryResult`します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-187">After the Send shape, add a Receive shape and name it `ReceiveQueryResult`.</span></span> <span data-ttu-id="c9e8f-188">図形のメッセージの種類を設定**QueryResultMsg**します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-188">Set the message type of the shape to **QueryResultMsg**.</span></span>  
  
6. <span data-ttu-id="c9e8f-189">Salesforce にクエリ要求を送信し、応答で、クエリの結果を受信するポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-189">Add a port to send query requests to Salesforce and receive the query result in response.</span></span> <span data-ttu-id="c9e8f-190">ポート構成ウィザードでは、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-190">In the Port Configuration wizard, select the following options:</span></span>  
  
   - <span data-ttu-id="c9e8f-191">ポート名を指定`SalesforceRESTInterface`します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-191">Specify the port name as `SalesforceRESTInterface`.</span></span>  
  
   - <span data-ttu-id="c9e8f-192">新しいポートの種類を作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-192">Select the option to create a new port type.</span></span>  
  
   - <span data-ttu-id="c9e8f-193">設定**通信パターン**に*要求-応答*します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-193">Set **Communication Pattern** to *Request-Response*.</span></span>  
  
   - <span data-ttu-id="c9e8f-194">設定**ポートの通信方向**に*要求の送信と応答の受信を行います*設定と**ポートのバインド**に*以降指定*.</span><span class="sxs-lookup"><span data-stu-id="c9e8f-194">Set **Port direction of communication** to *I’ll be sending a request and receiving a response* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="c9e8f-195">接続、**要求**送信図形にポートの操作 (*SendQueryRequest*) および**応答**受信図形にポートの操作 (*ReceiveQueryResult*)。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-195">Connect the **Request** operation of port to the Send shape (*SendQueryRequest*) and the **Response** operation of the port to the Receive shape (*ReceiveQueryResult*).</span></span> <span data-ttu-id="c9e8f-196">次のスクリーン ショットは、Salesforce にクエリ要求の送信と応答の受信のプロセスを表すオーケストレーションの一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-196">The following screenshot depicts the part of the orchestration that represents the process of sending the query request to Salesforce and receiving a response.</span></span>  
  
     <span data-ttu-id="c9e8f-197">![Salesforce にクエリを送信し、応答を受信する](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")</span><span class="sxs-lookup"><span data-stu-id="c9e8f-197">![Send a query to Salesforce and receive response](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")</span></span>  
  
   <span data-ttu-id="c9e8f-198">このトピックでは、Salesforce にクエリ要求を送信し、Salesforce で作成された営業案件に関する詳細 (など、製品、数量など) を受信するオーケストレーションを更新しました。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-198">In this topic, we updated the orchestration to send a query request to Salesforce and receive more details (such as products, quantity, etc.) about the opportunity that is created in Salesforce.</span></span> <span data-ttu-id="c9e8f-199">以降のトピックでは、オンプレミスの SQL Server データベースに、Salesforce 応答を入力するには、このソリューションを更新します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-199">In the subsequent topics, we will update this solution to enter the Salesforce response into an on-premise SQL Server database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e8f-200">参照</span><span class="sxs-lookup"><span data-stu-id="c9e8f-200">See Also</span></span>  
 [<span data-ttu-id="c9e8f-201">ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e8f-201">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)
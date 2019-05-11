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
# <a name="step-3b-retrieve-opportunity-details-from-salesforce-using-the-wcf-webhttp-adapter"></a>手順 3 b:Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得します。
このセクションで、オーケストレーションを受信した営業案件通知を処理して、通知から営業案件名を抽出するを使用して Salesforce に送信する要求クエリを作成するを強化します。 これには、営業案件に関連付けられている製品に関する特定の詳細を取得します。 Salesforce からクエリ応答の受信に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 これを実現するには、次の手順を実行します。  
  
-   Salesforce にクエリ メッセージを送信するスキーマとメッセージ変数を作成します。  
  
-   営業案件に関連付けられている製品の詳細を取得するクエリを作成するための営業案件通知からの値を使用するマップを作成します。  
  
-   Salesforce からクエリ応答を受信するスキーマを作成します。  
  
-   要求および応答スキーマにメッセージ変数を作成します。  
  
## <a name="create-schema-and-message-variables-to-send-query-messages-to-salesforce"></a>Salesforce にクエリ メッセージを送信するには、スキーマとメッセージ変数を作成します。  
 Salesforce から営業案件通知から利用できる情報を使用して製品の詳細を取得、Salesforce にクエリを送信する必要があります。 クエリは、XML メッセージとして Salesforce に送信されます。 そのため、次の手順で要求メッセージのスキーマを作成します。 以降の手順は営業案件の製品の詳細を取得するためのクエリを作成するには、このスキーマで営業案件通知スキーマをマップします。  
  
#### <a name="to-create-a-schema-for-sending-query-request"></a>クエリ要求を送信するためのスキーマを作成するには  
  
1. 新しいスキーマを追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 「`QueryRequest.xsd`」という名前を入力します。  
  
2. ルート ノードの名前を変更`QueryRequest`します。 QueryRequest レコードの下の子フィールド要素を追加し、名前`Query`します。  
  
3. 昇格、**クエリ**オーケストレーション内で使用できるように、スキーマ内の要素。 後の手順では、クエリ文字列を割り当てる、昇格させたこの要素を使用します。  
  
    右クリックし、**クエリ**要素を指す**昇格**、 をクリックし、**クイック昇格**します。 これは、結果、作成、 **PropertySchema.xsd**でスキーマを**クエリ**要素。 PropertySchema の名前空間に注意してください。 必要があります、今後、このセクションの手順で物理ポートを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
4. すべての変更を保存します。  
  
## <a name="map-the-opportunity-notification-schema-to-the-query-schema"></a>営業案件通知スキーマをクエリ スキーマにマップします。  
 営業案件に関連付けられている製品の詳細を取得するには、Salesforce に次のようなクエリを送信する必要があります。  
  
```  
SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '<opportunity_name>'  
```  
  
 私たちの前の手順で、クエリ メッセージのスキーマを既に作成しています。 この手順では、クエリ要求スキーマに、営業案件通知スキーマをマップし、functoid を使用して、このクエリを作成します。 このクエリは値として渡される、**クエリ**内の要素、 **QueryRequest.xsd**スキーマ。  
  
#### <a name="to-map-the-opportunity-notification"></a>営業案件通知をマップするには  
  
1. マップを追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 マップの名前を`Notification_QueryRequest.btm`します。  
  
2. 送信元スキーマを設定**NotificationService_soap_sforce_com_2005_09_outbound.xsd**します。 送信先スキーマを設定**QueryRequest**.xsd。  
  
3. 追加、**文字列連結**functoid をマッピング画面。 開く、**文字列連結 Functoid の構成** ダイアログ ボックスし、次のように入力値を指定します。  
  
   |||  
   |-|-|  
   |Input [0]|SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '|  
   |Input [1]|ソース スキーマの Name 要素を名前の要素の値を 2 番目の入力として使用する functoid に接続します。|  
   |[2] の入力|'**に注意してください。** 最後の入力値に対してのみ単一引用符 (') を指定します。|  
  
    次のスクリーン ショットの構成を示しています、**文字列連結**functoid。  
  
    ![文字列連結 functoid の構成](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")  
  
    次の 3 つの入力パラメーターが連結された場合は、Salesforce に送信するに必要なクエリが形成されます。  
  
4. 次のスクリーン ショットに示すように、文字列連結 functoid を送信先スキーマ内のクエリの要素に接続します。  
  
    ![通知応答をクエリ スキーマにマップする](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")  
  
5. マップに変更を保存します。  
  
## <a name="creating-schema-to-receive-the-query-response-message"></a>クエリの応答メッセージを受信するスキーマの作成  
 このセクションでは、Salesforce からクエリ応答メッセージを受信するスキーマを作成します。 このセクションで、クエリの応答のスキーマを手動で作成します。  
  
#### <a name="to-create-a-schema-to-receive-the-query-response"></a>クエリの応答を受信するスキーマを作成するには  
  
1. 新しいスキーマを追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトし、名前を付けます`QueryResult.xsd`します。  
  
2. Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017)オブジェクトは Salesforce から受信したクエリの応答を示しています。 そのため、ように、次のスキーマを作成します。  
  
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
  
    スキーマの構造は次のようになります。  
  
    ![Salesforce からクエリ応答のスキーマ](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")  
  
3. スキーマの変更を保存します。  
  
## <a name="create-message-variables-for-queryrequest-and-queryresult-schemas"></a>QueryRequest および QueryResult スキーマのメッセージ変数を作成します。  
 QueryRequest および QueryResult スキーマを作成した後は、2 つのメッセージ型を表すオーケストレーションで、2 つのメッセージ変数を作成する必要があります。  
  
#### <a name="to-create-message-variables"></a>メッセージ変数を作成するには  
  
1.  開く、 **NotificationService.odx**オーケストレーション、オーケストレーション ビューで 2 つの新しいメッセージを追加します。 メッセージの名前は設定`QueryRequestMsg`と`QueryResultMsg`します。  
  
2.  メッセージの種類を設定**QueryRequestMsg**として**BtsSalesforceIntegration.QueryRequest**します。  
  
3.  メッセージの種類を設定**QueryResultMsg**として**BtsSalesforceIntegration.QueryResult**します。  
  
4.  オーケストレーションに変更を保存します。  
  
## <a name="update-the-orchestration-to-send-message-to-salesforce-and-receive-a-response"></a>Salesforce にメッセージを送信し、応答を受信するオーケストレーションを更新します。  
 トピックの[手順 3 a:BizTalk Server に Salesforce の営業案件通知を受信](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)、Salesforce から営業案件通知を受け取るし、受信確認を送信するオーケストレーションを構築しました。 この手順では、営業案件に関連する製品の詳細を取得し、応答を受信する Salesforce にクエリ要求を送信するには、このオーケストレーションを構築します。 この手順では、スキーマ (QueryRequest.xsd と QueryResult.xsd) および使用するメッセージ変数 (QueryRequestMsg と QueryResultMsg) を既に作成しましたがいます。  
  
#### <a name="to-send-a-query-request-to-salesforce-and-receive-a-response"></a>Salesforce にクエリ要求を送信し、応答を受信するには  
  
1. 後のメッセージの構築図形を追加、 **SendNotificationAck**図形。 図形の名前を設定`ConstructQuery`設定と、**構築メッセージ**プロパティを**QueryRequestMsg**します。  
  
2. 内で、 **ConstructQuery**図形を追加、**変換**図形。 変換の構成 ダイアログ ボックスを開くための変換図形をダブルクリックします。 ダイアログ ボックスで、選択、**既存のマップ**、オプションをドロップダウン リストから選択して**BtsSalesforceIntegration.Notification_QueryRequest**します。 設定**ソース**に**NotificaitonMessage**、**先**に**QueryRequestMsg**、順にクリックします**OK**.  
  
3. 内で、 **ConstructQuery**図形、変換図形の後にメッセージの割り当て図形を追加します。 メッセージの割り当て図形をダブルクリックし、次の式を追加します。  
  
   ```  
   QueryRequestMsg(BtsSalesforceIntegration.PropertySchema.Query) = QueryRequestMsg.Query;  
   ```  
  
    これによりの値を渡して、**クエリ**内の要素、 **QueryRequestMsg**スキーマの昇格要素**クエリ**プロパティ スキーマ。 Wcf-webhttp ポートを構成するときに要求メッセージにクエリの値を動的に渡すをこの要素を使用します。  
  
4. 後に、 **ConstructQuery**図形を送信図形を追加します。 図形の名前は`SendQueryRequest`としてメッセージの種類を設定および**QueryRequestMsg**します。  
  
5. 送信図形の後に受信図形を追加し、名前`ReceiveQueryResult`します。 図形のメッセージの種類を設定**QueryResultMsg**します。  
  
6. Salesforce にクエリ要求を送信し、応答で、クエリの結果を受信するポートを追加します。 ポート構成ウィザードでは、次のオプションを選択します。  
  
   - ポート名を指定`SalesforceRESTInterface`します。  
  
   - 新しいポートの種類を作成するオプションを選択します。  
  
   - 設定**通信パターン**に*要求-応答*します。  
  
   - 設定**ポートの通信方向**に*要求の送信と応答の受信を行います*設定と**ポートのバインド**に*以降指定*.  
  
     接続、**要求**送信図形にポートの操作 (*SendQueryRequest*) および**応答**受信図形にポートの操作 (*ReceiveQueryResult*)。 次のスクリーン ショットは、Salesforce にクエリ要求の送信と応答の受信のプロセスを表すオーケストレーションの一部を示しています。  
  
     ![Salesforce にクエリを送信し、応答を受信する](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")  
  
   このトピックでは、Salesforce にクエリ要求を送信し、Salesforce で作成された営業案件に関する詳細 (など、製品、数量など) を受信するオーケストレーションを更新しました。 以降のトピックでは、オンプレミスの SQL Server データベースに、Salesforce 応答を入力するには、このソリューションを更新します。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)
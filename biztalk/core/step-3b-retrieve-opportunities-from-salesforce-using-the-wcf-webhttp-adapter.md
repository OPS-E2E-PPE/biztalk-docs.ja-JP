---
title: '手順 3 b: Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得 |Microsoft ドキュメント'
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
ms.openlocfilehash: 05312890d7cd21810651e7e41a8418080912f72f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279554"
---
# <a name="step-3b-retrieve-opportunity-details-from-salesforce-using-the-wcf-webhttp-adapter"></a>手順 3 b: Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得
このセクションでは、受信する営業案件通知を処理するオーケストレーションを強化し、通知から営業案件名を抽出し、それを使用して Salesforce に送信する要求クエリを作成します。 こうすることで、営業案件に関連付けられている製品固有の詳細情報を取得します。 Salesforce からのクエリ応答は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されます。 これを達成するには、次の手順を実行します。  
  
-   Salesforce にクエリ メッセージを送信するためのスキーマとメッセージ変数を作成します。  
  
-   営業案件通知の値を使用して、営業案件に関連付けられている製品の詳細を取得するクエリを作成するためのマップを作成します。  
  
-   Salesforce からクエリ応答を受信するためのスキーマを作成します。  
  
-   要求および応答スキーマのためのメッセージ変数を作成します。  
  
## <a name="create-schema-and-message-variables-to-send-query-messages-to-salesforce"></a>Salesforce にクエリ メッセージを送信するためのスキーマおよびメッセージ変数を作成する  
 営業案件通知から利用できる情報を利用して Salesforce から製品詳細を取得するには、クエリを Salesforce に送信する必要があります。 クエリは XML メッセージとして Salesforce に送信されます。 次の手順では、要求メッセージのスキーマを作成します。 次の手順では、営業案件通知スキーマをこのスキーマにマッピングし、営業案件の製品詳細を取得するためのクエリを作成します。  
  
#### <a name="to-create-a-schema-for-sending-query-request"></a>クエリ要求を送信するためのスキーマを作成するには  
  
1.  新しいスキーマを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトに追加します。 「`QueryRequest.xsd`」という名前を入力します。  
  
2.  ルート ノードの名前を`QueryRequest`です。 QueryRequest レコードの下の子フィールド要素を追加し、名前`Query`です。  
  
3.  昇格、**クエリ**がオーケストレーション内で使用可能になるように、スキーマ内の要素。 後の手順では、昇格させたこの要素を使用して、クエリ文字列を割り当てます。  
  
     右クリックし、**クエリ**要素を指す**昇格**、クリックして**クイック昇格**です。 これは、結果、作成、 **PropertySchema.xsd**を持つスキーマ、**クエリ**要素。 PropertySchema の名前空間をメモします。 これは、この後の手順で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで物理ポートを構成する際に必要となります。  
  
4.  すべての変更を保存します。  
  
## <a name="map-the-opportunity-notification-schema-to-the-query-schema"></a>営業案件通知スキーマをクエリ スキーマにマップする  
 営業案件に関連付けられている製品詳細を取得するには、次のようなクエリを Salesforce に送信する必要があります。  
  
```  
SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '<opportunity_name>'  
```  
  
 前の手順で、クエリ メッセージのスキーマを既に作成しています。 この手順では、営業案件通知スキーマをクエリ要求スキーマにマップし、Functoid を使用してこのクエリを作成します。 このクエリの値として渡される、**クエリ**内の要素、 **QueryRequest.xsd**スキーマです。  
  
#### <a name="to-map-the-opportunity-notification"></a>営業案件通知をマップするには  
  
1.  マップを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトに追加します。 マップの名前を`Notification_QueryRequest.btm`です。  
  
2.  送信元スキーマを設定**NotificationService_soap_sforce_com_2005_09_outbound.xsd**です。 送信先スキーマを設定**QueryRequest**.xsd です。  
  
3.  追加、**文字列連結**functoid をマッピング画面にします。 開く、**文字列連結 Functoid の構成** ダイアログ ボックスし、次のように入力値を指定します。  
  
    |||  
    |-|-|  
    |Input[0]|SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '|  
    |Input [1]|Name 要素を 2 番目の入力として使用するために、送信元スキーマの Name 要素を Functoid に接続します。|  
    |[2] の入力|'**注:** 最後の入力値に対してのみ単一引用符 (') を指定します。|  
  
     次のスクリーン ショットの構成を示しています、**文字列連結**functoid です。  
  
     ![文字列連結 functoid の構成](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")  
  
     3 つの入力パラメーターを連結すると、Salesforce に送信するために必要なクエリが形成されます。  
  
4.  次のスクリーンショットにあるように、文字列連結 Functoid を送信先スキーマの Query 要素に接続します。  
  
     ![通知応答をマップするクエリ スキーマ](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")  
  
5.  マップへの変更を保存します。  
  
## <a name="creating-schema-to-receive-the-query-response-message"></a>クエリ応答メッセージを受信するスキーマを作成する  
 このセクションでは、Salesforce からクエリ応答メッセージを受信するスキーマを作成します。 このセクションでは、クエリ応答のためのスキーマを手動で作成します。  
  
#### <a name="to-create-a-schema-to-receive-the-query-response"></a>クエリ応答を受信するスキーマを作成するには  
  
1.  新しいスキーマを追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトおよび名前を付けます`QueryResult.xsd`です。  
  
2.  Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017)オブジェクトは Salesforce から受信したクエリの応答を示しています。 次の項目を表すスキーマをビルドします。  
  
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
  
     スキーマの構造は以下のようになります。  
  
     ![Salesforce からクエリ応答のスキーマ](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")  
  
3.  スキーマへの変更を保存します。  
  
## <a name="create-message-variables-for-queryrequest-and-queryresult-schemas"></a>QueryRequest および QueryResult スキーマのメッセージ変数を作成する  
 QueryRequest および QueryResult スキーマを作成したら、2 つのメッセージの種類を表すための 2 つのメッセージ変数をオーケストレーションに作成する必要があります。  
  
#### <a name="to-create-message-variables"></a>メッセージ変数を作成するには  
  
1.  開く、 **NotificationService.odx**オーケストレーション、オーケストレーション ビューで 2 つの新しいメッセージを追加します。 メッセージの名前は設定`QueryRequestMsg`と`QueryResultMsg`です。  
  
2.  メッセージの種類を設定**QueryRequestMsg**として**BtsSalesforceIntegration.QueryRequest**です。  
  
3.  メッセージの種類を設定**QueryResultMsg**として**BtsSalesforceIntegration.QueryResult**です。  
  
4.  オーケストレーションへの変更を保存します。  
  
## <a name="update-the-orchestration-to-send-message-to-salesforce-and-receive-a-response"></a>Salesforce にメッセージを送信し、応答を受信するためのオーケストレーションを更新する  
 トピックの[Step 3 a: BizTalk Server に Salesforce 営業案件通知を受信](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)、Salesforce から営業案件通知を受信し、受信確認を送信するオーケストレーションを構築しました。 このステップでは、Salesforce にクエリ応答を送信するこのオーケストレーションを作成し、営業案件に関連する製品詳細を取得し、応答を受信します。 この手順で使用するスキーマ (QueryRequest.xsd と QueryResult.xsd) およびメッセージ変数 (QueryRequestMsg と QueryResultMsg) は既に作成しています。  
  
#### <a name="to-send-a-query-request-to-salesforce-and-receive-a-response"></a>Salesforce にクエリ要求を送信し、応答を受信するには  
  
1.  後のメッセージの構築図形を追加、 **SendNotificationAck**図形です。 図形の名前を設定`ConstructQuery`設定と、**構築メッセージ**プロパティを**QueryRequestMsg**です。  
  
2.  内で、 **ConstructQuery**図形を追加、**変換**図形です。 変換図形をダブルクリックして、[変換の構成] ダイアログ ボックスを開きます。 ダイアログ ボックスで、選択、**既存のマップ**オプション、し、ドロップダウン リストから選択**BtsSalesforceIntegration.Notification_QueryRequest**です。 設定**ソース**に**NotificaitonMessage**、**先**に**QueryRequestMsg**、順にクリック**OK**.  
  
3.  内で、 **ConstructQuery**図形、変換図形の後にメッセージの割り当て図形を追加します。 メッセージの割り当て図形をダブルクリックして、次の式を追加します。  
  
    ```  
    QueryRequestMsg(BtsSalesforceIntegration.PropertySchema.Query) = QueryRequestMsg.Query;  
    ```  
  
     これによりの値を渡して、**クエリ**内の要素、 **QueryRequestMsg**スキーマの昇格要素**クエリ**プロパティ スキーマです。 WCF-WebHttp ポートを構成するときは、この要素を使用してクエリの値を動的に要求メッセージに渡します。  
  
4.  後に、 **ConstructQuery**図形、送信図形を追加します。 図形の名前は`SendQueryRequest`としてメッセージの種類を設定および**QueryRequestMsg**です。  
  
5.  送信図形の後に受信図形を追加し、名前`ReceiveQueryResult`です。 図形のメッセージの種類を設定**QueryResultMsg**です。  
  
6.  Salesforce にクエリ要求を送信し、応答のクエリ結果を受信するためのポートを追加します。 ポート構成ウィザードで、次のオプションを選択します。  
  
    -   ポート名を指定`SalesforceRESTInterface`です。  
  
    -   新しいポート種類を作成するオプションを選択します。  
  
    -   設定**通信パターン**に*要求-応答*です。  
  
    -   設定**ポートの通信方向**に*要求の送信と応答の受信を行います*設定と**ポートのバインド**に*以降を指定*.  
  
     接続、**要求**送信図形にポートの操作 (*SendQueryRequest*) および**応答**受信図形にポートの操作 (*ReceiveQueryResult*)。 次のスクリーンショットは、Salesforce へのクエリ要求の送信と応答の受信プロセスを表すオーケストレーションの一部を示しています。  
  
     ![Salesforce にクエリを送信し、応答受信](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")  
  
 このトピックでは、Salesforce にクエリ要求を送信し、Salesforce で作成された営業案件に関する詳細 (製品、数量など) を受信するようにオーケストレーションを更新しました。 次のトピックでは、このソリューションを更新して、Salesforce 応答を社内の SQL Server データベースに入力します。  
  
## <a name="see-also"></a>参照  
 [手順 3: Visual Studio での BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)
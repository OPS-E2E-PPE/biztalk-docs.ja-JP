---
title: '手順 2: Wcf-custom の一方向の構成の受信ポート |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way receive port, configuring
- migration
ms.assetid: e2a8f074-64d5-4e6c-84d0-318fb606c0ba
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d3320e7a2e6b948309087f2b33def57db9db0c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990299"
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a>手順 2: Wcf-custom の一方向の構成の受信ポート
![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、SAP システムからフラット ファイル IDOC を受信する WCF カスタム ポートを構成します。 ポートを構成した後、BizTalk を構成する受信ポートの WCF カスタムを使用するアプリケーション。  
  
## <a name="prerequisites"></a>前提条件  
 構築して SAP システムから Idoc を受信する vPrev BizTalk プロジェクトをデプロイする必要があります。  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a>Wcf-custom 一方向受信ポートを構成するには  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 受信ポートを作成するアプリケーションを展開します。  
  
4. 右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**します。  
  
5. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6. **受信場所**] タブで [**新規**します。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
7. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  受信場所の名前を指定します。  
  
   2.  **型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
8. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドに、SAP システムからメッセージを受信する接続 URI を指定します。 SAP システムからメッセージを受信する接続 URI は、次の形式である必要があります。  
  
      ```  
      sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
      ```  
  
       次の図では、指定した uri のポートのプロパティ ダイアログ ボックスを示しています。  
  
       ![接続を SAP からメッセージを受信する URI](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")  
  
       接続 URI の詳細については、[SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)を参照してください。  
  
   2. をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。 受信ポートのバインドのプロパティを指定することを確認します。  
  
      |プロパティのバインド|値を設定します。|  
      |----------------------|------------------|  
      |flatFileSegmentIndicator|**SegmentType**します。 これは、フラット ファイル IDOC 内の各セグメントのセグメントの種類を含める必要があることを示します。|  
      |padReceivedIdocWithSpaces|**[True]**。 IDOC の各行が、正しい長さにスペースが埋め込まれるかどうかを指定します。|  
      |receiveIDocFormat|**文字列**します。 これは、1 つの文字列フィールドとして IDOC メッセージを表す必要がありますを指定します。|  
  
       バインド プロパティの詳細については、[mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。  
  
   3. をクリックして、**他**タブをクリックし、SAP システムへの接続に資格情報を指定します。  
  
   4. をクリックして、**メッセージ** タブで、および、**受信 BizTalk メッセージ本文**セクションで、選択、**パス**オプション。  
  
   5. **本文のパス式**テキスト ボックスに、XML メッセージからフラット ファイル IDOC を抽出する XPath クエリを指定します。 これにより、受信ポートが IDOC からデータを抽出しの一部である XML タグをトリム、 **ReceiveIdoc** WCF ベースの操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 メッセージ スキーマの詳細については、 **ReceiveIdoc**操作を参照してください[IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)します。  
  
       ![フラットを抽出する XPath クエリ&#45;ファイル IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")  
  
       次の XPath クエリを指定する必要があります。  
  
      ```  
      /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
      ```  
  
   6. **ノード エンコード**ドロップダウン リストで、**文字列**します。  
  
   7. クリックして**適用**、順にクリックします**OK**します。  
  
9. 受信場所のプロパティ ダイアログ ボックスから、**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
10. **受信パイプライン**ドロップダウン リストで、 **ConvertToXML**します。 このフラット ファイル逆アセンブラー パイプラインは、既に XML IDOC フラット ファイル IDOC に変換する vPrev BizTalk プロジェクトの部分です。  
  
11. **[OK]** をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1. BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**オーケストレーションが展開されている BizTalk アプリケーションを展開します。  
  
2. BizTalk アプリケーションを右クリックし、**構成**します。  
  
3. 左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4. で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
   1. WCF カスタムでは、このトピックの前半で作成したポートが表示されます。  
  
   2. フラット ファイル IDOC を受信は、file ポートを選択します。  
  
   3. **[OK]** をクリックします。  
  
      アプリケーションを構成する方法の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)を参照してください。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して SAP システムから Idoc を受信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 」の説明に従って、フラット ファイル IDOC を受信することによって、移行済みの BizTalk アプリケーションにテストすること今すぐ必要があります[手順 3: 移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: SAP の IDOC 受信 BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)
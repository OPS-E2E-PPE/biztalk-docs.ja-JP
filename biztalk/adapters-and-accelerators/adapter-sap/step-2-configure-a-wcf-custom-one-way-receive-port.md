---
title: '手順 2: 構成 Wcf-custom 一方向受信ポート |Microsoft ドキュメント'
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
ms.openlocfilehash: 6edf75f08bdf6a321188e484eb4f363366f8eb95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218554"
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a>手順 2: 構成 Wcf-custom 一方向受信ポート
![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:** SAP システムからフラット ファイル IDOC を受信する WCF カスタム ポートを構成するこの手順でします。 BizTalk を構成するポートを構成すると、受信ポートの Wcf-custom を使用するアプリケーション。  
  
## <a name="prerequisites"></a>前提条件  
 構築し、SAP システムから Idoc を受信する vPrev BizTalk プロジェクトを展開した必要があります。  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a>Wcf-custom 一方向の受信ポートを構成するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  受信ポートを作成するアプリケーションを展開します。  
  
4.  右クリック**受信ポート**、指す**新規**、 をクリック**一方向の受信ポート**です。  
  
5.  **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6.  **受信場所** タブで、をクリックして**新規**です。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
7.  **受信場所のプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  受信場所の名前を指定します。  
  
    2.  **型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
8.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、接続、SAP システムからメッセージを受信 URI を指定します。 SAP システムからメッセージを受信する URI の接続は、次の形式である必要があります。  
  
        ```  
        sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
        ```  
  
         次の図は、指定された URI でポートのプロパティ ダイアログ ボックスを示しています。  
  
         ![接続 URI SAP からメッセージを受信する](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")  
  
         接続 URI の詳細については、次を参照してください。 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)です。  
  
    2.  クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **sapBinding**です。 受信ポートのバインドのプロパティを指定することを確認してください。  
  
        |プロパティのバインド|値を設定します。|  
        |----------------------|------------------|  
        |flatFileSegmentIndicator|**SegmentType**です。 これは、フラット ファイル IDOC 内の各セグメントのセグメントの種類を含める必要があることを示します。|  
        |padReceivedIdocWithSpaces|**[True]**。 IDOC 内の各行が正しい長さにスペースが埋め込まれるかどうかを指定します。|  
        |receiveIDocFormat|**文字列**です。 これは、IDOC メッセージを 1 つの文字列フィールドとして表現する必要がありますを指定します。|  
  
         バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
    3.  クリックして、**他**タブをクリックし、SAP システムへの接続に資格情報を指定します。  
  
    4.  クリックして、**メッセージ**] タブで、し、[、**受信 BizTalk メッセージ本文**セクションで、選択、**パス**オプション。  
  
    5.  **本文のパス式**テキスト ボックスで、XML メッセージからフラット ファイル IDOC を抽出する XPath クエリを指定します。 これにより、受信ポートが IDOC からデータを抽出しの一部である XML タグを小さくするとき、 **ReceiveIdoc** WCF ベースの操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 メッセージ スキーマの詳細については、 **ReceiveIdoc**操作を参照してください[IDOC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)です。  
  
         ![XPath フラット & #45 を抽出するクエリにはファイルの IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")  
  
         次の XPath クエリを指定する必要があります。  
  
        ```  
        /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
        ```  
  
    6.  **ノード エンコード**ドロップダウン リストで、**文字列**です。  
  
    7.  をクリックして**適用**、順にクリック**OK**です。  
  
9. 受信場所のプロパティ ダイアログ ボックスから、**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
10. **受信パイプライン**ドロップダウン リストで、 **ConvertToXML**です。 このフラット ファイル逆アセンブラー パイプラインはフラット ファイル IDOC を XML IDOC に変換する vPrev BizTalk プロジェクトの一部では既にです。  
  
11. **[OK]** をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1.  BizTalk Server 管理コンソールで、次のように展開します。 **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションに展開します。  
  
2.  BizTalk アプリケーションを右クリックし、**構成**です。  
  
3.  左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4.  下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
    1.  このトピックの前半で作成したポートを受信する Wcf-custom を選択します。  
  
    2.  フラット ファイル IDOC を受信するファイル ポートを選択します。  
  
    3.  **[OK]** をクリックします。  
  
     アプリケーションの構成の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)です。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して SAP システムから Idoc を受信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 必要があります今すぐアプリケーションをテストする移行された BizTalk フラット ファイル IDOC を受信して」の説明に従って[手順 3: アプリケーションをテストする移行](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: SAP を移行する BizTalk プロジェクトの IDOC を受信](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)
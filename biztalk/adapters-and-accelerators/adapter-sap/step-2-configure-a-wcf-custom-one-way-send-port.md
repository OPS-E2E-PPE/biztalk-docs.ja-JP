---
title: "手順 2: Wcf-custom 一方向送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f332e11aef32285fff84f0fe5f65834b1b20fc04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a>手順 2: Wcf-custom 一方向送信ポートを構成します。
![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:**このステップで、フラット ファイル IDOC を SAP システムに送信する WCF カスタム ポートを構成します。 ポートを構成した後は、Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 構築し、SAP システムに Idoc を送信する vPrev BizTalk プロジェクトを展開した必要があります。  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a>Wcf-custom 一方向の送信ポートを構成するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  送信ポートを作成するアプリケーションを展開します。  
  
4.  右クリック**送信ポート**、指す**新規**、 をクリック**静的な一方向送信ポート**です。  
  
5.  **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6.  **型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
7.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)**フィールドで、接続、SAP システムにメッセージを送信する URI を指定します。 接続 URI の詳細については、次を参照してください。 [SAP システムの接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
         ![送信ポートで指定された接続 URI](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")  
  
    2.  **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 フラット ファイル IDOC を送信するを使用する必要があります、 **SendIdoc** WCF ベースによって公開される操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 **SendIdoc**操作により、弱い型指定のスキーマが Idoc を送信するクライアントはアダプターです。 詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。 次の図に示しています、**アクション**のアクションを含むテキスト ボックス、 **SendIdoc**操作します。  
  
         ![送信ポートでアクションの指定](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")  
  
    3.  クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **sapBinding**です。  
  
    4.  クリックして、**資格情報**タブし、SAP システムへの接続に資格情報を指定します。  
  
    5.  クリックして、**メッセージ**] タブで、し、[、**送信 WCF メッセージ本文**セクションで、選択、**テンプレート**オプション。  
  
    6.  **XML**テキスト ボックスで、WCF メッセージを構築するために使用されるテンプレートを指定します。 これによりに準拠したメッセージを作成する、 **SendIdoc** WCF ベースの操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 メッセージの構造の詳細については、 **SendIdoc**操作を参照してください[IDOC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)です。  
  
         ![送信 WCF メッセージのテンプレートを指定](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")  
  
         SendIdoc 操作は、次のテンプレートを指定する必要があります。  
  
        ```  
        <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
        <idocData>\<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
        </SendIdoc>  
        ```  
  
         上記のテンプレート、`bts-msg-body`がファイルに関連付けられているフラット ファイル逆アセンブラーを使用して作成された XML IDOC の受信ポート。 XML IDOC は SendIdoc メッセージにカプセル化します。  
  
    7.  をクリックして**適用**、順にクリック**OK**です。  
  
8.  **送信ポートのプロパティ** ダイアログ ボックスから、**送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
9. **送信パイプライン**ドロップダウン リストで、 **ConvertToFlatFile**です。 このフラット ファイル アセンブラー パイプラインは、vPrev BizTalk プロジェクトの一部では既にし、XML IDOC をフラット ファイル IDOC に変換するために使用します。  
  
10. **[OK]**をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1.  BizTalk Server 管理コンソールで、次のように展開します。 **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションに展開します。  
  
2.  BizTalk アプリケーションを右クリックし、**構成**です。  
  
3.  左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4.  下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
    1.  フラット ファイル IDOC を削除するファイル ポートを選択します。  
  
    2.  このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。  
  
    3.  **[OK]**をクリックします。  
  
     アプリケーションの構成の詳細についてを参照してください「どのように構成するアプリケーションへ」 [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)です。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して SAP システムに Idoc を送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 」の説明に従って、フラット ファイル IDOC を送信することによって移行済みの BizTalk アプリケーションにテストすること今すぐ必要があります[手順 3: アプリケーションをテストする移行](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: SAP 送信 IDOC の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)
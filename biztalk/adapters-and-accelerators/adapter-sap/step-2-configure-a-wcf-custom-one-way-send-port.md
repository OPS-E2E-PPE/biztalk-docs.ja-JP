---
title: 手順 2:Wcf-custom 一方向送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5daec84fac1987fccc015da9d457e26f86dea61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372838"
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a>手順 2:Wcf-custom 一方向送信ポートを構成します。
![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、フラット ファイル IDOC を SAP システムに送信する WCF カスタム ポートを構成します。 ポートを構成した後は、Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 構築して Idoc を SAP システムに送信する vPrev BizTalk プロジェクトをデプロイする必要があります。  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a>Wcf-custom 一方向の送信ポートを構成するには  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 送信ポートを作成するアプリケーションを展開します。  
  
4. 右クリックして**送信ポート**、 をポイント**新規**、 をクリック**静的な一方向送信ポート**します。  
  
5. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6. **型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
7. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドに、SAP システムにメッセージを送信する接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を使用すると、作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
       ![送信ポートで指定された接続 URI](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 フラット ファイル IDOC を送信するには、使用する必要があります、 **SendIdoc** WCF ベースによって公開される操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 **SendIdoc**操作には、厳密に型指定のスキーマが Idoc を送信するアダプターのクライアントが使用できます。 詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。 次に示します、**アクション**の操作は、テキスト ボックス、 **SendIdoc**操作。  
  
       ![送信ポートでアクションを指定](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")  
  
   3. をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。  
  
   4. をクリックして、**資格情報**タブし、SAP システムへの接続に資格情報を指定します。  
  
   5. をクリックして、**メッセージ** タブで、および、**送信 WCF メッセージ本文**セクションで、選択、**テンプレート**オプション。  
  
   6. **XML**テキスト ボックスに、WCF メッセージの構築に使用されるテンプレートを指定します。 これにより、準拠するメッセージを作成する、 **SendIdoc** WCF ベースの操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 メッセージの構造の詳細については、 **SendIdoc**操作を参照してください[IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)します。  
  
       ![送信 WCF メッセージのテンプレートを指定](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")  
  
       SendIdoc 操作の場合は、次のテンプレートを指定する必要があります。  
  
      ```  
      <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
      <idocData><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
      </SendIdoc>  
      ```  
  
       上記のテンプレート、`bts-msg-body`がファイルに関連付けられているフラット ファイル逆アセンブラーを使用して作成された XML の IDOC の受信ポート。 XML の IDOC は SendIdoc メッセージでカプセル化されます。  
  
   7. クリックして**適用**、順にクリックします**OK**します。  
  
8. **送信ポートのプロパティ** ダイアログ ボックスから、**送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
9. **送信パイプライン**ドロップダウン リストで、 **ConvertToFlatFile**します。 このフラット ファイル アセンブラー パイプラインは、vPrev BizTalk プロジェクトの一部になってし、フラット ファイル IDOC を XML IDOC に変換するために使用します。  
  
10. **[OK]** をクリックします。  
  
### <a name="to-configure-the-biztalk-application"></a>BizTalk アプリケーションを構成するには  
  
1. BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**オーケストレーションが展開されている BizTalk アプリケーションを展開します。  
  
2. BizTalk アプリケーションを右クリックし、**構成**します。  
  
3. 左側のウィンドウを構成するオーケストレーションをクリックします。 右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。  
  
4. で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。  
  
   1. フラット ファイル IDOC をドロップする場所、ファイル ポートを選択します。  
  
   2. このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。  
  
   3. **[OK]** をクリックします。  
  
      アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)します。  
  
## <a name="next-steps"></a>次の手順  
 WCF ベースを使用して、SAP システムに Idoc を送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 」の説明に従って、フラット ファイル IDOC を送信することによって、移行済みの BizTalk アプリケーションにテストすること今すぐ必要があります[手順 3。移行したアプリケーションをテスト](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: SAP の IDOC 送信 BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)
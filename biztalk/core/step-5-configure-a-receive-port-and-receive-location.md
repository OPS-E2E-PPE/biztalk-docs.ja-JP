---
title: "手順 5: 構成する受信ポートと受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43fc8d12-5fde-4ddf-a7f0-770f078ba66b
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8ec436657aefaceb71207d37808936aa6eaa1a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a>手順 5: 構成する受信ポートと受信場所
![手順 5. の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 このステップでは、Fabrikam パーティ用に設定されたフォルダ内の 850 メッセージを受信するための受信ポートと受信場所を構成します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a>850 メッセージを受信するための受信ポートと受信場所を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**です。 右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
2.  受信ポートのプロパティ ダイアログ ボックスで、**名前**フィールドに「`ReceiveEDI_fromTHEM_A`です。  
  
3.  をクリックして**受信場所**をクリックしてコンソール ツリーで、**新規**右側のペインでします。  
  
4.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**フィールドに「`fromTHEM_4010_850`です。  
  
5.  **型****ファイル**、順にクリック**構成**です。  
  
    > [!NOTE]
    >  テスト メッセージはフォルダに配信されるフラット ファイルであるため、受信場所のトランスポートの種類は FILE です。  
  
6.  **FILE トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**参照**横に、**受信フォルダー**フィールドです。 **フォルダーの参照** ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \fromthem をクリックして**OK**です。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、変更、**ファイル マスク**に **\*.txt**  をクリック**OK**です。  
  
    > [!NOTE]
    >  入力テスト メッセージがテキスト ファイル SamplePO.txt であるため、ファイル マスクは *.txt に設定します。  
  
8.  **受信場所のプロパティ**] ダイアログ ボックスで、**受信パイプライン**フィールドで、[ **EdiReceive**です。  
  
    > [!NOTE]
    >  EDI インターチェンジ (AS2 トランスポートを経由して配信される EDI インターチェンジを除く) の受信に使用される受信パイプラインは、EdiReceive パイプラインです (AS2 トランスポートを経由して配信される EDI インターチェンジの受信に使用される受信パイプラインは、AS2EdiReceive 受信パイプラインです)。  
  
    > [!NOTE]
    >  [EdiReceive] が受信パイプラインのドロップダウン リストに表示されていなければ、アプリケーションが BizTalk EDI アプリケーションを参照していない可能性があります。 参照を追加するを参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。  
  
9. をクリックして**[ok]**、順にクリック**OK**もう一度です。  
  
    > [!NOTE]
    >  BizTalk サービスに対するログオン特権を持つアカウントは、fromTHEM_4010_850 受信場所に関連付けられた受信フォルダー ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM) に対する完全なアクセス許可も持っている必要があります。 持っていない場合は、受信場所を有効にしようとするとエラーが表示されます。 受信フォルダーのアクセス許可を変更するには、[セキュリティ] タブに移動、**プロパティ**Windows エクスプ ローラーでそのフォルダーのダイアログ ボックス。  
  
10. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**受信場所**を右クリックして**fromTHEM_4010_850**、順にクリック**を有効にする**です。  
  
## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**toOrderSystem**)」の説明に従って、850 メッセージを OrderSystem に送信する[手順 6: 組織にデータを送信する送信ポートを構成する](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージおよび受信確認を受信するためのポートを構成します。](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)
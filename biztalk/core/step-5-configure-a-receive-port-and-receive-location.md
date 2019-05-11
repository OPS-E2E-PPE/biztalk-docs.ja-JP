---
title: 手順 5:構成を受信ポートと受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43fc8d12-5fde-4ddf-a7f0-770f078ba66b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4f4976c585caf858c27680b156ec3d01b09d439
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244355"
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a>手順 5:構成を受信ポートと受信場所
![手順 5. の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 この手順では、受信ポートと Fabrikam パーティを設定するフォルダーに 850 メッセージを受信するための受信場所を構成します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a>受信 850 メッセージを受信するための場所および受信ポートを構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**します。 右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  
  
2. 受信ポートのプロパティ ダイアログ ボックスでの**名前**フィールドに、入力`ReceiveEDI_fromTHEM_A`します。  
  
3. をクリックして**受信場所**コンソール ツリーをクリックで**新規**右側のウィンドウでします。  
  
4. **受信場所のプロパティ** ダイアログ ボックスで、**名前**フィールドに、入力`fromTHEM_4010_850`します。  
  
5. **型**を選択します**ファイル**、 をクリックし、**構成**します。  
  
   > [!NOTE]
   >  テスト メッセージがフォルダーに配信されるフラット ファイルであるために、受信場所のトランスポートの種類はファイルです。  
  
6. **FILE トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**参照**横に、**受信フォルダー**フィールド。 **フォルダーの参照** ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \fromthem をクリック**OK**します。  
  
7. **FILE トランスポートのプロパティ** ダイアログ ボックスで、変更、**ファイル マスク**に **\*.txt**  をクリック**OK**します。  
  
   > [!NOTE]
   >  入力テスト メッセージがテキスト ファイル SamplePO.txt であるために、ファイル マスクは *.txt に設定します。  
  
8. **受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**フィールドで、 **EdiReceive**します。  
  
   > [!NOTE]
   >  AS2 トランスポートを経由して配信されるものを除く、EDI インターチェンジを受信するために使用する受信パイプラインは、EdiReceive パイプラインです。 (AS2EdiReceive 受信パイプラインは AS2 トランスポート経由で配信される EDI インターチェンジの受信に使用します)。  
  
   > [!NOTE]
   >  EdiReceive 受信パイプラインのドロップダウン リストが表示されていない場合、アプリケーションに、BizTalk EDI アプリケーションへの参照をことはできません。 参照を追加するを参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。  
  
9. をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
   > [!NOTE]
   >  BizTalk サービスに対するログオン特権を持つアカウントが、fromTHEM_4010_850 受信場所に関連付けられた受信フォルダーの完全なアクセス許可を付与するもする必要があります ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\processedi_testlocations\fromthem)。 それ以外の場合は、受信場所を有効にする際、エラーが表示されます。 受信フォルダーのアクセス許可を変更するには、[セキュリティ] タブに移動、**プロパティ**Windows エクスプ ローラーでは、そのフォルダーのダイアログ ボックス。  
  
10. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**受信場所**、右クリック**fromTHEM_4010_850**、順にクリックします**を有効にする**します。  
  
## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**toOrderSystem**)」の説明に従って、850 メッセージを OrderSystem に送信する[手順 6。組織にデータを送信する送信ポートを構成する](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)します。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージおよび受信確認を受信するポートの構成](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)
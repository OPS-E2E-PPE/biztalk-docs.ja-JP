---
title: 手順 4:取引先、Partner1 のパーティとビジネス プロファイルの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db50d0f6-e838-4e92-8548-a63a2c445d55
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db279e32601603a8f539d6e95627f522e5f7bd85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392577"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a>手順 4:取引先のパーティとビジネス プロファイルを構成します。
![手順 9 の 4](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")  
  
 この手順では、取引先パートナーを組織に 850 メッセージを送信し、代わりに、997 受信確認メッセージを受信する Fabrikam のパーティとビジネス プロファイルを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a>取引先のパーティとビジネス プロファイルを構成するには  
  
1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 **Microsoft BizTalk Server**をクリックし、**BizTalk Server 管理**します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。 右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。  
  
3. **パーティ プロパティ** ダイアログ ボックスに、入力**Fabrikam**で、**名前**フィールド。  
  
4. クリア、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスをオンします。 指定する チェック ボックスをオフにすると、パーティ (この場合、 **Fabrikam**) BizTalk Server をホストしていません。  
  
5. **[OK]** をクリックします。  
  
6. パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。  
  
7. **プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力`Fabrikam_Profile`で、**名前**テキスト ボックス。  
  
   > [!NOTE]
   >  プロファイルがという名前のパーティを作成するときに*PartyName*(_p) が自動的に作成します。 このプロファイルは、新規に作成する代わりに使用できます。 プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。 **全般** ページで、プロファイルの名前を指定します。  
  
8. **[OK]** をクリックします。  
  
## <a name="next-steps"></a>次の手順  
 受信場所を構成する (**fromTHEM_4010_850**)」の説明に従って、Fabrikam から 850 メッセージを受信する[手順 5。構成を受信ポートと受信場所](../core/step-5-configure-a-receive-port-and-receive-location.md)します。  
  
## <a name="see-also"></a>参照  
 [EDI のプロパティの構成](../core/configuring-edi-properties.md)
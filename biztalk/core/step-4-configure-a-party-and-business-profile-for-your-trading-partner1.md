---
title: '手順 4: 取引、Partner1 のパーティとビジネス プロファイルの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: a7b8be8215b790e74a3c1a8ecd8324d62454c2ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277418"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a>手順 4: 取引先のパーティとビジネス プロファイルを構成します。
![手順 4. 9 の](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")  
  
 このステップでは、取引先が 850 メッセージを自組織に送信し、それに対する 997 受信確認メッセージを受信するように、取引先 Fabrikam のパーティおよびビジネス プロファイルを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a>取引先のパーティとビジネス プロファイルを構成するには  
  
1.  開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール をクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 **Microsoft BizTalk Server**をクリックし、**BizTalk Server 管理**です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]の順に展開および**BizTalk グループ**です。 右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。  
  
3.  **パーティ プロパティ** ダイアログ ボックスで、入力**Fabrikam**で、**名前**フィールドです。  
  
4.  クリア、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスをオンします。 チェック ボックスをオフにすることを指定、パーティ (この場合、 **Fabrikam**) BizTalk Server をホストしていません。  
  
5.  **[OK]** をクリックします。  
  
6.  パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。  
  
7.  **プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力`Fabrikam_Profile`で、**名前**テキスト ボックス。  
  
    > [!NOTE]
    >  パーティを作成するときに、という名前のプロファイル*PartyName*_Profile が自動的に作成します。 新しいプロファイルを作成する代わりに、このプロファイルを使用できます。 プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。 **全般** ページで、プロファイルの名前を指定します。  
  
8.  **[OK]** をクリックします。  
  
## <a name="next-steps"></a>次の手順  
 受信場所を構成する (**fromTHEM_4010_850**)」の説明に従って、Fabrikam から 850 メッセージを受信する[手順 5: 受信ポートと受信場所を構成する](../core/step-5-configure-a-receive-port-and-receive-location.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI のプロパティを構成します。](../core/configuring-edi-properties.md)
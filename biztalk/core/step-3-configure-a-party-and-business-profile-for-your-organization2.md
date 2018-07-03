---
title: '手順 3: Organization2 のパーティとビジネス プロファイルの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 024d1ec7-237a-43cb-8159-90f9c71a670e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 809c8bd4080a7d2ddf14d9c84e98c050e198e6cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000363"
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a>手順 3: 組織のパーティとビジネス プロファイルを構成します。
![手順 3/11](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")  
  
 このステップでは、取引先から 864 メッセージを受信し、997 受信確認メッセージと非同期 MDN を返すように、組織のパーティとビジネス プロファイルを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a>組織のパーティおよびビジネス プロファイルを構成するには  
  
1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリックし、 **BizTalk Server 管理コンソール**.  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。 右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。  
  
3. **パーティ プロパティ** ダイアログ ボックスに、入力**Contoso**で、**名前**フィールド。  
  
4. 選択、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスをオンします。 指定するチェック ボックスをオン、パーティ (この場合、 **Contoso**) も BizTalk Server をホストします。  
  
5. **[OK]** をクリックします。  
  
6. パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。  
  
7. **プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力`Contoso_Profile`で、**名前**テキスト ボックス。  
  
   > [!NOTE]
   >  パーティを作成すると、プロファイルも作成されます。 新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。 プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。 **全般** ページで、プロファイルの名前を指定します。  
  
8. **[OK]** をクリックします。  
  
## <a name="next-steps"></a>次の手順  
 パートナー組織のパーティとビジネス プロファイルを構成する (**Fabrikam**)」の説明に従って、[手順 4: パーティとビジネス プロファイル、取引先パートナーを構成](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)します。  
  
## <a name="see-also"></a>参照  
 [EDI のプロパティの構成](../core/configuring-edi-properties.md)
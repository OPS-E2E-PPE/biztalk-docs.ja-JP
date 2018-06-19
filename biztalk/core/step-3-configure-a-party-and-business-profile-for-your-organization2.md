---
title: '手順 3: Organization2 用のパーティとビジネス プロファイルの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: c7cb8e65d85ef189a17fc95b3599a5e26da0d308
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277634"
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a>手順 3: 組織のパーティとビジネス プロファイルを構成します。
![手順 11 の 3](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")  
  
 このステップでは、取引先から 864 メッセージを受信し、997 受信確認メッセージと非同期 MDN を返すように、組織のパーティとビジネス プロファイルを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a>組織のパーティおよびビジネス プロファイルを構成するには  
  
1.  開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール をクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、クリックして**BizTalk Server 管理コンソール**.  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]の順に展開および**BizTalk グループ**です。 右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。  
  
3.  **パーティ プロパティ** ダイアログ ボックスで、入力**Contoso**で、**名前**フィールドです。  
  
4.  選択、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスをオンします。 チェック ボックスをオンにすることを指定、パーティ (この場合、 **Contoso**) も BizTalk Server をホストします。  
  
5.  **[OK]** をクリックします。  
  
6.  パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。  
  
7.  **プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力`Contoso_Profile`で、**名前**テキスト ボックス。  
  
    > [!NOTE]
    >  パーティを作成すると、プロファイルも作成されます。 新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。 プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。 **全般** ページで、プロファイルの名前を指定します。  
  
8.  **[OK]** をクリックします。  
  
## <a name="next-steps"></a>次の手順  
 パートナー組織のパーティとビジネス プロファイルを構成する (**Fabrikam**)」の説明に従って、[手順 4:、取引先のパーティとビジネス プロファイルを構成する](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI のプロパティを構成します。](../core/configuring-edi-properties.md)
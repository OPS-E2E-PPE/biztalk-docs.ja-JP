---
title: 追跡を構成する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring [HAT tracking], receive ports
- tracking, receive ports
- receive ports, tracking
- configuring, tracking
- receive ports, configuring
- tracking, configuring
- HAT, receive ports
- configuring, receive ports
- managing [receive ports], tracking
ms.assetid: dd569e84-cb1c-4191-912a-0c2eb2781a85
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08b03b737cc00016ad37d7eab8d8eeda5cffd3a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023952"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a>受信ポートの追跡を構成する方法
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して受信ポートの追跡を構成する方法 (メッセージ本文や昇格させたプロパティを表示するオプションなど) について説明します。 これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実装の稼動状況を監視し、ボトルネックを識別できます。 構成する追跡の設定は、受信ポートのすべてのインスタンスに適用されます。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト: メッセージとインスタンス データの追跡](../core/checklist-message-and-instance-data-tracking.md)  
  
 構成する追跡の設定は、受信ポートのすべてのインスタンスに適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-tracking-for-a-receive-port"></a>受信ポートの追跡を構成するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、受信ポートの追跡を構成する BizTalk アプリケーションを展開します。  
  
3. クリックして**受信ポート**受信ポートを右クリックし、クリックして**追跡**します。  
  
   > [!NOTE]
   >  受信ポートでメッセージ本文の追跡を有効にする前に、受信ポートを本当に追跡するかどうかを確認します。この処理はオーバーヘッドになる可能性があります。 たとえば、受信パイプライン RcvPipe が異なる受信ポートの複数の受信場所で使用されます。 メッセージ本文の追跡 RcvPipe でオプションを有効にした場合の潜在顧客はメッセージ本文の追跡では、すべての受信場所を行いたい場合があります。 このため、メッセージをセット本文の追跡では、必要に応じてポートを受信します。  
  
4. 次の表に示すように、必要な追跡オプションを構成し、 **OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**|受信前にメッセージの内容を保存および追跡する場合は、このチェック ボックスをオンにします。|  
   |**メッセージ本文の追跡 - ポート処理後の要求メッセージ**|受信後にメッセージの内容を保存および追跡する場合は、このチェック ボックスをオンにします。|  
   |||  
   |||  
   |**メッセージのプロパティ - ポート処理前に、の要求メッセージの追跡します。**|受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。|  
   |**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**|送信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。|  
   |||  
   |||  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)
---
title: 追跡を構成する方法、受信ポート |Microsoft ドキュメント
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
ms.openlocfilehash: 0e18748a5d9ff8088d09dfe28bf23c7b729b6afc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249106"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a>受信ポートの追跡を構成する方法
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して受信ポートの追跡を構成する方法 (メッセージ本文や昇格させたプロパティを表示するオプションなど) について説明します。 これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実装の稼動状況を監視し、ボトルネックを識別できます。 構成する追跡の設定は、受信ポートのすべてのインスタンスに適用されます。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト: メッセージとインスタンス データの追跡](../core/checklist-message-and-instance-data-tracking.md)  
  
 構成する追跡の設定は、受信ポートのすべてのインスタンスに適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-tracking-for-a-receive-port"></a>受信ポートの追跡を構成するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートの追跡を構成する BizTalk アプリケーションを展開します。  
  
3.  をクリックして**受信ポート**受信ポートを右クリックし、クリックして、**追跡**です。  
  
    > [!NOTE]
    >  受信ポートでメッセージ本文の追跡を有効にする前に、受信ポートを本当に追跡するかどうかを確認します。この処理はオーバーヘッドになる可能性があります。 たとえば、受信パイプライン RcvPipe が異なる受信ポートの複数の受信場所で使用されます。 メッセージ本文の追跡 RcvPipe でオプションを有効にした場合は、メッセージ本文のすべての受信場所で、実行する可能性がありますいないを追跡につながります。 そのため、設定、メッセージ本文の追跡では、必要に応じてポートを受信します。  
  
4.  次の表の説明に従って、必要な追跡オプションを構成し、をクリックして**OK**です。  
  
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
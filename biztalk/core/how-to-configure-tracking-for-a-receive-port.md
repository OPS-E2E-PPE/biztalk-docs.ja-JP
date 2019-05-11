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
ms.openlocfilehash: a6f45158939210c3b084aa29234bee1b4a032b6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385898"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a>追跡を構成する方法、受信ポート
このトピックでは、使用する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをメッセージ本文や昇格させたプロパティを表示するオプションなど、受信ポートの追跡を構成する. 正常性を監視できます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実装し、ボトルネックを識別します。 構成する追跡の設定は、すべての受信ポートのインスタンスに適用されます。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト。メッセージとインスタンス データ追跡](../core/checklist-message-and-instance-data-tracking.md)  
  
 構成する追跡の設定は、すべての受信ポートのインスタンスに適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-tracking-for-a-receive-port"></a>受信ポートの追跡を構成するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループと受信ポートの追跡を構成する BizTalk アプリケーションを展開します。  
  
3. クリックして**受信ポート**受信ポートを右クリックし、クリックして**追跡**します。  
  
   > [!NOTE]
   >  メッセージ本文の受信ポートの追跡を有効にするには、まったく; 受信ポートを追跡することを確認しますオーバーヘッドが考えられます。 たとえば、受信パイプライン RcvPipe が、別の受信ポートで複数の受信場所に使用されます。 メッセージ本文の追跡 RcvPipe でオプションを有効にした場合の潜在顧客はメッセージ本文の追跡では、すべての受信場所を行いたい場合があります。 このため、メッセージをセット本文の追跡では、必要に応じてポートを受信します。  
  
4. 次の表に示すように、必要な追跡オプションを構成し、 **OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**|保存し、メッセージが受信されるまで、メッセージの内容を追跡するには、このチェック ボックスを選択します。|  
   |**メッセージ本文の追跡 - ポート処理後の要求メッセージ**|保存し、メッセージが受信された後メッセージの内容を追跡するには、このチェック ボックスを選択します。|  
   |||  
   |||  
   |**メッセージのプロパティ - ポート処理前に、の要求メッセージの追跡します。**|受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。|  
   |**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**|送信メッセージの昇格させたプロパティを追跡したい場合は、このチェック ボックスをオンにします。|  
   |||  
   |||  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)
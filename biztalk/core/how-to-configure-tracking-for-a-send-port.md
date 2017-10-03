---
title: "送信ポートの追跡を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- configuring, tracking
- tracking, send ports
- configuring [HAT tracking], send ports
- send ports, tracking
- managing [send ports], configuring
- tracking, configuring
- send ports, configuring
- managing [send ports], tracking
- HAT, send ports
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60ba83b7d3451599a0422ec370fed41eeba94407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-send-port"></a>送信ポートの追跡を構成する方法
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信ポートの追跡を構成する方法 (メッセージ本文や昇格させたプロパティを表示するオプションなど) について説明します。 これにより、BizTalk 実装の稼動状況を監視し、ボトルネックを識別できます。 構成する追跡の設定は、送信ポートのすべてのインスタンスに適用されます。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-tracking-for-a-send-port"></a>送信ポートの追跡を構成するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートの追跡を構成する BizTalk アプリケーションを展開します。  
  
3.  をクリックして**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**追跡**です。  
  
    > [!NOTE]
    >  1 つの送信ポートは 1 つの送信パイプラインにのみ関連付けることができます。 送信パイプラインでメッセージ本文の追跡が無効になっている場合、送信ポートでも追跡できるものはありません。 そのようなシナリオでは、その送信ポートで [追跡] オプションを無効にできます。  
  
4.  次の表の説明に従って、必要な追跡オプションを構成し、をクリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**|受信前にメッセージの内容を保存および追跡できるようにする場合は、このチェック ボックスをオンにします。 **注:**メッセージ本文パイプラインの追跡が正常にポート処理前に、の応答メッセージを追跡するために有効にする必要があります。|  
    |**メッセージ本文の追跡 - ポート処理後の要求メッセージ**|受信後にメッセージの内容を保存および追跡できるようにする場合は、このチェック ボックスをオンにします。|  
    |||  
    |||  
    |**メッセージのプロパティ - ポート処理前に、の要求メッセージの追跡します。**|受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。|  
    |**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**|送信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。|  
    |||  
    |||  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)
---
title: オーケストレーションの追跡を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, tracking
- orchestrations, HAT
- managing [orchestrations], tracking
- configuring [HAT tracking], orchestrations
- tracking, orchestrations
- HAT, orchestrations
ms.assetid: 8f5ed525-11f8-4bef-95c4-cfe9c971b663
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c64d7521bf6d65458f66bb0ef06d08421edf1b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013195"
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a>オーケストレーションの追跡を構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションの追跡を構成する方法について説明します。  
  
 作成とクエリの使用に関する詳細については、[、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)を参照してください。 追跡機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-tracking-for-an-orchestration"></a>オーケストレーションの追跡を構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、追跡を構成するオーケストレーションを含むアプリケーションを展開します。  
  
3. クリックして**オーケストレーション**をクリックして、追跡を構成するオーケストレーションを右クリックして**プロパティ**します。  
  
4. をクリックして、**追跡**タブや次の表に示すように、必要な追跡オプションを選択します をクリックし、 **OK**します。  
  
   |オプション|説明|  
   |------------|-----------------|  
   |**イベントの追跡 - オーケストレーションの開始と終了**|ビジネス プロセス全体の処理の前後にオーケストレーション インスタンスを追跡するには、このチェック ボックスをオンにします。 オーケストレーションの追跡を行うことで、追跡クエリ結果ビューでインスタンスを確認できるようになります。|  
   |**イベントの追跡 - メッセージの送信および受信**|メッセージの送信イベントと受信イベントを追跡する場合は、このチェック ボックスをオンにします。 このチェック ボックスは選択した場合にのみ使用可能な**オーケストレーションの開始と終了**チェック ボックスをオンします。|  
   |**イベントの追跡の図形の開始と終了**|オーケストレーション デバッガーでオーケストレーション インスタンスをデバッグする必要がある場合はこのチェック ボックスをオンにします。 このチェック ボックスがオンの場合、オーケストレーション デバッガーのイベントの一覧が設定されます。 このチェック ボックスは選択した場合にのみ使用可能な**オーケストレーションの開始と終了**チェック ボックスをオンします。|  
   |**オーケストレーション処理の前に、のメッセージ本文の追跡**|オーケストレーション インスタンスによる処理の前に実際のメッセージの内容を保存および追跡するには、このチェック ボックスをオンにします。 このチェック ボックスは選択した場合にのみ使用可能な**メッセージの送信および受信**チェック ボックスをオンします。|  
   |**オーケストレーション処理の後のメッセージ本文の追跡**|オーケストレーション インスタンスによる処理の後に実際のメッセージの内容を保存および追跡するには、このチェック ボックスをオンにします。 このチェック ボックスは選択した場合にのみ使用可能な**メッセージの送信および受信**チェック ボックスをオンします。|  
   |**メッセージのプロパティ - 受信メッセージを追跡します。**|受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。|  
   |**送信メッセージのメッセージ プロパティを追跡します。**|送信メッセージの昇格させたプロパティを追跡するには、このチェック ボックスを選択します。|  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)
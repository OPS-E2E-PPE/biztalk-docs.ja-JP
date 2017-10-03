---
title: "オーケストレーションの追跡を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, tracking
- orchestrations, HAT
- managing [orchestrations], tracking
- configuring [HAT tracking], orchestrations
- tracking, orchestrations
- HAT, orchestrations
ms.assetid: 8f5ed525-11f8-4bef-95c4-cfe9c971b663
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ebae70ec70fb58a4a935be6b2c46f39cfafba59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a>オーケストレーションの追跡を構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションの追跡を構成する方法について説明します。  
  
 詳細については、作成して、クエリを使用して、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。 追跡機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-tracking-for-an-orchestration"></a>オーケストレーションの追跡を構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk グループを展開し、**アプリケーション**、し、追跡を構成する場合、オーケストレーションを含むアプリケーションを展開します。  
  
3.  をクリックして**オーケストレーション**、追跡を構成しオーケストレーションを右クリックして**プロパティ**です。  
  
4.  クリックして、**追跡**タブを次の表に示すように、必要な追跡オプションを選択し、をクリックして**OK**です。  
  
    |オプション|Description|  
    |------------|-----------------|  
    |**イベントの追跡-オーケストレーションの開始と終了**|ビジネス プロセス全体の処理の前後にオーケストレーション インスタンスを追跡するには、このチェック ボックスをオンにします。 オーケストレーションの追跡を行うことで、追跡クエリ結果ビューでインスタンスを確認できるようになります。|  
    |**イベントの追跡 - メッセージの送信および受信**|メッセージの送信イベントと受信イベントを追跡する場合は、このチェック ボックスをオンにします。 このチェック ボックスは選択した場合にのみ使用可能な**オーケストレーションの開始と終了**チェック ボックスをオンします。|  
    |**イベントの追跡-図形の開始と終了**|オーケストレーション デバッガーでオーケストレーション インスタンスをデバッグする必要がある場合はこのチェック ボックスをオンにします。 このチェック ボックスがオンの場合、オーケストレーション デバッガーのイベントの一覧が設定されます。 このチェック ボックスは選択した場合にのみ使用可能な**オーケストレーションの開始と終了**チェック ボックスをオンします。|  
    |**オーケストレーション処理の前に、のメッセージ本文の追跡**|オーケストレーション インスタンスによる処理の前に実際のメッセージの内容を保存および追跡するには、このチェック ボックスをオンにします。 このチェック ボックスは選択した場合にのみ使用可能な**メッセージの送信および受信**チェック ボックスをオンします。|  
    |**オーケストレーション処理の後にメッセージ本文の追跡**|オーケストレーション インスタンスによる処理の後に実際のメッセージの内容を保存および追跡するには、このチェック ボックスをオンにします。 このチェック ボックスは選択した場合にのみ使用可能な**メッセージの送信および受信**チェック ボックスをオンします。|  
    |**メッセージのプロパティ - 着信メッセージを追跡します。**|受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。|  
    |**送信メッセージのメッセージ プロパティを追跡します。**|送信メッセージの昇格させたプロパティを追跡するには、このチェック ボックスを選択します。|  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)
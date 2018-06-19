---
title: ルーティングを有効にする方法が失敗したメッセージの受信ポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, routing
- managing [receive ports], errors
- managing [receive ports], failed messages
- enabling, routing
- messages, failed messages
- routing, messages
- managing [receive ports], routing
- messages, routing
- receive ports, errors
- routing, receive ports
- routing, failed messages
- errors, receive ports
ms.assetid: 22366664-545d-4981-9bde-4df48b115002
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59020dc67fa2d5b070ffc95b31648d382a66437b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254090"
---
# <a name="how-to-enable-routing-for-failed-messages-for-a-receive-port"></a>受信ポートが処理に失敗したメッセージのルーティングを有効にする方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートが処理するメッセージのルーティングを有効にする方法について説明します。 このオプションを有効にすると、処理に失敗したメッセージが、他の送信ポートやオーケストレーション スケジュールなど、メッセージをサブスクライブするアプリケーションにルーティングされます。 このオプションを無効にした場合 (既定)、失敗したメッセージは中断され、否定受信確認応答 (NACK) が生成されます。 失敗したメッセージの管理に関する背景情報については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-enable-routing-for-failed-messages-for-a-receive-port"></a>受信ポートが処理に失敗したメッセージのルーティングを有効にするには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、失敗したメッセージのルーティングを構成する BizTalk アプリケーションを展開します。  
  
3.  をクリックして**受信ポート**受信ポートを右クリックし、クリックして**プロパティ**です。  
  
4.  選択、**失敗したメッセージの有効化のルーティングを**チェック ボックスをクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)
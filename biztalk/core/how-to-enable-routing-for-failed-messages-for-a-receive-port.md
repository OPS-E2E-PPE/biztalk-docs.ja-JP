---
title: ルーティングを有効にする方法が失敗したメッセージの受信ポート |Microsoft Docs
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
ms.openlocfilehash: 7ac7ee9ef22ee3d0c452e47c886ff3298570d2c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974539"
---
# <a name="how-to-enable-routing-for-failed-messages-for-a-receive-port"></a>受信ポートが処理に失敗したメッセージのルーティングを有効にする方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートが処理するメッセージのルーティングを有効にする方法について説明します。 このオプションを有効にすると、処理に失敗したメッセージが、他の送信ポートやオーケストレーション スケジュールなど、メッセージをサブスクライブするアプリケーションにルーティングされます。 このオプションを無効にした場合 (既定)、失敗したメッセージは中断され、否定受信確認応答 (NACK) が生成されます。 失敗したメッセージの管理に関する背景情報は、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-enable-routing-for-failed-messages-for-a-receive-port"></a>受信ポートが処理に失敗したメッセージのルーティングを有効にするには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、失敗したメッセージのルーティングを構成する BizTalk アプリケーションを展開します。  
  
3. クリックして**受信ポート**受信ポートを右クリックし、クリックして**プロパティ**します。  
  
4. 選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンにして**OK**。  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)
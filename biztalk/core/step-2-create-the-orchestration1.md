---
title: 手順 2:作成、Orchestration1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a88cafbb-3b6f-4d27-8516-79a2391b4e31
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738dc5e784087b559cde9ffb82d3706f568fe160
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392741"
---
# <a name="step-2-create-the-orchestration"></a>手順 2:オーケストレーションを作成します。
オーケストレーションのセットアップは、BeginDocTest というプロジェクトを使用して次のようには。  
  
- ポート  
  
- メッセージ  
  
- 送受信  
  
- メッセージの構築  
  
- 変換  
  
  オーケストレーションは、例外処理を行いません。 J. D. Edwards OneWorld では、BeginDoc およびロールバックは、接続がタイムアウトした場合、暗黙のトランザクション内の後続の操作を実行します。BizTalk オーケストレーションが j. d. の変更をロールバックすることが何もする必要はありませんので Edwards OneWorld は、します。 ただし、タイムアウトでは、BizTalk オーケストレーションで例外が発生します。 BizTalk は、例外をイベント ログに記録されます。 例外処理オーケストレーションを追加する場合は、「方法を追加、例外のキャッチ ブロック」と「方法に補正ブロックを追加」Microsoft BizTalk Server のヘルプを参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [タスク 1:ポートを作成します。](../core/task-1-create-the-ports2.md)  
  
-   [タスク 2:メッセージを作成します。](../core/task-2-create-the-messages1.md)  
  
-   [タスク 3:受信図形と送信の構成](../core/task-3-configure-the-send-and-receive-shapes1.md)  
  
-   [タスク 4:メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape2.md)  
  
-   [タスク 5:変換図形を構成します。](../core/task-5-configure-the-transform-shape1.md)
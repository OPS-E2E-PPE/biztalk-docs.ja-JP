---
title: "手順 2: 作成、Orchestration2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08d65525-77a9-4be2-a509-40ea60fa7401
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13973edb14fbaed331a33eff429d623a33c3ff71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-orchestration"></a>手順 2: オーケストレーションを作成します。
次に示すオーケストレーションのセットアップには、BeginDocTest という名前のプロジェクトを使用します。  
  
 • ポート  
  
 • メッセージ  
  
 • 送受信  
  
 • メッセージの構築  
  
 • 変換  
  
 オーケストレーションは、例外処理を行いません。 J. D. Edwards EnterpriseOne では、BeginDoc とことはロールバックされます、接続がタイムアウトした場合、暗黙のトランザクション内の後続の操作を実行します。BizTalk オーケストレーションが j. d. の変更をロールバックのために何もする必要はありませんので Edwards EnterpriseOne で行ったです。 ただし、タイムアウトになった場合、BizTalk オーケストレーションで例外が発生します。 例外は、BizTalk によってイベント ログに記録されます。 オーケストレーションに例外処理を追加する場合、Microsoft BizTalk 2006 メイン ヘルプの「例外のキャッチ ブロックを追加する方法」および「補正ブロックを追加する方法」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [タスク 1: ポートを作成します。](../core/task-1-create-the-ports1.md)  
  
-   [タスク 2: メッセージを作成します。](../core/task-2-create-the-messages2.md)  
  
-   [タスク 3: 送信、受信図形と構成](../core/task-3-configure-the-send-and-receive-shapes2.md)  
  
-   [タスク 4: メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape1.md)  
  
-   [タスク 5: 変換図形を構成します。](../core/task-5-configure-the-transform-shape2.md)
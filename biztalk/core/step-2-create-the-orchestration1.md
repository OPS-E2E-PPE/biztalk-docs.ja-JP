---
title: '手順 2: 作成、Orchestration1 |Microsoft Docs'
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
ms.openlocfilehash: 9802b7c75b704ec34c399df8ecc432ed22d342e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982211"
---
# <a name="step-2-create-the-orchestration"></a>手順 2: オーケストレーションを作成します。
次に示すオーケストレーションのセットアップには、BeginDocTest という名前のプロジェクトを使用します。  
  
- [ポート]  
  
- メッセージ  
  
- 送受信  
  
- メッセージの構築  
  
- 変換  
  
  オーケストレーションは、例外処理を行いません。 J. D. Edwards OneWorld では、BeginDoc およびロールバックは、接続がタイムアウトした場合、暗黙のトランザクション内の後続の操作を実行します。BizTalk オーケストレーションが j. d. の変更をロールバックすることが何もする必要はありませんので Edwards OneWorld は、します。 ただし、タイムアウトになった場合、BizTalk オーケストレーションで例外が発生します。 例外は、BizTalk によってイベント ログに記録されます。 オーケストレーションに例外処理を追加する場合、Microsoft BizTalk Server ヘルプの「例外のキャッチ ブロックを追加する方法」および「補正ブロックを追加する方法」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [タスク 1: ポートの作成](../core/task-1-create-the-ports2.md)  
  
-   [タスク 2: メッセージの作成](../core/task-2-create-the-messages1.md)  
  
-   [タスク 3: 受信図形と送信図形の構成](../core/task-3-configure-the-send-and-receive-shapes1.md)  
  
-   [タスク 4: メッセージの構築図形の構成](../core/task-4-configure-the-construct-message-shape2.md)  
  
-   [タスク 5: 変換図形の構成](../core/task-5-configure-the-transform-shape1.md)
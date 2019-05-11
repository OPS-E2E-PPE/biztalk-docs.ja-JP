---
title: バッチ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- Messaging Engine, batching
- batching, batch size
- batching, about batching
- batching, configuring
- batching, Messaging Engine
ms.assetid: eadc177a-d395-4f99-8dab-aa706fd8ea00
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 941ded3f6b88c835c2eae819099449ed7d4e6974
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529092"
---
# <a name="batching"></a>バッチ処理
*バッチ処理*をラウンド トリップのデータベースを最適化できるように、一連のメッセージのシリアル化された処理します。 バッチが; アトミック作業単位とはこれは、すべて成功するか、すべて失敗します。 バッチ内の 1 つの操作が成功した場合は、別の操作が失敗したバッチを構成するすべての操作が無効になり、繰り返す必要があります。  
  
 BizTalk Server では、バッチ処理を使用します。  
  
-   複数のメッセージのトランザクションのコストを償却します。  
  
-   ラウンド トリップの内部データベースの数を減らすことで速度を上げる。  
  
-   BizTalk Server 非同期 API を使用して、BizTalk Server スレッド プールのより効率的に使用をします。  
  
## <a name="applying-batching"></a>バッチ処理の適用  
 バッチ処理して、受信場所の高度なプロパティで構成されて、送信ポート側で自動的に有効にします。  
  
## <a name="lowering-the-batch-size"></a>バッチ サイズの縮小  
 次のインスタンスの場合、バッチ サイズを小さく必要があります。  
  
-   サイズの大きいメッセージを処理するときに  
  
-   トリップがボトルネックでない場合、データベース ラウンド  
  
> [!NOTE]
>  変更するときに注意してください、 **LargeMessageThreshold**設定します。 バッチ サイズに平均メッセージ サイズを乗算より小さい**LargeMessageThreshold**しない限り、バッチ サイズは 1 に設定します。  
  
## <a name="see-also"></a>参照  
 [メッセージング エンジン](../core/the-messaging-engine.md)   
 [受信処理用メッセージをバッチ処理](../core/batching-messages-for-receive-processing.md)   
 [送信処理用メッセージのバッチ処理](../core/batching-messages-for-send-processing.md)
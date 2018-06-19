---
title: バッチ処理 |Microsoft ドキュメント
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
ms.openlocfilehash: ca31344e60daa88a37c21d0f90b6cf2d2a8aa5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230890"
---
# <a name="batching"></a>バッチ処理
*バッチ処理*をラウンド トリップのデータベースを最適化できるようにする一連のメッセージのシリアル化された処理します。 バッチは、アトミックな作業単位です。つまり、バッチはすべて成功するか、すべて失敗するかのどちらかになります。 バッチ内のある操作が成功しても、別の操作が失敗した場合は、そのバッチを構成するすべての操作が無効になり、もう一度やり直す必要があります。  
  
 BizTalk Server では、次の目的でバッチ処理を使用します。  
  
-   トランザクションのコストを複数のメッセージに分割する。  
  
-   内部的なデータベース ラウンド トリップ数を減らして速度を上げる。  
  
-   BizTalk Server 非同期 API の使用により、BizTalk Server スレッド プールの利用を効率化する。  
  
## <a name="applying-batching"></a>バッチ処理の適用  
 バッチ処理は、受信場所の詳細プロパティで設定され、送信ポート側で自動的に有効化されます。  
  
## <a name="lowering-the-batch-size"></a>バッチ サイズの縮小  
 次の場合は、バッチ サイズを縮小する必要があります。  
  
-   サイズの大きなメッセージを処理する場合  
  
-   データベース ラウンド トリップがボトルネックでない場合  
  
> [!NOTE]
>  変更するときに注意してください、 **LargeMessageThreshold**設定します。 メッセージの平均サイズを乗算するバッチ サイズにする必要がありますよりも低い**LargeMessageThreshold**しない限り、バッチ サイズは 1 を設定します。  
  
## <a name="see-also"></a>参照  
 [メッセージング エンジン](../core/the-messaging-engine.md)   
 [受信処理用メッセージをバッチ処理](../core/batching-messages-for-receive-processing.md)   
 [送信処理のメッセージのバッチ処理](../core/batching-messages-for-send-processing.md)
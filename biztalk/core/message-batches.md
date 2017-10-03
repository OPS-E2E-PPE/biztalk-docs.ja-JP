---
title: "メッセージのバッチ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f893d16-2670-4463-9a89-6f5be912a045
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25866ac076d77eae13d2ab5378a7582f584b6670
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-batches"></a>メッセージ バッチ
一括処理する必要があるメッセージのグループがアダプターに存在する場合は、これらのメッセージをバッチで処理してパフォーマンスを最適化します。 プログラム的には、メッセージ バッチとは関連する操作が含まれているメッセージの集まりということになります。 各メッセージを個別に送信するのではなく、バッチ内のメッセージをグループ化、によっては、リソースとタスクの処理の使用を最適化します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バッチ処理を使用します。  
  
-   トランザクションのコストを複数のメッセージに分割する。  
  
-   内部的なデータベース ラウンド トリップ数を減らして速度を上げる。  
  
-   メッセージを非同期的に処理することにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] スレッド プールの利用を効率化する。  
  
 バッチは、アトミックな作業単位です。 つまり、操作はすべて成功するか、すべて失敗するかのどちらかになります。 バッチ内のある操作が成功しても、別の操作が失敗した場合は、そのバッチを構成するすべての操作が無効になり、メッセージを再送信する必要があります。 そのため、アダプターは、失敗したバッチに対して 3 つの処理を実行する必要があります。  
  
-   どのメッセージの処理に失敗したのかを特定する。  
  
-   失敗したメッセージに対する処理を決定する。  
  
-   失敗しなかったメッセージを再送信する。
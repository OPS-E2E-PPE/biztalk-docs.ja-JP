---
title: "複数の受信、MSMQ アダプタを使用して場所を管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, threads
- receive locations, multiple
- threads
- receive locations, MSMQ adapters
- receive locations, threads
- configuring [MSMQ adapters], receive locations
ms.assetid: 5b2ee043-bcc9-443b-84b0-df7f487159eb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72438551d2ecab09b918808d43e7d7de6d600677
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a>MSMQ アダプタを使用して複数の受信場所を管理する方法
MSMQ アダプタは、パフォーマンスを強化するためにマルチスレッド化されています。 多くの受信場所があり、すべての受信場所に十分な数のスレッドを確保できない場合があります。 この場合、一部の受信場所でメッセージを取得できなくなります。 この問題を解決するための 3 つの方法を次に示します。  
  
-   コンピュータに BizTalk ホストを追加し、ホスト間で受信場所を分担します。 ホストを追加すると、より多くのスレッドを受信場所に確保できるようになります。  
  
-   設定、**シリアル処理**プロパティを`True`受信場所ごとにします。 このプロパティを `True` に設定すると、各受信場所に 1 つずつスレッドが割り当てられます。 これにより、プール内の使用可能なスレッドが増加します。 ただし、この方法ではパフォーマンスが低下する場合もあります。  
  
-   MSMQ アダプターの受信ハンドラーのホストに利用できるスレッドの数を増やすにレジストリを変更します。 詳細については、次を参照してください。、**ホスト用 CLR Hosting スレッド値を変更**のセクション[構成パラメーターに影響を与えるアダプター パフォーマンス](../core/configuration-parameters-that-affect-adapter-performance.md)です。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)
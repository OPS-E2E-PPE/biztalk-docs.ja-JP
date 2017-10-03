---
title: "MQSeries アダプターのパフォーマンスの最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a46455c-a8d2-4427-99bb-4e3c6dbd9566
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d4a2bd1f2cfa338d31fd574879d73249d74d08b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-mqseries-adapter-performance"></a>MQSeries アダプターのパフォーマンスを最適化します。
パフォーマンスを向上させる、可能な場合は、次の設定を使用して、MQSeries アダプターを構成します。  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a>MQSeries 受信アダプタのポーリング スレッドの値を調整します。  
 指定された値を増やす**スレッド**で、 **MQSeries トランスポートのプロパティ**受信場所の MQSeries アダプタを構成するときにします。 このプロパティを既定値は 2 から 5 の値を大きくにメッセージを受信 MQSeries アダプタの使用率が大幅に向上します。  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a>MQSeries のトランザクション サポートを無効にする受信場所必要ない場合  
 MQSeries アダプターのトランザクションのサポートには、大幅なオーバーヘッドが発生します。 トランザクションのサポートがない場合、ビジネス要件、設定、**トランザクションがサポートされている**値で、 **MQSeries トランスポートのプロパティ** ダイアログ ボックスの既定値から**をはい**に**いいえ**です。  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a>不要な場合、MQSeries アダプターでメッセージの順次配送を無効にします。  
 このプロパティを有効にするはそのままから受信した MQSeries キューに送信されるメッセージの順次配送が適用されますが、パフォーマンスに影響します。 順次配送を有効にすると、メッセージング ランタイムは指定された MQSeries キューからメッセージを受信するのに 1 つのスレッドを使用します。 順序付けられたメッセージの配信がビジネス要件ではないの場合、値を変更しない、既定の**Ordered**プロパティに、 **MQSeries トランスポートのプロパティ**として設定 ダイアログ ボックス**なし順序付け**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のパフォーマンスを最適化します。](../technical-guides/optimizing-biztalk-server-performance.md)
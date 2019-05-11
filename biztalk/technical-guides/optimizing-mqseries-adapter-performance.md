---
title: MQSeries アダプターのパフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a46455c-a8d2-4427-99bb-4e3c6dbd9566
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba12a46e17c8c521afef62e7c0ad5a9f51afe35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291424"
---
# <a name="optimizing-mqseries-adapter-performance"></a>MQSeries アダプターのパフォーマンスを最適化します。
パフォーマンスを向上させる、可能な場合は、次の設定を使用して、MQSeries アダプターを構成します。  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a>MQSeries 受信アダプタのポーリング スレッドの値を調整します。  
 指定された値を増やす**スレッド**で、 **MQSeries トランスポートのプロパティ**受信場所が MQSeries アダプターを構成する場合。 このプロパティを既定値の 2 から 5 の値に増やすことがメッセージを受信できる MQSeries アダプターの使用率が大幅に向上します。  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a>受信場所の MQSeries のトランザクション サポートを無効にする必要ない場合  
 MQSeries アダプターのトランザクション サポートでは、かなりのオーバーヘッドが発生します。 トランザクションのサポートがビジネス要件ではない場合、設定、**トランザクションがサポートされている**値、 **MQSeries トランスポートのプロパティ** ダイアログ ボックスの既定値から**はい**に**いいえ**します。  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a>不要な場合は、MQSeries アダプターに関するメッセージの順次配送を無効にします。  
 このプロパティを有効にするから受信したか、または、MQSeries キューに送信とメッセージの順次配送が適用されますが、パフォーマンスに影響します。 順次配送を有効にすると、メッセージング ランタイムは、特定の MQSeries キューからメッセージを受信するのに 1 つのスレッドを使用します。 メッセージの配信は、ビジネス要件ではありませんが注文された場合、値を変更しない、既定の**Ordered**プロパティ、 **MQSeries トランスポートのプロパティ** ダイアログ ボックスとして設定された**なし順序付け**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)
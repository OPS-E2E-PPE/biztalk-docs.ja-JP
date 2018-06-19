---
title: アダプターのパフォーマンスを向上させるためにバッチ処理の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65589925-af94-45f1-b501-37c21618b2cf
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dbee8e5b238af0a6dc7f15d54b85d85e0c4b26c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300386"
---
# <a name="configuring-batching-to-improve-adapter-performance"></a>アダプターのパフォーマンスを向上させるためにバッチ処理の構成
アダプターがバッチを処理する方法には、パフォーマンスに大きな影響を及ぼすことができます。 トランザクションごとに一定の遅延が発生するため、複数の操作を 1 つのバッチにまとめることによってトランザクションの数を最小限に抑える必要があります。  
  
 メッセージを送信している場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バッチで制限しないメッセージ数のみに基づいてバッチ サイズ。 たとえば、2 つのバッチ サイズは、アダプターの 4 つのメッセージを取得する場合のサイズを 4 KB、8 KB、1 MB、および 5 MB それぞれ、られる最初のバッチ サイズの 12 KB になり、2 番目のバッチになります 6 MB のサイズを変更します。 BizTalk メッセージング エンジンは各バッチのすべてのメッセージを順に処理するため、この例の 2 つ目のバッチの処理速度は 1 つ目のバッチに比べて大幅に低下します。 このプロパティの効果は、スループットの低下がします。  
  
 この問題を処理するためには、メッセージの数と合計 (バイト単位では、バッチ サイズ)、バッチ内のバイト数の両方に基づいて、バッチをお勧めします。 合計バイト数の最適な数はありません。 ただし、通常の処理のシナリオでバッチ サイズが 1 MB を超える場合は開始する不適切な同時実行性とスループットが発生します。  
  
 アダプターは、通常、実稼働環境でさまざまなサイズのメッセージを処理します。 受信メッセージのサイズは大きく異なる可能性があります。 その結果、バッチを構築するのに常にメッセージの数と合計バイト数を使用します。
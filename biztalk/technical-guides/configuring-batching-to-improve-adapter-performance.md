---
title: アダプターのパフォーマンスを向上させるためにバッチ処理の構成 |Microsoft Docs
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
ms.openlocfilehash: c5276c6a979783a5ab6a5e4d73573eec95cabd25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244056"
---
# <a name="configuring-batching-to-improve-adapter-performance"></a>アダプターのパフォーマンスを向上させるためにバッチ処理の構成
アダプターがバッチを処理する方法には、パフォーマンスに大きな影響を及ぼすことができます。 各トランザクションに関連付けられている一定の遅延があるため、1 つのバッチには、複数の操作を組み合わせることによってトランザクションの数を最小限にしようとする必要があります。  
  
 メッセージを送信する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バッチで制限しないメッセージ数のみに基づいてバッチ サイズ。 など、2 つのバッチ サイズは、アダプターの 4 つのメッセージを取得する場合のサイズを 4 KB、8 KB 1 MB 5 MB それぞれられる最初のバッチ サイズの 12 KB になり、2 つ目のバッチになります 6 MB のサイズを変更します。 BizTalk メッセージング エンジンが単一のバッチ内のすべてのメッセージを順番に処理するため、この例では、2 番目のバッチは最初のバッチに比べて大幅に低下処理されます。 このプロパティの効果は、スループットの低下します。  
  
 この問題を処理するためには、メッセージの数とバッチ (バッチ サイズ (バイト単位) は、) のバイト数の合計数の両方に基づいて、バッチをお勧めします。 最適な数の合計バイト数はありません。 ただし、通常の処理のシナリオでは、バッチ サイズが 1 MB を超える場合は、開始が低い同時実行性とスループットが発生します。  
  
 アダプターは、一般に運用環境でさまざまなサイズのメッセージを処理します。 受信メッセージのサイズが大きく異なる可能性があります。 結果として、バッチの作成に常にメッセージの数と合計バイト数を使用します。
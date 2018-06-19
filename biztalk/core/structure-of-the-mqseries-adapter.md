---
title: MQSeries アダプターの構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6239b78f0b9bd2c44a314b7ba0ba6ace8f3b78e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278498"
---
# <a name="structure-of-the-mqseries-adapter"></a>MQSeries アダプターの構造
MQSeries アダプタは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で実行されるアダプタと MQSeries Server for Windows で実行される COM+ アプリケーション (MQSAgent) の 2 つの部分で構成されます。 この関係を次の図に示します。  
  
 ![MQSeries アダプター コンポーネント](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")  
  
 アダプタによって、MQSAgent アプリケーションとの通信が行われます。 その後、MQSAgent アプリケーションによって、MQSeries Server for Windows との通信が行われます。 コンピュータに MQSeries Server for Windows をインストールした場合、アダプタと同じコンピュータにエージェントをインストールできます。  
  
 アダプタの送信部分では、メッセージを MQSAgent に送信します。 MQSAgent を使用して、 **MQPut**、MQSeries キュー マネージャにメッセージを送信します。  
  
 アダプタの受信部分では、MQSAgent をポーリングし、メッセージがあるかどうかを確認します。 メッセージがあるときに、MQSAgent が実行する、 **MQGet**メッセージを取得します。 MQSAgent では、キュー マネージャからメッセージを取得するときの待機時間が 3 秒にハードコードされています。  
  
> [!NOTE]
>  アダプタのポーリング間隔を設定できます。 ポーリング間隔を 3 秒未満に設定すると、待機間隔にポーリング間隔が設定されます。  
  
 トランザクションでは、メッセージの送信アクションと受信アクションの両方が発生する場合があります。 これにより、アダプタがメッセージをロールバックし、送信操作または受信操作を再試行できる可能性があります。 トランザクションの詳細については、次を参照してください。 [MQSeries アダプターのバッチ処理とトランザクション処理](../core/mqseries-adapter-batching-and-transaction-handling.md)です。  
  
 アダプタは複数のコンピュータ間で動作するため、セキュリティに関する問題が発生する可能性があります。 たとえば、悪意のあるプログラムによってエージェントの権限が借用され、データがキャプチャされる場合があります。 アダプタとエージェントの拡張保護の詳細については、次を参照してください。 [MQSeries アダプタのセキュリティ](../core/mqseries-adapter-security.md)です。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md)   
 [MQSeries アダプターとは何ですか。](../core/what-is-the-mqseries-adapter.md)
---
title: MQSeries アダプターの構造 |Microsoft Docs
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
ms.openlocfilehash: 21bd7d9dee24e8235aff34a14babd4cc69240c74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379942"
---
# <a name="structure-of-the-mqseries-adapter"></a>MQSeries アダプターの構造
MQSeries アダプターが 2 つの部分: で実行されるアダプタ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、MQSAgent COM + アプリケーション、Windows の MQSeries サーバーの下で実行されているとします。 次の図は、この関係を示します。  
  
 ![MQSeries アダプター コンポーネント](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")  
  
 アダプターは、MQSAgent アプリケーションと通信します。 さらに、MQSAgent アプリケーションは Windows の MQSeries Server と通信します。 MQSeries Server を Windows のコンピューターにインストールする場合は、アダプターと同じコンピューターにエージェントをインストールできます。  
  
 アダプターの送信部分は、メッセージを MQSAgent に送信します。 MQSAgent を使用して、 **MQPut**、MQSeries キュー マネージャにメッセージを送信します。  
  
 アダプターの受信部分では、メッセージがないかどうかに、MQSAgent をポーリングします。 メッセージがある場合、MQSAgent を実行、 **MQGet**メッセージを取得します。 MQSAgent には、キュー マネージャーからメッセージを取得するためのハード コーディングされた 3 秒待機が含まれています。  
  
> [!NOTE]
>  アダプターのポーリング間隔を設定することができます。 ポーリング間隔を 3 秒未満に設定すると、待機間隔はポーリング間隔を設定します。  
  
 両方の送信とアクションがトランザクションで発生するメッセージが表示されます。 これにより、アダプターがメッセージをロールバック、および送信を再試行してください。 または、操作を受信します。 トランザクションの詳細については、次を参照してください。 [MQSeries アダプターのバッチ処理とトランザクション処理](../core/mqseries-adapter-batching-and-transaction-handling.md)します。  
  
 アダプターは、1 つ以上のコンピューター間では、セキュリティ上の問題があります。 エージェントとキャプチャのデータが悪意のあるプログラムの権限を借用でした。 アダプターとエージェントの拡張保護の詳細については、次を参照してください。 [MQSeries アダプターのセキュリティ](../core/mqseries-adapter-security.md)します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md)   
 [MQSeries アダプターとは](../core/what-is-the-mqseries-adapter.md)
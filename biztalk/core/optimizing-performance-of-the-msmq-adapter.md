---
title: MSMQ アダプターのパフォーマンスを最適化する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, performance
- performance, MSMQ adapters
- configuring [MSMQ adapters], performance
ms.assetid: f8537ea8-a96e-4874-bcaf-cd1442a50bd4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5624eb6cf88f45d1ecad0b68fee3f5f7b8a8ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007339"
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a>MSMQ アダプターのパフォーマンスを最適化します。
MSMQ アダプターの最適化は、送信側と受信側で異なります。 受信側では、受信場所のプロパティを設定して、最適化を制御します。 送信側では、オーケストレーションを使用して、最適化を制御できます。  
  
## <a name="receive-optimization"></a>受信側の最適化  
 受信側では、アダプターで 1 つの実行スレッドを使用できます。 アダプターが 1 つのスレッドまたは複数のスレッドを使用するかどうかの設定によって異なります、**順次処理**次のように、受信場所のプロパティ。  
  
-   このプロパティが**True**アダプターが 1 つのスレッドで動作します。 アダプターは一度に 1 つのメッセージに制限されるので、メモリが節約されます。 この実質的に設定されていることを確認**バッチ サイズ**を 1 つ (1) プロパティ シートに割り当てられた値に関係なく。  
  
-   ときに**順次処理**は**False**アダプターが複数のスレッドを実行し、処理できる複数のメッセージ、時に、パフォーマンスを増加させます。  
  
 設定する必要があります**順次処理**に**True**サーバー リソースの管理を重視する場合、または数またはメッセージのサイズは、使用可能なメモリを使い果たす可能性があります。  
  
 値を減らすことによって、メモリ使用量を制御することも**バッチ サイズ**受信場所でします。 バッチ サイズは小さいほど、メモリに保持されるメッセージ数が少なくなるため、メモリ使用量が削減されます。  
  
 送信ポートと受信場所を別のコンピューターに配置した場合も、メモリ使用量を削減できます。  
  
## <a name="send-optimization"></a>送信側の最適化  
 送信側では、サンプル オーケストレーションを使用することで、同等の単一メッセージ処理をアーカイブできます。 このサンプルでは、1 つのメッセージを送信した後、受信確認を受け取るまで次のメッセージの送信を待機します。 詳細については、次を参照してください。[コードから MSMQ 受信場所の作成と送信ポートを方法](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)です。  
  
## <a name="remote-transactional-read-operations"></a>リモート トランザクションの読み取り操作  
 BizTalk server の MSMQ アダプターはトランザクション MSMQ キューからのリモート読み取り操作をすることが可能です。  MSMQ 4.0 以降のバージョンがリモート トランザクションの読み取り操作をサポートしているためです。  しかし、一般に、トランザクションの読み取り操作には時間がかかります。 パフォーマンスを最適化するために、この操作は、他の選択肢がない場合にのみ使用してください。  
  
## <a name="see-also"></a>参照  
 [MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)   
 [MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)   
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)
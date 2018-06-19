---
title: トランスポートの種類の分離と処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transport types, decoupling processing
- processing, decoupling transport types
- transport types
- transport types, service solutions
- service solution tutorial, MQSeries adapters
- processing, service solutions
- service solution tutorial, decoupling transport type and processing
- correlations, MQSeries adapters
- MQSeries adapters, correlations
- MQSeries adapters, service solutions
ms.assetid: 0b2c733a-e2c7-42ff-a733-f712fde38f7e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b14522c6bbf9393bc22f632c4db5eeb5e4a22a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238602"
---
# <a name="decoupling-transport-type-and-processing"></a>トランスポートの種類の分離と処理
サービス指向ソリューションでは、ビジネス プロセスとメッセージの送受信の詳細を明確に区別することがよくあります。 これによって、ビジネス プロセスまたはソリューションのメッセージ処理部分を個別に変更できます。  
  
 サービス指向ソリューションには、この設計方針に違反する箇所が 1 か所あります。 このセクションでは、状況、可能性のある代替方法、および選択された構造について説明します。  
  
## <a name="correlation-and-the-mqseries-adapter"></a>関連付けと MQSeries アダプタ  
 MQSeries アダプタを使用するため、標準の BizTalk Server 関連付け識別子は使用できません。 独自の関連付け識別子システムを持つ IBM バックエンド システムに関連付け識別子が使用されるためです。 代わりに、使用する必要があります、 **MQSeries.MQMD_CorrelId**と**MQSeries.MQMD_MsgID**プロパティです。 これらのプロパティを使用すると、トランスポート固有の情報がオーケストレーション (つまり、ビジネス プロセス) に配置されることがあります。  
  
 この依存関係を処理するには、BizTalk Server の関連付け識別子を使用し、カスタム パイプライン コンポーネントを使用して MQSeries の関連付け識別子を変換する方法があります。 これにより、シナリオが複雑になります。 また、トランスポートが変更された場合、2 つのパイプライン コンポーネントを変更する必要があります。 最終的に、パイプライン コンポーネントの依存関係が解決されないで再配置されます。  
  
 別の方法として、MQSeries 固有の関連付け処理を個別のオーケストレーションに分離し、そのオーケストレーションを呼び出す方法があります。 これにより、ビジネス プロセスの独立性が確保されます。 ただし、オーケストレーション間のコンパイル時の依存関係が発生します。 トランスポートを変更する場合、両方のオーケストレーションの再コンパイルが必要です (ソリューションのスタブ バージョンからアダプタ バージョンへの移行など)。 また、この呼び出しにより、ソリューションの応答時間が長くなります。  
  
 複雑になりパフォーマンスが低下する可能性を考慮した場合、オーケストレーションの MQSeries の関連付けを直接使用することが最も簡単です。  
  
 アダプターとオーケストレーションの相関関係に関する詳細については、次を参照してください。 [MQSCorrelationSetOrchestration (BizTalk Server サンプル)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)です。  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのサービスの実装の要点](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [MQSCorrelationSetOrchestration (BizTalk Server サンプル)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)
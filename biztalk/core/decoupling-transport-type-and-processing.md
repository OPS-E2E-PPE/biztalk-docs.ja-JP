---
title: トランスポートの種類の分離と処理 |Microsoft Docs
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
ms.openlocfilehash: 23a65f525664d44a53760e5cb905e4db10f0f8a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352467"
---
# <a name="decoupling-transport-type-and-processing"></a>トランスポートの種類の分離と処理
サービス指向ソリューションでは、クリア行は、多くの場合、ビジネス プロセスとメッセージの送受信の詳細の間存在します。 これにより、ビジネス プロセスまたはソリューションのメッセージ処理部分を個別に変更することができます。  
  
 サービス指向ソリューションでは、1 つの場所では、この設計原則に違反します。 このセクションでは、状況、代替、および選択されている構造について説明します。  
  
## <a name="correlation-and-the-mqseries-adapter"></a>関連付けと MQSeries アダプター  
 MQSeries アダプターを使用するには、標準の BizTalk Server 関連付け識別子を使用できません。 これは、相関関係 id を独自の関連付け識別子システムを持つ IBM バックエンド システムに移動するためです。 代わりに、使用する必要があります、 **MQSeries.MQMD_CorrelId**と**MQSeries.MQMD_MsgID**プロパティ。 オーケストレーションで、そのため、ビジネス プロセスのトランスポートに固有の情報を配置する可能性があるこれらのプロパティを使用します。  
  
 この依存関係を処理する方法の 1 つは、BizTalk Server 関連付け識別子を使用して、for MQSeries 関連付け識別子を変換するカスタム パイプライン コンポーネントを使用することです。 これにより、複雑さがシナリオに追加します。 さらに、トランスポートが変更された場合、2 つのパイプライン コンポーネントを変更する必要があります。 また、それを解決するのではなく、(パイプラインのコンポーネント) 内の依存関係を再配置が最終的には。  
  
 別のオプションは、MQSeries 固有の関連付けを個別のオーケストレーション処理を分離し、そのオーケストレーションの呼び出しになります。 これにより、ビジネス プロセスの独立性が保持されます。 ただし、これは、オーケストレーションのコンパイル時の依存関係について説明します。 トランスポートを変更するには、両方のオーケストレーション (として、たとえばの移行のスタブからソリューションのアダプター バージョンに) 再コンパイルする必要があります。 呼び出しは、ソリューションの応答時間にも追加します。  
  
 追加の複雑性とパフォーマンスが低下することを指定するには、ことが最も簡単、オーケストレーションから直接 MQSeries の関連付けを使用します。  
  
 アダプターとオーケストレーションの相関関係の詳細については、次を参照してください。 [MQSCorrelationSetOrchestration (BizTalk Server サンプル)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)します。  
  
## <a name="see-also"></a>参照  
 [サービスの実装の要点指向のソリューション](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [MQSCorrelationSetOrchestration (BizTalk Server サンプル)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)
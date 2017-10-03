---
title: "パラレルなコンボイ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Parallel Task shape [Orchestration Designer], concurrent receive tasks
- messages, convoys
- correlation sets, concurrent receive tasks
- correlation sets, Parallel Task shape [Orchestration Designer]
- orchestrations, messages
- messages, correlating to orchestrations
ms.assetid: 036aa8c0-f49c-47f0-ac1e-6c667bca3811
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c6993aa3c5dd47cb5b554dd8ab2080020ebb80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="parallel-convoys"></a>パラレルなコンボイ
パラレルなコンボイによって、複数の単一メッセージを結合して必要とされる結果を実現することができます。 関連する一連のメッセージは任意の順序で受信されることがありますが、BizTalk Server は、プロセスの開始前にそのメッセージのすべてを受信する必要があります。  
  
 たとえば、病院が新しい患者を受け入れる場合、病院は、保険情報、病歴、連絡先情報など患者からの情報をいくつか必要とします。 保険の専門家、看護士、受付など職種の異なる何人かの人でこの情報を収集します。 これらの情報は異なる複数のシステムで処理されます。 これらの情報がどのような順序で収集され、提出されるかは決まっていません。 たとえば、情報収集者は別の患者の相手をするのに忙しいかもしれないし、医療記録部門のスケジュールが遅れている場合や保険システムが正しく機能していない場合もあります。 患者に関するこの情報を組織立った方法で収集することは、その患者が病院にいる間は常に必要となります。 これによって、患者は適切な医療処置と正確な医療費の請求を受けることが保証されます。  
  
 上記のシナリオは、パラレルなコンボイ メッセージの処理を必要とするビジネス シナリオの例です。 そのビジネス要件では、患者を病院に受け入れる前に、3 つの異なる種類のメッセージを受け取ることが指定されます。 これらの 3 つのメッセージは、保険メッセージ、病歴メッセージ、患者メッセージです。 患者に関するこれらのメッセージのいずれもが最初に届くメッセージとなる可能性があり、これによって競合状態が発生します。 解決するのにはこの問題は、3 つ**受信**図形が入れられます、**並列アクション**図形および各受信がアクティブとしてマークされて = True です。 これによって、3 つのうちどのメッセージでもオーケストレーションを開始できるようになります。 オーケストレーション インスタンスは、処理をさらには進めず、他の 2 つのメッセージが到着するまで待機します。  
  
## <a name="implementing-parallel-convoys"></a>パラレルなコンボイの実装  
 パラレルなコンボイは、BizTalk Server の "パラレルな相関受信" のメッセージング デザイン パターンを使用して実装できます。 パラレルな相関受信が相関関係の 2 つまたは複数の分岐でステートメントを受信、**並列アクション**図形です。 関連付けを複数の並列タスクで初期化する場合は、関連付けられた受信のそれぞれで、まったく同じ関連付けのセットを初期化する必要があります。 関連するメッセージを受信するこのようなタスクが実際の初期化を実行する最初およびで他のタスクの検証は実行、**並列アクション**オーケストレーションの図形です。  
  
 パラレルなコンボイの実装の例を参照してください、SDK サンプル「パラレルなコンボイ」 [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。  
  
## <a name="see-also"></a>参照  
 [コンボイ シナリオの](../core/working-with-convoy-scenarios.md)   
 [シーケンシャルなコンボイ](../core/sequential-convoys.md)
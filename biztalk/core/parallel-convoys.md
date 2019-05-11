---
title: パラレルなコンボイ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Parallel Task shape [Orchestration Designer], concurrent receive tasks
- messages, convoys
- correlation sets, concurrent receive tasks
- correlation sets, Parallel Task shape [Orchestration Designer]
- orchestrations, messages
- messages, correlating to orchestrations
ms.assetid: 036aa8c0-f49c-47f0-ac1e-6c667bca3811
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edc797c59332d9a2453f38afd5daffabfbcdac9d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393418"
---
# <a name="parallel-convoys"></a>パラレルなコンボイ
パラレルなコンボイにより、複数の単一メッセージを結合して必要な結果を実現します。 一連の関連メッセージが任意の順序で受信されることは、BizTalk Server は、プロセスを開始する前にそれらのすべてを受け取る必要があります。  
  
 たとえば、新しい患者を病院に受け入れる、ときに、病院、保険情報、過去の病歴、および連絡先情報など患者からのいくつかの情報が必要です。 複数のスタッフは、保険の専門家、看護師、受付など、この情報を収集します。 複数の異なるシステムでは、この情報を処理します。 コレクションとこの送信順序とは限りません情報が発生します。 たとえば、情報コレクターがビジー状態の他の患者である可能性があります、医療記録部門がありますの背後にある自分のスケジュールでまたは保険システムが正しく機能していません。 整理された方法で、患者の情報をアセンブルする必要があります、患者が病院に費やした時間全体で発生します。 これにより、患者が適切な注意と正確な課金を受け取ることが保証されます。  
  
 上記のシナリオでは、パラレルなコンボイ メッセージの処理を必要とするビジネス シナリオの例を示します。 ビジネス要件では、患者を病院の受け入れを許可する前に次の 3 つの異なる種類のメッセージの受信によって決まります。 これら 3 つのメッセージは、保険、履歴、および患者メッセージです。 これらのメッセージのいずれかは、患者の最初のメッセージ、競合状態が作成されます。 解決するのにはこの問題は、3 つ**受信**図形が入れられます、**並列アクション**図形と各受信は、アクティブ化としてマークされて = True。 これにより、オーケストレーションを開始する 3 つのメッセージのいずれかです。 オーケストレーション インスタンスは、さらに処理を続行する前に他の 2 つのメッセージが到着するまで待機します。  
  
## <a name="implementing-parallel-convoys"></a>パラレルなコンボイの実装  
 パラレルなコンボイを使用して実装することができます、"パラレルな相関受信"メッセージング デザイン パターンを BizTalk Server です。 パラレルな相関受信が相関関係の 2 つ以上の分岐でステートメントを受信する**並列アクション**図形。 相関関係は、1 つ以上の並列タスクで初期化されている場合、関連付けられた受信の各はまったく同じ相関関係のセットを初期化する必要があります。 相関関係を持つメッセージを受信するこのようなタスクが実際の初期化を実行する最初と検証は他のタスクを実行、**並列アクション**オーケストレーションの図形。  
  
 パラレルなコンボイの実装などの SDK サンプル「パラレルなコンボイ」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
## <a name="see-also"></a>参照  
 [コンボイ シナリオの](../core/working-with-convoy-scenarios.md)   
 [シーケンシャルなコンボイ](../core/sequential-convoys.md)
---
title: 調整のしきい値の調整。タイミングと理由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9afb26c8-e5f4-4b78-9a45-a1263e3cb6ab
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fa8ad1a9c8c9c94bc41bc4ca33b3fb8763d2b69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360117"
---
# <a name="adjusting-throttling-thresholds-when-and-why"></a>調整のしきい値の調整。タイミングと理由
調整する際、1 つのサイズが収まらないすべて。 最適な設定にする必要がありますを決定する要素の範囲があります。 BizTalk Server が効果的にシステムを保護することからテストを通じて実証されている既定値を提供するすぐに使えるバックログ過多など。 ただし、一部のシナリオでは、厳しすぎる時間ことが考えられます。 次の例では、この点を説明します。  
  
## <a name="example-1-peak-loads-and-database-size"></a>例 1 : ピーク時の負荷とデータベースのサイズ  
 BizTalk Server 上に構築された各ソリューションには、最大持続可能スループット (MST) があります。 負荷がこのレベルを下回っている限り、システムが維持できるその負荷、無期限に定義します。 ただし、実際がするに時間の経過と共に変化しない安定した負荷よりも、山と谷ロード プロファイルが一般的です。  
  
 負荷を無期限に維持の最も高いピーク時の対応しているシステムのビルドではなく、コスト効率にピーク時の負荷、ある程度のバックログを処理したり、谷中に回復するシステムを構築します。 ただし、ピーク時に想定されるバックログが読み込まれる場合は、既定のデータベースのサイズの値の制限を超えるシステムは入力を制限してバックログをブロックし。 これが望ましくない場合など、すべての入力ファイルとして、できるだけ早く使用する必要があるため、ソリューションは発生させる、データベース サイズがしきい値を調整する前に、想定されるバックログを受け入れるように。  
  
## <a name="example-2-memory-usage-optimization"></a>例 2:メモリ使用量の最適化  
 調整では、処理速度を測定するために別のリソースは、メモリの量はホスト プロセスを使用できます。 小さすぎる、使用可能なメモリを取得、しきい値と比較して、調整は速度が低下する、エンジンの取得で作業するホスト キューからメッセージの数。 特定の量と今日のエンタープライズ クラスのサーバー上のメモリの可用性にばらつき、特にで x64 がサポート[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]しきい値は発生またはメモリ使用量を最適化するために削減する非常にうまく必要があります。  
  
## <a name="recommendation"></a>推奨  
 スロットル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]なしで、システムの適切な保護を提供する既定で構成されます。 既定の設定は、should not、ただし、常識では、最適です。 制限のかどうかは調整が行われて、表示する状態のパフォーマンス カウンターを監視し、自分のゲージのスロットルを適用する上のリソースが基づいている場合 (たとえば、データベースのサイズまたはメモリ使用率) がまたはの上で使用される、スロットルの調整しきい値は切り上げまたは切り捨てです。
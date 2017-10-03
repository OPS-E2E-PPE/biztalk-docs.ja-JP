---
title: "制限のしきい値の調整: タイミングと理由 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9afb26c8-e5f4-4b78-9a45-a1263e3cb6ab
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b49ae78d4b2d0cf2dabfc69af9023b1e8676dea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adjusting-throttling-thresholds-when-and-why"></a>制限のしきい値の調整: タイミングと理由
制限に関しては、あらゆる状況に対応できる汎用の設定は存在しません。 最適な設定はさまざまな要因によって決まります。 BizTalk Server が提供する既定値は、バックログ過多などの問題からシステムを有効に保護することがテストを通じて実証されています。 ただし、シナリオによっては、既定値を使用すると設定が厳しくなり過ぎる場合があります。 この点について、次の各例で説明します。  
  
## <a name="example-1-peak-loads-and-database-size"></a>例 1: 負荷がピークとデータベースのサイズ  
 BizTalk Server を基に構築された各ソリューションには、維持可能な最大スループット (MST) が設定されています。 負荷がこのレベルを下回っている限り、定義上、システムはその負荷を無期限に維持できます。 ところが実際には、時間が経過しても負荷が一定のままであることはなく、負荷プロファイルが上下に変動するのが一般的です。  
  
 最高時の負荷を無期限に維持できるシステムを構築するよりも、負荷がピークのときにある程度のバックログを処理でき、負荷が最も低いときに回復できるシステムを構築した方が、コスト効果が高くなります。 ただし、負荷のピーク時に想定されるバックログがデータベース サイズの既定の制限値を上回ると、システムは入力を制限してバックログをブロックします。 すべての入力ファイルを可能な限り短時間で処理する必要がある場合など、このような事態が望ましくない場合は、対策としてデータベース サイズのしきい値を引き上げ、想定されるバックログを制限が作動しないうちに受け入れられるようにします。  
  
## <a name="example-2-memory-usage-optimization"></a>例 2: メモリ使用量の最適化  
 処理速度を測定するために制限で使用されるもう 1 つのリソースは、プロセスをホストするために使用できるメモリの量です。 使用可能なメモリがしきい値に比べて小さすぎると、エンジンが作業対象のホスト キューから取得するメッセージの数が制限によって削減されます。 最近のエンタープライズ クラスのサーバーでは、特に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で x64 がサポートされるようになったことで、メモリの量と可用性にばらつきが見られます。このような要因により、メモリ使用量を最適化するためにしきい値の引き上げまたは引き下げが必要になると考えられます。  
  
## <a name="recommendation"></a>推奨  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、追加設定なしでシステムが適切に保護されるように制限の既定値が構成されています。 既定の設定はしないで、ただし、実行される与えに最適なです。 パフォーマンス カウンターで制限の状態を監視して制限が実行されているかどうかを確認し、制限の基準となるリソース (データベース サイズやメモリ使用量など) が過度に使用されているか、または十分に活用されていないかを各自で判断して、制限のしきい値を適宜調整してください。
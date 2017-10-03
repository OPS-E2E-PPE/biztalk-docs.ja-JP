---
title: "ロード テストとスループットのテストを実行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ff86ebd-a77f-4e29-bfea-0306e88bbf67
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3da46b2dc3208208305e60e9efbfadd0c60d7d32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="performing-load-and-throughput-testing"></a>ロード テストとスループットのテストを実行します。
必要があります使用可能なパフォーマンスとストレスのテストの実稼働環境に一致する環境です。 この環境は、すべての標準的なサービスをインストールし、監視エージェントとウイルス対策ソフトウェアなど、実行に必要です。  
  
## <a name="how-adding-applications-affects-load"></a>アプリケーションを追加すると、負荷にどのように影響する方法  
 また、実稼働環境で同じハードウェア上で実行される他の BizTalk アプリケーションと共に新しい BizTalk アプリケーションをテストする必要があります。 これは、新しい BizTalk アプリケーションを実行するコンピューターに追加の負荷を配置するため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と SQL Server。 これは、ホストで使用されるアルゴリズムの制限に照らし合わせて重要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 制限のアルゴリズムが使用可能なリソースの合計数を監視し、新しい BizTalk アプリケーションによって発生する追加の負荷で実行中のすべての BizTalk アプリケーションに影響を与える制限の条件が引き起こされる可能性がありますのでします。 詳細については、次を参照してください。[どのように BizTalk Server を実装してホスト Throttling](http://go.microsoft.com/fwlink/?LinkId=154389) (http://go.microsoft.com/fwlink/?LinkId=154389)。  
  
## <a name="testing-load-and-determining-recovery-time"></a>ロード テストと、復旧時間を決定します。  
 パフォーマンスとストレスを運用環境に配置する前にすべての BizTalk アプリケーションをテストする必要があります。 ピーク時の負荷と予想される負荷に対してテストを実行する必要があります。 BizTalk アプリケーションの最大の維持可能なスループット (MST) を決定する必要があります。 さらに、ピーク ロードから回復するシステムに要する時間を決定する必要があります。 場合は、システムは負荷のピーク時から完全に回復は [次へ] のピーク時の負荷が実行されるまで、システムの背後に段階的に離れた位置が表示されますを完全に回復することはできません。 詳細については、以下をご覧ください。  
  
-   [維持可能な最大のエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkId=154388)(http://go.microsoft.com/fwlink/?LinkId=154388)  
  
-   [維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)  
  
## <a name="see-also"></a>参照  
 [チェックリスト: テスト運用の準備](../technical-guides/checklist-testing-operational-readiness.md)
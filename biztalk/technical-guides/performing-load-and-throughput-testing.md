---
title: ロード テストとスループットのテストを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff86ebd-a77f-4e29-bfea-0306e88bbf67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d4313c073abff7022de99ac1d38375599b6ee43
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966915"
---
# <a name="performing-load-and-throughput-testing"></a>ロード テストとスループットのテストを実行します。
必要があります使用可能なパフォーマンスとストレス テスト、運用環境に一致する環境。 この環境には、すべての標準的なサービスをインストールし、監視エージェントとウイルス対策ソフトウェアなど、実行している必要があります。  
  
## <a name="how-adding-applications-affects-load"></a>アプリケーションを追加すると、負荷にどのように影響する方法  
 運用環境で同じハードウェア上で実行するようになっている他の BizTalk アプリケーションと共に新しい BizTalk アプリケーションをテストすることも必要があります。 これは、新しい BizTalk アプリケーションを実行しているコンピューターで追加の負荷を配置するため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と SQL Server。 これは、ホストで使用されるアルゴリズムの制限に照らし合わせて重要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 調整アルゴリズムは、合計使用可能なリソースを監視し、そのため、新しい BizTalk アプリケーションで発生する追加の負荷が実行中のすべての BizTalk アプリケーションに影響が制限の条件を誘発可能性があります。 詳細については、次を参照してください。[どのように BizTalk Server 実装ホスト Throttling](http://go.microsoft.com/fwlink/?LinkId=154389) (<http://go.microsoft.com/fwlink/?LinkId=154389>)。  
  
## <a name="testing-load-and-determining-recovery-time"></a>ロード テストと復旧時間を決定します。  
 パフォーマンスとストレスを運用環境に配置する前にすべての BizTalk アプリケーションをテストする必要があります。 予想される負荷とピーク時の負荷に対してテストを実行する必要があります。 BizTalk アプリケーションの最大持続可能スループット (MST) を決定する必要があります。 さらに、ピーク ロードから回復するシステムにかかる時間を決定する必要があります。 システムが完全にピーク時の負荷から復旧しない場合、[次へ] のピーク時の前に負荷が発生したを実行し、システムの背後にある段階的に離れた受け取ります、完全に回復することはできませんを実行します。 詳細については、以下をご覧ください。  
  
-   [維持可能な最大のエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkId=154388)(http://go.microsoft.com/fwlink/?LinkId=154388)  
  
-   [維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)  
  
## <a name="see-also"></a>参照  
 [チェックリスト: 運用準備のテスト](../technical-guides/checklist-testing-operational-readiness.md)
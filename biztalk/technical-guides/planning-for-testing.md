---
title: テストの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca2f5f29-9eea-4f4d-9781-75c231db4605
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1457191c414204f76cdf1c47bedc10f56ce357cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242614"
---
# <a name="planning-for-testing"></a>テストの計画
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] テストは、単体テスト、機能テスト、ロード テスト、および可用性テストを含むいくつかのカテゴリに分類できます。 このトピックでは、ユニットとロード テスト、および各を計画する方法について説明します。  
  
## <a name="planning-for-unit-testing"></a>単体テストの計画  
 単体テストは、その個々 の単位のコードの検証に使用されるプロシージャは設計どおりに取り組んでいます。 単体テストは、「障害」テストとして考えることができます。ソフトウェアは、さまざまな条件下で必要な機能を実行して、ソフトウェアは、これらの条件下で発生するエラーを処理できますか。  
  
 個々 のコンポーネントで通常の単体テストが実行されるため、関連付けられているテスト ベッドは実際に運用環境の処理機能必要はありません。 このため、ハードウェア リソースを大幅に削減を必要とする仮想サーバー環境での単体テストの実行を検討してください。  
  
 単体テストの仮想化環境で実行できるもう 1 つの側面をステージングします。 ステージング環境は、単体テストの BizTalk ソリューションの実際の展開のプロセスです。 使用可能なハードウェア リソースを最大化するには、ステージング環境用の Virtual Server の使用を検討してください。  
  
 使用しての詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境で、次を参照してください。[仮想サーバー中にリリース管理プロセスにを使用して](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ)します。 単体テストの BizTalk ソリューションに役立つツールについては、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)します。 単体テストを実行するための考慮事項のチェックリストについては、次を参照してください。[単体テストを実行する](../technical-guides/performing-unit-testing.md)します。  
  
## <a name="planning-for-load-testing"></a>ロード テストの計画  
 ロード テストは、最大持続可能なパフォーマンスを測定し、BizTalk ソリューションのパフォーマンスを追跡し、ソリューションのスループットを抑制するボトルネックを削除し、維持可能な最大のプロセスです。 ロード テストと削除からのボトルネックの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください、 [BizTalk Server 2009 パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkID=150492)(<http://go.microsoft.com/fwlink/?LinkID=150492>)。  
  
 ロード テストの BizTalk ソリューションに役立つツールについては、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)します。 ロード テストに関する考慮事項のチェックリストについては、次を参照してください。[読み込みを実行すると、スループットのテスト](../technical-guides/performing-load-and-throughput-testing.md)します。  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a>有効期間にわたって、ソリューションのテスト計画します。  
 単体テストと負荷の増加、または新しい機能またはコンポーネントとして発生する可能性がある潜在的な問題を明らかにするためのソリューションの有効期間全体での一般的なテスト計画、ソリューションの初期段階で特に重要ですがロード テストソリューションに追加されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)   
 [チェックリスト:運用準備のテスト](../technical-guides/checklist-testing-operational-readiness.md)
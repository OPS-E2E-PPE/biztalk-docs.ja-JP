---
title: テストの計画 |Microsoft ドキュメント
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
ms.openlocfilehash: 12bdf5f35d5d612ec077ebdac83339c5a6838109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302362"
---
# <a name="planning-for-testing"></a>テストの計画
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テストは、単体テスト、機能テスト、ロード テスト、および可用性のテストを含むいくつかのカテゴリに分類できます。 このトピックでは、ユニットとロード テストと各を計画する方法について説明します。  
  
## <a name="planning-for-unit-testing"></a>単体テストの計画  
 単体テストは、その個々 のコード単位の検証に使用するプロシージャが、設計どおりに機能します。 単体テストできると見なすこと「の障害対応」のテスト: ソフトウェアは、さまざまな条件で必要な機能を実行でき、これらの条件で発生したエラーをソフトウェアで処理しますか?  
  
 単体テストは通常、個々 のコンポーネントで実行される、ために、関連付けられているテスト ベッドは、実稼働環境の処理能力必要はありません。 このため、ハードウェア リソースを大幅に削減を必要とする仮想サーバー環境での単体テストの実行を検討してください。  
  
 単体テストの仮想化環境で実行できるもう 1 つの側面をステージングするとします。 ステージングとは、単体テストの BizTalk ソリューションの実際の展開のプロセスです。 使用できるハードウェア リソースを最大限には、ステージング環境の仮想サーバーを使用して検討してください。  
  
 使用しての詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境で、次を参照してください。[を使用して仮想サーバー中に、リリース管理プロセス](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ)です。 単体テストの BizTalk ソリューションに役立つツールについては、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)です。 単体テストを実行するための考慮事項のチェックリストについては、次を参照してください。[単体テストを実行する](../technical-guides/performing-unit-testing.md)です。  
  
## <a name="planning-for-load-testing"></a>ロード テストの計画  
 ロード テストは、維持可能な最大のパフォーマンスを測定し、BizTalk ソリューションのパフォーマンスを追跡し、ソリューションのスループットを抑制するボトルネックを削除することで維持可能な最大のプロセスです。 ロード テストとからのボトルネックを解消の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください、 [BizTalk Server 2009 パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
 ロード テストの BizTalk ソリューションに役立つツールについては、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)です。 ロード テストに関する考慮事項のチェックリストについては、次を参照してください。[読み込みを実行すると、スループットのテスト](../technical-guides/performing-load-and-throughput-testing.md)です。  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a>ソリューションの有効期間のテスト計画します。  
 単体テストと新機能またはコンポーネントとして、または負荷の増加として発生する可能性がある潜在的な問題を明らかにするためのソリューションの有効期間全体で一般的なテスト計画早い段階で、このソリューションの特に重要なロード テストソリューションに追加されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)   
 [チェックリスト: テスト運用の準備](../technical-guides/checklist-testing-operational-readiness.md)
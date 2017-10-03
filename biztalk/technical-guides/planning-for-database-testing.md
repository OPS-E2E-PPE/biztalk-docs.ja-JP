---
title: "データベースのテストの計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4cf5e1f-a960-4702-a050-a2cdacddcbca
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c0f9b54c866b3ab3d1eebc56bb815284ba3d7c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-database-testing"></a>データベースのテストの計画
完全な負荷が BizTalk ソリューションのテストは、ultimate の成功または失敗、ソリューションで目立つように判別されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスがのパフォーマンスに依存するので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、テストし、BizTalk ソリューションのテストに頻繁に焦点を当てていますの最適化と最適化を実行しているコンピューターの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を収容する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
## <a name="considerations-when-planning-for-database-testing"></a>データベースのテストを計画する際の考慮事項  
 データベースのテストを計画する場合は、次を考慮してください。  
  
1.  **テスト環境が、実稼働環境をできるだけと一致することを確認します。** 単体テストの Microsoft HYPER-V Server 2008 などの仮想環境を使用して、まったく問題ありません。ただし、可能な限り、最終的な実稼働環境に一致するハードウェアに対してすべてのロード/ストレス テストを実行してください。  
  
2.  **維持可能な最大のスループット、BizTalk Server システムの維持可能な最大の追跡スループットを測定する計画**です。 最大スループットは、BizTalk Server システムは、実稼働環境で無制限に処理できるメッセージ トラフィックの最大負荷として測定されます。 次のトピックの手順に従って[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。  
  
    -   [維持可能な最大のエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)。  
  
    -   [維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)。  
  
     これらのトピックでは、システム、計測する必要があります、パラメーター、MST をテストする場合に従う一般的な推奨事項に対する負荷を生成する方法について説明します。  
  
3.  **方法の影響について理解する BizTalk Server**  
     **ホスト制限を実装します。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト制限アルゴリズムのワークロードを中程度しようとしました。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ワークロードがホスト インスタンスの容量を超えないまたはいずれかのダウン ストリーム ホスト インスタンスのことを確認するインスタンスをホストします。 制限メカニズムは自律的で、既定の構成オプションは、ほとんどの適切な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]シナリオを処理します。 読み込み/ストレス テストを実装する前に、制限メカニズムをよく理解が必要、ただし、です。 詳細については、次を参照してください。[を最適化するリソース使用状況を通じてホスト制限](http://go.microsoft.com/fwlink/?LinkId=155770)(http://go.microsoft.com/fwlink/?LinkId=155770) で[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。
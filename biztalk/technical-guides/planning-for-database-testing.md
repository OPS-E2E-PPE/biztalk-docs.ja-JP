---
title: データベースのテストの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4cf5e1f-a960-4702-a050-a2cdacddcbca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bce48244f67fd757fae5c2657634274625677850
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996619"
---
# <a name="planning-for-database-testing"></a>データベースのテストの計画
Ultimate の成功または失敗のソリューションで目立つようを図、BizTalk ソリューションの徹底的な負荷をテストします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスのためのパフォーマンスに依存しているが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、テストしソリューションのテストに頻繁に重点を置いています BizTalk の最適化、および実行しているコンピューターの最適化[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が収容[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
## <a name="considerations-when-planning-for-database-testing"></a>データベースのテストを計画する際の考慮事項  
 データベースのテストを計画するときは、次を考慮してください。  
  
1. **テスト環境が運用環境をできるだけと一致することを確認します。** 単体テストの Microsoft HYPER-V Server 2008 などの仮想環境を使用することはまったく問題ありません。ただし、すべてのロード/ストレス テストは、可能な限り、最終的な運用環境に一致するハードウェアに対して実行する必要があります。  
  
2. **維持可能な最大のスループットと、BizTalk Server システムの維持可能な最大の追跡スループットを測定する**します。 維持可能な最大のスループットは、実稼働環境で BizTalk Server システムを無制限に処理できるメッセージ トラフィックの最大負荷として測定されます。 BizTalk Server ヘルプで、次のトピックの手順に従います。  
  
   - [維持可能な最大のエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)します。  
  
   - [維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)します。  
  
     これらのトピックでは、システム、測定する必要があるパラメーター、MST をテストするときに実行する一般的な推奨事項に対する負荷を生成する方法について説明します。  
  
3. **方法の理解 BizTalk Server**  
    **ホスト制限を実装します。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト制限アルゴリズムのワークロードをモデレートしようとしました。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のインスタンスに、ワークロードがホスト インスタンスの容量を超えていないこと、またはいずれかのダウン ストリーム ホスト インスタンスをホストします。 制限メカニズムは自律的と既定の構成オプションは、大半の適切な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]シナリオを処理します。 ただし、ロード/ストレス テストを実装する前に、制限メカニズムを理解がある必要があります。 詳細については、次を参照してください。[を最適化するリソースをホストの調整](http://go.microsoft.com/fwlink/?LinkId=155770)(<http://go.microsoft.com/fwlink/?LinkId=155770>) BizTalk Server のヘルプ。
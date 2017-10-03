---
title: "開発、テスト、ステージング、実稼働環境の計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c83a42d-117f-4a24-a669-b3e4e1c9a056
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25eb6aadd41526adeecb9c5a249d38384fb532ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-the-development-testing-staging-and-production-environments"></a>開発、テスト、ステージング、実稼働環境の計画
このトピックでは、BizTalk ソリューションのリリース管理プロセスで使用される環境について説明します。 同様に、エンタープライズ ソフトウェア ソリューションを開発および BizTalk ソリューションをリリースするときに確立されているソフトウェアのリリース管理のガイドラインに従ってください。 このプロセスは、次の段階を含める必要があります。  
  
-   開発  
  
-   Testing (テスト)  
  
-   ステージング  
  
-   Production  
  
 理想的には、他の環境からは独立した個別の環境でのリリース管理プロセスの各ステージを完了する必要があります。 実際には、1 つまたは複数のハードウェア、時刻、またはその他のリソース制約のための環境を結合する必要があります。 最低限には、他の環境から実稼働環境を分離する必要があります。  
  
> [!NOTE]  
>  最新のインストールとアップグレードの手順について[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]で個別にダウンロードとして入手できますが、 [BizTalk Server 2010 のドキュメント ページ](http://go.microsoft.com/fwlink/?LinkID=194815)(http://go.microsoft.com/fwlink/?LinkID=194815)。  
  
##  <a name="BKMK_VirtualServ"></a>リリース管理プロセス中に Virtual Server を使用します。  
 開発、単体テスト、および「仮想」の環境でのステージングを実行してください。 Microsoft では、Microsoft Virtual Server 2005 R2、Windows Server 2008 HYPER-V、および Microsoft HYPER-V Server 2008 などの仮想化製品の範囲を提供します。 [Microsoft Virtual Server 2005 R2](http://go.microsoft.com/fwlink/?LinkId=71365) (http://go.microsoft.com/fwlink/?LinkId=71365) は無料でダウンロードとして入手できます。 開発作業を実行するには、単体テスト、および仮想環境でのステージング優れた柔軟性を提供および使用するために必要なそれ以外の場合よりも大幅に削減のハードウェア リソース。 仮想環境を使用する場合は、ホスト コンピューターとホスト オペレーティング システム用のメモリの 512 MB の追加で実行されている各仮想マシンには、少なくとも 512 MB のメモリを割り当てます。  
  
 たとえば、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 5 つの仮想マシンを使用している環境 (2 台のコンピューターを実行している[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、2 つ Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のクラスター ノードと 1 つのドメイン コント ローラー) に 3 GB のメモリがホスト コンピューターにインストールされている場合は。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境で 2 GB を超えるメモリが必要、インストールされているメモリの最大量がホストのオペレーティング システムからアクセスできることを確認するホスト コンピューター上の 64 ビット バージョンの Windows のインストールを検討します。  
  
> [!NOTE]  
>  使用に関する推奨事項について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境で、次を参照してください。 [BizTalk Server 2009 Hyper-v ガイド](http://go.microsoft.com/fwlink/?LinkId=151834)(http://go.microsoft.com/fwlink/?LinkId=151834)。  
  
> [!NOTE]  
>  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]仮想化ソフトウェアでマイクロソフト サポート技術情報の記事 842301 に一覧表示のいずれかで実行されているサポートされたオペレーティング システムを完全にサポート[仮想マシンで Microsoft BizTalk Server サポート](http://go.microsoft.com/fwlink/?LinkId=158861)(http://go.microsoft.com/fwlink/ しますか。LinkId = 158861)。 ただし、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]サポート技術情報の記事に記載されているもの以外の仮想化ソフトウェアで実行されているサポートされたオペレーティング システムにインストールされている場合を想定どおりに行うことはできます。  
  
## <a name="development-environment"></a>開発環境  
 BizTalk ソリューションに使用される BizTalk プロジェクトは、開発環境で作成されます。 使用するコンピューターに、次のソフトウェアをインストールする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発環境。  
  
-   インターネット インフォメーション サービス (IIS)  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] クライアント ツール  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](次のコンポーネントを含む)  
  
    -   ドキュメント  
  
    -   管理ツール  
  
    -   開発ツールおよび SDK  
  
    -   追加のソフトウェア  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、開発時にローカルでホストされるようにします。  
  
-   通常は開発者では、必要なソフトウェアがインストールされた独自の開発用コンピューター (物理または仮想) が必要です。  
  
> [!NOTE]  
>  購入し、非運用環境の MSDN サブスクリプションのライセンスを使用することをお勧めします。 MSDN サブスクリプション ライセンスは、同じソフトウェアのライセンスのコスト、大幅な割引価格で提供されます。 MSDN サブスクリプションの取得の詳細については、次を参照してください。 [MSDN サブスクリプション](http://go.microsoft.com/fwlink/?LinkID=96006)(http://go.microsoft.com/fwlink/?LinkID=96006)。  
  
## <a name="testing-environment"></a>テスト環境  
 仮想環境では、単体テストを実行できます。 ただし、物理ハードウェアとソフトウェア、実稼働環境と同じである環境でのテスト、パフォーマンスを行う必要があります。  
  
 テスト環境を使用すると、最大のスループット (MST) と、BizTalk ソリューションの維持可能な最大の追跡スループットなどのパフォーマンス特性を測定します。 したがってと一致させてください、物理的な実稼働環境にできるだけです。 パフォーマンスの測定の詳細については、BizTalk ソリューションの特性を参照してください[エンジン パフォーマンス特性](http://go.microsoft.com/fwlink/?LinkId=155771)(http://go.microsoft.com/fwlink/?LinkId = 155771) または[BizTalk Server 2009 Performance Optimization Guide](http://go.microsoft.com/fwlink/?LinkID=150492) (http://go.microsoft.com/fwlink/?LinkID = 150492)。  
  
## <a name="staging-environment"></a>ステージング環境  
 通常、「単体テスト」をステージング環境を使用して、BizTalk ソリューションを実際に展開します。 ステージング環境にインストールされているソフトウェアは運用環境にインストールされているソフトウェアとほぼ同じ必要があります。 ただし、この環境は、パフォーマンスを測定するために使用することはできませんので、ステージング環境でバーチャル マシンを使用できる可能性があります、します。 ステージング環境に BizTalk アプリケーションの展開の詳細については、次を参照してください。 [BizTalk アプリケーション展開のタスクをステージング](http://go.microsoft.com/fwlink/?LinkID=154686)(http://go.microsoft.com/fwlink/?LinkID=154686)。  
  
## <a name="production-environment"></a>実稼働環境  
 運用環境は、実行中の BizTalk ソリューションをホストする「ライブ」環境です。 運用環境では、リリース管理プロセスの最終的なエンドポイントし、開発、単体テスト、ロード テスト、および他の環境でのステージングに発生した以前ホスト BizTalk アプリケーションに対してのみ必要があります。 完全な単体テスト、ロード テスト、および事前はステージング ヘルプ最大パフォーマンスや運用環境で BizTalk アプリケーションの稼働時間を確認してください。  
  
## <a name="guidelines-for-allocating-servers"></a>サーバーを割り当てるためのガイドライン  
 実稼働環境で使用する BizTalk サーバーと SQL server の物理コンピューターの特定の数を指定するリリース管理プロセスの各ステージに割り当てる必要がありますの数が予期されたに、次のガイドラインが目安を提供しますこれらは大まかな。アーキテクチャによって変更される可能性がある見積もりです。  
  
> [!NOTE]  
>  仮想サーバーは、開発、ステージング環境で使用することがあり、単体テストにも使用できます。 すべてのパフォーマンス テストは、実稼働環境での物理ハードウェアに一致する物理ハードウェア上で実行してください。  
  
|運用環境 (物理ハードウェアの推奨される) で使用されている BizTalk Server を実行しているコンピューター|開発サーバー (仮想または物理ハードウェア)|テスト サーバー (物理ハードウェアの推奨)|ステージング サーバー (仮想または物理ハードウェア)|合計はありません。 BizTalk Server を実行しているコンピューターの|  
|-------------------------------------------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------|------------------------------------------------------|---------------------------------------------------|  
|1|2|1|1|5|  
|2|2|2|1|7|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
|推定はありません。 運用環境 (物理ハードウェアの推奨される) で使用される SQL Server を実行しているコンピューターの|開発サーバー (仮想または物理ハードウェア)|テスト サーバー (物理ハードウェアの推奨)|ステージング サーバー (仮想または物理ハードウェア)|合計はありません。 SQL Server を実行しているコンピューターの|  
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------|------------------------------------------------------|-----------------------------------------------|  
|1|1|1|1|4|  
|2|1|2|1|6|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
## <a name="see-also"></a>参照  
 [BizTalk server 環境のプランニング](../technical-guides/planning-the-environment-for-biztalk-server.md)
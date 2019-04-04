---
title: 開発、テスト、ステージング、および運用環境の計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c83a42d-117f-4a24-a669-b3e4e1c9a056
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d72440595adb34b822b70e934985f88f79c66d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996051"
---
# <a name="planning-the-development-testing-staging-and-production-environments"></a>開発、テスト、ステージング、および運用環境の計画
このトピックでは、BizTalk ソリューションのリリース管理プロセスで使用される環境について説明します。 リリースの BizTalk ソリューションの開発と、エンタープライズ ソフトウェア ソリューションと同様に確立されているソフトウェア リリースの管理ガイドラインに従ってください。 このプロセスは、次の段階を含める必要があります。  
  
- 開発  
  
- Testing (テスト)  
  
- ステージング  
  
- Production  
  
  理想的には、他の環境から独立した個別の環境でリリース管理プロセスの各ステージを完了する必要があります。 現実的には、1 つまたは複数のハードウェア、時刻、またはその他のリソースの制約のための環境を結合する必要があります。 最低でも、他の環境から運用環境を分離する必要があります。  
  
> [!NOTE]
>  BizTalk Server の最新のインストールとアップグレードの手順が記載されている[BizTalk Server の新機能新規、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。 
> 
> ##  <a name="BKMK_VirtualServ"></a> リリース管理プロセス中に Virtual Server を使用します。  
>  開発、単体テスト、および「仮想」環境でステージングを実行してください。 開発作業を実行するには、単体テスト、および仮想環境でのステージング優れた柔軟性を提供し、それ以外の場合に必要なよりも大幅に削減のハードウェア リソースを使用します。 仮想環境を使用する場合は、ホスト コンピューターと 512 MB の追加、ホスト オペレーティング システムのメモリで実行されている仮想マシンごとに少なくとも 512 MB のメモリを割り当てます。  
  
 たとえば、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 5 つの仮想マシンを使用している環境 (を実行している 2 台のコンピューター [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、2 つ Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のクラスター ノードと 1 つのドメイン コント ローラー)、3 GB のホスト コンピューターにインストールされているメモリを計画しては。 場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2 GB を超えるメモリが必要な環境をインストールされているメモリの最大量がホストのオペレーティング システムからアクセスできることを確認するホスト コンピューターで Windows の 64 ビット版のインストールを検討してください。  
  
> [!NOTE]
>  使用に関する推奨事項の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境で、次を参照してください。 [BizTalk Server 2009 Hyper-v ガイド](http://go.microsoft.com/fwlink/?LinkId=151834)(<http://go.microsoft.com/fwlink/?LinkId=151834>)。  
> 
> [!NOTE]
>  BizTalk Server は、Microsoft サポート技術情報の記事 842301 の仮想化ソフトウェアのいずれかで実行されているサポートされるオペレーティング システムで完全にサポートが[仮想マシンでMicrosoftBizTalkServerのサポータビリティ](https://support.microsoft.com/kb/842301). ただし、サポート技術情報の記事に記載されているもの以外の仮想化ソフトウェアで実行されているサポートされるオペレーティング システムにインストールされている場合に期待どおりに BizTalk Server を実行しない可能性があります。  
  
## <a name="development-environment"></a>開発環境  
 開発環境では、BizTalk ソリューションに使用される BizTalk プロジェクトが作成されます。 使用するコンピューターで、次のソフトウェアをインストールする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発環境。  
  
- インターネット インフォメーション サービス (IIS)  
  
- Visual Studio  
  
- SQL Server クライアント ツール  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (次のコンポーネントを含む)  
  
  -   ドキュメント  
  
  -   管理ツール  
  
  -   開発ツールおよび SDK  
  
  -   追加のソフトウェア  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、開発時にローカルでホストされるようにします。  
  
- 通常は開発者では、必要なソフトウェアがインストールされた独自の開発用コンピューター (物理または仮想) が必要です。  
  
> [!NOTE]  
>  購入して、非運用環境用 Visual Studio サブスクリプションを使用することをお勧めします。 Visual Studio サブスクリプションは、同じソフトウェアのリテール ライセンスのコストの大幅な割引価格で提供されます。 参照してください[Visual Studio サブスクリプション](https://visualstudio.com/subscriptions)します。  
  
## <a name="testing-environment"></a>テスト環境  
 仮想環境での単体テストを行うことができます。 ただし、ハードウェアとソフトウェアを運用環境と同じである物理環境でのテスト、パフォーマンスを行う必要があります。  
  
 テスト環境を使用して、最大持続可能スループット (MST) と、BizTalk ソリューションの維持可能な最大の追跡スループットなどのパフォーマンス特性を測定します。 物理的な運用環境は、可能な限り、したがって一致する必要があります。 パフォーマンスの測定の詳細については、BizTalk ソリューションの特性を参照してください[エンジン パフォーマンスの特性](../core/engine-performance-characteristics.md)、または[BizTalk Server パフォーマンス最適化ガイド](../technical-guides/biztalk-server-2010-performance-optimization-guide.md)します。
  
## <a name="staging-environment"></a>ステージング環境  
 通常、「単体テストを」ステージング環境を使用する BizTalk ソリューションを実際に展開します。 ステージング環境にインストールされているソフトウェア、実稼働環境にインストールされているソフトウェアとする必要があります。 ただし、この環境は、パフォーマンスを測定するために使用することはできませんので、ステージング環境で仮想コンピューターを使用してかまいませんが、します。 ステージング環境に BizTalk アプリケーションの展開の詳細については、[BizTalk アプリケーション展開のタスクをステージング](../core/staging-tasks-for-biztalk-application-deployment.md)を参照してください。
  
## <a name="production-environment"></a>運用環境  
 運用環境は、実行中の BizTalk ソリューションをホストする「ライブ」環境です。 運用環境では、リリース管理プロセスの最後のエンドポイントし、開発、単体テスト、ロード テスト、およびその他の環境でのステージングが発生した以前ホスト BizTalk アプリケーションのみをする必要があります。 完全な単体テスト、ロード テスト、および事前はステージングのヘルプでの最大のパフォーマンスや運用環境で BizTalk アプリケーションの稼働時間を確認します。  
  
## <a name="guidelines-for-allocating-servers"></a>サーバーを割り当てるためのガイドライン  
 運用環境で使用する BizTalk サーバーおよび SQL server の物理コンピューターの特定の数を指定されたリリース管理プロセスの各ステージに割り当てる必要がありますの数の次のガイドラインが原則を提供しますは大まかな。アーキテクチャによって変更される可能性は概算値。  
  
> [!NOTE]  
>  仮想サーバーは、開発、ステージング環境で使用することがあり、単体テストも使用できます。 運用環境で物理ハードウェアに一致する物理ハードウェア上で、すべてのパフォーマンス テストを実行してください。  
  
|(物理ハードウェアをお勧めします) を運用環境で使用される BizTalk Server を実行しているコンピューター|開発サーバー (仮想または物理ハードウェア)|テスト サーバー (物理ハードウェアをお勧めします)|ステージング サーバー (仮想または物理ハードウェア)|合計はありません。 BizTalk Server を実行しているコンピューターの|  
|---|---|---|---|---|  
|1|2|1|1|5|  
|2|2|2|1|7|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
|推定はありません。 運用環境 (物理ハードウェアをお勧めします) で使用される SQL Server を実行しているコンピューターの|開発サーバー (仮想または物理ハードウェア)|テスト サーバー (物理ハードウェアをお勧めします)|ステージング サーバー (仮想または物理ハードウェア)|合計はありません。 SQL Server を実行しているコンピューターの|  
|---|---|---|---|---|  
|1|1|1|1|4|  
|2|1|2|1|6|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の環境の計画](../technical-guides/planning-the-environment-for-biztalk-server.md)
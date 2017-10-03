---
title: "サーバーのシナリオ アーキテクチャのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e3afb57-c3ff-4314-9605-cf9fe936e63f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34a437cdc306a25d8f5e688880c55530ea9703f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="test-scenario-server-architecture"></a>テスト シナリオのサーバーのアーキテクチャ
このトピックでは、ロード テスト中にサーバーと、ロード テストの実行対象となる、個別のサーバーのアーキテクチャ間のメッセージ フローの概要を示します。  
  
## <a name="overview-of-message-flow-during-load-testing"></a>ロード テスト中にメッセージ フローの概要  
 次の図は、ロード テスト中にサーバー間でメッセージのフローとすべてのテスト シナリオに使用されるサーバー アーキテクチャのジェネリックの概要を説明します。  
  
> [!NOTE]  
>  各テストされた個別のサーバー アーキテクチャは、セクションで説明**基準サーバー アーキテクチャ**です。  
  
 次の図は、メッセージ フローの概要を示します。 図の番号は、以下の図に示す手順に対応します。  
  
 ![メッセージ フローの概要](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")  
メッセージ フローの概要  
  
1.  ロード テストがロード エージェント コント ローラー コンピューターで開始される**VSTS_TestController**:  
  
    -   上の Visual Studio 2008 プロジェクト**VSTS_TestController**を実行します。 プロジェクトは、指定された BizUnit XML 構成ファイルを読み込みます、および BizUnit 構成ファイルで定義されているステップの実行を開始する BizUnit クラスのインスタンスを読み込みます。  
  
        > [!NOTE]  
        >  BizUnit によって使用される XML 構成ファイルの詳細についてを参照してください「の定義のテストを使用して、XML 構成ファイル」に[http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432)です。  
  
    -   「準備」テストの実行に準備メッセージを送信を開始するように求めるダイアログ ボックスを表示するコマンドを実行するテストのセットアップ手順を完了すると、BizUnit プロジェクト」の手順のいずれか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
    -   準備メッセージは、別の Visual Studio 2008 のテスト プロジェクトから送信された**VSTS_TestController**です。 "ウォーム アップする"テスト環境システム キャッシュを初期化することによって、準備メッセージが送信されます。  
  
    -   すべての事前通知メッセージが処理されます。BizUnit インスタンスは、メインのテスト実行でテストされているすべてのコンピューターのパフォーマンス モニター カウンターを読み込んで、メインのテストの実行用のメッセージを送信する入力を求められる ダイアログ ボックスを表示するコマンドを実行します。  
  
    -   Visual Studio 2008 のロード テスト プロジェクトに**VSTS_TestController**メイン テストの実行のメッセージを送信するロード テスト エージェント コンピューターに指示します。  
  
2.  テストがロード テスト エージェント コンピューターである送信メッセージに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ロード テスト コント ローラー コンピューターに Visual Studio 2008 のロード テスト プロジェクトの app.config ファイルで指定されているコンピューター (**VSTS_TestController**)。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターには、ロード テスト エージェント コンピューターによって送信されるメッセージが表示される、このロード テストの 2 つの方法でメッセージが受信された要求-応答の受信場所。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースにメッセージを公開します。  
  
    -   メッセージは、オーケストレーションによって使用されます。  
  
    -   オーケストレーションは、送信請求-応答送信ポート、ダウン ストリームの電卓サービスを呼び出す 2 つの方法にバインドされます。  
  
    > [!NOTE]  
    >  ダウン ストリームの電卓サービスがで説明されている Windows Communication Foundation サンプルに基づいて[http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762)です。 Windows Communication Foundation サンプルはダウンロード[http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352)です。  
  
4.  電卓サービスからの要求を消費する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に応答を返します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信請求-応答送信ポート。  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]応答を処理し、メッセージ ボックス データベースへの応答メッセージが引き続き発生します。 その後、電卓の web サービスからの応答メッセージを BizTalk 要求-応答ポートでメッセージ ボックス データベースから取得され、応答メッセージは、ロード テスト エージェント コンピューターに配信されます。  
  
## <a name="baseline-server-architecture"></a>ベースライン サーバー アーキテクチャ  
 HYPER-V ロールがインストールされていない、ベースライン サーバー アーキテクチャの両方と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]ホスト オペレーティング システムにインストールされました。 これは、「ベースライン」パフォーマンス メトリックを確立するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]物理ハードウェア環境のソリューションです。  
  
 次の図に、物理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]基準サーバー アーキテクチャ層。  
  
 ![物理 BizTalk & #47。物理 SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")  
物理的な BizTalk Server/物理 SQL Server (ベースライン)  
  
-   **BizTalk Server** 2 - 次のように構成されている BizTalk Server コンピューター。  
  
    -   1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してコンピューター **6** GB の RAM と**8**プロセッサ コアを使用できます。  
  
    -   1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してコンピューター **3** GB の RAM と**4**プロセッサ コアを使用できます。  
  
    -   6 + 3 の合計 = **9** GB RAM と 8 + 4 = **12**プロセッサ コアの利用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
-   **SQL Server** - 1[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]次のように構成されたコンピューター。  
  
    -   **8** GB の RAM が使用できます。  
  
    -   **4**プロセッサ コアを使用できます。  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a>BizTalk Server の仮想/物理 SQL Server  
 次の図では、仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]階層。  
  
 ![仮想 BizTalk & #47。物理 SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")  
BizTalk Server の仮想/物理 SQL Server  
  
 このシナリオでは、ロード テストがに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンで実行されていると[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]物理ハードウェア上で実行されています。  
  
> [!NOTE]  
>  次に示すメモリおよびプロセッサのコアの割り当てが HYPER-V 仮想マシンまたは物理ハードウェア上で特定のコンピューターが実行しているかどうかをされている唯一の違いの各非基準シナリオと同じです。  
  
-   **BizTalk Server** - 3[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次のように構成されている s コンピューター。  
  
    -   3 GB の RAM がそれぞれに割り当てられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]3 x 3 の合計を使用してコンピューター = **9** GB の RAM が使用できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
    -   4 コア プロセッサがそれぞれに割り当てられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]3 行 x 4 の合計を使用してコンピューター = **12**プロセッサ コアの利用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
-   **SQL Server** - 1[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]次のように構成されたコンピューター。  
  
    -   **8** GB の RAM が使用できます。  
  
    -   **4**プロセッサ コアを使用できます。  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a>BizTalk Server の仮想/仮想 SQL Server  
 次の図仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと仮想[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]別の HYPER-V ホスト コンピューター上のコンピューター。  
  
 ![仮想 BizTalk & #47。仮想 SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")  
BizTalk Server の仮想/仮想 SQL Server  
  
 このシナリオでは、ロード テストがに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンで実行されていると[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンで実行します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンが別の HYPER-V ホスト コンピューターで実行されました。  
  
> [!NOTE]  
>  このシナリオでメモリおよびプロセッサ コアの割り当ては、割り当てメモリおよびプロセッサ コアのと同じ、 **BizTalk Server の仮想/物理 SQL Server**シナリオ、されていることが唯一の違い[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]されました物理ハードウェアではなく、HYPER-V 仮想マシン上で実行するように構成します。  
  
## <a name="consolidated-environment"></a>統合環境  
 次の図仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと仮想[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]コンピューターが 1 つの HYPER-V ホスト コンピューターに統合します。  
  
 ![仮想 BizTalk & #47。仮想 SQL & #47。統合](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")  
統合環境  
  
 このシナリオでは、ロード テストがに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンで実行されていると[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンで実行します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンがすべて、同じ HYPER-V ホスト コンピューターで実行します。  
  
> [!NOTE]  
>  このシナリオでメモリおよびプロセッサ コアの割り当ては、割り当てメモリおよびプロセッサ コアのと同じ、**仮想の BizTalk Server/仮想 SQL Server**シナリオ、唯一の違いを両方、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンが同じ HYPER-V ホスト コンピューターで実行するように構成します。  
  
## <a name="see-also"></a>参照  
 [テスト シナリオの概要](../technical-guides/test-scenario-overview.md)
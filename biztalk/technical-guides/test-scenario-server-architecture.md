---
title: テスト シナリオ サーバーのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e3afb57-c3ff-4314-9605-cf9fe936e63f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4394ab90c9a20ebb081f5d8844a2ad727ac1c71b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301648"
---
# <a name="test-scenario-server-architecture"></a>テスト シナリオ サーバー アーキテクチャ
このトピックでは、ロード テスト中にサーバーとロード テストの実行対象のサーバー アーキテクチャ間でメッセージ フローの概要を示します。  
  
## <a name="overview-of-message-flow-during-load-testing"></a>ロード テスト中のメッセージ フローの概要  
 次の図では、すべてのテスト_ケースとロード テスト中にサーバー間でメッセージのフローに使用するサーバーのアーキテクチャのジェネリックの概要を示します。  
  
> [!NOTE]  
>  各テストされた個別のサーバー アーキテクチャが、セクションで説明した**ベースライン サーバー アーキテクチャ**します。  
  
 次の図は、メッセージ フローの概要を示します。 図の番号は、図は、以下の手順に対応します。  
  
 ![メッセージ フローの概要](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")  
メッセージ フローの概要  
  
1. ロード エージェント コント ローラー コンピューターでロード テストが開始される**VSTS_TestController**:  
  
   - 上の Visual Studio 2008 プロジェクト**VSTS_TestController**を実行します。 プロジェクトは、指定のための BizUnit XML 構成ファイルを読み込みます、および BizUnit 構成ファイルで定義されているステップの実行を開始する BizUnit クラスのインスタンスを読み込みます。  
  
     > [!NOTE]  
     >  BizUnit で使用される XML 構成ファイルの詳細についてを参照してください「を定義するテストを使用して、XML 構成ファイル」に[ http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432)します。  
  
   - 「準備」テストの実行に事前通知メッセージを送信を開始することを求めるダイアログ ボックスを表示するコマンドを実行するテストのセットアップ手順を完了すると、BizUnit プロジェクトでの手順のいずれか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
   - 別の Visual Studio 2008 のテスト プロジェクトから準備メッセージの送信**VSTS_TestController**します。 「ウォーム アップ」テスト環境システム キャッシュを初期化することにより、準備メッセージが送信されます。  
  
   - すべての準備の後にメッセージが処理されました。BizUnit インスタンスでは、メインのテスト実行でテストされているすべてのコンピューターのパフォーマンス モニター カウンターを読み込み、メインのテストの実行用にメッセージを送信するように求められます ダイアログ ボックスを表示するコマンドを実行します。  
  
   - 上の Visual Studio 2008 のロード テスト プロジェクト**VSTS_TestController**メイン テストの実行のメッセージを送信するロード テスト エージェント コンピューターに指示します。  
  
2. テストがロード テスト エージェント コンピューターである送信メッセージに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ロード テスト コント ローラー コンピューターで Visual Studio 2008 のロード テスト プロジェクトの app.config ファイルで指定されたコンピューター (**VSTS_TestController**)。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ロード テスト エージェント コンピューターによって送信されたメッセージを受信、メッセージを受信して 2 つの方法でこのロード テストの要求-応答の受信場所。  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースには、メッセージを公開します。  
  
   - メッセージは、オーケストレーションによって使用されます。  
  
   - オーケストレーションは、送信請求-応答送信ポート、ダウン ストリームの電卓サービスを呼び出す 2 つの方法にバインドされます。  
  
   > [!NOTE]  
   >  ダウン ストリームの電卓サービスに記載されている Windows Communication Foundation サンプルに基づいて[ http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762)します。 Windows Communication Foundation サンプル、ダウンロードできる[ http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352)します。  
  
4. 電卓サービスからの要求を使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]への応答を返すと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信請求-応答送信ポート。  
  
5. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 応答を処理し、応答メッセージをメッセージ ボックス データベースを保持します。 電卓の web サービスからの応答メッセージは、BizTalk の要求-応答ポートでメッセージ ボックス データベースから取得され、応答のメッセージは、ロード テスト エージェント コンピューターに配信されます。  
  
## <a name="baseline-server-architecture"></a>ベースライン サーバーのアーキテクチャ  
 HYPER-V の役割がインストールされていない、ベースライン サーバー アーキテクチャの両方と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト オペレーティング システムにインストールされた SQL Server とします。 「基準」のパフォーマンス メトリックを確立するためにこれは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]物理ハードウェア環境でのソリューションです。  
  
 次の図は、物理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とベースライン サーバーのアーキテクチャ用に SQL Server 層。  
  
 ![物理 BizTalk&#47;物理 SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")  
BizTalk Server の物理/物理 SQL Server (ベースライン)  
  
- **BizTalk Server** 2 - 次のように構成されている BizTalk Server コンピューター。  
  
  - 1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してコンピューター **6** GB の RAM と**8**プロセッサ コアを使用できます。  
  
  - 1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してコンピューター **3** GB の RAM と**4**プロセッサ コアを使用できます。  
  
  - 合計 6 + 3 = **9** GB RAM と 8 + 4 = **12**の使用可能なプロセッサ コア[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
- **SQL Server** -次のように構成されている 1 台の SQL Server コンピューター。  
  
  -   **8** GB の RAM が使用できます。  
  
  -   **4**プロセッサ コアを使用できます。  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a>BizTalk Server の仮想/物理 SQL Server  
 次の図は、仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]レベル。  
  
 ![仮想 BizTalk&#47;物理 SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")  
BizTalk Server の仮想/物理 SQL Server  
  
 このシナリオでは、ロード テストに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンと物理ハードウェアで実行されている SQL Server で実行されています。  
  
> [!NOTE]  
>  次に示すメモリおよびプロセッサ コアの割り当てが、HYPER-V 仮想マシンまたは物理ハードウェア上で特定のコンピューターが実行しているかどうかをされている唯一の違いの各非ベースライン シナリオと同じです。  
  
- **BizTalk Server** - 3[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のコンピューターが次のように構成されています。  
  
  - 3 GB の RAM がそれぞれに割り当てられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]3 x 3 の合計を使用してコンピューター = **9** GB の RAM の使用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
  - 4 コア プロセッサは、それぞれに割り当てられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター 3 x 4 の合計 = **12**プロセッサ コアの使用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- **SQL Server** -次のように構成されている 1 台の SQL Server コンピューター。  
  
  -   **8** GB の RAM が使用できます。  
  
  -   **4**プロセッサ コアを使用できます。  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a>BizTalk Server の仮想/仮想 SQL Server  
 次の図は、仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと別の HYPER-V で仮想 SQL Server コンピューターのホスト コンピューター。  
  
 ![仮想 BizTalk&#47;仮想 SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")  
BizTalk Server の仮想/仮想 SQL Server  
  
 このシナリオでは、ロード テストに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、HYPER-V 仮想マシンで実行されていると[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンで実行されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンが別の HYPER-V ホスト コンピューターで実行されました。  
  
> [!NOTE]
>  このシナリオでのメモリおよびプロセッサ コアの割り当てがメモリおよびプロセッサ コアの割り当てと同じ、 **BizTalk Server の仮想/物理 SQL Server**シナリオ、されていることが唯一の違い[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]されました物理ハードウェアではなく、HYPER-V 仮想マシンで実行するように構成します。  
  
## <a name="consolidated-environment"></a>統合環境  
 次の図に示します仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと仮想 SQL Server コンピューターが 1 つの HYPER-V ホスト コンピューターに統合します。  
  
 ![仮想 BizTalk&#47;仮想 SQL&#47;統合](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")  
統合環境  
  
 このシナリオでは、ロード テストに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、HYPER-V 仮想マシンで実行されていると[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンで実行されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンがすべて、同じ HYPER-V ホスト コンピューターで実行します。  
  
> [!NOTE]
>  このシナリオでのメモリおよびプロセッサ コアの割り当てがメモリおよびプロセッサ コアの割り当てと同じ、**仮想 BizTalk サーバー/仮想 SQL Server**シナリオ、唯一の違いを両方、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンが同じ HYPER-V ホスト コンピューターで実行するように構成しました。  
  
## <a name="see-also"></a>参照  
 [テスト シナリオの概要](../technical-guides/test-scenario-overview.md)
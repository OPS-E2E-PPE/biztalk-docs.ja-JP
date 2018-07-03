---
title: BizTalk Server の 64 ビットのサポートの概要 |Microsoft Docs
description: アダプター、プロセス、BizTalk 管理コンソール、BAM ツール、アセンブリ、オーケストレーション、および BizTalk Server では、複数の 64 ビット サポート
ms.custom: ''
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52ae9037-a7af-48e4-b6a3-bff7600802de
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bf9af93cfad3f495e56a3e1390006b2654f8571
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013787"
---
# <a name="biztalk-server-64-bit-support"></a>BizTalk Server での 64 ビットのサポート
このトピックでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での 64 ビットのサポートに関して、よく寄せられる質問に回答します。  
  
## <a name="which-versions-of-64-bit-windows-are-supported"></a>どのバージョンの 64 ビット Windows がサポートされているのですか?  
 すべてのエディション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サポートされているオペレーティング システムで 32 ビットの実行とネイティブの 64 ビット実行をサポートします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 32 ビットおよび 64 ビットの構成オプションが含まれています。 
 
  [BizTalk Server 2016 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
  
 [BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)  
  
## <a name="is-there-an-extra-cost-for-64-bit-support"></a>64 ビットのサポートに追加コストはかかりますか?  
 No. 64 ビットのサポートが追加料金なしで含まれています。  
  
## <a name="is-itanium-based-hardware-supported"></a>Itanium ベースのハードウェアでサポートされていますか?  
 BizTalk ランタイム、ありません。 BizTalk データベースでは、[はい] です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、AMD64 または EM64T をサポートする CPU ハードウェアが必要です。 その結果、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Itanium ベースの 64 ビット Cpu で実行されている Windows でサポートされていません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Itanium ベースで実行されているサポート[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 したがって、すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースは Itanium 64 ビット CPU でサポートされています。  
  
## <a name="which-biztalk-server-processes-run-in-64-bit-mode"></a>どの BizTalk Server プロセスが 64 ビット モードで実行されますか?  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実行可能ファイルは、いくつかの異なるサーバー ランタイム内部でホストされます。 次の表に、64 ビット モードで実行される [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスを示します。  
  
|Process|32 ビットのサポート|64 ビットのサポート|  
|-------------|---------------------|---------------------|  
|HTTP ベース アダプター (IIS)|はい|部分的|  
|BizTalk ホスト インスタンス|はい|はい|  
|エンタープライズ SSO|はい|はい|  
|BAM ポータル (IIS)|はい|いいえ|  
|SQL Server|はい|はい|  
  
##### <a name="http-based-adapters-iis"></a>HTTP ベース アダプター (IIS)  
 HTTP や SOAP アダプターのような [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントは、インターネット インフォメーション サービス (IIS) 内部でホストされて実行されます。 すべてのアダプターは、32 ビット IIS モードでサポートされます。 一部のアダプターは、64 ビット IIS モードでの実行をサポートします。 64 ビット アダプターの完全なリストについては、このトピックの後半にあるアダプターのリストを参照してください。  
  
##### <a name="biztalk-host-instances"></a>BizTalk ホスト インスタンス  
 BizTalk ホストは、サーバーの論理グループであり、それぞれがホスト インスタンスと呼ばれます。 各ホスト インスタンスは、BTSNTSvc.exe に基づいて NT サービスとしてデプロイされます。 オーケストレーションおよびインプロセス アダプターが読み込まれ、ホスト インスタンスで実行されます。 使用して 32 ビットまたは 64 ビットのいずれかのモードで実行するホスト インスタンスを構成することができます、 **32 ビットのみ**チェック ボックス オプション、**ホストのプロパティ** ダイアログ ボックスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
##### <a name="enterprise-sso"></a>エンタープライズ SSO  
 Microsoft エンタープライズ シングル サインオン (SSO) は、専用の NT サービス (ENTSSO.exe) で実行され、 32 ビット [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] ではネイティブ 32 ビットであり、64 ビット [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] ではネイティブ 64 ビットです。  
  
##### <a name="bam-portal-iis"></a>BAM ポータル (IIS)  
 ビジネス アクティビティ監視 (BAM) ポータル コンポーネントは、32 ビット ASP.NET 3.5 を使用して IIS で実行する必要があります。 BAM ポータルは、WOW モードの 64 ビット ハードウェアで実行されます。 「で実行されている 64 ビット環境で BAM ポータル」を参照してください[BAM ポータル構成のカスタマイズ](../core/customizing-the-bam-portal-configuration.md)します。  
  
##### <a name="sql-server"></a>SQL Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、32 ビット バージョンと 64 ビット バージョンの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] で相互運用可能なネイティブ トランスポート プロトコルを介して、Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] とやり取りします。 したがって、32 ビットおよび 64 ビットの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実行可能ファイルは、32 ビット バージョンまたは 64 ビット バージョンの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] とやり取りできます。 すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ストアド プロシージャは、32 ビットまたは 64 ビットの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] でサポートされます。  
  
## <a name="what-about-32-bit64-bit-support-in-non-server-processes"></a>サーバー プロセス以外の 32 ビット/64 ビット サポートはどうなっていますか?  
 **Microsoft Visual Studio**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] デザイナー実行可能ファイルが 32 ビットの内部でホストされている[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]IDE。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Microsoft を使用して 64 ビットのプロジェクトの開発をサポートしている[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]に展開されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 **Microsoft 管理コンソール (MMC)**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールは、64 ビット [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] においても、32 ビット Microsoft 管理コンソール (MMC) アプリケーションとしてのみ動作します。 エンタープライズ SSO は、32 ビットおよび 64 ビット MMC をサポートします。  
  
 **Internet Explorer**  
  
 BAM クライアントの場合は、64 ビット [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] で 32 ビット Internet Explorer をインストールして使用する必要があります。  
  
## <a name="how-do-i-enable-native-64-bit-execution-of-orchestrations"></a>オーケストレーションのネイティブ 64 ビットの実行を有効にするにはどうすればよいですか?  
 存在するホスト インスタンスで実行するオーケストレーションを割り当てる、 **32 ビットのみ**プロパティが選択されていません。 ホスト インスタンスは、Windows x64 マシンで実行される必要があります。  
  
## <a name="can-i-build-net-assemblies-that-run-in-64-bit-orchestrations"></a>64 オーケストレーションで動作する .NET アセンブリをビルドできますか?  
 可能。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 開発者は、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、64 ビット実行をサポートするアセンブリを作成できます。 これらは、オーケストレーションと共に展開し、ネイティブ 64 ビット実行用に構成されたホスト インスタンスで実行することができます。  
  
## <a name="will-net-framework-20-compiled-assemblies-jit-compile-properly-in-both-32-bit-and-64-bit"></a>.NET Framework 2.0 コンパイル済みアセンブリは、32 ビットおよび 64 ビットで適切に JIT コンパイルされますか?  
 可能。 アセンブリをコンパイルした場合、 [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 2.0 と**AnyCPU**フラグ、32 ビットまたは 64 ビット Clr で適切に 1 つの DLL が JIT コンパイルします。  
  
## <a name="can-i-install-both-32-bit-and-64-bit-components-in-a-single-biztalk-msi-package"></a>32 ビット コンポーネントと 64 ビット コンポーネントを 1 つの BizTalk MSI パッケージでインストールできますか?  
 可能。 管理者は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションから MSI パッケージ ファイルを作成できます。 MSI ファイルには、BizTalk アプリケーションに追加された、32 ビットおよび 64 ビットの DLL や EXE を含めることができます。 32 ビット Windows には、32 ビットの DLL や EXE しかインストールされません。 [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] x64 には、32 ビットと 64 ビット両方の DLL や EXE がインストールされます。  
  
## <a name="how-do-32-bit-biztalk-server-executables-run-on-windows-x64"></a>32 ビット BizTalk Server 実行可能ファイルは、Windows x64 でどのように動作しますか?  
 Windows x64 は、32 ビットおよび 64 ビット実行可能ファイルを同じマシンで実行できます。 32 ビット実行可能ファイルの場合は、WOW64 サービスを使用して、32 ビット ランタイム環境がエミュレートされます。  
  
## <a name="will-32-bit-biztalk-server-executables-have-4gb-of-addressable-process-memory-on-windows-x64"></a>32 ビット BizTalk Server 実行可能ファイルのアドレス指定可能なプロセス メモリは Windows x64 上に 4 GB 保持されますか?  
 可能。 [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] x64 では、32 ビット BTSNTSVC および IIS プロセスが WOW64 で実行され、4 GB の仮想メモリすべて使用する場合があります。 これは、32 ビット Windows のアドレス指定可能な仮想メモリの既定値 2 GB を改善したものです。  
  
 メモリの制限のしきい値は、使用可能なメモリの割合 (%) または絶対値算出として設定できます。 以下に例を示します。  
  
-   使用可能な割合 (0 ～ 100) を使用する場合は、2,048 MB に対するパーセント値を入力します。  
  
-   絶対値を使用する場合は、4,096 MB (32 ビット制限) までの任意の値 (MB 単位) を指定できます。 64 ビット ホストでは、64 ビット アドレスの理論上の上限である 2 TB まで指定できます。  
  
## <a name="which-adapters-are-capable-of-running-in-64-bit-mode"></a>どのアダプターが 64 ビット モードで動作しますか?  
 既定では、32 ビット [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]、および 64 ビット [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] の WOW64 で、すべてのアダプターを 32 ビット モードで実行できます。 次のアダプターは、ネイティブ 64 ビット モード (ホスト プロセスは IIS または BTSNTSVC) で実行できます。  
  
-   ファイル  
  
-   HTTP  
  
-   MSMQ (MSMQ)  
  
-   MQSeries  
  
-   SFTP  
  
-   SMTP (SMTP)  
  
-   SOAP  
  
-   WCF  
  
> [!NOTE]
>  MQSeries アダプターは、32 ビットおよび 64 ビット プロセスの両方でサポートされます。 アダプターには、Windows 上で IBM WebSphere MQ サーバーを実行する MQSeries エージェントがあります。 [インストール用のコンピューターを準備](../install-and-config-guides/prepare-your-computer-for-installation.md)MQ の要件を示します。  
> 
> [!NOTE]
>  場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションが (SSO、SQL アダプター、MQSeries、MQSAgent、Oracle、やなどの)、Windows Server 2003 コンピューターに接続し、インストール[934016](http://support.microsoft.com/kb/934016)と[934849](http://support.microsoft.com/kb/934849)これらの Windows server2003 サーバー。  
> 
> [!NOTE]
>  64 ビット ホスト インスタンスでの FTP アダプター、POP3 アダプター、および MIME デコーダーの実行は、サポートされていません。  
  
## <a name="are-persisted-biztalk-orchestrations-dependent-on-32-bit-or-64-bit-runtimes"></a>保存された BizTalk オーケストレーションは、32 ビットまたは 64 ビット ランタイムに依存しますか?  
 No. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 32 ビットまたは 64 ビット ランタイムに依存しない形式を使用してランタイム コンポーネントを保持します。 オーケストレーション、メッセージ、ポートもランタイム コンポーネントです。 この保存モデルでは、管理者は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データの互換性を保ったまま、ホスト構成を 32 ビットと 64 ビットの間で切り替えることができます。  
  
## <a name="when-i-upgrade-to-biztalk-server-will-my-biztalk-hosts-run-as-64-bit-by-default"></a>BizTalk Server にアップグレードすると、BizTalk ホストは既定で 64 ビットとして動作しますか?  
 No. 既定では、BizTalk Server へのアップグレードでは 32 ビットとしてすべての BizTalk ホスト インスタンスがのみマークします。 管理者は、Windows x64 コンピューターで新しいホスト インスタンスを作成し、それを使用するようにアプリケーションを構成する必要があります。  
  
## <a name="can-i-have-a-mixed-biztalk-server-group-that-includes-both-32-bit-and-64-bit-biztalk-runtimes"></a>32 ビットと 64 ビットの両方の BizTalk ランタイムを含む "混合" BizTalk Server グループを使用できますか?  
 可能。  
  
## <a name="what-languages-are-supported-on-64-bit-runtimes"></a>64 ビット ランタイムではどの言語がサポートされますか?  
 32 ビットおよび 64 ビット ランタイムの両方で、サポート言語がすべてサポートされます。  
  
## <a name="what-64-bit-sql-server-components-are-required-to-configure-bam-tools"></a>BAM ツールの構成に必要な 64 ビット SQL Server コンポーネント  
 構成ウィザードは 32 ビット プロセスであるため、64 ビットの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] との通信を可能にする特定のコンポーネントが必要です。 次の [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] クライアント コンポーネントをインストールして、BAM ツールの構成を有効にする必要があります。  
  
-   接続コンポーネント  
  
-   管理ツール  
  
-   レガシ コンポーネント  
  
## <a name="see-also"></a>参照  
 [パフォーマンスおよび容量の計画](../core/performance-and-capacity-planning.md)

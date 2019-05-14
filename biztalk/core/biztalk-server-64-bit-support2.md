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
ms.openlocfilehash: 3cf1c475cdd3f318fe92a3de7bc6150047f214a5
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530458"
---
# <a name="biztalk-server-64-bit-support"></a>BizTalk Server での 64 ビットのサポート
このトピックでは、Microsoft の 64 ビットのサポートについてよく寄せられる質問を回答[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="which-versions-of-64-bit-windows-are-supported"></a>64 ビット Windows のバージョンがサポートされていますか。  
 すべてのエディション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サポートされているオペレーティング システムで 32 ビットの実行とネイティブの 64 ビット実行をサポートします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 32 ビットおよび 64 ビットの構成オプションが含まれています。 
 
  [BizTalk Server 2016 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
  
 [BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)  
  
## <a name="is-there-an-extra-cost-for-64-bit-support"></a>追加の 64 ビットのサポートの料金はありますか。  
 No. 64 ビットのサポートが追加料金なしで含まれています。  
  
## <a name="is-itanium-based-hardware-supported"></a>Itanium ベースのハードウェアがサポートされますか。  
 BizTalk ランタイム、ありません。 BizTalk データベースでは、[はい] です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AMD64 または EM64T をサポートする CPU ハードウェアが必要です。 その結果、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Itanium ベースの 64 ビット Cpu で実行されている Windows でサポートされていません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Itanium ベースで実行されているサポート[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 したがって、すべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは Itanium 64 ビット Cpu でサポートされます。  
  
## <a name="which-biztalk-server-processes-run-in-64-bit-mode"></a>BizTalk Server プロセスは、64 ビット モードで実行しますか。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実行可能ファイルは、いくつかの別のサーバー ランタイム内部でホストされます。 次の表を一覧する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスが 64 ビット モードで実行します。  
  
|[処理]|32 ビットのサポート|64 ビットのサポート|  
|-------------|---------------------|---------------------|  
|HTTP ベース アダプター (IIS)|はい|部分的|  
|BizTalk ホスト インスタンス|はい|はい|  
|Enterprise SSO|はい|はい|  
|BAM ポータル (IIS)|はい|いいえ|  
|SQL Server|はい|はい|  
  
##### <a name="http-based-adapters-iis"></a>HTTP ベース アダプター (IIS)  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP の場合などのコンポーネントと SOAP アダプターがホストされているし、インターネット インフォメーション サービス (IIS) 内で実行します。 すべてのアダプターは、32 ビット IIS モードでサポートされます。 一部のアダプターでは、64 ビット IIS モードで実行をサポートします。 64 ビット アダプターの完全な一覧は、このトピックの後半のアダプターの一覧を参照してください。  
  
##### <a name="biztalk-host-instances"></a>BizTalk ホスト インスタンス  
 BizTalk ホストは、サーバー、ホスト インスタンスと呼ばれるそれぞれの論理グループです。 各ホスト インスタンスは、BTSNTSvc.exe に基づいて NT サービスとしてデプロイされます。 オーケストレーションおよびインプロセス アダプターが読み込まれ、ホスト インスタンスで実行されます。 使用して 32 ビットまたは 64 ビットのいずれかのモードで実行するホスト インスタンスを構成することができます、 **32 ビットのみ**チェック ボックス オプション、**ホストのプロパティ** ダイアログ ボックスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
##### <a name="enterprise-sso"></a>Enterprise SSO  
 Microsoft エンタープライズ シングル サインオン (SSO) は、専用の NT サービス (ENTSSO.exe) で実行されます。 32 ビット ネイティブ 32 ビットは[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]と 64 ビット ネイティブ 64 ビット[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]します。  
  
##### <a name="bam-portal-iis"></a>BAM ポータル (IIS)  
 ビジネス アクティビティ監視 (BAM) ポータル コンポーネントは、32 ビット ASP.NET 3.5 を使用して IIS で実行する必要があります。 BAM ポータルは、WOW モードで 64 ビット ハードウェア上で実行されます。 「で実行されている 64 ビット環境で BAM ポータル」を参照してください[BAM ポータル構成のカスタマイズ](../core/customizing-the-bam-portal-configuration.md)します。  
  
##### <a name="sql-server"></a>SQL Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Microsoft と通信する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]32 ビットおよび 64 ビット バージョンの間で相互運用可能なネイティブ トランスポート プロトコルを介して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 そのため、32 ビットおよび 64 ビット[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行可能ファイルは、の 32 ビットまたは 64 ビットのいずれかのバージョンと通信できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 すべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストアド プロシージャは 32 ビットでサポートされているか、または 64 ビット[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。  
  
## <a name="what-about-32-bit64-bit-support-in-non-server-processes"></a>サーバー プロセス以外での 32 ビット/64 ビットのサポートについて説明します。  
 **Microsoft Visual Studio**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] デザイナー実行可能ファイルが 32 ビットの内部でホストされている[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]IDE。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Microsoft を使用して 64 ビットのプロジェクトの開発をサポートしている[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]に展開されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 **Microsoft 管理コンソール (MMC)**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを 64 ビット上でも、32 ビットの Microsoft 管理コンソール (MMC) アプリケーションとしてのみ実行[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]します。 エンタープライズ SSO MMC の 32 ビットと 64 ビットの両方をサポートしています。  
  
 **Internet Explorer**  
  
 BAM クライアントをインストールして、64 ビットで使用される 32 ビット Internet Explorer を必要と[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]します。  
  
## <a name="how-do-i-enable-native-64-bit-execution-of-orchestrations"></a>オーケストレーションのネイティブの 64 ビット実行を有効にする方法  
 存在するホスト インスタンスで実行するオーケストレーションを割り当てる、 **32 ビットのみ**プロパティが選択されていません。 ホスト インスタンスは、Windows x64 マシンで実行する必要があります。  
  
## <a name="can-i-build-net-assemblies-that-run-in-64-bit-orchestrations"></a>64 ビットのオーケストレーションで実行される .NET アセンブリを構築できますか。  
 可能。 使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発者は、64 ビット実行をサポートするアセンブリを作成できます。 これらは、オーケストレーションと共に展開し、ネイティブの 64 ビット実行用に構成されたホスト インスタンスで実行することができます。  
  
## <a name="will-net-framework-20-compiled-assemblies-jit-compile-properly-in-both-32-bit-and-64-bit"></a>32 ビットおよび 64 ビットの両方で適切に .NET Framework 2.0 でコンパイルされたアセンブリ JIT コンパイルされますか。  
 可能。 アセンブリをコンパイルした場合、 [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 2.0 と**AnyCPU**フラグ、32 ビットまたは 64 ビット Clr で適切に 1 つの DLL が JIT コンパイルします。  
  
## <a name="can-i-install-both-32-bit-and-64-bit-components-in-a-single-biztalk-msi-package"></a>1 つの BizTalk MSI パッケージで 32 ビットと 64 ビットの両方のコンポーネントをインストールできますか。  
 可能。 管理者からの MSI パッケージ ファイルを作成できます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。 MSI ファイルは、32 ビットおよび 64 ビットの Dll と Exe を BizTalk アプリケーションに追加されたに含めることができます。 32 ビットの Windows で 32 ビットの Dll や Exe しかはインストールされます。  [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] X64、32 ビットと 64 ビットの両方の Dll や Exe がインストールされます。  
  
## <a name="how-do-32-bit-biztalk-server-executables-run-on-windows-x64"></a>Windows x64 で 32 ビット BizTalk Server 実行可能ファイルの実行方法  
 Windows x64 では、同じコンピューターに 32 ビットと 64 ビットの両方の実行可能ファイルを実行する機能を提供します。 32 ビット実行可能ファイルは、32 ビット ランタイム環境をエミュレートするためには、WOW64 サービスを使用します。  
  
## <a name="will-32-bit-biztalk-server-executables-have-4gb-of-addressable-process-memory-on-windows-x64"></a>32 ビット BizTalk Server 実行可能ファイルは Windows x64 で 4 GB のアドレス指定可能なプロセスのメモリがあるでしょうか。  
 可能。  [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] X64、32 ビット BTSNTSVC および IIS のプロセスが WOW64 で実行し、4 GB の仮想メモリを利用することがあります。 この既定値の 32 ビット Windows の仮想メモリをアドレス指定可能な 2 GB です。  
  
 パーセント (%) のメモリ スロットルのしきい値を設定することができます。利用できない場合、または絶対値で指定します。 以下に例を示します。  
  
-   % 利用できる (0-100) を使用する場合は、2,048 MB に対するパーセントが、入力した値。  
  
-   絶対値を使用するかどうかは、入力した値は mb 単位で値を指定できます 4,096 MB (32 ビット制限)。 64 ビットのホスト上には、2 TB の上限は理論上の 64 ビットのアドレスより高い値を指定できます。  
  
## <a name="which-adapters-are-capable-of-running-in-64-bit-mode"></a>どのアダプターが 64 ビット モードで実行されているのでしょうか。  
 既定では、すべてのアダプターは 32 ビット実行を 32 ビット モードでできます[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]と 64 ビットの wow64[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]します。 次のアダプターは、IIS または BTSNTSVC ホスト プロセス) の「ネイティブの 64 ビット モードで実行できます。  
  
-   ファイル  
  
-   HTTP  
  
-   MSMQ (MSMQ)  
  
-   MQSeries  
  
-   SFTP  
  
-   SMTP (SMTP)  
  
-   SOAP  
  
-   WCF  
  
> [!NOTE]
>  MQSeries アダプターは、32 ビットと 64 ビットの両方のプロセスでサポートされます。 アダプターは、Windows の IBM WebSphere MQ Server 上で実行される MQSeries エージェントが。 [インストール用のコンピューターを準備](../install-and-config-guides/prepare-your-computer-for-installation.md)MQ の要件を示します。  
> 
> [!NOTE]
>  場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションが (SSO、SQL アダプター、MQSeries、MQSAgent、Oracle、やなどの)、Windows Server 2003 コンピューターに接続し、インストール[934016](http://support.microsoft.com/kb/934016)と[934849](http://support.microsoft.com/kb/934849)これらの Windows server2003 サーバー。  
> 
> [!NOTE]
>  FTP アダプター、POP3 アダプター、および MIME デコーダーを 64 ビット ホスト インスタンスで実行されていることはサポートされていません。  
  
## <a name="are-persisted-biztalk-orchestrations-dependent-on-32-bit-or-64-bit-runtimes"></a>永続化された BizTalk オーケストレーションは、32 ビットまたは 64 ビット ランタイムに依存しますか。  
 No. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 32 ビットまたは 64 ビット ランタイムに依存しない形式を使用してランタイム コンポーネントを保持します。 これには、オーケストレーション、メッセージ、およびポートが含まれます。 この永続化モデルにより、管理者の非互換性を作成することがなく 32 ビットと 64 ビットのホストの構成を切り替えられる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データ。  
  
## <a name="when-i-upgrade-to-biztalk-server-will-my-biztalk-hosts-run-as-64-bit-by-default"></a>BizTalk Server にアップグレードした場合、BizTalk ホストは動作 64 ビットとして既定ででしょうか。  
 No. 既定では、BizTalk Server へのアップグレードでは 32 ビットとしてすべての BizTalk ホスト インスタンスがのみマークします。 管理者は、Windows x64 コンピューターで新しいホスト インスタンスを作成し、それらを使用するアプリケーションを構成する必要があります。  
  
## <a name="can-i-have-a-mixed-biztalk-server-group-that-includes-both-32-bit-and-64-bit-biztalk-runtimes"></a>BizTalk ランタイムの 32 ビットと 64 ビットの両方を含む「混合」BizTalk Server グループがあることができますか。  
 可能。  
  
## <a name="what-languages-are-supported-on-64-bit-runtimes"></a>どのような言語は、64 ビット ランタイムでサポートされますか。  
 サポートされているすべての言語は、32 ビットと 64 ビットの両方のランタイムでサポートされます。  
  
## <a name="what-64-bit-sql-server-components-are-required-to-configure-bam-tools"></a>どのような 64 ビット SQL Server コンポーネントは、BAM ツールを構成するために必要ですか。  
 構成ウィザードは 32 ビット プロセスです。特定のコンポーネントが 64 ビットとの通信を許可する必要がありますので[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 インストールする必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]BAM ツールの構成を有効にするクライアント コンポーネント。  
  
-   接続コンポーネント  
  
-   管理ツール  
  
-   レガシ コンポーネント  
  
## <a name="see-also"></a>参照  
 [パフォーマンスおよび容量の計画](../core/performance-and-capacity-planning.md)

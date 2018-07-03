---
title: 構成のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 902e591a-4ff4-4053-b329-0c022f44999a
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79f2d2ec9e87a22d07802f52b063f279d65ab8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973195"
---
# <a name="troubleshooting-configuration"></a><span data-ttu-id="3d657-102">構成のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3d657-102">Troubleshooting Configuration</span></span>
<span data-ttu-id="3d657-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行する 1 つ以上のコンピューター上にデータベースを作成し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が使用するテーブル、ロール、およびストアド プロシージャをそのデータベースに格納して、実行時に使用される .NET アセンブリを BizTalk 管理データベースに展開します。</span><span class="sxs-lookup"><span data-stu-id="3d657-103">The Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program creates databases on one or more computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], populates the databases with tables, roles, and stored procedures used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and deploys .NET assemblies used during runtime to the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="3d657-104">このセクションでは、構成エラーを解決するためのトラブルシューティング手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d657-104">This section discusses troubleshooting techniques to resolve configuration errors.</span></span> <span data-ttu-id="3d657-105">一般的な構成の問題とその解決方法の一覧も含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d657-105">It also lists some common configuration problems and how to resolve these problems.</span></span>  
  
## <a name="configuration-logging"></a><span data-ttu-id="3d657-106">構成のログ記録</span><span class="sxs-lookup"><span data-stu-id="3d657-106">Configuration Logging</span></span>  
 <span data-ttu-id="3d657-107">構成プログラムが既定で実行しているコンピューターの一時ディレクトリに格納されている構成ログ ファイルに詳細な情報を書き込みます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3d657-107">The configuration program writes detailed information to a configuration log file which by default is located in the temp directory of the computer running[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3d657-108">TEMP 環境変数によって指定されているフォルダーを確認するには、そのコンピューターでコマンド プロンプトを開き、次のコマンドを入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3d657-108">To determine the folder that is specified by the TEMP environment variable open a command prompt on this computer, type the following command, and then press ENTER:</span></span>  
  
 <span data-ttu-id="3d657-109">**エコー %temp%**</span><span class="sxs-lookup"><span data-stu-id="3d657-109">**echo %TEMP%**</span></span>  
  
 <span data-ttu-id="3d657-110">構成ログ ファイルの内容は、実行された構成手順の概要と、構成処理中に発生した疑いのあるエラーに関する診断情報です。</span><span class="sxs-lookup"><span data-stu-id="3d657-110">The configuration log file contains a summary of the configuration steps performed, as well as diagnostic information about any failures that may occur during the configuration process.</span></span> <span data-ttu-id="3d657-111">構成エラーが発生した場合、メモ帳などのテキスト エディターでは、構成ログを開くし、エラーの考えられる原因は、ログ ファイルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d657-111">If a configuration error occurs, open the configuration log in a text editor such as Notepad and check the log file for possible causes of the error.</span></span>  
  
## <a name="troubleshooting-tools"></a><span data-ttu-id="3d657-112">トラブルシューティング ツール</span><span class="sxs-lookup"><span data-stu-id="3d657-112">Troubleshooting Tools</span></span>  
 <span data-ttu-id="3d657-113">SQL Server プロファイラー、Filemon、または Regmon を使用して、構成エラーに関する追加情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="3d657-113">Use SQL Server Profiler, Filemon, or Regmon to gather additional information about configuration failures.</span></span> <span data-ttu-id="3d657-114">これらのツールの詳細については、次を参照してください。[トラブルシューティングのために使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d657-114">For more information about these tools, see [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="3d657-115">既知の問題</span><span class="sxs-lookup"><span data-stu-id="3d657-115">Known Issues</span></span>  
  
#### <a name="configuration-fails-when-biztalk-server-and-sql-server-are-installed-on-separate-computers"></a><span data-ttu-id="3d657-116">BizTalk Server と SQL Server が別のコンピューターにインストールされていると構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="3d657-116">Configuration fails when BizTalk Server and SQL Server are installed on separate computers</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-117">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-117">Problem</span></span>  
 <span data-ttu-id="3d657-118">エンタープライズ シングル サインオン (SSO) コンポーネントを構成しようとすると、次のようなエラーが発生して構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d657-118">Configuration fails with errors similar to the following when attempting to configure the Enterprise Single Sign-On (SSO) component:</span></span>  
  
 <span data-ttu-id="3d657-119">SSO データベースへのアクセスを試みているときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3d657-119">An error occurred while attempting to access the SSO database.</span></span>  
  
 <span data-ttu-id="3d657-120">関数: FieldInfoCreate</span><span class="sxs-lookup"><span data-stu-id="3d657-120">Function: FieldInfoCreate</span></span>  
  
 <span data-ttu-id="3d657-121">- または -</span><span class="sxs-lookup"><span data-stu-id="3d657-121">-or-</span></span>  
  
 <span data-ttu-id="3d657-122">シングル サインオン (SSO) サービスの有効化に失敗しました (エラー コード 0X800706BA)</span><span class="sxs-lookup"><span data-stu-id="3d657-122">Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-123">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-123">Cause</span></span>  
 <span data-ttu-id="3d657-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、構成操作は分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキストで行われます。このため、それらのコンピューターの間のネットワークで MSDTC 機能を利用可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d657-124">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on different computers then the configuration operations are performed under the context of a Distributed Transaction Coordinator (MSDTC) transaction and MSDTC functionality must be available over the network between these computers.</span></span> <span data-ttu-id="3d657-125">実行するコンピューター間のネットワークで MSDTC 機能は利用でできないかどうか[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]し、このエラーが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="3d657-125">If MSDTC functionality is not available over the network between the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] then this error can occur.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-126">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-126">Resolution</span></span>  
 <span data-ttu-id="3d657-127">次の手順では、 [MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)を実行するコンピューター間のネットワークで MSDTC 機能を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3d657-127">Follow the steps in [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md) to ensure MSDTC functionality over the network between the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
#### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a><span data-ttu-id="3d657-128">ウイルス対策ソフトウェアの干渉によって構成エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="3d657-128">Antivirus software interferes with configuration and causes configuration failures</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-129">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-129">Problem</span></span>  
 <span data-ttu-id="3d657-130">ウイルス対策ソフトウェアによって構成プログラムが誤ってウイルスと判断されると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d657-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration fails when antivirus software incorrectly determines that the configuration program is a virus.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-131">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-131">Cause</span></span>  
 <span data-ttu-id="3d657-132">ウイルス対策ソフトウェアが更新されていない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正当な (ウイルスではない) プログラムとしてプログラムを構成します。</span><span class="sxs-lookup"><span data-stu-id="3d657-132">The antivirus software has not been updated to include the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program as a legitimate (non-virus) program.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-133">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-133">Resolution</span></span>  
 <span data-ttu-id="3d657-134">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムが正当な (ウイルスではない) プログラムとして認識されるようにウイルス対策プログラムを構成するか、構成プログラムを実行する間、ウイルス対策ソフトウェアを一時的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="3d657-134">Configure the antivirus program to recognize the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program as a legitimate (non-virus) program or else temporarily disable the antivirus software while the configuration program is running.</span></span>  
  
#### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a><span data-ttu-id="3d657-135">"ファイルまたはアセンブリ名 'FileName.dll'、またはその依存関係の 1 つが見つかりませんでした" というエラーによって構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="3d657-135">Configuration fails with a "File or assembly name FileName.dll, or one of its dependencies, was not found" error</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-136">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-136">Problem</span></span>  
 <span data-ttu-id="3d657-137">構成プロセスで次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d657-137">An error similar to the following is displayed during the configuration process:</span></span>  
  
 <span data-ttu-id="3d657-138">BizTalk システム アセンブリ "C:\Program Files\Microsoft\" を展開できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3d657-138">Failed to deploy BizTalk system assembly "C:\Program Files\Microsoft\\</span></span>  
  
 <span data-ttu-id="3d657-139">BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll します。</span><span class="sxs-lookup"><span data-stu-id="3d657-139">BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll.</span></span> <span data-ttu-id="3d657-140">[未指定]</span><span class="sxs-lookup"><span data-stu-id="3d657-140">Unspecified</span></span>  
  
 <span data-ttu-id="3d657-141">例外: ファイルまたはアセンブリ名 filename.dll、またはいずれか、</span><span class="sxs-lookup"><span data-stu-id="3d657-141">exception: File or assembly name FileName .dll, or one of its</span></span>  
  
 <span data-ttu-id="3d657-142">依存関係の 1 つが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="3d657-142">dependencies, was not found.</span></span> <span data-ttu-id="3d657-143">ファイルまたはアセンブリ名 FileName.dll、または</span><span class="sxs-lookup"><span data-stu-id="3d657-143">File or assembly name FileName .dll, or</span></span>  
  
 <span data-ttu-id="3d657-144">その依存関係の 1 つが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="3d657-144">one of its dependencies, was not found."</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-145">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-145">Cause</span></span>  
 <span data-ttu-id="3d657-146">このエラーは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターの一時フォルダーに対する書き込みアクセス許可がネットワーク サービス アカウントにない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="3d657-146">This error can occur if the Network Service account does not have write permissions to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3d657-147">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成では、構成の間に .NET アセンブリを BizTalk 管理データベースに展開するために Windows Management Instrumentation (WMI) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d657-147">During configuration, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration uses Windows Management Instrumentation (WMI) to deploy .NET assemblies to the BizTalk Management database.</span></span> <span data-ttu-id="3d657-148">WMI はこれらのアセンブリを BizTalk 管理データベースに展開する際にネットワーク サービス アカウントを借用するため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターの一時フォルダーに対する書き込みアクセス許可がネットワーク サービス アカウントに必要です。</span><span class="sxs-lookup"><span data-stu-id="3d657-148">WMI impersonates the Network Service account while deploying these assemblies to the BizTalk Management database and so the Network Service account must have write access to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-149">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-149">Resolution</span></span>  
 <span data-ttu-id="3d657-150">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターの一時フォルダーに対する書き込みアクセス許可をネットワーク サービス アカウントに与えてから、再度構成プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d657-150">Grant the Network Service account write access to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and run the configuration program again.</span></span> <span data-ttu-id="3d657-151">TEMP 環境変数で指定されているフォルダーを決定するには、コンピューターでコマンド プロンプトを開き、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3d657-151">To determine the folder that is specified by the TEMP environment variable, open a command prompt on the computer, type the following command, and then press ENTER:</span></span>  
  
```  
echo %TEMP%  
```  
  
#### <a name="configuration-of-the-group-fails-if-the-netbios-name-of-the-computer-running-sql-server-exceeds-15-characters"></a><span data-ttu-id="3d657-152">SQL Server を実行しているコンピューターの NetBIOS 名が 15 文字より長いとグループの構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="3d657-152">Configuration of the group fails if the NetBIOS name of the computer running SQL Server exceeds 15 characters</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-153">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-153">Problem</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3d657-154"> のグループの構成が失敗して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成ログに次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d657-154"> group configuration fails and an error similar to the following is displayed in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration log:</span></span>  
  
 <span data-ttu-id="3d657-155">2006-08-29 23:54:00:0902 [WARN] AdminLib GetBTSMessage: hrErr 80070547; を =</span><span class="sxs-lookup"><span data-stu-id="3d657-155">2006-08-29 23:54:00:0902 [WARN] AdminLib GetBTSMessage: hrErr=80070547;</span></span>  
  
 <span data-ttu-id="3d657-156">Msg=ドメイン コントローラーから構成情報を読み取れま</span><span class="sxs-lookup"><span data-stu-id="3d657-156">Msg=Configuration information could not be read from the domain</span></span>  
  
 <span data-ttu-id="3d657-157">せんでした。コンピューターが有効ではないか、ま</span><span class="sxs-lookup"><span data-stu-id="3d657-157">controller, either because the machine is unavailable, or access has</span></span>  
  
 <span data-ttu-id="3d657-158">たはアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="3d657-158">been denied.;</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-159">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-159">Cause</span></span>  
 <span data-ttu-id="3d657-160">この問題は、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターの NetBIOS 名が 15 文字より長い場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="3d657-160">This problem occurs if the length of the NetBIOS name for the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] exceeds 15 characters.</span></span> <span data-ttu-id="3d657-161">NetBIOS 名が 15 文字より長いと、Windows が NetBIOS 名を 15 文字に切り詰めるため、NetBIOS 名がそのコンピューターの完全修飾ドメイン名 (FQDN) や DNS 名の最初の部分に一致しなくなります。</span><span class="sxs-lookup"><span data-stu-id="3d657-161">If the NetBIOS name exceeds 15 characters then Windows truncates the NetBIOS name to 15 characters and the NetBIOS name will no longer match the first part of the fully qualified domain name (FQDN) or DNS name of this computer.</span></span> <span data-ttu-id="3d657-162">NetBIOS 名がコンピューターの FQDN の最初の部分に一致しないと、グループの構成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d657-162">If the NetBIOS name does not match the first part of the FQDN of the computer, group configuration will fail.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-163">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-163">Resolution</span></span>  
 <span data-ttu-id="3d657-164">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターの NetBIOS 名を 15 文字以内の名前に変更して、再度構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d657-164">Change the NetBIOS name of the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] to a name with no more than 15 characters and run configuration again.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d657-165">コンピューターの名前を変更した場合は、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d657-165">You must restart the computer if you rename it.</span></span>  
  
#### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a><span data-ttu-id="3d657-166">指定したデータベースと同じ名前の SQL Server データベース ファイルが SQL Server のデータ フォルダーに既に存在していると構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="3d657-166">Configuration fails if a SQL Server database file that has the same name as the specified database already exists in the SQL Server data folder</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-167">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-167">Problem</span></span>  
 <span data-ttu-id="3d657-168">次のようなエラーが発生して構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d657-168">Configuration fails with an error similar to the following:</span></span>  
  
 <span data-ttu-id="3d657-169">BAM データベースを設定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3d657-169">Failed to set up BAM database(s)</span></span>  
  
 <span data-ttu-id="3d657-170">'BAMPrimaryImport' のログインで要求されたデータベースを開けません。</span><span class="sxs-lookup"><span data-stu-id="3d657-170">Cannot open database requested in login 'BAMPrimaryImport'</span></span>  
  
 <span data-ttu-id="3d657-171">ログインは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d657-171">Logon fails.</span></span> <span data-ttu-id="3d657-172">ユーザーのログオンに失敗しました '*biztalk \biztalkuser*'</span><span class="sxs-lookup"><span data-stu-id="3d657-172">Logon failed for user '*BizTalk\BizTalkUser*'</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-173">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-173">Cause</span></span>  
 <span data-ttu-id="3d657-174">このエラーは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターの \MSSQL\data フォルダーに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムが作成しようとしている .mdf ファイルまたは .ldf ファイルと同じ名前の .mdf ファイルまたは .ldf ファイルが既に存在する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="3d657-174">This error can occur if an .mdf file or an .ldf file already exists in the \MSSQL\data folder of the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that has the same name as the .mdf file or the .ldf file that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program is trying to create.</span></span> <span data-ttu-id="3d657-175">データベースのために作成される .mdf ファイルと .ldf ファイルの名前は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムで指定したデータベースの名前に .mdf 拡張子と .ldf 拡張子を追加して生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d657-175">The names of the .mdf file and the .ldf file that are created for the databases are derived from the name of the database that is specified in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program with an .mdf and an .ldf extension appended.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-176">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-176">Resolution</span></span>  
 <span data-ttu-id="3d657-177">この問題を解決するには、以下のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d657-177">To resolve this behavior, use one of the following methods:</span></span>  
  
-   <span data-ttu-id="3d657-178">現在作成しているデータベースの名前と一致する名前を持つ .mdf ファイルや .ldf ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="3d657-178">Delete any .mdf files or .ldf files that have names that match the names of any databases that you are creating.</span></span>  
  
-   <span data-ttu-id="3d657-179">SQL Server の \Program Files\Microsoft SQL Server\MSSQL\data フォルダーに既に存在する .mdf ファイルや .ldf ファイルの名前と一致しないデータベース名を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d657-179">Choose database names that do not match the names of any .mdf files or .ldf files that already exist in the \Program Files\Microsoft SQL Server\MSSQL\data folder of your SQL server.</span></span>  
  
#### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a><span data-ttu-id="3d657-180">ドメイン コントローラーでローカル アカウントを指定すると構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="3d657-180">Configuration fails on a domain controller when specifying local accounts</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-181">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-181">Problem</span></span>  
 <span data-ttu-id="3d657-182">ドメイン コントローラーで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムを実行しているときに、BizTalkServerApplication ホストか BizTalkIsolatedHost ホストのいずれかにローカル グループ (BizTalk ホスト ユーザー グループなど) を指定すると、構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d657-182">When running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program on a domain controller, configuration fails if you specified a local group (for example, BizTalk Host Users Group) for either the BizTalkServerApplication host or the BizTalkIsolatedHost host.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-183">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-183">Cause</span></span>  
 <span data-ttu-id="3d657-184">ドメイン コントローラーでは、ローカル Windows グループが自動的にドメイン Windows グループとして処理されます (ドメイン コントローラーにはローカル Windows グループのようなものは存在しません)。</span><span class="sxs-lookup"><span data-stu-id="3d657-184">A domain controller automatically treats a local Windows group as a domain Windows group (there is no such thing as local Windows group on a domain controller).</span></span> <span data-ttu-id="3d657-185">構成プログラムの実行中にホストにローカル Windows グループを指定した場合、そのグループに対して [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ログオンを作成しようとすると構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d657-185">If you specified a local Windows group for the host while running the configuration program, configuration will fail when trying to create a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] logon for the group.</span></span> <span data-ttu-id="3d657-186">サーバーがドメイン コントローラーに設定されていると、構成プログラムのローカル Windows グループ オプションが無効になりません。</span><span class="sxs-lookup"><span data-stu-id="3d657-186">The configuration program does not disable the local Windows group option when the server is a domain controller.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-187">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-187">Resolution</span></span>  
 <span data-ttu-id="3d657-188">構成中に作成されるホストに対してはドメイン グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d657-188">Specify domain groups for the hosts that are created during configuration.</span></span>  
  
#### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a><span data-ttu-id="3d657-189">SQL サーバーの名前が変更されていると構成プログラムが SQL Server 分析データベースの作成に失敗する</span><span class="sxs-lookup"><span data-stu-id="3d657-189">Configuration fails to create SQL Server Analysis database if the SQL server has been renamed</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-190">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-190">Problem</span></span>  
 <span data-ttu-id="3d657-191">SQL Server 分析サーバーをインストールしたコンピューターの名前を変更した場合、新しい SQL Server 分析データベースを作成しようとすると構成プログラムが失敗して、次のようなエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d657-191">If you have renamed the computer on which you installed SQL Server Analysis Server, the configuration program fails when it tries to create the new SQL Server Analysis database and an error similar to the following is generated:</span></span>  
  
 <span data-ttu-id="3d657-192">リポジトリに接続できません。</span><span class="sxs-lookup"><span data-stu-id="3d657-192">Cannot connect to the repository.</span></span>  
  
 <span data-ttu-id="3d657-193">分析サーバー:\<マシン名\></span><span class="sxs-lookup"><span data-stu-id="3d657-193">Analysis server: \<machine name\></span></span>  
  
 <span data-ttu-id="3d657-194">エラー:</span><span class="sxs-lookup"><span data-stu-id="3d657-194">Error:</span></span>  
  
 <span data-ttu-id="3d657-195">'\\\\< マシン名\>\MsOLAPRepository$\msmdrep.mdb' は有効なパスではありません。</span><span class="sxs-lookup"><span data-stu-id="3d657-195">'\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.</span></span>  
  
 <span data-ttu-id="3d657-196">パス名のスペルが正しいこと、および</span><span class="sxs-lookup"><span data-stu-id="3d657-196">Make sure that you correctly spell the path name and that you are</span></span>  
  
 <span data-ttu-id="3d657-197">ファイルが存在するサーバーに接続していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d657-197">connected to the server on which the file resides.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-198">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-198">Cause</span></span>  
 <span data-ttu-id="3d657-199">SQL Server 分析サーバーをインストールしたコンピューターの新しい名前を構成プログラムが特定できません。</span><span class="sxs-lookup"><span data-stu-id="3d657-199">The configuration program is unable to determine the new name of the computer on which you installed SQL Server Analysis Server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-200">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-200">Resolution</span></span>  
 <span data-ttu-id="3d657-201">以下の手順を手動で実行し、分析サーバーを新しいコンピューター名で更新します。</span><span class="sxs-lookup"><span data-stu-id="3d657-201">Perform the following manual steps to update Analysis Server with the new computer name:</span></span>  
  
1.  <span data-ttu-id="3d657-202">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server**、 をポイント**Analysis Services**をクリックして**分析マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="3d657-202">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Analysis Services**, and then click **Analysis Manager**.</span></span>  
  
2.  <span data-ttu-id="3d657-203">**分析マネージャー**ナビゲーション ウィンドウで、ダブルクリックして、**分析サーバー**ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="3d657-203">In the **Analysis Manager** navigation panel, double-click the **Analysis Servers** node to expand it.</span></span>  
  
3.  <span data-ttu-id="3d657-204">リポジトリ接続文字列を編集して、選択すると、サーバーを右クリックして**リポジトリ接続文字列の編集**します。</span><span class="sxs-lookup"><span data-stu-id="3d657-204">Right-click the server with the repository connection string you want to edit, and then select **Edit Repository Connection String**.</span></span>  
  
4.  <span data-ttu-id="3d657-205">**リポジトリ接続文字列の編集** ダイアログ ボックスでこの文字列内のサーバー名を確認しが正しくない場合、新しいコンピューター名を更新します。</span><span class="sxs-lookup"><span data-stu-id="3d657-205">In the **Edit Repository Connection String** dialog box, verify the server name in this string and update it to the new computer name if it is incorrect.</span></span>  
  
5.  <span data-ttu-id="3d657-206">次の場所に移動します: \<*インストール ディレクトリ*\>\Program Files\Microsoft Analysis services \bin です。</span><span class="sxs-lookup"><span data-stu-id="3d657-206">Navigate to the following location: \<*installation directory*\>\Program Files\Microsoft Analysis Services\Bin.</span></span>  
  
6.  <span data-ttu-id="3d657-207">右クリックし、 **Bin**フォルダー、およびクリック**共有とセキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="3d657-207">Right-click the **Bin** folder, and then click **Sharing and Security**.</span></span> <span data-ttu-id="3d657-208">**Bin のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d657-208">The **Bin Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="3d657-209">**Bin のプロパティ**ダイアログ ボックスで、をクリックして、**共有** タブに、すべてのオンライン分析処理 (OLAP) 管理者が完全なアクセス許可をこのフォルダーにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d657-209">In the **Bin Properties** dialog box, click the **Sharing** tab to verify that all Online Analytical Processing (OLAP) administrators have full permissions to this folder.</span></span>  
  
#### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a><span data-ttu-id="3d657-210">Visual Studio からアセンブリを再展開すると構成データベースからアイテムが消える</span><span class="sxs-lookup"><span data-stu-id="3d657-210">Artifacts Disappear from Configuration Database on Redeployment of Assemblies from Visual Studio</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-211">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-211">Problem</span></span>  
 <span data-ttu-id="3d657-212">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをプロジェクト レベルで再展開すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MMC を更新したときに、再展開したプロジェクトを参照しているプロジェクトに含まれているすべてのアイテムが消えたように見えます。</span><span class="sxs-lookup"><span data-stu-id="3d657-212">When a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project is redeployed at the project level within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], all artifacts contained within the project that reference the project being redeployed will appear to vanish when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MMC is refreshed.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-213">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-213">Cause</span></span>  
 <span data-ttu-id="3d657-214">この問題の原因を示すために、ユーザーが Maps プロジェクトを再展開しようとしているサンプル BizTalk Server ソリューションに基づく例について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="3d657-214">To illustrate the cause of this problem, consider the following example based on a sample BizTalk Server solution where a user wants to redeploy the Maps project.</span></span> <span data-ttu-id="3d657-215">プロジェクトをコンパイルすると個々のアセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d657-215">Note that compiling projects yields individual assemblies.</span></span> <span data-ttu-id="3d657-216">次の図は、ユーザーが再展開を行う前のソリューションの状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d657-216">The following figure indicates the state of the solution before the user does a redeployment.</span></span> <span data-ttu-id="3d657-217">アイテム間の関係は次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="3d657-217">The relationships among the artifacts are as follows:</span></span>  
  
- <span data-ttu-id="3d657-218">Orch1、Orch2、Maps、Pipelines、および Schemas はプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3d657-218">Orch1, Orch2, Maps, Pipelines, and Schemas are projects.</span></span>  
  
- <span data-ttu-id="3d657-219">Orch1 は Maps を参照し、Maps は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="3d657-219">Orch1 references Maps, which in turn references Schemas.</span></span>  
  
- <span data-ttu-id="3d657-220">Orch2 は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="3d657-220">Orch2 references Schemas.</span></span>  
  
- <span data-ttu-id="3d657-221">Pipelines は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="3d657-221">Pipelines references Schemas.</span></span>  
  
  <span data-ttu-id="3d657-222">![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")</span><span class="sxs-lookup"><span data-stu-id="3d657-222">![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")</span></span>  
  
  <span data-ttu-id="3d657-223">ユーザーが Visual Studio の既定のプロジェクト設定を使用して Maps プロジェクトを再展開すると、次の図のように、Orch1、Orch2、および Pipeline の各アイテムが消えてしまいます。</span><span class="sxs-lookup"><span data-stu-id="3d657-223">If the user redeploys the Maps project using the default Visual Studio project settings, the Orch1, Orch2, and Pipeline artifacts vanish, as shown in the following figure.</span></span>  
  
  <span data-ttu-id="3d657-224">![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")</span><span class="sxs-lookup"><span data-stu-id="3d657-224">![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")</span></span>  
  
  <span data-ttu-id="3d657-225">Maps の再展開は、現在展開されている Maps.dll アセンブリの展開を解除して、新しい Maps.dll ファイルを展開する、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="3d657-225">Redeploying Maps is a two-step process of undeploying the currently deployed Maps.dll assembly, and then deploying the new Maps.dll file.</span></span> <span data-ttu-id="3d657-226">Visual Studio は、再デプロイ プロセスの一環として自動的に次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d657-226">Visual Studio performs these steps automatically as part of the redeployment process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d657-227">前の文は厳密には正しくありません。というのも、これらの手順は Visual Studio で常に行われるものなので、正しく行われているかどうかを意識することはありません。</span><span class="sxs-lookup"><span data-stu-id="3d657-227">The preceding sentence is not strictly correct because these are steps that Visual Studio always does so there is no notion of it being the proper way.</span></span>  
  
 <span data-ttu-id="3d657-228">ここで重要な点は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] が BizTalk Server アセンブリの展開を解除するためには、そのアセンブリに依存しているすべての (展開フラグが設定されている) アセンブリの展開を解除しなければならないということです。</span><span class="sxs-lookup"><span data-stu-id="3d657-228">The key point is that in order to undeploy a BizTalk Server assembly, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] has to undeploy all assemblies that are dependent upon that assembly that have the deploy flag set.</span></span> <span data-ttu-id="3d657-229">この例で言うと、再展開の最初の展開解除の手順を実行するには、BizTalk Server が Orch1.dll (Maps.dll に依存している) の展開を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d657-229">In our example, to perform the first undeployment step of the redeployment, BizTalk Server needs to undeploy Orch1.dll (which depends on Maps.dll).</span></span> <span data-ttu-id="3d657-230">Maps.dll の展開を解除する際、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] は Schemas.dll の展開も解除します (展開フラグが設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="3d657-230">During the undeployment of Maps.dll, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] also undeploys Schemas.dll (assuming it has the deploy flag set).</span></span> <span data-ttu-id="3d657-231">Schemas.dll の展開を解除するには、Orch2.dll と Pipelines.dll (いずれも Schemas.dll に依存している) の展開を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d657-231">In order to undeploy Schemas.dll, Visual Studio needs to undeploy Orch2.dll and Pipelines.dll (both of which depend on Schemas.dll).</span></span>  
  
 <span data-ttu-id="3d657-232">問題の存在を[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Maps.dll とそれが依存するアセンブリのみを再デプロイ: この場合は Schemas.dll します。</span><span class="sxs-lookup"><span data-stu-id="3d657-232">A problem exists in that [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] redeploys only Maps.dll and the assemblies that it depends upon: in this case, Schemas.dll.</span></span> <span data-ttu-id="3d657-233">そのため、ユーザーが BizTalk Server MMC を更新すると、Orch1、Orch2、および Pipeline の各アセンブリが消えたように見えますが、Maps.dll と Schemas.dll は引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d657-233">So when the user refreshes the BizTalk Server MMC, the Orch1, Orch2, and Pipeline assemblies seem to have vanished, but Maps.dll and Schemas.dll are still visible.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-234">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-234">Resolution</span></span>  
 <span data-ttu-id="3d657-235">メイン プロジェクト (他のプロジェクトを参照しているプロジェクト) に対して次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d657-235">For the main project (that references other projects) do the following:</span></span>  
  
1.  <span data-ttu-id="3d657-236">ソリューション エクスプローラーで、ソリューション ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="3d657-236">In Solution Explorer, right-click the solution node.</span></span>  
  
2.  <span data-ttu-id="3d657-237">クリックして**プロパティ**を開く、**ソリューション プロパティ ページ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3d657-237">Click **Properties** to open the **Solution Property Pages** dialog box.</span></span>  
  
3.  <span data-ttu-id="3d657-238">をクリックして**構成プロパティ**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="3d657-238">Click **Configuration Properties**, and then click **Configuration**.</span></span>  
  
4.  <span data-ttu-id="3d657-239">クリア、**デプロイ**参照先のプロジェクトのチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="3d657-239">Clear the **Deploy** check box for the referenced project.</span></span>  
  
5.  <span data-ttu-id="3d657-240">ソリューション エクスプローラーで、新しいソリューション レベルの展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d657-240">In Solution Explorer, execute a new solution-level deployment.</span></span> <span data-ttu-id="3d657-241">これを行うには、ソリューション ノードを右クリックし をクリックし、**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="3d657-241">To do this, right-click the solution node and then click **Deploy Solution**.</span></span>  
  
#### <a name="supported-virtual-directory-types"></a><span data-ttu-id="3d657-242">サポートされている仮想ディレクトリのタイプ</span><span class="sxs-lookup"><span data-stu-id="3d657-242">Supported Virtual Directory Types</span></span>  
 <span data-ttu-id="3d657-243">関連付けられている仮想ディレクトリが型の場合にのみ、エクスポート操作は成功を MSI のエクスポートを実行しようと、オーケストレーションから Web サービスを参照するときに**IIsWebVirtualDir**または**IIsWebDirectory**.</span><span class="sxs-lookup"><span data-stu-id="3d657-243">When referencing Web services from an orchestration and attempting to do an MSI export, the export operation will succeed only if the associated virtual directories are of type **IIsWebVirtualDir** or **IIsWebDirectory**.</span></span> <span data-ttu-id="3d657-244">**IIsWebVirtualDir**と**IIsWebDirectory**は IIS メタベースに表示されるノードの種類。</span><span class="sxs-lookup"><span data-stu-id="3d657-244">**IIsWebVirtualDir** and **IIsWebDirectory** are the node types that appear in the IIS metabase.</span></span> <span data-ttu-id="3d657-245">**IIsWebVirtualDir**の仮想ディレクトリ、**パス**絶対ファイル フォルダーを指すプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d657-245">**IIsWebVirtualDir** is a virtual directory with a **Path** property that points to an absolute file folder.</span></span> <span data-ttu-id="3d657-246">**IIsWebDirectory**仮想ディレクトリでは、**パス**プロパティ別のサブフォルダーでは通常、相対ファイル フォルダーを参照および**IIsWebVirtualDir**または**IIsWebDirectory**ノード。</span><span class="sxs-lookup"><span data-stu-id="3d657-246">**IIsWebDirectory** is a virtual directory without a **Path** property and thus refers to a relative file folder, typically a subfolder of another **IIsWebVirtualDir** or **IIsWebDirectory** node.</span></span> <span data-ttu-id="3d657-247">メタベース階層でフォルダーを表すものとしてはこの 2 つのタイプが一般的です。</span><span class="sxs-lookup"><span data-stu-id="3d657-247">These two types are the ones typically seen in the metabase hierarchy to describe folders.</span></span>  
  
 <span data-ttu-id="3d657-248">型の仮想ディレクトリ**IIsConfigObject**はサポートされていませんし、この場合、MSI のエクスポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d657-248">Virtual directories of type **IIsConfigObject** are not supported and the MSI export will fail in this case.</span></span> <span data-ttu-id="3d657-249">**IIsConfigObject**が、予期しないメタベース ノード タイプは BizTalk Server が正しく処理されないか、有効なノード型か、正しく作成されていない (およびしたがって無効な) メタベース エントリを示す値。</span><span class="sxs-lookup"><span data-stu-id="3d657-249">**IIsConfigObject** is an unexpected metabase node type that is either a valid node type that BizTalk Server is not handling properly or an indication of an improperly created (and thus invalid) metabase entry.</span></span> <span data-ttu-id="3d657-250">このような状況では、BizTalk Server によって次のようエラー メッセージが表示されます: 予期しないディレクトリ エントリ"IIS://LM/W3SVC/1/ROOT/BadVdir/"種類 IIsConfigObject します。</span><span class="sxs-lookup"><span data-stu-id="3d657-250">In this situation BizTalk Server will display an error message something like the following: Unexpected directory entry " IIS://LM/W3SVC/1/ROOT/BadVdir/" of type IIsConfigObject.</span></span>  
  
#### <a name="unable-to-view-group-information-after-removing-stale-logons"></a><span data-ttu-id="3d657-251">古いログオンを削除するとグループ情報を表示できなくなる</span><span class="sxs-lookup"><span data-stu-id="3d657-251">Unable to view Group information after removing stale logons</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3d657-252">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-252">Problem</span></span>  
 <span data-ttu-id="3d657-253">構成中に古いログオンを見つけて削除すると、グループ情報を表示できなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d657-253">If, during configuration, you encounter and delete stale logons, you may not be able to view Group information.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3d657-254">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-254">Cause</span></span>  
 <span data-ttu-id="3d657-255">これは既知の構成の問題です。</span><span class="sxs-lookup"><span data-stu-id="3d657-255">This is a known configuration issue.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3d657-256">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-256">Resolution</span></span>  
 <span data-ttu-id="3d657-257">Host Windows グループのログオンを削除して再構成すると解決する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d657-257">It may help to delete the Host Windows group logons and then reconfigure.</span></span> <span data-ttu-id="3d657-258">それでもグループ情報を表示できない場合は、マイクロソフト製品サポートにご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="3d657-258">If the Group information is still not available, contact Microsoft Product Support.</span></span>  
  
##### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a><span data-ttu-id="3d657-259">BizTalk Server のインストール後にコンピューター名を変更できない</span><span class="sxs-lookup"><span data-stu-id="3d657-259">Cannot change computer name after BizTalk Server is installed</span></span>  
  
###### <a name="problem"></a><span data-ttu-id="3d657-260">問題</span><span class="sxs-lookup"><span data-stu-id="3d657-260">Problem</span></span>  
 <span data-ttu-id="3d657-261">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターのコンピューター名を変更し、コンピューターを再起動 (リブート) すると、エラー メッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d657-261">When you change the computer name on a computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and you restart (reboot) the computer, error messages may occur.</span></span>  
  
###### <a name="cause"></a><span data-ttu-id="3d657-262">原因</span><span class="sxs-lookup"><span data-stu-id="3d657-262">Cause</span></span>  
 <span data-ttu-id="3d657-263">SQL Server はコンピューター名の変更をサポートしていないため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールおよび構成された後のコンピューター名の変更はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="3d657-263">SQL Server does not support changing the computer name, so [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not support changing the computer name once [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed and configured.</span></span>  
  
###### <a name="resolution"></a><span data-ttu-id="3d657-264">解決策</span><span class="sxs-lookup"><span data-stu-id="3d657-264">Resolution</span></span>  
 <span data-ttu-id="3d657-265">BizTalk Server のインストール後はコンピューター名を変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3d657-265">We recommend that you do not change computer names after you install BizTalk Server.</span></span>
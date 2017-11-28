---
title: "Oracle E-business Suite アダプターでの運用上の問題のトラブルシューティング |Microsoft ドキュメント"
description: "一般的な問題と Oracle EBS アダプターの BizTalk アダプター パック (BAP) の解決策"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92f888c185a7c7bea800986615da04ce57c80db0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="98f50-103">Oracle E-business Suite アダプターでの運用上の問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="98f50-103">Troubleshoot Operational Issues with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="98f50-104">このセクションで説明を使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="98f50-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="98f50-105">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="98f50-105">Enabling Tracing</span></span>  
 <span data-ttu-id="98f50-106">トレースのサポートの詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、[診断トレースとメッセージ ログを Oracle E-business Suite アダプターで](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="98f50-106">For more information about tracing support in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], [Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="98f50-107">既知の問題</span><span class="sxs-lookup"><span data-stu-id="98f50-107">Known Issues</span></span>  
 <span data-ttu-id="98f50-108">使用する場合に発生する可能性が最も一般的なエラーは、次のとおり、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、およびその考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="98f50-108">The following are the most common errors you might encounter when using the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <span data-ttu-id="98f50-109"><a name="BKMK_LoadBindings"></a>アダプターのバインドを読み込み中にエラー</span><span class="sxs-lookup"><span data-stu-id="98f50-109"><a name="BKMK_LoadBindings"></a> Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="98f50-110">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-110">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-111">起動しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="98f50-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="98f50-112">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-112">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-113">起動しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="98f50-113">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="98f50-114">一方、アダプターのバインドは、エンタープライズ アプリケーション用の特定のクライアント ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="98f50-114">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="98f50-115">次の理由の一方または両方について、この問題に直面する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98f50-115">You might face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="98f50-116">必要な LOB クライアント ソフトウェアは、アダプターがインストールされているコンピューターにインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="98f50-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="98f50-117">含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了したとき、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="98f50-117">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="98f50-118">ただし、1 つだけのエンタープライズ アプリケーションに LOB クライアント ライブラリをインストールする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98f50-118">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="98f50-119">その結果、GUI は、他のアダプターのバインドを読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="98f50-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="98f50-120">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-120">**Resolution**</span></span>  
  
-   <span data-ttu-id="98f50-121">必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認してください、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="98f50-121">Make sure that the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="98f50-122">サポートされているクライアントのバージョンについてで利用可能なインストール ガイドを参照してください。\<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="98f50-122">For information about the supported client versions, see the installation guide available at \<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="98f50-123">必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="98f50-123">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <span data-ttu-id="98f50-124"><a name="BKMK_Display"></a>Oracle E-business Suite アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="98f50-124"><a name="BKMK_Display"></a> The Oracle E-Business Suite adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="98f50-125">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-125">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-126">付属するアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]アダプターの一覧に表示されない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="98f50-126">Unlike the earlier version of the adapters shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="98f50-127">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-127">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-128">最新[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]WCF カスタム バインドがします。</span><span class="sxs-lookup"><span data-stu-id="98f50-128">The latest [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="98f50-129">そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="98f50-129">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
 <span data-ttu-id="98f50-130">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-130">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-131">明示的に追加することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="98f50-131">You can explicitly add the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the Oracle E-Business Suite adapter to BizTalk Server Administration console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <span data-ttu-id="98f50-132"><a name="BKMK_MissingAction"></a>Oracle E-business Suite で操作の実行中のエラー</span><span class="sxs-lookup"><span data-stu-id="98f50-132"><a name="BKMK_MissingAction"></a> Error while performing operations on the Oracle E-Business Suite</span></span>  
 <span data-ttu-id="98f50-133">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-133">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-134">Oracle E-business Suite を使用して、すべての操作を実行するときに、アダプターは、次のエラーを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="98f50-134">The adapter gives the following error when performing any operation on the Oracle E-Business Suite using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="98f50-135">**の[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="98f50-135">**For [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="98f50-136">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-136">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-137">メッセージの WCF アクションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="98f50-137">The WCF action for the message is not specified.</span></span> <span data-ttu-id="98f50-138">WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="98f50-138">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="98f50-139">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-139">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-140">送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="98f50-140">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="98f50-141">手順については、次を参照してください。 [Oracle E-business Suite の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="98f50-141">For instructions, see [Configure the SOAP action for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md).</span></span> <span data-ttu-id="98f50-142">参照してください[メッセージと Oracle EBS アダプターのメッセージ スキーマを](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)各操作のアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="98f50-142">See [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md) to see a list of actions for each operation.</span></span>  
  
###  <span data-ttu-id="98f50-143"><a name="BKMK_WrongClient"></a>要求メッセージが受信場所にドロップされたときに、Oracle クライアントのバージョンを誤ったため BizTalk プロセスがクラッシュ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98f50-143"><a name="BKMK_WrongClient"></a> BizTalk process might crash due to an incorrect Oracle client version when a request message is dropped at the receive location</span></span>  
 <span data-ttu-id="98f50-144">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-144">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-145">BizTalk オーケストレーションで定義されている受信場所で要求メッセージをドロップすると、オーケストレーションがメッセージを処理して、BizTalk ホスト (BTSNTSvc.exe) がクラッシュし、再起動します。</span><span class="sxs-lookup"><span data-stu-id="98f50-145">After a request message is dropped at a receive location defined in a BizTalk orchestration, the orchestration consumes the message and BizTalk host (BTSNTSvc.exe) crashes and restarts.</span></span>  
  
 <span data-ttu-id="98f50-146">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-146">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-147">Oracle クライアントをインストールすると、PATH 変数に最新のクライアント アセンブリへの参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="98f50-147">Installing the Oracle client adds the reference to the latest client assemblies in the PATH variable.</span></span> <span data-ttu-id="98f50-148">また、Oracle クライアント アセンブリの最新のインストールへの参照には、既存のクライアント アセンブリへの参照が前に付けます。</span><span class="sxs-lookup"><span data-stu-id="98f50-148">Also, the references to the most recent installation of the Oracle client assembly precede the reference to the existing client assemblies.</span></span> <span data-ttu-id="98f50-149">そのため、最新の Oracle クライアントのインストールがサポートされているクライアントのバージョンのでない場合 BizTalk ホストがクラッシュし、再起動します。</span><span class="sxs-lookup"><span data-stu-id="98f50-149">So, if the most recent Oracle client installation is not of a supported client version, BizTalk host crashes and then restarts.</span></span>  
  
 <span data-ttu-id="98f50-150">たとえば、パス変数は、次の参照をサポートされている Oracle クライアント 11.1.0.7 がコンピューターに既にインストールされてを想定します。</span><span class="sxs-lookup"><span data-stu-id="98f50-150">For example, assume that the supported Oracle client 11.1.0.7 is already installed on the computer and the PATH variable has the following reference:</span></span>  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 <span data-ttu-id="98f50-151">サポートされていない Oracle クライアント、たとえば 10.2.0.3 というが同じコンピューターにインストールされている場合、パス変数は、次の参照が得られます。</span><span class="sxs-lookup"><span data-stu-id="98f50-151">If an unsupported Oracle client, for example 10.2.0.3, is installed on the same computer, the PATH variable will have the following reference:</span></span>  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 <span data-ttu-id="98f50-152">サポートされていないクライアントのバージョンがサポートされているバージョンより前に参照されているため BizTalk ホストがクラッシュすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="98f50-152">Note that the unsupported client version is referenced before the supported version and hence BizTalk host crashes.</span></span> <span data-ttu-id="98f50-153">実行する 1 つ以上の BizTalk ホストがある場合は、アダプターをホストする 1 つがクラッシュします。</span><span class="sxs-lookup"><span data-stu-id="98f50-153">If there are more than one BizTalk hosts running, then the one hosting the adapter crashes.</span></span>  
  
 <span data-ttu-id="98f50-154">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-154">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-155">1 つ以上の Oracle クライアントが同じコンピューターにインストールされている場合は、PATH 変数に、他の Oracle クライアント バージョンの前に、サポートされている Oracle クライアントのバージョンが参照されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="98f50-155">If more than one Oracle client is installed on the same computer, make sure the supported Oracle client version is referenced before the other Oracle client versions in the PATH variable.</span></span> <span data-ttu-id="98f50-156">たとえば、サポートされている Oracle クライアントのバージョンが 11.1.0.7 の場合は、PATH 変数で参照する必要がありますようになります。</span><span class="sxs-lookup"><span data-stu-id="98f50-156">For example, if the supported Oracle client version is 11.1.0.7, the reference in the PATH variable must look like:</span></span>  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <span data-ttu-id="98f50-157"><a name="BKMK_Overflow"></a>操作の実行にオーバーフロー例外をスロー アダプター</span><span class="sxs-lookup"><span data-stu-id="98f50-157"><a name="BKMK_Overflow"></a> Adapter might throw an overflow exception on executing an operation</span></span>  
 <span data-ttu-id="98f50-158">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-158">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-159">データセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型を含む操作を実行しようとする場合は、アダプターを使用して、アダプターではオーバーフロー例外がスロー可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98f50-159">Using the adapter, if you try to perform an operation containing Oracle numeric data types inside DataSets or weakly-typed REF CURSORS, the adapter might throw an overflow exception.</span></span>  
  
 <span data-ttu-id="98f50-160">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-160">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-161">これは、データセットまたはそれぞれの .NET 型に収まらない弱い型指定の REF CURSOR の内部 Oracle 数値データ型の大きな値を指定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="98f50-161">This happens if you supply a large value for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS that cannot fit into the respective .NET type.</span></span>  
  
 <span data-ttu-id="98f50-162">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-162">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-163">データセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型の大きな値を渡す場合は、セーフである入力の値を設定して有効にする必要があります、 **EnableSafeTyping**にプロパティのバインド**true**.</span><span class="sxs-lookup"><span data-stu-id="98f50-163">If you want to pass large values for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS, you must enable safe typing by setting the value of the **EnableSafeTyping** binding property to **true**.</span></span> <span data-ttu-id="98f50-164">文字列としてデータセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型を公開するセーフである入力の有効化します。</span><span class="sxs-lookup"><span data-stu-id="98f50-164">Enabling safe typing exposes the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS as strings.</span></span>  
  
###  <span data-ttu-id="98f50-165"><a name="BKMK_Arithmetic"></a>ExecuteScalar 操作の実行に算術オーバーフロー例外をスロー アダプター</span><span class="sxs-lookup"><span data-stu-id="98f50-165"><a name="BKMK_Arithmetic"></a> Adapter might throw an arithmetic overflow exception on executing an ExecuteScalar operation</span></span>  
 <span data-ttu-id="98f50-166">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-166">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-167">大きな数を取得する ExecuteScalar 操作で SELECT ステートメントを実行しようとする場合は、アダプターを使用して、アダプターは、次の例外がスローされます"System.OverflowException: 算術演算でオーバーフローが発生しました。"。</span><span class="sxs-lookup"><span data-stu-id="98f50-167">Using the adapter, if you try to execute a SELECT statement in an ExecuteScalar operation that retrieves a large number, the adapter throws the following exception: “System.OverflowException: Arithmetic operation resulted in an overflow.”</span></span>  
  
 <span data-ttu-id="98f50-168">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-168">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-169">これは、ODP.NET で ExecuteScalar 操作の既知の制限により発生します。</span><span class="sxs-lookup"><span data-stu-id="98f50-169">This happens due to the known limitation of ExecuteScalar operation in ODP.NET.</span></span> <span data-ttu-id="98f50-170">ODP.NET が .NET 10 進数のデータ型へのデータに合わせてしようとし、結果が大きすぎる .NET 10 進数型に収まるように、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="98f50-170">ODP.NET tries to fit in the data into the .NET Decimal data type, and if the result is too large to fit in the .NET Decimal type, the exception is thrown.</span></span>  
  
 <span data-ttu-id="98f50-171">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-171">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-172">ExecuteScalar 操作で、SELECT ステートメントで TO_CHAR() を使用して、文字列として返されるデータを変換します。</span><span class="sxs-lookup"><span data-stu-id="98f50-172">Use TO_CHAR() in the SELECT statement in the ExecuteScalar operation to convert the returned data as string.</span></span>  
  
###  <span data-ttu-id="98f50-173"><a name="BKMK_AppContext"></a>アダプターのクライアントが操作の実行では、次の例外をスローします。"を取得できませんでしたユーザー id、責任の id、アプリケーション id。確認の正しい値が渡されたかどうか。"</span><span class="sxs-lookup"><span data-stu-id="98f50-173"><a name="BKMK_AppContext"></a> Adapter client might throw the following exception on executing an operation: “Could not retrieve user id, responsibility id, application id.  Check if correct values were passed in.”</span></span>  
 <span data-ttu-id="98f50-174">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-174">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-175">Oracle E-business Suite の成果物 (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセット) に対する操作を実行している場合、アダプターのクライアントはこの例外をスロー可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98f50-175">The adapter clients might throw this exception if you are performing operations on Oracle E-Business Suite artifacts (interface tables, interface views, concurrent programs, and request sets).</span></span>  
  
 <span data-ttu-id="98f50-176">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-176">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-177">これは、インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセットに対する操作の実行中に Oracle ユーザー名、パスワード、および責任の名前の組み合わせが正しくないを指定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="98f50-177">This happens if you supply an incorrect combination of Oracle user name, password, and responsibility name while performing operations on interface tables, interface views, concurrent programs, and request sets.</span></span> <span data-ttu-id="98f50-178">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]これらの成果物のアプリケーション コンテキストを設定するためにこれらの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="98f50-178">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] requires these values in order to set the application context for these artifacts.</span></span> <span data-ttu-id="98f50-179">アプリケーション コンテキストの設定に関する詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="98f50-179">For more information about setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
 <span data-ttu-id="98f50-180">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-180">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-181">正しい Oracle ユーザー名、パスワード、および Oracle E-business Suite の成果物のアプリケーション コンテキストを適切に設定する責任の組み合わせを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98f50-181">You must specify a correct combination of the Oracle user name, password, and responsibility to appropriately set application context for an Oracle E-Business Suite artifact.</span></span> <span data-ttu-id="98f50-182">Oracle ユーザー名とパスワードの値を指定するには、使用する必要があります、 **OracleUserName**と**OraclePassword**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="98f50-182">To specify values for Oracle user name and password, you must use the **OracleUserName** and **OraclePassword** binding properties.</span></span> <span data-ttu-id="98f50-183">Oracle 責任の値を指定するには、使用するか、 **OracleEBSResponsibilityName**プロパティまたはメッセージのコンテキスト プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="98f50-183">To specify value for the Oracle responsibility, you can either use the **OracleEBSResponsibilityName** binding property or message context property.</span></span>  
  
###  <span data-ttu-id="98f50-184"><a name="BKMK_RootNode"></a>RootNode TypeName BizTalk プロジェクト内のエラー</span><span class="sxs-lookup"><span data-stu-id="98f50-184"><a name="BKMK_RootNode"></a> Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="98f50-185">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-185">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-186">BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:</span><span class="sxs-lookup"><span data-stu-id="98f50-186">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="98f50-187">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-187">**Resolution**</span></span>  
  
1.  <span data-ttu-id="98f50-188">クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="98f50-188">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="98f50-189">**RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。</span><span class="sxs-lookup"><span data-stu-id="98f50-189">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <span data-ttu-id="98f50-190"><a name="BKMK_InvalidBinding"></a>Visual Studio でのアダプターの使用時の無効なバインドの警告</span><span class="sxs-lookup"><span data-stu-id="98f50-190"><a name="BKMK_InvalidBinding"></a> Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="98f50-191">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-191">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-192">アプリケーションを作成するアダプターを使用すると[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98f50-192">When you use the adapter to create an application in [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="98f50-193">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-193">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-194">この警告が表示されます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインド、`oracleEBSBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="98f50-194">This warning appears because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding, `oracleEBSBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="98f50-195">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-195">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-196">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="98f50-196">You can safely ignore this warning.</span></span>  
  
###  <span data-ttu-id="98f50-197"><a name="BKMK_Notify"></a>BizTalk Server が、同じアプリケーションで 1 つ以上の通知スキーマを使用して、同じホスト上の複数のアプリケーション間で通知スキーマを使用するか、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="98f50-197"><a name="BKMK_Notify"></a> BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="98f50-198">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-198">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-199">BizTalk Server は、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="98f50-199">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="98f50-200">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-200">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-201">これは、次のいずれかのため発生します。</span><span class="sxs-lookup"><span data-stu-id="98f50-201">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="98f50-202">1 つ以上を生成する、BizTalk Server プロジェクトでの通知スキーマを BizTalk Server アプリケーションに展開し、Oracle データベースから通知を受け取るアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="98f50-202">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the Oracle database.</span></span> <span data-ttu-id="98f50-203">競合が通知スキーマは、一般的なであるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。</span><span class="sxs-lookup"><span data-stu-id="98f50-203">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="98f50-204">複数のプロジェクトが発生した場合、BizTalk Server が配置されたプロジェクトの各プロジェクトの場合、同じホスト上の別の BizTalk Server アプリケーションの各通知スキーマを生成したし、し、実行、アプリケーションまたはアプリケーションからの通知を受信するにはOracle データベースです。</span><span class="sxs-lookup"><span data-stu-id="98f50-204">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the Oracle database.</span></span> <span data-ttu-id="98f50-205">スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるため競合があるさまざまな BizTalk Server アプリケーションおよびアセンブリの下でデプロイされる共通のスキーマ間でします。</span><span class="sxs-lookup"><span data-stu-id="98f50-205">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="98f50-206">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-206">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-207">BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="98f50-207">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="98f50-208">同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションからの通知スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="98f50-208">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <span data-ttu-id="98f50-209"><a name="BKMK_Timeout"></a>Visual Studio での Oracle E-business Suite 成果物の参照中にタイムアウト例外</span><span class="sxs-lookup"><span data-stu-id="98f50-209"><a name="BKMK_Timeout"></a> Timeout Exception while browsing Oracle E-Business Suite Artifacts in Visual Studio</span></span>  
 <span data-ttu-id="98f50-210">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-210">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-211">Oracle E-business Suite のアイテムの閲覧中に、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクトを使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]タイムアウト例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98f50-211">While browsing Oracle E-Business Suite artifacts in a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] project using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] you might encounter a timeout exception.</span></span>  
  
 <span data-ttu-id="98f50-212">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-212">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-213">これは、Oracle E-business Suite をホストしているサーバーが低速なサーバーがリモートの場所にある、または 検索するスキーマが成果物の数が多い場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98f50-213">This might happen if the server hosting the Oracle E-Business Suite is slow, server is located at a remote location, or the schema you are looking under has a large number of artifacts.</span></span>  
  
 <span data-ttu-id="98f50-214">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-214">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-215">値を大きくかを選択できます、 **SendTimeout**に検索式を入力、またはプロパティのバインド、**カテゴリで検索**を成果物の数を減らすためにテキスト ボックスをアダプター取得します。</span><span class="sxs-lookup"><span data-stu-id="98f50-215">You can either choose to increase the value of the **SendTimeout** binding property or provide a search expression in the **Search in category** text box to reduce the number of artifacts that the adapter retrieves.</span></span>  
  
 <span data-ttu-id="98f50-216">バインドのプロパティを指定する方法の詳細については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="98f50-216">For more information about specifying binding properties, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span> <span data-ttu-id="98f50-217">Oracle E-business Suite でアイテムを検索する方法に関する詳細については、次を参照してください。[参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="98f50-217">For more information about searching artifacts in Oracle E-Business Suite, see [Browse, search, and get metadata for Oracle E-Business Suite operations](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).</span></span>  
  
###  <span data-ttu-id="98f50-218"><a name="BKMK_MemUsage"></a>メモリ使用量とスレッド数の増加トランザクション受信操作で、アダプターを使用する場合</span><span class="sxs-lookup"><span data-stu-id="98f50-218"><a name="BKMK_MemUsage"></a> Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="98f50-219">**問題**</span><span class="sxs-lookup"><span data-stu-id="98f50-219">**Problem**</span></span>  
  
 <span data-ttu-id="98f50-220">ポーリングなどのトランザクション受信操作で**かどうかはデータをポーリングするテーブルで使用できる**アダプターがポーリングを継続しは、メモリ使用量とスレッド数の増加が発生する期間にわたっています。</span><span class="sxs-lookup"><span data-stu-id="98f50-220">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="98f50-221">**原因**</span><span class="sxs-lookup"><span data-stu-id="98f50-221">**Cause**</span></span>  
  
 <span data-ttu-id="98f50-222">**かどうかはデータをポーリングするテーブルで使用できる**の後にすべて受信タイムアウト サイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。</span><span class="sxs-lookup"><span data-stu-id="98f50-222">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="98f50-223">そのため、時間の期間にわたって、スレッドの数とメモリの使用量が増加します。</span><span class="sxs-lookup"><span data-stu-id="98f50-223">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="98f50-224">ただし、一部のデータをポーリングするテーブルには、同じスレッドが継続後続のすべてのポーリングを実行します。</span><span class="sxs-lookup"><span data-stu-id="98f50-224">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="98f50-225">**解決策**</span><span class="sxs-lookup"><span data-stu-id="98f50-225">**Resolution**</span></span>  
  
 <span data-ttu-id="98f50-226">設定を推奨、 **ReceiveTimeout**に最大の可能な値は 24.20:31:23.6470000 (24 日)、新しいスレッドが 24 日間にのみを生成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="98f50-226">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="98f50-227">これにより、メモリ使用量とスレッド数が大きくならないが多すぎるが早すぎます。</span><span class="sxs-lookup"><span data-stu-id="98f50-227">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
 <span data-ttu-id="98f50-228">詳細については、 **ReceiveTimeout**バインディング プロパティを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="98f50-228">For more information about the **ReceiveTimeout** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="98f50-229">バインドのプロパティを指定する方法の詳細については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="98f50-229">For instructions on specifying binding properties, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98f50-230">付いたアダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。</span><span class="sxs-lookup"><span data-stu-id="98f50-230">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f50-231">参照</span><span class="sxs-lookup"><span data-stu-id="98f50-231">See Also</span></span>  
[<span data-ttu-id="98f50-232">Oracle EBS アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="98f50-232">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
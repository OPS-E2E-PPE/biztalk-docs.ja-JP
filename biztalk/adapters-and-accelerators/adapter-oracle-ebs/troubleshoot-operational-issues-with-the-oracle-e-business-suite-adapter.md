---
title: Oracle E-business Suite アダプターを使用した運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的な問題と Oracle EBS アダプターの BizTalk アダプター パック (BAP) の解決策
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d119afaea2382e1ede6c780a40bbe2bf4329860f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989992"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="0bdac-103">Oracle E-business Suite アダプターを使用した運用上の問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-103">Troubleshoot Operational Issues with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="0bdac-104">このセクションを使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="0bdac-105">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-105">Enabling Tracing</span></span>  
 <span data-ttu-id="0bdac-106">トレースのサポートの詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、[診断トレースとメッセージ ログの Oracle E-business Suite アダプターで](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-106">For more information about tracing support in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], [Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="0bdac-107">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0bdac-107">Known Issues</span></span>  
 <span data-ttu-id="0bdac-108">使用する場合に発生する可能性が最も一般的なエラーを次に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]と共に、考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-108">The following are the most common errors you might encounter when using the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <a name="BKMK_LoadBindings"></a> <span data-ttu-id="0bdac-109">アダプターのバインドを読み込み中にエラー</span><span class="sxs-lookup"><span data-stu-id="0bdac-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="0bdac-110">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-110">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-111">開始しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0bdac-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="0bdac-112">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-112">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-113">開始しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0bdac-113">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="0bdac-114">さらに、アダプターのバインドは、エンタープライズ アプリケーションの特定のクライアント ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-114">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="0bdac-115">この問題は次の理由の両方またはいずれかに直面する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-115">You might face this issue for one or both of the following reasons:</span></span>  
  
- <span data-ttu-id="0bdac-116">アダプターがインストールされているコンピューターでは、必要な LOB クライアント ソフトウェアがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="0bdac-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
- <span data-ttu-id="0bdac-117">含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了した、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-117">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="0bdac-118">ただし、1 つだけのエンタープライズ アプリケーション用に LOB クライアント ライブラリをインストールする場合があります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-118">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="0bdac-119">その結果、GUI の他のアダプターのバインドの読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
  <span data-ttu-id="0bdac-120">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-120">**Resolution**</span></span>  
  
- <span data-ttu-id="0bdac-121">必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-121">Make sure that the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="0bdac-122">サポートされているクライアントのバージョンについてで使用可能なインストール ガイドを参照してください。\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-122">For information about the supported client versions, see the installation guide available at \<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
- <span data-ttu-id="0bdac-123">必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-123">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_Display"></a> <span data-ttu-id="0bdac-124">Oracle E-business Suite アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="0bdac-124">The Oracle E-Business Suite adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="0bdac-125">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-125">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-126">付属のアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]でアダプターの一覧が表示されない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0bdac-126">Unlike the earlier version of the adapters shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="0bdac-127">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-127">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-128">最新[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]WCF カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-128">The latest [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="0bdac-129">そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-129">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
 <span data-ttu-id="0bdac-130">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-130">**Resolution**</span></span>  
  
 <span data-ttu-id="0bdac-131">明示的に追加することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-131">You can explicitly add the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the Oracle E-Business Suite adapter to BizTalk Server Administration console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_MissingAction"></a> <span data-ttu-id="0bdac-132">Oracle E-business suite 操作の実行中のエラー</span><span class="sxs-lookup"><span data-stu-id="0bdac-132">Error while performing operations on the Oracle E-Business Suite</span></span>  
 <span data-ttu-id="0bdac-133">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-133">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-134">Oracle E-business Suite を使用して、操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-134">The adapter gives the following error when performing any operation on the Oracle E-Business Suite using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="0bdac-135">**BizTalk Server 用**</span><span class="sxs-lookup"><span data-stu-id="0bdac-135">**For BizTalk Server**</span></span>  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  <span data-ttu-id="0bdac-136">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-136">**Cause**</span></span>  
  
  <span data-ttu-id="0bdac-137">メッセージの WCF アクションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="0bdac-137">The WCF action for the message is not specified.</span></span> <span data-ttu-id="0bdac-138">WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="0bdac-138">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
  <span data-ttu-id="0bdac-139">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-139">**Resolution**</span></span>  
  
  <span data-ttu-id="0bdac-140">送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-140">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="0bdac-141">手順については、[for Oracle E-business Suite の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bdac-141">For instructions, see [Configure the SOAP action for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md).</span></span> <span data-ttu-id="0bdac-142">参照してください[メッセージと Oracle EBS アダプターのメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)各操作のアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-142">See [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_WrongClient"></a> <span data-ttu-id="0bdac-143">要求メッセージが受信場所で削除されるとき、BizTalk プロセスが不適切な Oracle クライアントのバージョンのためクラッシュ</span><span class="sxs-lookup"><span data-stu-id="0bdac-143">BizTalk process might crash due to an incorrect Oracle client version when a request message is dropped at the receive location</span></span>  
 <span data-ttu-id="0bdac-144">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-144">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-145">要求メッセージを削除した後には、BizTalk オーケストレーションで定義されている受信場所で、オーケストレーションはメッセージを使用し、BizTalk ホスト (BTSNTSvc.exe) がクラッシュしたし、再起動します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-145">After a request message is dropped at a receive location defined in a BizTalk orchestration, the orchestration consumes the message and BizTalk host (BTSNTSvc.exe) crashes and restarts.</span></span>  
  
 <span data-ttu-id="0bdac-146">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-146">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-147">Oracle クライアントをインストールすると、PATH 変数に最新のクライアント アセンブリへの参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="0bdac-147">Installing the Oracle client adds the reference to the latest client assemblies in the PATH variable.</span></span> <span data-ttu-id="0bdac-148">また、Oracle クライアント アセンブリの最新のインストールへの参照の前に、既存のクライアント アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="0bdac-148">Also, the references to the most recent installation of the Oracle client assembly precede the reference to the existing client assemblies.</span></span> <span data-ttu-id="0bdac-149">そのため、サポートされているクライアントのバージョンの最新の Oracle クライアントのインストールでない場合、BizTalk ホストがクラッシュし、し再起動します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-149">So, if the most recent Oracle client installation is not of a supported client version, BizTalk host crashes and then restarts.</span></span>  
  
 <span data-ttu-id="0bdac-150">たとえば、11.1.0.7、サポートされている Oracle クライアントがコンピューターに既にインストールされていること、および PATH 変数は、次の参照。</span><span class="sxs-lookup"><span data-stu-id="0bdac-150">For example, assume that the supported Oracle client 11.1.0.7 is already installed on the computer and the PATH variable has the following reference:</span></span>  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 <span data-ttu-id="0bdac-151">場合は、次のようにサポートされていない Oracle クライアント、10.2.0.3 という例は、同じコンピューターにインストールされて、PATH 変数は、次の参照になります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-151">If an unsupported Oracle client, for example 10.2.0.3, is installed on the same computer, the PATH variable will have the following reference:</span></span>  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 <span data-ttu-id="0bdac-152">サポートされていないクライアントのバージョンがサポートされているバージョンの前に参照されていることと、BizTalk ホストがクラッシュするために注意してください。</span><span class="sxs-lookup"><span data-stu-id="0bdac-152">Note that the unsupported client version is referenced before the supported version and hence BizTalk host crashes.</span></span> <span data-ttu-id="0bdac-153">実行している 1 つ以上の BizTalk ホストがある場合は、アダプターをホストする 1 つがクラッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-153">If there are more than one BizTalk hosts running, then the one hosting the adapter crashes.</span></span>  
  
 <span data-ttu-id="0bdac-154">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-154">**Resolution**</span></span>  
  
 <span data-ttu-id="0bdac-155">1 つ以上の Oracle クライアントが同じコンピューターにインストールされているの場合は、PATH 変数に、他の Oracle クライアント バージョンの前にサポートされている Oracle クライアントのバージョンが参照されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0bdac-155">If more than one Oracle client is installed on the same computer, make sure the supported Oracle client version is referenced before the other Oracle client versions in the PATH variable.</span></span> <span data-ttu-id="0bdac-156">たとえば、サポートされている Oracle クライアントのバージョンが 11.1.0.7 の場合は、PATH 変数に参照する必要がありますようになります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-156">For example, if the supported Oracle client version is 11.1.0.7, the reference in the PATH variable must look like:</span></span>  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <a name="BKMK_Overflow"></a> <span data-ttu-id="0bdac-157">アダプター操作の実行にオーバーフロー例外をスロー</span><span class="sxs-lookup"><span data-stu-id="0bdac-157">Adapter might throw an overflow exception on executing an operation</span></span>  
 <span data-ttu-id="0bdac-158">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-158">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-159">データセットまたは厳密に型指定の REF CURSOR の内部で Oracle の数値データ型を格納している操作を実行しようとする場合、アダプターを使用して、アダプターは、オーバーフロー例外をスロー可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-159">Using the adapter, if you try to perform an operation containing Oracle numeric data types inside DataSets or weakly-typed REF CURSORS, the adapter might throw an overflow exception.</span></span>  
  
 <span data-ttu-id="0bdac-160">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-160">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-161">これは、大規模なデータセットや、それぞれの .NET 型に収まらない厳密に型指定の REF CURSOR の内部で Oracle の数値データ型の値を指定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-161">This happens if you supply a large value for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS that cannot fit into the respective .NET type.</span></span>  
  
 <span data-ttu-id="0bdac-162">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-162">**Resolution**</span></span>  
  
 <span data-ttu-id="0bdac-163">データセットまたは厳密に型指定の REF CURSOR、Oracle の数値データ型の大きな値を渡す場合は、安全な」と入力の値を設定して有効にする必要があります、 **EnableSafeTyping**プロパティをバインド**true**.</span><span class="sxs-lookup"><span data-stu-id="0bdac-163">If you want to pass large values for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS, you must enable safe typing by setting the value of the **EnableSafeTyping** binding property to **true**.</span></span> <span data-ttu-id="0bdac-164">安全な入力を有効にすると、データセットまたは厳密に型指定の REF CURSOR、Oracle の数値データ型が文字列として公開します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-164">Enabling safe typing exposes the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS as strings.</span></span>  
  
###  <a name="BKMK_Arithmetic"></a> <span data-ttu-id="0bdac-165">アダプター、ExecuteScalar 操作の実行に算術オーバーフロー例外をスロー</span><span class="sxs-lookup"><span data-stu-id="0bdac-165">Adapter might throw an arithmetic overflow exception on executing an ExecuteScalar operation</span></span>  
 <span data-ttu-id="0bdac-166">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-166">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-167">大きな数を取得、ExecuteScalar 操作で SELECT ステートメントを実行しようとする場合、アダプターを使用して、アダプターは、次の例外がスローされます"System.overflowexception:: 算術演算結果オーバーフローが発生します。"。</span><span class="sxs-lookup"><span data-stu-id="0bdac-167">Using the adapter, if you try to execute a SELECT statement in an ExecuteScalar operation that retrieves a large number, the adapter throws the following exception: “System.OverflowException: Arithmetic operation resulted in an overflow.”</span></span>  
  
 <span data-ttu-id="0bdac-168">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-168">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-169">これは、ODP.NET ExecuteScalar 操作の既知の制限のため発生します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-169">This happens due to the known limitation of ExecuteScalar operation in ODP.NET.</span></span> <span data-ttu-id="0bdac-170">ODP.NET が .NET の 10 進数のデータ型へのデータに合わせてしようとし、結果が大きすぎて、.NET の Decimal 型に収まるように、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0bdac-170">ODP.NET tries to fit in the data into the .NET Decimal data type, and if the result is too large to fit in the .NET Decimal type, the exception is thrown.</span></span>  
  
 <span data-ttu-id="0bdac-171">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-171">**Resolution**</span></span>  
  
 <span data-ttu-id="0bdac-172">ExecuteScalar 操作で SELECT ステートメントで TO_CHAR() を使用して、文字列として返されるデータを変換します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-172">Use TO_CHAR() in the SELECT statement in the ExecuteScalar operation to convert the returned data as string.</span></span>  
  
###  <a name="BKMK_AppContext"></a> <span data-ttu-id="0bdac-173">アダプター クライアントの操作の実行では、次の例外がスロー:"を取得できませんでしたユーザー id、責任の id、アプリケーション id。確認の正しい値が渡されたかどうか。"</span><span class="sxs-lookup"><span data-stu-id="0bdac-173">Adapter client might throw the following exception on executing an operation: “Could not retrieve user id, responsibility id, application id.  Check if correct values were passed in.”</span></span>  
 <span data-ttu-id="0bdac-174">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-174">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-175">アダプターのクライアントは、Oracle E-business Suite アーティファクト (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセット) に対する操作を実行している場合、この例外をスロー可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-175">The adapter clients might throw this exception if you are performing operations on Oracle E-Business Suite artifacts (interface tables, interface views, concurrent programs, and request sets).</span></span>  
  
 <span data-ttu-id="0bdac-176">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-176">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-177">これは、インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求セットに対する操作の実行中に Oracle ユーザー名、パスワード、および責任の名前の組み合わせが正しくないを指定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-177">This happens if you supply an incorrect combination of Oracle user name, password, and responsibility name while performing operations on interface tables, interface views, concurrent programs, and request sets.</span></span> <span data-ttu-id="0bdac-178">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]これらの成果物のアプリケーションのコンテキストを設定するにはこれらの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="0bdac-178">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] requires these values in order to set the application context for these artifacts.</span></span> <span data-ttu-id="0bdac-179">アプリケーション コンテキストの設定の詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bdac-179">For more information about setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
 <span data-ttu-id="0bdac-180">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-180">**Resolution**</span></span>  
  
 <span data-ttu-id="0bdac-181">Oracle ユーザー名、パスワード、および Oracle E-business Suite の成果物のアプリケーションのコンテキストを適切に設定する必要がありますの適切な組み合わせを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-181">You must specify a correct combination of the Oracle user name, password, and responsibility to appropriately set application context for an Oracle E-Business Suite artifact.</span></span> <span data-ttu-id="0bdac-182">Oracle ユーザー名とパスワードの値を指定するに使用する必要があります、 **OracleUserName**と**OraclePassword**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-182">To specify values for Oracle user name and password, you must use the **OracleUserName** and **OraclePassword** binding properties.</span></span> <span data-ttu-id="0bdac-183">Oracle 責任の値を指定するには、使用できます、 **OracleEBSResponsibilityName**プロパティまたはメッセージのコンテキスト プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-183">To specify value for the Oracle responsibility, you can either use the **OracleEBSResponsibilityName** binding property or message context property.</span></span>  
  
###  <a name="BKMK_RootNode"></a> <span data-ttu-id="0bdac-184">BizTalk プロジェクト内の RootNode TypeName とエラー</span><span class="sxs-lookup"><span data-stu-id="0bdac-184">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="0bdac-185">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-185">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-186">BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:</span><span class="sxs-lookup"><span data-stu-id="0bdac-186">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="0bdac-187">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-187">**Resolution**</span></span>  
  
1.  <span data-ttu-id="0bdac-188">クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-188">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="0bdac-189">**RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。</span><span class="sxs-lookup"><span data-stu-id="0bdac-189">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_InvalidBinding"></a> <span data-ttu-id="0bdac-190">Visual Studio で、アダプターを使用する際に無効なバインド警告</span><span class="sxs-lookup"><span data-stu-id="0bdac-190">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="0bdac-191">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-191">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-192">アプリケーションを作成するアダプターを使用すると[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]とアダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bdac-192">When you use the adapter to create an application in [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="0bdac-193">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-193">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-194">この警告が表示されます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインド、`oracleEBSBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-194">This warning appears because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding, `oracleEBSBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="0bdac-195">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-195">**Resolution**</span></span>  
  
 <span data-ttu-id="0bdac-196">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="0bdac-196">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_Notify"></a> <span data-ttu-id="0bdac-197">同じアプリケーション内で 1 つ以上の通知スキーマを使用するか、同じホスト上の複数のアプリケーションで通知スキーマを使用している場合、BizTalk Server は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-197">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="0bdac-198">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-198">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-199">BizTalk Server では、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-199">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="0bdac-200">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-200">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-201">これは、次のいずれかの原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-201">This happens because of either of the following:</span></span>  
  
- <span data-ttu-id="0bdac-202">1 つ以上を生成した通知スキーマを BizTalk Server プロジェクトで、BizTalk Server アプリケーションに展開し、Oracle データベースから通知を受け取るアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-202">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the Oracle database.</span></span> <span data-ttu-id="0bdac-203">競合が通知のスキーマは共通であるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-203">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
- <span data-ttu-id="0bdac-204">複数のプロジェクトが発生した場合、同じホスト上の別の BizTalk Server アプリケーションを各プロジェクト配置されたプロジェクト、BizTalk Server の各通知スキーマを生成したから通知を受信するアプリケーションを実行し、Oracle データベース。</span><span class="sxs-lookup"><span data-stu-id="0bdac-204">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the Oracle database.</span></span> <span data-ttu-id="0bdac-205">競合が、スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるために展開 BizTalk Server アプリケーションとアセンブリのさまざまな一般的なスキーマの間であります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-205">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
  <span data-ttu-id="0bdac-206">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-206">**Resolution**</span></span>  
  
  <span data-ttu-id="0bdac-207">BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-207">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="0bdac-208">同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションから通知スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-208">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_Timeout"></a> <span data-ttu-id="0bdac-209">Visual Studio での Oracle E-business Suite の成果物の閲覧中にタイムアウトの例外</span><span class="sxs-lookup"><span data-stu-id="0bdac-209">Timeout Exception while browsing Oracle E-Business Suite Artifacts in Visual Studio</span></span>  
 <span data-ttu-id="0bdac-210">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-210">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-211">Oracle E-business Suite のアイテムの閲覧中に、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクトを使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]タイムアウト例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-211">While browsing Oracle E-Business Suite artifacts in a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] project using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] you might encounter a timeout exception.</span></span>  
  
 <span data-ttu-id="0bdac-212">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-212">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-213">これは、Oracle E-business Suite をホストするサーバーが遅い、サーバーがリモートの場所にある、または 検索するスキーマに含まれる成果物の数が多い場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-213">This might happen if the server hosting the Oracle E-Business Suite is slow, server is located at a remote location, or the schema you are looking under has a large number of artifacts.</span></span>  
  
 <span data-ttu-id="0bdac-214">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-214">**Resolution**</span></span>  
  
 <span data-ttu-id="0bdac-215">値を大きくかを選択できます、 **SendTimeout**に検索式を入力、またはプロパティのバインド、**カテゴリで検索**成果物の数を削減するテキスト ボックスをアダプター取得します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-215">You can either choose to increase the value of the **SendTimeout** binding property or provide a search expression in the **Search in category** text box to reduce the number of artifacts that the adapter retrieves.</span></span>  
  
 <span data-ttu-id="0bdac-216">バインドのプロパティを指定する方法については、[for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bdac-216">For more information about specifying binding properties, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span> <span data-ttu-id="0bdac-217">Oracle E-business Suite でアーティファクトの検索に関する詳細については、[参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bdac-217">For more information about searching artifacts in Oracle E-Business Suite, see [Browse, search, and get metadata for Oracle E-Business Suite operations](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).</span></span>  
  
###  <a name="BKMK_MemUsage"></a> <span data-ttu-id="0bdac-218">メモリ使用量とスレッド数の増加、トランザクション受信操作で、アダプターを使用する場合</span><span class="sxs-lookup"><span data-stu-id="0bdac-218">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="0bdac-219">**問題**</span><span class="sxs-lookup"><span data-stu-id="0bdac-219">**Problem**</span></span>  
  
 <span data-ttu-id="0bdac-220">ポーリングなどのトランザクション受信操作で**かどうかデータがないポーリングされるテーブルで使用できる**アダプターがポーリングを継続しは、時間の期間にわたってメモリ使用量とスレッド数の増加が発生します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-220">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="0bdac-221">**原因**</span><span class="sxs-lookup"><span data-stu-id="0bdac-221">**Cause**</span></span>  
  
 <span data-ttu-id="0bdac-222">**かどうかはデータがないポーリングされるテーブルで使用できる**後にすべて受信タイムアウトのサイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-222">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="0bdac-223">そのため、期間のスレッドの数とメモリ使用量が増加します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-223">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="0bdac-224">ただし、ポーリングされるテーブルにいくつかのデータがある場合、同じスレッドは、すべての後続のポーリングを実行する継続します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-224">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="0bdac-225">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0bdac-225">**Resolution**</span></span>  
  
 <span data-ttu-id="0bdac-226">設定をお勧め、 **ReceiveTimeout**に最大の可能な値である 24.20:31:23.6470000 (24 日)、新しいスレッドは 24 日間にのみを生成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0bdac-226">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="0bdac-227">メモリ使用量とスレッドの数が大きくが多すぎるが早すぎるようになります。</span><span class="sxs-lookup"><span data-stu-id="0bdac-227">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
 <span data-ttu-id="0bdac-228">詳細については、 **ReceiveTimeout**プロパティ、バインドを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="0bdac-228">For more information about the **ReceiveTimeout** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="0bdac-229">バインドのプロパティを指定する方法の詳細については、[for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bdac-229">For instructions on specifying binding properties, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bdac-230">アダプターを使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。</span><span class="sxs-lookup"><span data-stu-id="0bdac-230">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdac-231">参照</span><span class="sxs-lookup"><span data-stu-id="0bdac-231">See Also</span></span>  
[<span data-ttu-id="0bdac-232">Oracle EBS アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0bdac-232">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
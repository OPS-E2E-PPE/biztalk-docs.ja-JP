---
title: "Biztalk SQL アダプターでの運用上の問題のトラブルシューティング |Microsoft ドキュメント"
description: "共通の問題と、SQL アダプターの BizTalk アダプター パック (BAP) の解決策"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6850a1b8c3b0cb5d1356078fce8dc8f50c6963
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a><span data-ttu-id="9db66-103">SQL アダプタで運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="9db66-103">Troubleshoot Operational Issues with the SQL adapter</span></span>
<span data-ttu-id="9db66-104">このセクションで説明を使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="9db66-105">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9db66-105">Enabling Tracing</span></span>  
 <span data-ttu-id="9db66-106">アダプターの間でトレースを有効にする必要があります[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、問題の詳細については、いずれかを収集する SQL Server が使用中に発生して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-106">You must enable tracing between the adapter, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and SQL Server to gather more information about any issues you encounter while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="9db66-107">トレースのサポートの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[診断トレースおよび SQL アダプターでメッセージのログ記録](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="9db66-107">For more information about tracing support in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Diagnostic Tracing and Message Logging in the SQL adapter](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="9db66-108">既知の問題</span><span class="sxs-lookup"><span data-stu-id="9db66-108">Known Issues</span></span>  
 <span data-ttu-id="9db66-109">使用する場合に発生する可能性が最も一般的なエラーは、次のとおり、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、およびその考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="9db66-109">The following are the most common errors you might encounter when using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a><span data-ttu-id="9db66-110">アダプターのバインドを読み込み中にエラー</span><span class="sxs-lookup"><span data-stu-id="9db66-110">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="9db66-111">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-111">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-112">起動しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9db66-112">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="9db66-113">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-113">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-114">起動しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9db66-114">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="9db66-115">一方、アダプターのバインドは、エンタープライズ アプリケーション用の特定のクライアント ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="9db66-115">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="9db66-116">含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了した場合は、この問題に直面する可能性があります、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-116">You might face this issue if you did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="9db66-117">ただし、1 つだけのエンタープライズ アプリケーションに LOB クライアント ライブラリをインストールする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9db66-117">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="9db66-118">その結果、GUI は、他のアダプターのバインドを読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="9db66-118">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="9db66-119">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-119">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-120">必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9db66-120">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_SQLDisplay"></a><span data-ttu-id="9db66-121">SQL アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="9db66-121">The SQL adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="9db66-122">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-122">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-123">付属するアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]アダプターの一覧に表示されない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="9db66-123">Unlike the earlier version of the adapters shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="9db66-124">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-124">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-125">最新[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]WCF カスタム バインドがします。</span><span class="sxs-lookup"><span data-stu-id="9db66-125">The latest [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="9db66-126">そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-126">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="9db66-127">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-127">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-128">明示的に追加することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="9db66-128">You can explicitly add the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_MissingAction"></a><span data-ttu-id="9db66-129">SQL Server データベースに対する操作の実行中のエラー</span><span class="sxs-lookup"><span data-stu-id="9db66-129">Error while performing operations on a SQL Server database</span></span>  
 <span data-ttu-id="9db66-130">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-130">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-131">使用して SQL Server データベースに任意の操作を実行するときに、アダプターは、次のエラーを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-131">The adapter gives the following error when performing any operation on a SQL Server database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9db66-132">**BizTalk server**</span><span class="sxs-lookup"><span data-stu-id="9db66-132">**For BizTalk Server**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="9db66-133">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-133">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-134">メッセージの WCF アクションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="9db66-134">The WCF action for the message is not specified.</span></span> <span data-ttu-id="9db66-135">WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="9db66-135">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="9db66-136">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-136">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-137">送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9db66-137">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="9db66-138">手順については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="9db66-138">For instructions, see [Configure the SOAP action for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).</span></span> <span data-ttu-id="9db66-139">参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)各操作のアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="9db66-139">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_SQLInvalidOp"></a><span data-ttu-id="9db66-140">エラー コードでの InvalidOperationException FILESTREAM 操作の実行中に 5 を =</span><span class="sxs-lookup"><span data-stu-id="9db66-140">InvalidOperationException with ErrorCode=5 while performing FILESTREAM operations</span></span>  
 <span data-ttu-id="9db66-141">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-141">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-142">使用しているときに、次のエラーを取得する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] FILESTREAM 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9db66-142">You get the following error while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform FILESTREAM operations.</span></span>  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 <span data-ttu-id="9db66-143">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-143">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-144">SQL Server データベースに接続するデータベースの資格情報を指定する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9db66-144">You might have specified database credentials to connect to the SQL Server database.</span></span> <span data-ttu-id="9db66-145">FILESTREAM 操作を行うには、常に Windows 認証を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9db66-145">To perform FILESTREAM operations, you must always use Windows Authentication.</span></span> <span data-ttu-id="9db66-146">エラー コード「5」は、正しくない資格情報のためのアクセスが拒否されることを示します。</span><span class="sxs-lookup"><span data-stu-id="9db66-146">The error code “5” denotes that access is denied because of incorrect credentials.</span></span> <span data-ttu-id="9db66-147">別のエラー コードの詳細については、次を参照してください。[システム エラー コード (0 ~ 499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="9db66-147">For more information about the different error codes, see [System Error Codes (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx).</span></span>
  
 <span data-ttu-id="9db66-148">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-148">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-149">SQL Server データベースに接続するには、Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="9db66-149">Use Windows Authentication to connect to the SQL Server database.</span></span> <span data-ttu-id="9db66-150">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、これを行う空白のままユーザー名とパスワードのフィールド、Wcf-custom または WCF SQL ポートの構成 ダイアログ ボックスでします。</span><span class="sxs-lookup"><span data-stu-id="9db66-150">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can do so by leaving the user name and password fields blank in the WCF-Custom or WCF-SQL port configuration dialog box.</span></span>  
  
###  <a name="BKMK_SQLPolling"></a><span data-ttu-id="9db66-151">操作をポーリング返さないメッセージ PollingStatement と PolledDataAvailableStatement 有効なステートメントに指定されている場合でも</span><span class="sxs-lookup"><span data-stu-id="9db66-151">Polling operation does not return any messages even if valid statements are specified for PollingStatement and PolledDataAvailableStatement</span></span>  
 <span data-ttu-id="9db66-152">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-152">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-153">PollingStatement および PolledDataAvailableStatement のバインド プロパティの有効な値を指定する場合でもは、アダプターは SQL Server からポーリング メッセージを受け取りません。</span><span class="sxs-lookup"><span data-stu-id="9db66-153">Even if valid values are specified for the PollingStatement and PolledDataAvailableStatement binding properties, the adapter does not receive a polling message from SQL Server.</span></span>  
  
 <span data-ttu-id="9db66-154">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-154">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-155">他のトランザクションがアダプターをポーリングするテーブルのロックを取得するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9db66-155">Verify whether any other transaction has taken a lock on the table that the adapter is polling.</span></span>  
  
 <span data-ttu-id="9db66-156">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-156">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-157">別のトランザクションの一部として更新されるテーブルをポーリングする場合は、使用を検討"(nolock)"を使用したパラメーター PolledDataAvailableStatement バインド プロパティの指定されたクエリの一部として、ロックが適用される場合でも、データが返されることを確認するにはによって他のトランザクションです。</span><span class="sxs-lookup"><span data-stu-id="9db66-157">If you want to poll a table that is being updated as part of another transaction, you can consider using “with (nolock)” parameter as part of the query specified for PolledDataAvailableStatement binding property to ensure that data is returned even if a lock is imposed by the other transaction.</span></span> <span data-ttu-id="9db66-158">詳細については、次を参照してください。[データベース エンジンの SQL ロック](https://msdn.microsoft.com/library/ms190615.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="9db66-158">For more information, see [SQL Locking in the Database Engine](https://msdn.microsoft.com/library/ms190615.aspx).</span></span>
  
###  <a name="BKMK_SQLSingleOp"></a><span data-ttu-id="9db66-159">アダプターは、挿入、更新、または大量の BizTalk Server を使用して単一の操作でデータを削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9db66-159">The adapter fails to insert, update, or delete large volumes of data in a single operation using BizTalk Server</span></span>  
 <span data-ttu-id="9db66-160">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-160">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-161">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]大量のデータを使用して、1 つの操作での挿入、更新、削除に失敗した[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-161">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] fails to insert, update, or delete large volumes of data in a single operation using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9db66-162">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-162">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-163">挿入、更新、または大量のデータを削除する時間がかかる場合があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で操作が実行されている、トランザクションがタイムアウトになった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9db66-163">Inserting, updating, or deleting large volumes of data may take time and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] or the transaction in which the operation is being performed, may time out.</span></span>  
  
 <span data-ttu-id="9db66-164">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-164">**Resolution**</span></span>  
  
-   <span data-ttu-id="9db66-165">**BizTalk server**</span><span class="sxs-lookup"><span data-stu-id="9db66-165">**For BizTalk Server**</span></span>  
  
    1.  <span data-ttu-id="9db66-166">Machine.config には、WCF アダプターのタイムアウトを指定します。下にある machine.config ファイルに移動\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG し、次のような抜粋を追加します。</span><span class="sxs-lookup"><span data-stu-id="9db66-166">Specify the timeout for the WCF adapter in the machine.config. Navigate to the machine.config file under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
        ```  
        <configuration>  
         <system.transactions>  
          <machineSettings maxTimeout="02:00:00" />  
         </system.transactions>  
        </configuration>  
        ```  
  
         <span data-ttu-id="9db66-167">この設定では、WCF アダプターのタイムアウトは 2 時間に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9db66-167">With this setting, the WCF adapter timeout is set to 2 hours.</span></span>  
  
    2.  <span data-ttu-id="9db66-168">Machine.config には、MSDTC トランザクションのタイムアウト設定を指定します。下にある machine.config ファイルに移動\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG し、次のような抜粋を追加します。</span><span class="sxs-lookup"><span data-stu-id="9db66-168">Specify the timeout settings for MSDTC transactions in the machine.config. Navigate to the machine.config file under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
        ```  
        <system.transactions>   
                <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
            </system.transactions>  
  
        ```  
  
         <span data-ttu-id="9db66-169">この設定では、MSDTC のタイムアウトは 2 時間に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9db66-169">With this setting, the MSDTC timeout is set to 2 hours.</span></span> <span data-ttu-id="9db66-170">MSDTC のタイムアウトの既定値は、10 分です。</span><span class="sxs-lookup"><span data-stu-id="9db66-170">The default value for MSDTC timeout is 10 minutes.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="9db66-171">アダプターのクライアントと SQL Server を実行するコンピューターでこの変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9db66-171">You must make this change on the computers running the adapter client and SQL Server.</span></span> <span data-ttu-id="9db66-172">例では、アダプターのクライアントと SQL Server を実行しているコンピューターの名前で < computer_name > を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9db66-172">In the excerpt, replace <computer_name> with the name of computer running the adapter client and SQL Server.</span></span>  
  
    3.  <span data-ttu-id="9db66-173">設定、 **SendTimeout**バインディングのプロパティ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]非常に大きな値にします。</span><span class="sxs-lookup"><span data-stu-id="9db66-173">Set the **SendTimeout** binding property for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to a fairly large value.</span></span> <span data-ttu-id="9db66-174">バインドのプロパティを設定する方法の手順については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="9db66-174">For instructions on how to set the binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a><span data-ttu-id="9db66-175">データセットを含む応答メッセージを BizTalk Server のフル スキーマ検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="9db66-175">Full schema validation in BizTalk Server fails for response messages containing DataSet</span></span>  
 <span data-ttu-id="9db66-176">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-176">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-177">データセットでは、たとえばの ExecuteReader を含む応答メッセージを返す操作の完全スキーマの検証に失敗した[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-177">For operations that return a response message containing a DataSet, for example ExecuteReader, full schema validation fails in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9db66-178">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-178">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-179">データセットを含む応答メッセージのスキーマ完全検証を行わないをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9db66-179">We recommend you to not do a full schema validation for response messages containing a dataset.</span></span> <span data-ttu-id="9db66-180">代わりに、次の操作を行う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9db66-180">Instead, you could do the following:</span></span>  
  
1.  <span data-ttu-id="9db66-181">スキーマと応答メッセージを返すと、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9db66-181">Execute the operation once that returns the response message with the schema.</span></span>  
  
2.  <span data-ttu-id="9db66-182">.Xsd ファイルへの応答メッセージからスキーマをコピーし、BizTalk プロジェクトにこのファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="9db66-182">Copy the schema from the response message to a .xsd file and add this file to your BizTalk project.</span></span>  
  
3.  <span data-ttu-id="9db66-183">オーケストレーションで xpath クエリを使用して、応答メッセージからデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="9db66-183">Use an xpath query in your orchestration to extract the data from the response message.</span></span>  
  
###  <a name="BKMK_SQLRootNode"></a><span data-ttu-id="9db66-184">RootNode TypeName BizTalk プロジェクト内のエラー</span><span class="sxs-lookup"><span data-stu-id="9db66-184">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="9db66-185">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-185">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-186">BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:</span><span class="sxs-lookup"><span data-stu-id="9db66-186">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="9db66-187">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-187">**Resolution**</span></span>  
  
1.  <span data-ttu-id="9db66-188">クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="9db66-188">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="9db66-189">**RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。</span><span class="sxs-lookup"><span data-stu-id="9db66-189">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a><span data-ttu-id="9db66-190">アダプターは一時テーブルとストアド プロシージャを厳密に型指定のメタデータを生成できません。</span><span class="sxs-lookup"><span data-stu-id="9db66-190">Adapter fails to generate metadata of strongly-typed stored procedure with temporary tables</span></span>  
 <span data-ttu-id="9db66-191">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-191">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-192">アダプターは、それらの定義で一時テーブルが含まれた厳密に型指定されたストアド プロシージャのメタデータを生成に失敗します。</span><span class="sxs-lookup"><span data-stu-id="9db66-192">The adapter fails to generate metadata for strongly-typed stored procedures that include temporary tables in their definition.</span></span> <span data-ttu-id="9db66-193">アダプターは、次の例外を説明します。</span><span class="sxs-lookup"><span data-stu-id="9db66-193">The adapter gives the following exception.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 <span data-ttu-id="9db66-194">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-194">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-195">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]をそれらの定義内の一時テーブルを含む厳密に型指定されたストアド プロシージャのメタデータの生成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9db66-195">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support generating metadata for strongly-typed stored procedures that contain temporary tables in their definition.</span></span> <span data-ttu-id="9db66-196">代わりに、下から同じプロシージャのメタデータを生成する必要があります、**プロシージャ**ノードを使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-196">Instead, you should generate metadata for the same procedure from under the **Procedures** node while using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
###  <a name="BKMK_SQLVS2008"></a><span data-ttu-id="9db66-197">Visual Studio でのアダプターの使用時の無効なバインドの警告</span><span class="sxs-lookup"><span data-stu-id="9db66-197">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="9db66-198">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-198">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-199">Visual Studio でアプリケーションを作成するアダプターを使用して、アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9db66-199">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="9db66-200">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-200">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-201">この警告が表示されます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインド、`sqlBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9db66-201">This warning appears because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding, `sqlBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="9db66-202">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-202">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-203">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="9db66-203">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_SQLNotification"></a><span data-ttu-id="9db66-204">BizTalk Server が、同じアプリケーションで 1 つ以上の通知スキーマを使用して、同じホスト上の複数のアプリケーション間で通知スキーマを使用するか、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9db66-204">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="9db66-205">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-205">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-206">BizTalk Server は、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9db66-206">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="9db66-207">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-207">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-208">これは、次のいずれかのため発生します。</span><span class="sxs-lookup"><span data-stu-id="9db66-208">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="9db66-209">1 つ以上を生成する、BizTalk Server プロジェクトでの通知スキーマを BizTalk Server アプリケーションに展開し、通知を受信する SQL Server データベースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9db66-209">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="9db66-210">競合が通知スキーマは、一般的なであるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。</span><span class="sxs-lookup"><span data-stu-id="9db66-210">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="9db66-211">複数のプロジェクトが発生した場合、BizTalk Server が配置されたプロジェクトの各プロジェクトの場合、同じホスト上の別の BizTalk Server アプリケーションの各通知スキーマを生成したし、し、実行、アプリケーションまたはアプリケーションからの通知を受信するにはSQL Server データベースです。</span><span class="sxs-lookup"><span data-stu-id="9db66-211">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="9db66-212">スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるため競合があるさまざまな BizTalk Server アプリケーションおよびアセンブリの下でデプロイされる共通のスキーマ間でします。</span><span class="sxs-lookup"><span data-stu-id="9db66-212">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="9db66-213">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-213">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-214">BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9db66-214">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="9db66-215">同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションからの通知スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="9db66-215">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_SQLRestoreConn"></a><span data-ttu-id="9db66-216">アダプターのクライアントは、アダプターのクライアントと SQL Server データベース間の接続が復元された後に、演算を実行することで例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9db66-216">Adapter client throws an exception on performing an operation after the connectivity is restored between the adapter client and the SQL Server database</span></span>  
 <span data-ttu-id="9db66-217">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-217">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-218">アダプターのクライアントには、SQL Server データベースに対する操作を実行するのには、次の例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="9db66-218">Adapter client throws the following exception on executing an operation on the SQL Server database:</span></span>  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 <span data-ttu-id="9db66-219">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-219">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-220">操作の実行中に、アダプターが SQL Server データベースに接続し、操作を実行する SQL ADO.NET 接続プールから接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="9db66-220">During the execution of an operation, the adapter uses the connection from the SQL ADO.NET connection pool to connect to the SQL Server database, and perform the operation.</span></span> <span data-ttu-id="9db66-221">アダプターのクライアントと SQL Server データベース間で簡単なネットワーク障害がある場合、または SQL Server データベースを一時的にある場合は、SQL の ADO.NET 接続プール内のすべての接続が無効になります。</span><span class="sxs-lookup"><span data-stu-id="9db66-221">If there is a brief network outage between the adapter client and the SQL Server database or if the SQL Server database is down temporarily, all the connections in the SQL ADO.NET connection pool become invalid.</span></span> <span data-ttu-id="9db66-222">接続が復元され、SQL Server データベースで操作を実行しようとする、アダプターでは、同じの無効な接続を使用して、SQL の ADO.NET 接続プールからとアダプターのクライアントが例外をスローするため。</span><span class="sxs-lookup"><span data-stu-id="9db66-222">After the connectivity is restored and you try to perform an operation on the SQL Server database, the adapter uses the same invalid connections from the SQL ADO.NET connection pool, and therefore the adapter client throws the exception.</span></span>  
  
 <span data-ttu-id="9db66-223">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-223">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-224">アダプターのクライアントは、ここで例外をキャッチされ"n+1"として操作の再試行回数を指定する必要があります、操作の実行で再試行ロジックを実装する必要があります、"n"は MaxConnectionPoolSize バインディング プロパティに指定された値。</span><span class="sxs-lookup"><span data-stu-id="9db66-224">The adapter client should implement retry logic in their operation execution where they should catch the exception and specify the operation retry count as “n+1”, where “n” is the value specified for the MaxConnectionPoolSize binding property.</span></span> <span data-ttu-id="9db66-225">つまり、こと"n"が無効ですが表示される接続プール内の接続数がある場合は、理論上はアダプター クライアントを再試行する"n+1"の最大の有効な接続を取得し、そのため、操作を実行する時間。</span><span class="sxs-lookup"><span data-stu-id="9db66-225">This implies that if there are “n” number of connections in the connection pool that have been rendered invalid, theoretically the adapter client should retry for a maximum of “n+1” times to get a valid connection, and hence perform the operation.</span></span>  
  
 <span data-ttu-id="9db66-226">などを指定する、再試行回数は[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、開かれている、**プロパティ** ダイアログ ボックスをクリックして、アプリケーションで、送信ポートの**トランスポートの詳細オプション**とダイアログ ボックスの左側のウィンドウで、**トランスポートのオプション** 領域で値を指定、**再試行の回数** ボックスの一覧。</span><span class="sxs-lookup"><span data-stu-id="9db66-226">For example, to specify the retry count in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], open the **Properties** dialog box of a send port in an application, click **Transport Advanced Options** in the left pane of the dialog box, and in the **Transport Options** area, specify a value in the **Retry count** list.</span></span>  
  
###  <a name="BKMK_MemUsage"></a><span data-ttu-id="9db66-227">メモリ使用量とスレッド数の増加トランザクション受信操作で、アダプターを使用する場合</span><span class="sxs-lookup"><span data-stu-id="9db66-227">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="9db66-228">**問題**</span><span class="sxs-lookup"><span data-stu-id="9db66-228">**Problem**</span></span>  
  
 <span data-ttu-id="9db66-229">ポーリングなどのトランザクション受信操作で**かどうかはデータをポーリングするテーブルで使用できる**アダプターがポーリングを継続しは、メモリ使用量とスレッド数の増加が発生する期間にわたっています。</span><span class="sxs-lookup"><span data-stu-id="9db66-229">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="9db66-230">**原因**</span><span class="sxs-lookup"><span data-stu-id="9db66-230">**Cause**</span></span>  
  
 <span data-ttu-id="9db66-231">**かどうかはデータをポーリングするテーブルで使用できる**の後にすべて受信タイムアウト サイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。</span><span class="sxs-lookup"><span data-stu-id="9db66-231">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="9db66-232">そのため、時間の期間にわたって、スレッドの数とメモリの使用量が増加します。</span><span class="sxs-lookup"><span data-stu-id="9db66-232">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="9db66-233">ただし、一部のデータをポーリングするテーブルには、同じスレッドが継続後続のすべてのポーリングを実行します。</span><span class="sxs-lookup"><span data-stu-id="9db66-233">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="9db66-234">**解決策**</span><span class="sxs-lookup"><span data-stu-id="9db66-234">**Resolution**</span></span>  
  
 <span data-ttu-id="9db66-235">設定を推奨、 **ReceiveTimeout**に最大の可能な値は 24.20:31:23.6470000 (24 日)、新しいスレッドが 24 日間にのみを生成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9db66-235">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="9db66-236">これにより、メモリ使用量とスレッド数が大きくならないが多すぎるが早すぎます。</span><span class="sxs-lookup"><span data-stu-id="9db66-236">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9db66-237">SqlAdapterInboundTransactionBehavior が設定されている場合、TransactionTimeout が 24.20:31:23.6470000 (24 日) である最大の可能な値にも構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9db66-237">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="9db66-238">この回避策を使用する場合、トランザクション分離レベルを構成する場合のみ、SqlAdapterInboundTransactionBehavior を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9db66-238">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="9db66-239">それ以外の場合、その動作を削除することを勧めします。</span><span class="sxs-lookup"><span data-stu-id="9db66-239">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="9db66-240">詳細については、 **ReceiveTimeout**バインディング プロパティを参照してください[SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="9db66-240">For more information about the **ReceiveTimeout** binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="9db66-241">バインドのプロパティを指定する方法の詳細については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="9db66-241">For instructions on specifying binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9db66-242">付いたアダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。</span><span class="sxs-lookup"><span data-stu-id="9db66-242">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db66-243">参照</span><span class="sxs-lookup"><span data-stu-id="9db66-243">See Also</span></span>  
[<span data-ttu-id="9db66-244">SQL アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="9db66-244">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
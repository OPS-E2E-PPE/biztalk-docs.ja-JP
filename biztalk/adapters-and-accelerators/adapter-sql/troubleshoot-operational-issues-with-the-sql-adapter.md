---
title: Biztalk SQL アダプターを使用した運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的な問題と、SQL アダプターの BizTalk アダプター パック (BAP) の解決策
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d167777ccd9fd9ccb2ddc5a43410d798bde3e7b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367512"
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a><span data-ttu-id="9342a-103">SQL アダプターを使用した運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="9342a-103">Troubleshoot Operational Issues with the SQL adapter</span></span>
<span data-ttu-id="9342a-104">このセクションを使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="9342a-105">トレースの有効化</span><span class="sxs-lookup"><span data-stu-id="9342a-105">Enabling Tracing</span></span>  
 <span data-ttu-id="9342a-106">アダプターのトレースを有効にする必要があります[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、問題の詳細については、収集するために SQL Server が使用中に発生して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-106">You must enable tracing between the adapter, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and SQL Server to gather more information about any issues you encounter while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="9342a-107">トレースのサポートの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[診断トレースと SQL アダプターでメッセージのログ記録](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9342a-107">For more information about tracing support in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Diagnostic Tracing and Message Logging in the SQL adapter](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="9342a-108">既知の問題</span><span class="sxs-lookup"><span data-stu-id="9342a-108">Known Issues</span></span>  
 <span data-ttu-id="9342a-109">使用する場合に発生する可能性が最も一般的なエラーを次に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と共に、考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="9342a-109">The following are the most common errors you might encounter when using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a> <span data-ttu-id="9342a-110">アダプターのバインドを読み込み中にエラー</span><span class="sxs-lookup"><span data-stu-id="9342a-110">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="9342a-111">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-111">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-112">開始しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9342a-112">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="9342a-113">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-113">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-114">開始しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9342a-114">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="9342a-115">さらに、アダプターのバインドは、エンタープライズ アプリケーションの特定のクライアント ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="9342a-115">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="9342a-116">含まれているすべてのアダプターをインストールすると、アダプターの標準または完了のインストールを実行した場合に、この問題が発生する可能性があります、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-116">You might face this issue if you did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="9342a-117">ただし、1 つだけのエンタープライズ アプリケーション用に LOB クライアント ライブラリをインストールする場合があります。</span><span class="sxs-lookup"><span data-stu-id="9342a-117">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="9342a-118">その結果、GUI の他のアダプターのバインドの読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="9342a-118">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="9342a-119">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-119">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-120">必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9342a-120">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_SQLDisplay"></a> <span data-ttu-id="9342a-121">SQL アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="9342a-121">The SQL adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="9342a-122">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-122">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-123">付属のアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]でアダプターの一覧が表示されない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="9342a-123">Unlike the earlier version of the adapters shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="9342a-124">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-124">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-125">最新[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]WCF カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="9342a-125">The latest [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="9342a-126">そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-126">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="9342a-127">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-127">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-128">明示的に追加することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="9342a-128">You can explicitly add the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_MissingAction"></a> <span data-ttu-id="9342a-129">SQL Server データベースに対する操作の実行中のエラー</span><span class="sxs-lookup"><span data-stu-id="9342a-129">Error while performing operations on a SQL Server database</span></span>  
 <span data-ttu-id="9342a-130">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-130">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-131">使用して SQL Server データベースに対して任意の操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-131">The adapter gives the following error when performing any operation on a SQL Server database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="9342a-132">**BizTalk Server 用**</span><span class="sxs-lookup"><span data-stu-id="9342a-132">**For BizTalk Server**</span></span>  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  <span data-ttu-id="9342a-133">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-133">**Cause**</span></span>  
  
  <span data-ttu-id="9342a-134">メッセージの WCF アクションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="9342a-134">The WCF action for the message is not specified.</span></span> <span data-ttu-id="9342a-135">WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="9342a-135">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
  <span data-ttu-id="9342a-136">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-136">**Resolution**</span></span>  
  
  <span data-ttu-id="9342a-137">送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9342a-137">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="9342a-138">手順については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9342a-138">For instructions, see [Configure the SOAP action for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).</span></span> <span data-ttu-id="9342a-139">参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)各操作のアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="9342a-139">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_SQLInvalidOp"></a> <span data-ttu-id="9342a-140">Errorcode InvalidOperationException FILESTREAM 操作を実行中に 5 を =</span><span class="sxs-lookup"><span data-stu-id="9342a-140">InvalidOperationException with ErrorCode=5 while performing FILESTREAM operations</span></span>  
 <span data-ttu-id="9342a-141">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-141">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-142">使用中に次のエラーが発生した、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] FILESTREAM 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9342a-142">You get the following error while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform FILESTREAM operations.</span></span>  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 <span data-ttu-id="9342a-143">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-143">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-144">SQL Server データベースに接続するデータベース資格情報を指定する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9342a-144">You might have specified database credentials to connect to the SQL Server database.</span></span> <span data-ttu-id="9342a-145">FILESTREAM 操作を実行するには、必ずに Windows 認証を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9342a-145">To perform FILESTREAM operations, you must always use Windows Authentication.</span></span> <span data-ttu-id="9342a-146">エラー コード「5」では、正しくない資格情報のためのアクセスが拒否されることを示します。</span><span class="sxs-lookup"><span data-stu-id="9342a-146">The error code “5” denotes that access is denied because of incorrect credentials.</span></span> <span data-ttu-id="9342a-147">別のエラー コードの詳細については、次を参照してください。[システム エラー コード (0 ~ 499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="9342a-147">For more information about the different error codes, see [System Error Codes (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx).</span></span>
  
 <span data-ttu-id="9342a-148">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-148">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-149">SQL Server データベースに接続するには、Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="9342a-149">Use Windows Authentication to connect to the SQL Server database.</span></span> <span data-ttu-id="9342a-150">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、これを行う空白のままユーザー名とパスワードのフィールド、Wcf-custom または WCF SQL ポートの構成 ダイアログ ボックスでします。</span><span class="sxs-lookup"><span data-stu-id="9342a-150">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can do so by leaving the user name and password fields blank in the WCF-Custom or WCF-SQL port configuration dialog box.</span></span>  
  
###  <a name="BKMK_SQLPolling"></a> <span data-ttu-id="9342a-151">操作のポーリングは返しませんメッセージ PollingStatement と PolledDataAvailableStatement に有効なステートメントが指定されている場合でも</span><span class="sxs-lookup"><span data-stu-id="9342a-151">Polling operation does not return any messages even if valid statements are specified for PollingStatement and PolledDataAvailableStatement</span></span>  
 <span data-ttu-id="9342a-152">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-152">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-153">PollingStatement および PolledDataAvailableStatement のバインド プロパティの有効な値が指定されている場合でも、アダプターでは、SQL Server からは、ポーリング メッセージは受け取りません。</span><span class="sxs-lookup"><span data-stu-id="9342a-153">Even if valid values are specified for the PollingStatement and PolledDataAvailableStatement binding properties, the adapter does not receive a polling message from SQL Server.</span></span>  
  
 <span data-ttu-id="9342a-154">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-154">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-155">他のトランザクションが、アダプターがポーリングされるテーブルでロックを取得するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9342a-155">Verify whether any other transaction has taken a lock on the table that the adapter is polling.</span></span>  
  
 <span data-ttu-id="9342a-156">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-156">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-157">別のトランザクションの一部として更新されるテーブルをポーリングする場合は、PolledDataAvailableStatement バインド プロパティに指定されたクエリの一部として、ロックが適用される場合でもデータが返されるようにする"(nolock)"を使用したパラメーターを使用してを考慮することができます。その他のトランザクション。</span><span class="sxs-lookup"><span data-stu-id="9342a-157">If you want to poll a table that is being updated as part of another transaction, you can consider using “with (nolock)” parameter as part of the query specified for PolledDataAvailableStatement binding property to ensure that data is returned even if a lock is imposed by the other transaction.</span></span> <span data-ttu-id="9342a-158">詳細については、次を参照してください。[データベース エンジンの SQL ロック](https://msdn.microsoft.com/library/ms190615.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="9342a-158">For more information, see [SQL Locking in the Database Engine](https://msdn.microsoft.com/library/ms190615.aspx).</span></span>
  
###  <a name="BKMK_SQLSingleOp"></a> <span data-ttu-id="9342a-159">アダプターは、挿入、更新、または大量のデータを BizTalk Server を使用して 1 つの操作を削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9342a-159">The adapter fails to insert, update, or delete large volumes of data in a single operation using BizTalk Server</span></span>  
 <span data-ttu-id="9342a-160">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-160">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-161">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]が挿入、更新、または大量の 1 つの操作を使用してデータの削除に失敗した[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-161">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] fails to insert, update, or delete large volumes of data in a single operation using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9342a-162">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-162">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-163">挿入、更新、または大量のデータを削除していますが、時間がかかると[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を操作が実行される、トランザクションがタイムアウトになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9342a-163">Inserting, updating, or deleting large volumes of data may take time and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] or the transaction in which the operation is being performed, may time out.</span></span>  
  
 <span data-ttu-id="9342a-164">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-164">**Resolution**</span></span>  
  
- <span data-ttu-id="9342a-165">**BizTalk Server 用**</span><span class="sxs-lookup"><span data-stu-id="9342a-165">**For BizTalk Server**</span></span>  
  
  1. <span data-ttu-id="9342a-166">Machine.config ファイルでは、WCF アダプターのタイムアウトを指定します。Machine.config ファイルの下に移動\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG し、次のような抜粋を追加します。</span><span class="sxs-lookup"><span data-stu-id="9342a-166">Specify the timeout for the WCF adapter in the machine.config. Navigate to the machine.config file under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
     ```  
     <configuration>  
      <system.transactions>  
       <machineSettings maxTimeout="02:00:00" />  
      </system.transactions>  
     </configuration>  
     ```  
  
      <span data-ttu-id="9342a-167">この設定では、WCF アダプターのタイムアウトは 2 時間に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9342a-167">With this setting, the WCF adapter timeout is set to 2 hours.</span></span>  
  
  2. <span data-ttu-id="9342a-168">Machine.config ファイルでは、MSDTC トランザクションのタイムアウト設定を指定します。Machine.config ファイルの下に移動\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG し、次のような抜粋を追加します。</span><span class="sxs-lookup"><span data-stu-id="9342a-168">Specify the timeout settings for MSDTC transactions in the machine.config. Navigate to the machine.config file under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
     ```  
     <system.transactions>   
             <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
         </system.transactions>  
  
     ```  
  
      <span data-ttu-id="9342a-169">この設定では、MSDTC のタイムアウトは 2 時間に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9342a-169">With this setting, the MSDTC timeout is set to 2 hours.</span></span> <span data-ttu-id="9342a-170">MSDTC のタイムアウトの既定値は、10 分です。</span><span class="sxs-lookup"><span data-stu-id="9342a-170">The default value for MSDTC timeout is 10 minutes.</span></span>  
  
     > [!IMPORTANT]
     >  <span data-ttu-id="9342a-171">アダプターのクライアントと SQL Server を実行するコンピューターでこの変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9342a-171">You must make this change on the computers running the adapter client and SQL Server.</span></span> <span data-ttu-id="9342a-172">例では、< computer_name > をアダプターのクライアントと SQL Server を実行しているコンピューターの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9342a-172">In the excerpt, replace <computer_name> with the name of computer running the adapter client and SQL Server.</span></span>  
  
  3. <span data-ttu-id="9342a-173">設定、 **SendTimeout**のプロパティのバインド、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]非常に大きな値にします。</span><span class="sxs-lookup"><span data-stu-id="9342a-173">Set the **SendTimeout** binding property for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to a fairly large value.</span></span> <span data-ttu-id="9342a-174">バインドのプロパティを設定する方法については、次を参照してください。 [SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9342a-174">For instructions on how to set the binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a> <span data-ttu-id="9342a-175">データセットを含む応答メッセージの BizTalk Server の完全なスキーマ検証の失敗します。</span><span class="sxs-lookup"><span data-stu-id="9342a-175">Full schema validation in BizTalk Server fails for response messages containing DataSet</span></span>  
 <span data-ttu-id="9342a-176">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-176">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-177">たとえば ExecuteReader、データセットを含む応答メッセージを返す操作の完全なスキーマの検証に失敗した[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-177">For operations that return a response message containing a DataSet, for example ExecuteReader, full schema validation fails in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9342a-178">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-178">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-179">データセットを含む応答メッセージの完全なスキーマ検証を行わないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9342a-179">We recommend you to not do a full schema validation for response messages containing a dataset.</span></span> <span data-ttu-id="9342a-180">代わりに、次の操作を行う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9342a-180">Instead, you could do the following:</span></span>  
  
1.  <span data-ttu-id="9342a-181">スキーマと応答メッセージを返すと、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9342a-181">Execute the operation once that returns the response message with the schema.</span></span>  
  
2.  <span data-ttu-id="9342a-182">応答メッセージからスキーマを .xsd ファイルにコピーし、このファイルを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="9342a-182">Copy the schema from the response message to a .xsd file and add this file to your BizTalk project.</span></span>  
  
3.  <span data-ttu-id="9342a-183">オーケストレーションで xpath クエリを使用して、応答メッセージからデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="9342a-183">Use an xpath query in your orchestration to extract the data from the response message.</span></span>  
  
###  <a name="BKMK_SQLRootNode"></a> <span data-ttu-id="9342a-184">BizTalk プロジェクト内の RootNode TypeName とエラー</span><span class="sxs-lookup"><span data-stu-id="9342a-184">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="9342a-185">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-185">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-186">BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:</span><span class="sxs-lookup"><span data-stu-id="9342a-186">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="9342a-187">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-187">**Resolution**</span></span>  
  
1.  <span data-ttu-id="9342a-188">クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9342a-188">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="9342a-189">**RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。</span><span class="sxs-lookup"><span data-stu-id="9342a-189">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a> <span data-ttu-id="9342a-190">アダプターが一時テーブルとストアド プロシージャを厳密に型指定のメタデータの生成に失敗します。</span><span class="sxs-lookup"><span data-stu-id="9342a-190">Adapter fails to generate metadata of strongly-typed stored procedure with temporary tables</span></span>  
 <span data-ttu-id="9342a-191">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-191">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-192">アダプターは、その定義の一時テーブルを含む厳密に型指定されたストアド プロシージャのメタデータの生成に失敗します。</span><span class="sxs-lookup"><span data-stu-id="9342a-192">The adapter fails to generate metadata for strongly-typed stored procedures that include temporary tables in their definition.</span></span> <span data-ttu-id="9342a-193">アダプターは、次の例外を示します。</span><span class="sxs-lookup"><span data-stu-id="9342a-193">The adapter gives the following exception.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 <span data-ttu-id="9342a-194">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-194">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-195">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は、それらの定義の一時テーブルが含まれている厳密に型指定されたストアド プロシージャのメタデータの生成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9342a-195">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support generating metadata for strongly-typed stored procedures that contain temporary tables in their definition.</span></span> <span data-ttu-id="9342a-196">代わりの下にある同じプロシージャのメタデータを生成する必要があります、**プロシージャ**ノードを使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-196">Instead, you should generate metadata for the same procedure from under the **Procedures** node while using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
###  <a name="BKMK_SQLVS2008"></a> <span data-ttu-id="9342a-197">Visual Studio で、アダプターを使用する際に無効なバインド警告</span><span class="sxs-lookup"><span data-stu-id="9342a-197">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="9342a-198">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-198">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-199">Visual Studio でアプリケーションを作成するアダプターを使用すると、アダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9342a-199">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="9342a-200">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-200">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-201">この警告が表示されます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインド、`sqlBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9342a-201">This warning appears because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding, `sqlBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="9342a-202">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-202">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-203">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="9342a-203">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_SQLNotification"></a> <span data-ttu-id="9342a-204">同じアプリケーション内で 1 つ以上の通知スキーマを使用するか、同じホスト上の複数のアプリケーションで通知スキーマを使用している場合、BizTalk Server は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9342a-204">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="9342a-205">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-205">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-206">BizTalk Server では、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9342a-206">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="9342a-207">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-207">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-208">これは、次のいずれかの原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="9342a-208">This happens because of either of the following:</span></span>  
  
- <span data-ttu-id="9342a-209">1 つ以上を生成した通知スキーマを BizTalk Server プロジェクト内に BizTalk Server アプリケーションでは、展開し、SQL Server データベースから通知を受け取るアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9342a-209">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="9342a-210">競合が通知のスキーマは共通であるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。</span><span class="sxs-lookup"><span data-stu-id="9342a-210">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
- <span data-ttu-id="9342a-211">複数のプロジェクトが発生した場合、同じホスト上の別の BizTalk Server アプリケーションを各プロジェクト配置されたプロジェクト、BizTalk Server の各通知スキーマを生成したから通知を受信するアプリケーションを実行し、SQL Server データベース。</span><span class="sxs-lookup"><span data-stu-id="9342a-211">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="9342a-212">競合が、スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるために展開 BizTalk Server アプリケーションとアセンブリのさまざまな一般的なスキーマの間であります。</span><span class="sxs-lookup"><span data-stu-id="9342a-212">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
  <span data-ttu-id="9342a-213">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-213">**Resolution**</span></span>  
  
  <span data-ttu-id="9342a-214">BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9342a-214">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="9342a-215">同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションから通知スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="9342a-215">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_SQLRestoreConn"></a> <span data-ttu-id="9342a-216">アダプター クライアントは、アダプターのクライアントと SQL Server データベース間の接続が復元された後に、演算を実行することで例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9342a-216">Adapter client throws an exception on performing an operation after the connectivity is restored between the adapter client and the SQL Server database</span></span>  
 <span data-ttu-id="9342a-217">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-217">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-218">アダプターのクライアントでは、SQL Server データベースでの操作を実行する方法は、次の例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="9342a-218">Adapter client throws the following exception on executing an operation on the SQL Server database:</span></span>  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 <span data-ttu-id="9342a-219">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-219">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-220">操作の実行中に、アダプターが、SQL Server データベースに接続し、操作を実行する SQL ADO.NET 接続プールから接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="9342a-220">During the execution of an operation, the adapter uses the connection from the SQL ADO.NET connection pool to connect to the SQL Server database, and perform the operation.</span></span> <span data-ttu-id="9342a-221">アダプターのクライアントと SQL Server データベース間で簡単なネットワーク障害が発生した場合、または SQL Server データベースが一時的がダウンした場合は、SQL の ADO.NET 接続プール内のすべての接続は無効になります。</span><span class="sxs-lookup"><span data-stu-id="9342a-221">If there is a brief network outage between the adapter client and the SQL Server database or if the SQL Server database is down temporarily, all the connections in the SQL ADO.NET connection pool become invalid.</span></span> <span data-ttu-id="9342a-222">接続が復元され、SQL Server データベースに対して操作を実行しようとした、アダプターでは、同じ無効な接続を使用して、SQL の ADO.NET 接続プールからとアダプターのクライアントが例外をスローするため。</span><span class="sxs-lookup"><span data-stu-id="9342a-222">After the connectivity is restored and you try to perform an operation on the SQL Server database, the adapter uses the same invalid connections from the SQL ADO.NET connection pool, and therefore the adapter client throws the exception.</span></span>  
  
 <span data-ttu-id="9342a-223">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-223">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-224">アダプター クライアントは、その操作の実行が例外をキャッチし、"n+1"として操作の再試行回数を指定の場所での再試行ロジックを実装する必要があります、"n"は MaxConnectionPoolSize バインド プロパティに指定された値。</span><span class="sxs-lookup"><span data-stu-id="9342a-224">The adapter client should implement retry logic in their operation execution where they should catch the exception and specify the operation retry count as “n+1”, where “n” is the value specified for the MaxConnectionPoolSize binding property.</span></span> <span data-ttu-id="9342a-225">つまり、ことがレンダリングされている無効な接続プール内の接続数の"n"がある場合は、理論的には、アダプター クライアントが再試行"n+1"の最大の有効な接続を取得し、そのため、操作を実行する時間。</span><span class="sxs-lookup"><span data-stu-id="9342a-225">This implies that if there are “n” number of connections in the connection pool that have been rendered invalid, theoretically the adapter client should retry for a maximum of “n+1” times to get a valid connection, and hence perform the operation.</span></span>  
  
 <span data-ttu-id="9342a-226">などを指定する、再試行回数は[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、オープン、**プロパティ** ダイアログ ボックスのアプリケーションでの送信ポートをクリックします**トランスポートの詳細オプション**と、ダイアログ ボックスの左側のウィンドウで、。**トランスポート オプション**領域の値を指定、**再試行の回数**一覧。</span><span class="sxs-lookup"><span data-stu-id="9342a-226">For example, to specify the retry count in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], open the **Properties** dialog box of a send port in an application, click **Transport Advanced Options** in the left pane of the dialog box, and in the **Transport Options** area, specify a value in the **Retry count** list.</span></span>  
  
###  <a name="BKMK_MemUsage"></a> <span data-ttu-id="9342a-227">メモリ使用量とスレッド数の増加、トランザクション受信操作で、アダプターを使用する場合</span><span class="sxs-lookup"><span data-stu-id="9342a-227">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="9342a-228">**問題**</span><span class="sxs-lookup"><span data-stu-id="9342a-228">**Problem**</span></span>  
  
 <span data-ttu-id="9342a-229">ポーリングなどのトランザクション受信操作で**かどうかデータがないポーリングされるテーブルで使用できる**アダプターがポーリングを継続しは、時間の期間にわたってメモリ使用量とスレッド数の増加が発生します。</span><span class="sxs-lookup"><span data-stu-id="9342a-229">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="9342a-230">**原因**</span><span class="sxs-lookup"><span data-stu-id="9342a-230">**Cause**</span></span>  
  
 <span data-ttu-id="9342a-231">**かどうかはデータがないポーリングされるテーブルで使用できる**後にすべて受信タイムアウトのサイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。</span><span class="sxs-lookup"><span data-stu-id="9342a-231">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="9342a-232">そのため、期間のスレッドの数とメモリ使用量が増加します。</span><span class="sxs-lookup"><span data-stu-id="9342a-232">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="9342a-233">ただし、ポーリングされるテーブルにいくつかのデータがある場合、同じスレッドは、すべての後続のポーリングを実行する継続します。</span><span class="sxs-lookup"><span data-stu-id="9342a-233">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="9342a-234">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="9342a-234">**Resolution**</span></span>  
  
 <span data-ttu-id="9342a-235">設定をお勧め、 **ReceiveTimeout**に最大の可能な値である 24.20:31:23.6470000 (24 日)、新しいスレッドは 24 日間にのみを生成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9342a-235">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="9342a-236">メモリ使用量とスレッドの数が大きくが多すぎるが早すぎるようになります。</span><span class="sxs-lookup"><span data-stu-id="9342a-236">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9342a-237">SqlAdapterInboundTransactionBehavior が設定されている場合、TransactionTimeout が 24.20:31:23.6470000 (24 日) である最大の可能な値にも構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9342a-237">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="9342a-238">この回避策を使用する場合、トランザクション分離レベルを構成する場合のみ、SqlAdapterInboundTransactionBehavior を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9342a-238">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="9342a-239">それ以外の場合、これはその動作を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9342a-239">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="9342a-240">詳細については、 **ReceiveTimeout**プロパティ、バインドを参照してください[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="9342a-240">For more information about the **ReceiveTimeout** binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="9342a-241">バインドのプロパティを指定する方法の詳細については、次を参照してください。 [SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9342a-241">For instructions on specifying binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9342a-242">アダプターを使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。</span><span class="sxs-lookup"><span data-stu-id="9342a-242">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9342a-243">参照</span><span class="sxs-lookup"><span data-stu-id="9342a-243">See Also</span></span>  
[<span data-ttu-id="9342a-244">SQL アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="9342a-244">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
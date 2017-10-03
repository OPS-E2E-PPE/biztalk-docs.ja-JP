---
title: "SQL Server とアダプターのクライアント上の MSDTC を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c87f455-a8c4-4169-bf18-695926136df1
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf519044dc28d417d85682189dd4a52585310ac0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-msdtc-on-sql-server-and-adapter-client"></a><span data-ttu-id="90d27-102">SQL Server とアダプターのクライアント上の MSDTC を構成します。</span><span class="sxs-lookup"><span data-stu-id="90d27-102">Configure MSDTC on SQL Server and adapter client</span></span>
<span data-ttu-id="90d27-103">SQL Server を使用して、操作を実行、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (を通じて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデルで、または WCF チャネル モデル)、トランザクション スコープ内で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="90d27-103">The operations performed on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the WCF service model, or the WCF channel model) can be performed within a transaction scope.</span></span> <span data-ttu-id="90d27-104">場合は、クライアント プログラムは、同じトランザクションの一部として 1 つ以上のトランザクション リソースを持つ、トランザクションが MSDTC トランザクションに昇格を取得します。</span><span class="sxs-lookup"><span data-stu-id="90d27-104">If the client program has more than one transactional resource as part of the same transaction, the transaction gets elevated to an MSDTC transaction.</span></span> <span data-ttu-id="90d27-105">MSDTC トランザクションのスコープ内で操作を実行するアダプターを有効にするを実行しているコンピューターで MSDTC を両方を構成する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="90d27-105">To enable the adapter to perform operations within the scope of an MSDTC transaction, you must configure MSDTC both on the computer running the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and SQL Server.</span></span> <span data-ttu-id="90d27-106">また、Windows ファイアウォールの例外の一覧に、MSDTC を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d27-106">Also, you must add MSDTC to the exceptions list of Windows Firewall.</span></span> <span data-ttu-id="90d27-107">このセクションでは、アダプターのクライアントと SQL Server を実行するコンピューターでこれらのタスクを実行する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="90d27-107">This section provides information about how to perform these tasks on computers running the adapter client and SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90d27-108">SQL Server を使用して操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]常に 2 つのリソースが含まれます: SQL Server と SQL Server 上に存在する BizTalk メッセージ ボックスに接続するアダプター。</span><span class="sxs-lookup"><span data-stu-id="90d27-108">Performing operations on SQL Server using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] always involves two resources—the adapter connecting to SQL Server and the BizTalk Message Box residing on SQL Server.</span></span> <span data-ttu-id="90d27-109">そのため、すべての操作は実行を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC トランザクションのスコープ内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="90d27-109">Hence, all operations performed using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] are performed within the scope of an MSDTC transaction.</span></span> <span data-ttu-id="90d27-110">使用する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC を常に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d27-110">So, to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always enable MSDTC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90d27-111">場所アダプター クライアントは、データに書き込みません、Select 操作などの SQL Server データベースの操作のトランザクション内の操作を実行するは、追加のオーバーヘッドをしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90d27-111">For operations where the adapter client does not write any data to the SQL Server database, such as a Select operation, you might not want the additional overhead of performing the operations inside a transaction.</span></span> <span data-ttu-id="90d27-112">構成することができます、このような場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を設定してトランザクション コンテキストを使用せずに操作を実行する、 **UseAmbientTransaction**にプロパティのバインド**false**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-112">In such cases, you can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform operations without a transactional context by setting the **UseAmbientTransaction** binding property to **false**.</span></span> <span data-ttu-id="90d27-113">バインディング プロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="90d27-113">For more information about the binding property, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="90d27-114">このような場合にも MSDTC を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="90d27-114">In such cases, you do not need to configure MSDTC as well.</span></span>  
  
## <a name="configure-msdtc"></a><span data-ttu-id="90d27-115">MSDTC を構成します。</span><span class="sxs-lookup"><span data-stu-id="90d27-115">Configure MSDTC</span></span>  
  
1.  <span data-ttu-id="90d27-116">開いている**コンポーネント サービス**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-116">Open **Component Services**.</span></span>  

    <span data-ttu-id="90d27-117">または、**サーバー マネージャー****ツール**、し、**コンポーネント サービス**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-117">Or, In **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>  
  
2.  <span data-ttu-id="90d27-118">展開**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**、展開**分散トランザクション コーディネーター**、右クリック**ローカル DTC**を選択して**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-118">Expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="90d27-119">**[セキュリティ]** タブをクリックします。このタブでは、次のすべてを選択します。</span><span class="sxs-lookup"><span data-stu-id="90d27-119">Select the **Security** tab. In this tab, select all of the following:</span></span> 

  - <span data-ttu-id="90d27-120">**ネットワーク DTC アクセス**</span><span class="sxs-lookup"><span data-stu-id="90d27-120">**Network DTC Access**</span></span>
  - <span data-ttu-id="90d27-121">**リモート クライアントを許可します。**</span><span class="sxs-lookup"><span data-stu-id="90d27-121">**Allow Remote Clients**</span></span> 
  - <span data-ttu-id="90d27-122">**受信を許可する**</span><span class="sxs-lookup"><span data-stu-id="90d27-122">**Allow Inbound**</span></span> 
  - <span data-ttu-id="90d27-123">**送信を許可する**</span><span class="sxs-lookup"><span data-stu-id="90d27-123">**Allow Outbound**</span></span> 
  - <span data-ttu-id="90d27-124">**必要ない Authetnication**</span><span class="sxs-lookup"><span data-stu-id="90d27-124">**No Authetnication Required**</span></span>
  
4.  <span data-ttu-id="90d27-125">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="90d27-125">Select **OK** to save your changes.</span></span>  
  
5.  <span data-ttu-id="90d27-126">MSDTC サービスを再起動するのには、メッセージが表示されたら、選択**はい**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-126">If prompted to restarted the MSDTC service, select **Yes**.</span></span> <span data-ttu-id="90d27-127">MSDTC サービスを再起動した後は、プロパティとコンポーネント サービス MMC を閉じます。</span><span class="sxs-lookup"><span data-stu-id="90d27-127">After the MSDTC service is restarted, close the properties and the Component Services MMC.</span></span> 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a><span data-ttu-id="90d27-128">MSDTC を Windows ファイアウォールの例外リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="90d27-128">Add MSDTC to Windows Firewall exceptions list</span></span>  

> [!TIP] 
>  <span data-ttu-id="90d27-129">Microsoft 分散 Tansaction コーディネーター (MSDTC) は、ファイアウォールで既にできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="90d27-129">Microsoft Distributed Tansaction Coordinator (MSDTC) may already be allowed in your firewall.</span></span> <span data-ttu-id="90d27-130">その場合は、受信の規則として表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d27-130">If so, it is listed as an Inbound Rule.</span></span> <span data-ttu-id="90d27-131">表示されない場合は、このセクションを使用して、MSDTC を許可します。</span><span class="sxs-lookup"><span data-stu-id="90d27-131">If it's not listed, use this section to allow MSDTC.</span></span> 

1.  <span data-ttu-id="90d27-132">開いている**Windows ファイアウォール**を選択し、**詳細設定**左側です。</span><span class="sxs-lookup"><span data-stu-id="90d27-132">Open **Windows Firewall**, and select **Advanced Settings** on the left.</span></span>  

    <span data-ttu-id="90d27-133">または、**サーバー マネージャー****ツール**、し、**セキュリティが強化された Windows ファイアウォール**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-133">Or, In **Server Manager**, select **Tools**, and then select **Windows Firewall with Advanced Security**.</span></span>  
  
2.  <span data-ttu-id="90d27-134">右クリックして**受信の規則**を選択して**新しいルール**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-134">Right click **Inbound Rules**, and select **New Rule**.</span></span>  
  
3.  <span data-ttu-id="90d27-135">ウィザード。</span><span class="sxs-lookup"><span data-stu-id="90d27-135">In the wizard:</span></span> 

    1. <span data-ttu-id="90d27-136">選択**プログラム**を選択して**次**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-136">Select **Program**, and select **Next**.</span></span> 
    2. <span data-ttu-id="90d27-137">設定、**プログラムのパス**に`%SystemRoot%\system32\msdtc.exe`を選択し、**次**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-137">Set the **program path** to `%SystemRoot%\system32\msdtc.exe`, and select **Next**.</span></span>  
    3. <span data-ttu-id="90d27-138">**接続を許可する**を選択して**次**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-138">**Allow the connection**, and select **Next**.</span></span>
    4. <span data-ttu-id="90d27-139">選択**ドメイン**を選択して**次**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-139">Select **Domain**, and select **Next**.</span></span>
    5. <span data-ttu-id="90d27-140">など、任意の名前を入力`MSDTC for Oracle EBS`を選択して**完了**です。</span><span class="sxs-lookup"><span data-stu-id="90d27-140">Enter any name, such as `MSDTC for Oracle EBS`, and select **Finish**.</span></span>
  
5.  <span data-ttu-id="90d27-141">ウィザードを完了し、Windows ファイアウォールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="90d27-141">Complete the wizard, and close Windows Firewall.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="90d27-142">参照</span><span class="sxs-lookup"><span data-stu-id="90d27-142">See Also</span></span>  
[<span data-ttu-id="90d27-143">SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="90d27-143">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)
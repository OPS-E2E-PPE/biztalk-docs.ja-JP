---
title: "Oracle E-business Suite のトランザクションを許可する MS 分散トランザクション コーディネーターを有効にする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0597c050e1531d71a62af04fe6c825653076297c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a><span data-ttu-id="02732-102">Oracle E-business Suite のトランザクションを許可する MS 分散トランザクション コーディネーターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="02732-102">Enable MS distributed transaction coordinator to allow transactions for Oracle E-Business Suite</span></span>
<span data-ttu-id="02732-103">使用するアプリケーションの作成を開始する前に、MSDTC を構成、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="02732-103">Configure MSDTC before you start creating applications that use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
<span data-ttu-id="02732-104">Oracle E-business Suite を使用して、操作を実行、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (を通じて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデルで、または WCF チャネル モデル)、トランザクション スコープ内で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="02732-104">The operations performed on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the WCF service model, or the WCF channel model) can be performed within a transaction scope.</span></span> <span data-ttu-id="02732-105">場合は、クライアント プログラムは、同じトランザクションの一部として 1 つ以上のトランザクション リソースを持つ、トランザクションが MSDTC トランザクションに昇格を取得します。</span><span class="sxs-lookup"><span data-stu-id="02732-105">If the client program has more than one transactional resource as part of the same transaction, the transaction gets elevated to an MSDTC transaction.</span></span> <span data-ttu-id="02732-106">MSDTC トランザクションのスコープ内で操作を実行するアダプターを有効にするを実行しているコンピューターで MSDTC を構成、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、および Oracle E-business Suite でします。</span><span class="sxs-lookup"><span data-stu-id="02732-106">To enable the adapter to perform operations within the scope of an MSDTC transaction, configure MSDTC on the computer running the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], and on the Oracle E-Business Suite.</span></span> <span data-ttu-id="02732-107">また、追加 MSDTC、ファイアウォールの例外の一覧に、組み込みの Windows ファイアウォールがあります。</span><span class="sxs-lookup"><span data-stu-id="02732-107">Also, add MSDTC to the exceptions list in your firewall, which may be the built-in Windows Firewall.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="02732-108">MSDTC を構成する手順は、さまざまなオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="02732-108">The steps to configure MSDTC vary for different operating systems.</span></span> <span data-ttu-id="02732-109">このトピックに記載された手順は、Windows クライアントおよび Windows Server オペレーティング システムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="02732-109">The steps listed in this topic apply to Windows client and Windows Server operating systems.</span></span>  
  
## <a name="configure-msdtc"></a><span data-ttu-id="02732-110">MSDTC を構成します。</span><span class="sxs-lookup"><span data-stu-id="02732-110">Configure MSDTC</span></span>  
  
1.  <span data-ttu-id="02732-111">開いている**コンポーネント サービス**です。</span><span class="sxs-lookup"><span data-stu-id="02732-111">Open **Component Services**.</span></span>  

    <span data-ttu-id="02732-112">または、**サーバー マネージャー****ツール**、し、**コンポーネント サービス**です。</span><span class="sxs-lookup"><span data-stu-id="02732-112">Or, In **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>  
  
2.  <span data-ttu-id="02732-113">展開**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**、展開**分散トランザクション コーディネーター**、右クリック**ローカル DTC**を選択して**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="02732-113">Expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="02732-114">**[セキュリティ]** タブをクリックします。このタブでは、次のすべてを選択します。</span><span class="sxs-lookup"><span data-stu-id="02732-114">Select the **Security** tab. In this tab, select all of the following:</span></span> 

  - <span data-ttu-id="02732-115">**ネットワーク DTC アクセス**</span><span class="sxs-lookup"><span data-stu-id="02732-115">**Network DTC Access**</span></span>
  - <span data-ttu-id="02732-116">**リモート クライアントを許可します。**</span><span class="sxs-lookup"><span data-stu-id="02732-116">**Allow Remote Clients**</span></span> 
  - <span data-ttu-id="02732-117">**受信を許可する**</span><span class="sxs-lookup"><span data-stu-id="02732-117">**Allow Inbound**</span></span> 
  - <span data-ttu-id="02732-118">**送信を許可する**</span><span class="sxs-lookup"><span data-stu-id="02732-118">**Allow Outbound**</span></span> 
  - <span data-ttu-id="02732-119">**必要ない Authetnication**</span><span class="sxs-lookup"><span data-stu-id="02732-119">**No Authetnication Required**</span></span>
  
4.  <span data-ttu-id="02732-120">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="02732-120">Select **OK** to save your changes.</span></span>  
  
5.  <span data-ttu-id="02732-121">MSDTC サービスを再起動するのには、メッセージが表示されたら、選択**はい**です。</span><span class="sxs-lookup"><span data-stu-id="02732-121">If prompted to restarted the MSDTC service, select **Yes**.</span></span> <span data-ttu-id="02732-122">MSDTC サービスを再起動した後は、プロパティとコンポーネント サービス MMC を閉じます。</span><span class="sxs-lookup"><span data-stu-id="02732-122">After the MSDTC service is restarted, close the properties and the Component Services MMC.</span></span> 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a><span data-ttu-id="02732-123">MSDTC を Windows ファイアウォールの例外リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="02732-123">Add MSDTC to Windows Firewall exceptions list</span></span>  

> [!TIP] 
>  <span data-ttu-id="02732-124">Microsoft 分散 Tansaction コーディネーター (MSDTC) は、ファイアウォールで既にできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02732-124">Microsoft Distributed Tansaction Coordinator (MSDTC) may already be allowed in your firewall.</span></span> <span data-ttu-id="02732-125">その場合は、受信の規則として表示されます。</span><span class="sxs-lookup"><span data-stu-id="02732-125">If so, it is listed as an Inbound Rule.</span></span> <span data-ttu-id="02732-126">表示されない場合は、このセクションを使用して、MSDTC を許可します。</span><span class="sxs-lookup"><span data-stu-id="02732-126">If it's not listed, use this section to allow MSDTC.</span></span> 

1.  <span data-ttu-id="02732-127">開いている**Windows ファイアウォール**を選択し、**詳細設定**左側です。</span><span class="sxs-lookup"><span data-stu-id="02732-127">Open **Windows Firewall**, and select **Advanced Settings** on the left.</span></span>  

    <span data-ttu-id="02732-128">または、**サーバー マネージャー****ツール**、し、**セキュリティが強化された Windows ファイアウォール**です。</span><span class="sxs-lookup"><span data-stu-id="02732-128">Or, In **Server Manager**, select **Tools**, and then select **Windows Firewall with Advanced Security**.</span></span>  
  
2.  <span data-ttu-id="02732-129">右クリックして**受信の規則**を選択して**新しいルール**です。</span><span class="sxs-lookup"><span data-stu-id="02732-129">Right click **Inbound Rules**, and select **New Rule**.</span></span>  
  
3.  <span data-ttu-id="02732-130">ウィザード。</span><span class="sxs-lookup"><span data-stu-id="02732-130">In the wizard:</span></span> 

    1. <span data-ttu-id="02732-131">選択**プログラム**を選択して**次**です。</span><span class="sxs-lookup"><span data-stu-id="02732-131">Select **Program**, and select **Next**.</span></span> 
    2. <span data-ttu-id="02732-132">設定、**プログラムのパス**に`%SystemRoot%\system32\msdtc.exe`を選択し、**次**です。</span><span class="sxs-lookup"><span data-stu-id="02732-132">Set the **program path** to `%SystemRoot%\system32\msdtc.exe`, and select **Next**.</span></span>  
    3. <span data-ttu-id="02732-133">**接続を許可する**を選択して**次**です。</span><span class="sxs-lookup"><span data-stu-id="02732-133">**Allow the connection**, and select **Next**.</span></span>
    4. <span data-ttu-id="02732-134">選択**ドメイン**を選択して**次**です。</span><span class="sxs-lookup"><span data-stu-id="02732-134">Select **Domain**, and select **Next**.</span></span>
    5. <span data-ttu-id="02732-135">など、任意の名前を入力`MSDTC for Oracle EBS`を選択して**完了**です。</span><span class="sxs-lookup"><span data-stu-id="02732-135">Enter any name, such as `MSDTC for Oracle EBS`, and select **Finish**.</span></span>
  
5.  <span data-ttu-id="02732-136">ウィザードを完了し、Windows ファイアウォールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="02732-136">Complete the wizard, and close Windows Firewall.</span></span> 
  
## <a name="next"></a><span data-ttu-id="02732-137">Next</span><span class="sxs-lookup"><span data-stu-id="02732-137">Next</span></span> 
[<span data-ttu-id="02732-138">Oracle EBS アダプター用のサンプル</span><span class="sxs-lookup"><span data-stu-id="02732-138">Samples for the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)
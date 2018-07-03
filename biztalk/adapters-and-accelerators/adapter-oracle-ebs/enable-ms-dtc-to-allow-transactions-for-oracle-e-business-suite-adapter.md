---
title: Oracle E-business Suite のトランザクションを許可する MS 分散トランザクション コーディネーターを有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53037e9a7dc1ccc3c0ef21860696060ad1c046a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984995"
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a><span data-ttu-id="85fd9-102">Oracle E-business Suite のトランザクションを許可する MS 分散トランザクション コーディネーターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="85fd9-102">Enable MS distributed transaction coordinator to allow transactions for Oracle E-Business Suite</span></span>
<span data-ttu-id="85fd9-103">使用するアプリケーションの作成を開始する前に、MSDTC を構成、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-103">Configure MSDTC before you start creating applications that use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
<span data-ttu-id="85fd9-104">Oracle E-business Suite を使用して、操作を実行、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (を通じて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデル、または WCF チャネル モデル)、トランザクション スコープ内で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="85fd9-104">The operations performed on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the WCF service model, or the WCF channel model) can be performed within a transaction scope.</span></span> <span data-ttu-id="85fd9-105">クライアント プログラムは、1 つ以上のトランザクション リソースを同じトランザクションの一部としては場合、トランザクションは MSDTC トランザクションに昇格を取得します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-105">If the client program has more than one transactional resource as part of the same transaction, the transaction gets elevated to an MSDTC transaction.</span></span> <span data-ttu-id="85fd9-106">MSDTC トランザクションのスコープ内での操作を実行するアダプターを有効にするには、実行しているコンピューターで MSDTC を構成、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、Oracle E-business suite とします。</span><span class="sxs-lookup"><span data-stu-id="85fd9-106">To enable the adapter to perform operations within the scope of an MSDTC transaction, configure MSDTC on the computer running the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], and on the Oracle E-Business Suite.</span></span> <span data-ttu-id="85fd9-107">また、追加 MSDTC ファイアウォールで、例外の一覧に、組み込みの Windows ファイアウォールがあります。</span><span class="sxs-lookup"><span data-stu-id="85fd9-107">Also, add MSDTC to the exceptions list in your firewall, which may be the built-in Windows Firewall.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="85fd9-108">MSDTC を構成する手順は、さまざまなオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="85fd9-108">The steps to configure MSDTC vary for different operating systems.</span></span> <span data-ttu-id="85fd9-109">このトピックに記載の手順は、Windows クライアントおよび Windows Server オペレーティング システムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="85fd9-109">The steps listed in this topic apply to Windows client and Windows Server operating systems.</span></span>  
  
## <a name="configure-msdtc"></a><span data-ttu-id="85fd9-110">MSDTC を構成します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-110">Configure MSDTC</span></span>  
  
1. <span data-ttu-id="85fd9-111">開いている**コンポーネント サービス**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-111">Open **Component Services**.</span></span>  

   <span data-ttu-id="85fd9-112">または、**サーバー マネージャー**、**ツール**、し、**コンポーネント サービス**。</span><span class="sxs-lookup"><span data-stu-id="85fd9-112">Or, In **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>  
  
2. <span data-ttu-id="85fd9-113">展開**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**、展開**分散トランザクション コーディネーター**、右クリック**ローカル DTC**、選び**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-113">Expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and select **Properties**.</span></span>  
  
3. <span data-ttu-id="85fd9-114">**[セキュリティ]** タブをクリックします。このタブでは、次のすべてを選択します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-114">Select the **Security** tab. In this tab, select all of the following:</span></span> 

   - <span data-ttu-id="85fd9-115">**ネットワーク DTC アクセス**</span><span class="sxs-lookup"><span data-stu-id="85fd9-115">**Network DTC Access**</span></span>
   - <span data-ttu-id="85fd9-116">**リモート クライアントを許可します。**</span><span class="sxs-lookup"><span data-stu-id="85fd9-116">**Allow Remote Clients**</span></span> 
   - <span data-ttu-id="85fd9-117">**受信を許可する**</span><span class="sxs-lookup"><span data-stu-id="85fd9-117">**Allow Inbound**</span></span> 
   - <span data-ttu-id="85fd9-118">**送信を許可する**</span><span class="sxs-lookup"><span data-stu-id="85fd9-118">**Allow Outbound**</span></span> 
   - <span data-ttu-id="85fd9-119">**必要ない Authetnication**</span><span class="sxs-lookup"><span data-stu-id="85fd9-119">**No Authetnication Required**</span></span>
  
4. <span data-ttu-id="85fd9-120">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-120">Select **OK** to save your changes.</span></span>  
  
5. <span data-ttu-id="85fd9-121">MSDTC サービスを再起動するメッセージが表示されたら、選択**はい**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-121">If prompted to restarted the MSDTC service, select **Yes**.</span></span> <span data-ttu-id="85fd9-122">MSDTC サービスが再起動した後は、プロパティとコンポーネント サービス MMC を閉じます。</span><span class="sxs-lookup"><span data-stu-id="85fd9-122">After the MSDTC service is restarted, close the properties and the Component Services MMC.</span></span> 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a><span data-ttu-id="85fd9-123">MSDTC を Windows ファイアウォールの例外リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-123">Add MSDTC to Windows Firewall exceptions list</span></span>  

> [!TIP] 
>  <span data-ttu-id="85fd9-124">Microsoft 分散 Tansaction コーディネーター (MSDTC) は、ファイアウォールで既に許可場合があります。</span><span class="sxs-lookup"><span data-stu-id="85fd9-124">Microsoft Distributed Tansaction Coordinator (MSDTC) may already be allowed in your firewall.</span></span> <span data-ttu-id="85fd9-125">そうである場合は、受信の規則として表示されます。</span><span class="sxs-lookup"><span data-stu-id="85fd9-125">If so, it is listed as an Inbound Rule.</span></span> <span data-ttu-id="85fd9-126">表示されない場合は、このセクションを使用して、MSDTC を許可します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-126">If it's not listed, use this section to allow MSDTC.</span></span> 

1.  <span data-ttu-id="85fd9-127">開いている**Windows ファイアウォール**を選択し、**詳細設定**左側にします。</span><span class="sxs-lookup"><span data-stu-id="85fd9-127">Open **Windows Firewall**, and select **Advanced Settings** on the left.</span></span>  

    <span data-ttu-id="85fd9-128">または、**サーバー マネージャー**、**ツール**、し、**セキュリティが強化された Windows ファイアウォール**。</span><span class="sxs-lookup"><span data-stu-id="85fd9-128">Or, In **Server Manager**, select **Tools**, and then select **Windows Firewall with Advanced Security**.</span></span>  
  
2.  <span data-ttu-id="85fd9-129">右クリックして**受信の規則**、選択および**新しいルール**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-129">Right click **Inbound Rules**, and select **New Rule**.</span></span>  
  
3.  <span data-ttu-id="85fd9-130">ウィザード。</span><span class="sxs-lookup"><span data-stu-id="85fd9-130">In the wizard:</span></span> 

    1. <span data-ttu-id="85fd9-131">選択**プログラム**を選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-131">Select **Program**, and select **Next**.</span></span> 
    2. <span data-ttu-id="85fd9-132">設定、**プログラムのパス**に`%SystemRoot%\system32\msdtc.exe`を選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-132">Set the **program path** to `%SystemRoot%\system32\msdtc.exe`, and select **Next**.</span></span>  
    3. <span data-ttu-id="85fd9-133">**接続を許可する**、選び**次**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-133">**Allow the connection**, and select **Next**.</span></span>
    4. <span data-ttu-id="85fd9-134">選択**ドメイン**を選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-134">Select **Domain**, and select **Next**.</span></span>
    5. <span data-ttu-id="85fd9-135">などの任意の名前を入力します`MSDTC for Oracle EBS`、選び**完了**します。</span><span class="sxs-lookup"><span data-stu-id="85fd9-135">Enter any name, such as `MSDTC for Oracle EBS`, and select **Finish**.</span></span>
  
5.  <span data-ttu-id="85fd9-136">ウィザードを完了し、Windows ファイアウォールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="85fd9-136">Complete the wizard, and close Windows Firewall.</span></span> 
  
## <a name="next"></a><span data-ttu-id="85fd9-137">Next</span><span class="sxs-lookup"><span data-stu-id="85fd9-137">Next</span></span> 
[<span data-ttu-id="85fd9-138">Oracle EBS アダプター用のサンプル</span><span class="sxs-lookup"><span data-stu-id="85fd9-138">Samples for the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)
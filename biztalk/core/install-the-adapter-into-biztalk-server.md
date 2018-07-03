---
title: BizTalk Server にアダプターのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1164468d-75a9-4116-87a6-6055948c198b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13e810a14fec9b51c0d6b0ef1d7b55db234d0a0b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005627"
---
# <a name="install-the-adapter-into-biztalk-server"></a><span data-ttu-id="93b27-102">BizTalk Server へのアダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="93b27-102">Install the Adapter into BizTalk Server</span></span>
<span data-ttu-id="93b27-103">適切な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エントリがレジストリに書き込まれた後に、アダプターを BizTalk 管理データベースに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93b27-103">After the proper [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entries have been written to the registry the adapter must be added to the BizTalk Management database.</span></span> <span data-ttu-id="93b27-104">アダプターをこのデータベースに追加すると、アクティブに構成されたアダプターになり、正しく構成されている場合はメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="93b27-104">After the adapter is added to this database it is an actively configured adapter and can process messages when it is properly configured.</span></span> <span data-ttu-id="93b27-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用してアダプターをデータベースにインストールします。</span><span class="sxs-lookup"><span data-stu-id="93b27-105">You install the adapter into the database by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="93b27-106">データベース内のアダプターをインストールした後に、ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="93b27-106">After installing the adapter in the database, restart the host instance.</span></span>  

> [!NOTE]
>  <span data-ttu-id="93b27-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで追加した内容を表示できるようにするには、アダプターを HKLM レジストリに正しく登録し、必要なアダプター インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93b27-107">To be visible for addition in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, an adapter must be properly registered in the HKLM registry and must implement the necessary adapter interfaces.</span></span>  

### <a name="to-install-the-static-sample-adapter"></a><span data-ttu-id="93b27-108">静的なサンプル アダプターをインストールするには</span><span class="sxs-lookup"><span data-stu-id="93b27-108">To install the static sample adapter</span></span>  

1. <span data-ttu-id="93b27-109">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="93b27-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ダブルクリックして、 **BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="93b27-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the  **BizTalk Group** node.</span></span>  

3. <span data-ttu-id="93b27-111">展開**プラットフォームの設定**選択**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-111">Expand **Platform Settings** and select **Adapters**.</span></span>  

4. <span data-ttu-id="93b27-112">右クリック**アダプター**、 をクリックして**新規**、 をクリックし、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-112">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  

5. <span data-ttu-id="93b27-113">**アダプター プロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="93b27-113">In the **Adapter Properties** dialog box, do the following.</span></span>  


   |  <span data-ttu-id="93b27-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="93b27-114">Use this</span></span>   |                      <span data-ttu-id="93b27-115">目的</span><span class="sxs-lookup"><span data-stu-id="93b27-115">To do this</span></span>                       |
   |-------------|-------------------------------------------------------|
   |    <span data-ttu-id="93b27-116">名前</span><span class="sxs-lookup"><span data-stu-id="93b27-116">Name</span></span>     |                   <span data-ttu-id="93b27-117">型**静的**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-117">Type **Static**.</span></span>                    |
   |   <span data-ttu-id="93b27-118">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="93b27-118">Adapter</span></span>   | <span data-ttu-id="93b27-119">選択**Static dotnetfile**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="93b27-119">Select **Static DotNetFile** from the drop-down list.</span></span> |
   | <span data-ttu-id="93b27-120">説明</span><span class="sxs-lookup"><span data-stu-id="93b27-120">Description</span></span> |            <span data-ttu-id="93b27-121">型**静的アダプターのサンプル**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-121">Type **Sample Static Adapter**.</span></span>            |


6. <span data-ttu-id="93b27-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93b27-122">Click **OK**.</span></span>  

    <span data-ttu-id="93b27-123">これで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの右ウィンドウにあるアダプターの一覧に静的アダプターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93b27-123">The static adapter now appears in the list of adapters in the right window of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="to-stop-and-restart-the-host-instance"></a><span data-ttu-id="93b27-124">停止して、ホスト インスタンスを再起動するには</span><span class="sxs-lookup"><span data-stu-id="93b27-124">To stop and restart the host instance</span></span>  

1. <span data-ttu-id="93b27-125">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-125">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**.</span></span>  

2. <span data-ttu-id="93b27-126">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ダブルクリックして、 **BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="93b27-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the  **BizTalk Group** node.</span></span>  

3. <span data-ttu-id="93b27-127">展開**プラットフォームの設定**を選択します**ホスト**、し、 **BizTalkServerApplication**結果ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="93b27-127">Expand **Platform Settings**, select **Hosts**, and then select **BizTalkServerApplication** in the results pane.</span></span>  

4. <span data-ttu-id="93b27-128">ホスト インスタンス (通常は、コンピューター名) を右クリックし、をクリックし、**停止**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-128">Right-click the host instance (typically, the computer name), and then click **Stop**.</span></span>  

    <span data-ttu-id="93b27-129">ホスト インスタンスの状態に変わる**Stopped**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-129">The status of the host instance changes to **Stopped**.</span></span>  

5. <span data-ttu-id="93b27-130">結果ウィンドウで、ホスト インスタンスを右クリックし をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-130">In the results pane, right-click the host instance, and then click **Start**.</span></span>  

    <span data-ttu-id="93b27-131">ホスト インスタンスの状態に変わる**開始待ち**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-131">The status of the host instance changes to **Start pending**.</span></span> <span data-ttu-id="93b27-132">クリックする必要があります**更新**、またはホスト インスタンスを右クリックし、をクリックし、**更新**に状態を変更するには、**を実行している**します。</span><span class="sxs-lookup"><span data-stu-id="93b27-132">You must click **Refresh**, or right-click the host instance and then click **Refresh**, to change the status to **Running**.</span></span>
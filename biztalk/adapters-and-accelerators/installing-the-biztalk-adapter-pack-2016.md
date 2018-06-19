---
title: BizTalk Adapter Pack 2016 のインストール |Microsoft ドキュメント
description: BAP 2016、32 ビットと 64 ビットの標準またはカスタムのインストールはサイレント モードでインストールします。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f3e1717-8063-4460-bfdc-a933cd58a5c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7076b9c076b263a54a436c553b519671760ca473
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967792"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="80ce6-103">BizTalk Adapter Pack 2016 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-103">Install the BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="80ce6-104">インストール、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次の 2 つの方法で。</span><span class="sxs-lookup"><span data-stu-id="80ce6-104">Install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="80ce6-105">**対話モードで**: セットアップ ウィザードを実行</span><span class="sxs-lookup"><span data-stu-id="80ce6-105">**In interactive mode**: Run the setup wizard</span></span>  
  
-   <span data-ttu-id="80ce6-106">**サイレント モードで**: コマンドラインを使用して</span><span class="sxs-lookup"><span data-stu-id="80ce6-106">**In silent mode**: Use the command line</span></span>  
  
> [!IMPORTANT]
> - <span data-ttu-id="80ce6-107">インストールするコンピューターで管理者特権を持つ必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ウィザードまたはコマンドラインを使用してをインストールするかどうかのあるかにかかわらず、します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-107">You must have administrative privileges on the computer where you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], irrespective of whether you are installing using the wizard, or the command line.</span></span>  
> - <span data-ttu-id="80ce6-108">すべてのことを確認する、[ソフトウェアの前提条件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)がインストールする前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-108">Be sure all the [software prerequisites](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) are installed before installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>

## <a name="typical-vs-custom-installation"></a><span data-ttu-id="80ce6-109">標準セットアップとカスタム インストール</span><span class="sxs-lookup"><span data-stu-id="80ce6-109">Typical vs custom installation</span></span>  
<span data-ttu-id="80ce6-110">インストールの種類と各オプションでインストールされている機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-110">Lists the installation types, and the features that are installed with each option:</span></span>  
  
-   <span data-ttu-id="80ce6-111">**標準**と**完了**オプションは、関連付けられているデータ プロバイダーとすべてのアダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-111">The **Typical** and **Complete** options install all the adapters, with the associated data providers.</span></span> <span data-ttu-id="80ce6-112">インストールする特定のアダプターを選択するオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="80ce6-112">You do not have the option of choosing a specific adapter to install.</span></span>  
  
-   <span data-ttu-id="80ce6-113">**カスタム**オプションは、関連付けられているデータ プロバイダーと 1 つまたは複数のアダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-113">The **Custom** option installs one or more adapters, with the associated data providers.</span></span> <span data-ttu-id="80ce6-114">インストールするには、どのアダプターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-114">You can choose which adapters to install.</span></span> <span data-ttu-id="80ce6-115">データ プロバイダーをインストールする場合は、また、対応するアダプターをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80ce6-115">If you choose to install a data provider, you must also install the corresponding adapter.</span></span> <span data-ttu-id="80ce6-116">ただし、対応するデータ プロバイダーをインストールしなくても、アダプターをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-116">However, you can install an adapter without installing the corresponding data provider.</span></span> <span data-ttu-id="80ce6-117">これには、展開、 **ADO プロバイダー**ノード、およびインストールしたくないプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-117">Do this by expanding the **ADO Providers** node, and then selecting the providers that you don't want to install.</span></span> <span data-ttu-id="80ce6-118">参照してください**セットアップ ウィザードを使用してインストール**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="80ce6-118">See **Install using the setup wizard** (in this topic).</span></span>  
  
     <span data-ttu-id="80ce6-119">たとえば、インストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]もインストールする必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-119">For example, if you install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], you must also install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="80ce6-120">ただし、インストールすることができます、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]インストールしなくても、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-120">However, you can install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] without installing the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span>  
  
## <a name="32-bit-and-64-bit-install-scenarios"></a><span data-ttu-id="80ce6-121">32 ビットおよび 64 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="80ce6-121">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="80ce6-122">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]に使用できます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-122">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] can be used for:</span></span> 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="80ce6-123">デザイン時 (場合、LOB アプリケーションでの操作のメタデータの生成)</span><span class="sxs-lookup"><span data-stu-id="80ce6-123"> design time (when generating metadata for operations on LOB applications)</span></span>
  
-   <span data-ttu-id="80ce6-124">BizTalk Server 管理コンソール デザイン時 (物理ポートの作成)</span><span class="sxs-lookup"><span data-stu-id="80ce6-124">BizTalk Server Administration console design time (for creating physical ports)</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="80ce6-125">BizTalk Server 管理コンソールは、32 ビット Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-125">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="80ce6-126">BizTalk ランタイム (ときに送信し、LOB アプリケーションからメッセージを受信)</span><span class="sxs-lookup"><span data-stu-id="80ce6-126">BizTalk run time (when sending and receiving messages from LOB applications)</span></span>

<span data-ttu-id="80ce6-127">これらすべての検索の 1 台のコンピューターを使用したり、別のコンピューターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-127">You can use a single computer for all these taks, or use different computers.</span></span> <span data-ttu-id="80ce6-128">両方[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]と BizTalk MMC は 32 ビット プロセスが、32 ビットをインストールする必要があります[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]デザイン時のタスクを完了するコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-128">Because both [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on the computer where you complete the design-time tasks.</span></span> 

### <a name="32-bit-install-scenario"></a><span data-ttu-id="80ce6-129">32 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="80ce6-129">32-bit install scenario</span></span>
<span data-ttu-id="80ce6-130">各コンピューターで、次のソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-130">Install the following software on each computer.</span></span> <span data-ttu-id="80ce6-131">1 台のコンピューターを使用している場合、そのコンピューターにすべてのソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80ce6-131">If you are using a single computer, all the software must be installed on that computer.</span></span> 
 
1. <span data-ttu-id="80ce6-132">32 ビットをインストールします。[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ce6-132">Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</span></span>
2. <span data-ttu-id="80ce6-133">32 ビット インストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-133">Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>
3. <span data-ttu-id="80ce6-134">32 ビットのインストールの LOB クライアントおよびその他の Dll が必要です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-134">Install 32-bit LOB client and other required DLLs.</span></span>  
  
### <a name="64-bit-install-scenarios"></a><span data-ttu-id="80ce6-135">64 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="80ce6-135">64-bit install scenarios</span></span>
  
|<span data-ttu-id="80ce6-136">Visual Studio のデザイン時の</span><span class="sxs-lookup"><span data-stu-id="80ce6-136">For Visual Studio design time</span></span>|<span data-ttu-id="80ce6-137">MMC の BizTalk のデザイン時</span><span class="sxs-lookup"><span data-stu-id="80ce6-137">For BizTalk MMC design time</span></span>|<span data-ttu-id="80ce6-138">Biztalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="80ce6-138">For BizTalk run time</span></span>|<span data-ttu-id="80ce6-139">Visual Studio のデザイン時およびデザイン時の BizTalk MMC + BizTalk 実行時間</span><span class="sxs-lookup"><span data-stu-id="80ce6-139">For Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="80ce6-140">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-140">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-141">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-141">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-142">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-142">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="80ce6-143">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-143">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-144">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-144">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-145">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-145">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="80ce6-146">**32 ビット BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="80ce6-146">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="80ce6-147">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-147">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-148">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-148">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-149">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-149">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="80ce6-150">**64 ビットの BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="80ce6-150">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="80ce6-151">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-151">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-152">がインストール 64 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-152">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-153">-64 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-153">- Install 64-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="80ce6-154">**32 ビット BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="80ce6-154">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="80ce6-155">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-155">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-156">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-156">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-157">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-157">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="80ce6-158">**64 ビットの BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="80ce6-158">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="80ce6-159">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-159">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-160">がインストール 64 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-160">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-161">-64 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-161">- Install 64-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="80ce6-162">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-162">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="80ce6-163">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-163">- Install 32-bit LOB client and other required DLLs.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="80ce6-164">デザイン時のタスクを実行する任意のコンピューターでいずれかの操作を使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-164">On any computer where you want to do design-time tasks, using either [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="install-using-the-setup-wizard"></a><span data-ttu-id="80ce6-165">セットアップ ウィザードを使用したインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-165">Install using the setup wizard</span></span>  
<span data-ttu-id="80ce6-166">インストールする手順、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モードでします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-166">Steps to install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode.</span></span>  
  
1.  <span data-ttu-id="80ce6-167">実行、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-167">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**.</span></span>  
  
2.  <span data-ttu-id="80ce6-168">選択**Microsoft BizTalk Adapters インストール**です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-168">Select **Install Microsoft BizTalk Adapters**.</span></span> <span data-ttu-id="80ce6-169">次のウィンドウで、前提条件のすべての不足しているプログラムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-169">In the next window, any missing prerequisite programs are listed.</span></span> <span data-ttu-id="80ce6-170">いずれかが存在しない場合、不足しているプログラムを選択し、セットアップでは、それをインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-170">If any are missing, then select the missing program, and setup installs it for you.</span></span> 

    <span data-ttu-id="80ce6-171">たとえば、選択**手順 2: Microsoft BizTalk Adapter Pack のインストール**または**手順 3: インストール Microsoft BizTalk Adapter Pack (x64)** です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-171">For example, select **Step 2: Install Microsoft BizTalk Adapter Pack** or **Step 3: Install Microsoft BizTalk Adapter Pack (x64)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80ce6-172">インストールする場合、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]バーチャル マシンでは、セットアップ ウィザードの使用可能なディスク領域をチェックするメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-172">If you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on a virtual machine, the setup wizard may display a message that it's checking for available disk space.</span></span> <span data-ttu-id="80ce6-173">ハングまたはただ座っていて、このメッセージが表示されるかどうかは、ことをお勧め**サイレント モードでインストール**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="80ce6-173">If this message appears to hang or just sit there, then we recommend you **Install in silent mode** (in this topic).</span></span>  
  
3.  <span data-ttu-id="80ce6-174">[ようこそ] 画面で、次のように選択します。**次**です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-174">On the Welcome screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="80ce6-175">使用許諾契約書 (EULA) に同意し、**次**です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-175">Accept the end-user license agreement (EULA), and then select **Next**.</span></span>  
  
5.  <span data-ttu-id="80ce6-176">**セットアップの種類を選択して**:</span><span class="sxs-lookup"><span data-stu-id="80ce6-176">In **Choose Setup Type**:</span></span>  
  
    -   <span data-ttu-id="80ce6-177">最も一般的な機能をインストールする選択**標準**です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-177">To install the most common features, select **Typical**.</span></span>  
  
    -   <span data-ttu-id="80ce6-178">インストールするアダプターを選択するには、次のように選択します。**カスタム**、し、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-178">To select the adapters you want to install, select **Custom**, and then proceed to the next step.</span></span>  
  
    -   <span data-ttu-id="80ce6-179">すべての機能をインストールする選択**完了**です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-179">To install all the features, select **Complete**.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="80ce6-180">エンタープライズ アプリケーションとのインターフェイスで、選択に使用するアダプターのみをインストールする、**カスタム**インストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-180">To install only the adapter that you use to interface with your enterprise application, select the **Custom** installation.</span></span>  
  
6. <span data-ttu-id="80ce6-181">**必要な**カスタム インストールを選択した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="80ce6-181">**Required** only if you chose the Custom installation.</span></span> <span data-ttu-id="80ce6-182">選択した場合、**標準**または**完了**インストールし、この手順をスキップし、手順 7. に進みます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-182">If you chose the **Typical** or **Complete** installation, then skip this step, and go to step 7.</span></span>  
  
    1.  <span data-ttu-id="80ce6-183">**カスタム セットアップ**、展開**ベース アダプター**に利用可能なアダプターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="80ce6-183">In **Custom Setup**, expand **Base Adapters** to see the available adapters.</span></span>  
  
    2.  <span data-ttu-id="80ce6-184">必要のないアダプターの場合、アダプターの横にあるアイコンを選択し、**全体の機能は使用できません**です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-184">For the adapters that you don't want, select the icon next to the adapter, and then select **Entire feature will be unavailable**.</span></span>  
  
    3.  <span data-ttu-id="80ce6-185">展開**ADO プロバイダー**、しをインストールしたくないプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-185">Expand **ADO Providers**, and then select the providers that you don't want to install.</span></span>  
  
    4.  <span data-ttu-id="80ce6-186">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-186">Select **Next**.</span></span>  
  
7.  <span data-ttu-id="80ce6-187">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-187">Select **Install**.</span></span>  
  
8.  <span data-ttu-id="80ce6-188">**カスタマー エクスペリエンス向上プログラム**、登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-188">In **Customer Experience Improvement Program**, you can choose to enroll.</span></span> <span data-ttu-id="80ce6-189">登録する場合は、Microsoft と、次のデータを共有できます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-189">If you enroll, you can share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="80ce6-190">インストールしているコンピューターのハードウェアに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-190">Data related to the computer hardware on which you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="80ce6-191">使用するエンタープライズ アプリケーションのバージョンに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-191">Data related to the enterprise application versions you are using with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
     <span data-ttu-id="80ce6-192">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-192">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) provides more information.</span></span>  
     
     <span data-ttu-id="80ce6-193">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-193">Select **OK**.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="80ce6-194">修復モードで、セットアップを実行して、この設定を変更することが常に**プログラム**です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-194">You can always change this setting by running the Setup in Repair mode from **Programs**.</span></span>  
  
9. <span data-ttu-id="80ce6-195">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-195">Select **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a><span data-ttu-id="80ce6-196">サイレント モードでインストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-196">Install in silent mode</span></span>  
 <span data-ttu-id="80ce6-197">使用して、 **msiexec**サイレント インストールを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="80ce6-197">Use the **msiexec** command to do a silent installation.</span></span> <span data-ttu-id="80ce6-198">Msiexec コマンドの一部としてインストールする個々 のコンポーネントを入力します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-198">As part of the msiexec command, enter the individual components that you want to install.</span></span> <span data-ttu-id="80ce6-199">次の表に、内の各コンポーネントの値、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-199">The following table lists the values for each component in the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="80ce6-200">特定のコンポーネントをインストール (または削除) するのにには、これらの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-200">Use these values to install (or remove) specific components.</span></span> <span data-ttu-id="80ce6-201">ホスト インスタンスをインストール (または削除) するには、複数のコンポーネントは、コンマ区切りでこれらの値の組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-201">To install (or remove) more than one component, you can use a combination of these values separated by a comma.</span></span>  
  
|<span data-ttu-id="80ce6-202">コンポーネント名</span><span class="sxs-lookup"><span data-stu-id="80ce6-202">Component name</span></span>|<span data-ttu-id="80ce6-203">コマンド ライン プロパティの対応する値</span><span class="sxs-lookup"><span data-stu-id="80ce6-203">Corresponding value for command-line properties</span></span>|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|<span data-ttu-id="80ce6-204">DbFeature</span><span class="sxs-lookup"><span data-stu-id="80ce6-204">DbFeature</span></span>|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="80ce6-205">OracleEBSFeature</span><span class="sxs-lookup"><span data-stu-id="80ce6-205">OracleEBSFeature</span></span>|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|<span data-ttu-id="80ce6-206">SapBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="80ce6-206">SapBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="80ce6-207">SiebelBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="80ce6-207">SiebelBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|<span data-ttu-id="80ce6-208">SqlFeature</span><span class="sxs-lookup"><span data-stu-id="80ce6-208">SqlFeature</span></span>|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="80ce6-209">SapAdoFeature</span><span class="sxs-lookup"><span data-stu-id="80ce6-209">SapAdoFeature</span></span><br /><br /> <span data-ttu-id="80ce6-210">**注**: インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]もします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-210">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] also.</span></span>|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="80ce6-211">SiebelAdoFeature</span><span class="sxs-lookup"><span data-stu-id="80ce6-211">SiebelAdoFeature</span></span><br /><br /> <span data-ttu-id="80ce6-212">**注**: インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]もします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-212">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] also.</span></span>|  
|<span data-ttu-id="80ce6-213">すべてのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="80ce6-213">All components</span></span>|<span data-ttu-id="80ce6-214">ALL</span><span class="sxs-lookup"><span data-stu-id="80ce6-214">ALL</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="80ce6-215">機能名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-215">The feature names are case-sensitive.</span></span>  
  
 <span data-ttu-id="80ce6-216">次の手順は、のサイレント インストールを完了する方法を示します[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]さまざまなコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="80ce6-216">The following steps show you how to complete a silent installation of [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] for different components.</span></span>  
  
### <a name="silent-mode-steps"></a><span data-ttu-id="80ce6-217">サイレント モードの手順</span><span class="sxs-lookup"><span data-stu-id="80ce6-217">Silent mode steps</span></span>
  
1.  <span data-ttu-id="80ce6-218">コマンド プロンプトを開きに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]でルート、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-218">Open a command prompt, and go to the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] root in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span>  
  
2.  <span data-ttu-id="80ce6-219">インストールする内容に基づいて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-219">Run the following commands based on what you want to install:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80ce6-220">X64 ベースのプラットフォームでのサイレント インストールには、置換`AdaptersSetup.msi`で`AdaptersSetup64.msi`次のコマンドにします。</span><span class="sxs-lookup"><span data-stu-id="80ce6-220">To do silent installation on an x64-based platform, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi` in the following commands.</span></span>  
  
    -   <span data-ttu-id="80ce6-221">アダプターは、.NET Framework データ プロバイダーを含む、すべてをインストールする完全なインストールを実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-221">To perform a complete installation, which installs all the adapters including the .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   <span data-ttu-id="80ce6-222">のみをインストールする、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="80ce6-222">To install only the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-223">のみをインストールする、[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="80ce6-223">To install only the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-224">のみをインストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="80ce6-224">To install only the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-225">インストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]と共に[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="80ce6-225">To install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] along with [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-226">のみをインストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="80ce6-226">To install only the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-227">インストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]と共に[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="80ce6-227">To install the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] along with [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-228">のみをインストールする、[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="80ce6-228">To install only the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-229">すべてのベース アダプターをインストールするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-229">To install all the base adapters, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-230">2 つの .NET Framework データ プロバイダーをインストールするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-230">To install the two .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-231">コンマで区切って、コンポーネントでカスタム インストールのすべての型。</span><span class="sxs-lookup"><span data-stu-id="80ce6-231">Any type of custom installation by separating the components by a comma.</span></span> <span data-ttu-id="80ce6-232">たとえば、インストールするため、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]で、 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、および[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]型。</span><span class="sxs-lookup"><span data-stu-id="80ce6-232">For example, to install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] with the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], and the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="80ce6-233">CEIP をサイレント インストールの一部として登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="80ce6-233">You can also opt to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="80ce6-234">型:</span><span class="sxs-lookup"><span data-stu-id="80ce6-234">Type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         <span data-ttu-id="80ce6-235">既定では、オプションは false です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-235">By default the option is false.</span></span> 
  
        > [!IMPORTANT]
        >  <span data-ttu-id="80ce6-236">インストール中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでの評価版、CEIP の既定のオプションが true です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-236">While installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Evaluation version in silent mode, the default option for CEIP is true.</span></span>  
  
     <span data-ttu-id="80ce6-237">詳細については、 **msiexec**コマンドで、入力`msiexec`キーを押して、コマンド ライン`ENTER`です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-237">For more information about the **msiexec** command, type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="80ce6-238">移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-238">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
     
## <a name="known-install-issue"></a><span data-ttu-id="80ce6-239">インストールの既知の問題</span><span class="sxs-lookup"><span data-stu-id="80ce6-239">Known install issue</span></span>
<span data-ttu-id="80ce6-240">包括のインストールに関連する問題の一覧を表示するを参照してください**トラブルシューティング**アダプターごとにトピックです。</span><span class="sxs-lookup"><span data-stu-id="80ce6-240">For a comprehensive list of installation-related issues, refer to **Troubleshooting** topics for each adapter.</span></span>  
  
<span data-ttu-id="80ce6-241">**64 ビット コンピューターでセットアップを実行してはスキーマ ファイルにアクセス中にエラーをスローする可能性があります。**</span><span class="sxs-lookup"><span data-stu-id="80ce6-241">**Running setup on a 64-bit computer may throw an error while accessing schema file**</span></span>  
  
<span data-ttu-id="80ce6-242">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップによって、Microsoft.Adapters へのアクセス中にエラーがスローされます *。\<AdapterName\>*_schema.xml ファイルが、アダプターのインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="80ce6-242">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup throws an error while accessing the Microsoft.Adapters.*\<AdapterName\>*_schema.xml file, but proceeds with the adapter installation.</span></span>  
  
<span data-ttu-id="80ce6-243">**原因**</span><span class="sxs-lookup"><span data-stu-id="80ce6-243">**Cause**</span></span>  
  
<span data-ttu-id="80ce6-244">場合は 32 ビットと 64 ビットの両方のバージョン、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]がインストールされている同じコンピューター両方で使用されるターゲットのスキーマ ファイルは同じです。</span><span class="sxs-lookup"><span data-stu-id="80ce6-244">If both 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] are installed on the same computer, the target schema file used by both is the same.</span></span> <span data-ttu-id="80ce6-245">その結果、ファイルは、32 ビットでインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]64 ビットのインストーラーが、アクセスしようとするときに、IIS によって使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80ce6-245">As a result, the file installed by the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] might be in use by IIS when the 64-bit installer tries to access it.</span></span>  
  
<span data-ttu-id="80ce6-246">**解決策**</span><span class="sxs-lookup"><span data-stu-id="80ce6-246">**Resolution**</span></span>  
  
<span data-ttu-id="80ce6-247">Microsoft.Adapters を手動でコピーします。 *\<AdapterName\>*_schema.xml ファイルから*C:\Program files \microsoft BizTalk Adapter Pack (x64) \IIS スキーマ*に*C:\Windows\System32\inetsrv\config\schema*です。</span><span class="sxs-lookup"><span data-stu-id="80ce6-247">Manually copy the Microsoft.Adapters.*\<AdapterName\>*_schema.xml file from *C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas* to *C:\Windows\System32\inetsrv\config\schema*.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="80ce6-248">次の手順</span><span class="sxs-lookup"><span data-stu-id="80ce6-248">Next step</span></span>
[<span data-ttu-id="80ce6-249">ポスト インストール手順</span><span class="sxs-lookup"><span data-stu-id="80ce6-249">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)
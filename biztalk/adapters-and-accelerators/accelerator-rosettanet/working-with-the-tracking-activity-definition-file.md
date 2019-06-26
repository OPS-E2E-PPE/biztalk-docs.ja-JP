---
title: 追跡アクティビティ定義ファイルの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f528125d0fe25139dbd7b8e4a2a2792f42d9264
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379102"
---
# <a name="working-with-the-tracking-activity-definition-file"></a><span data-ttu-id="ccedb-102">追跡アクティビティ定義ファイルの操作</span><span class="sxs-lookup"><span data-stu-id="ccedb-102">Working with the Tracking Activity Definition File</span></span>
<span data-ttu-id="ccedb-103">アクティビティ定義ファイルには、追跡に関する情報が含まれています。 Microsoft® プロセスとメッセージ アクティビティ[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-103">The activity definition file contains information about the tracking process and message activities in Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ccedb-104">BizTalk ビジネス アクティビティ監視 (BAM) 追跡データを管理するのにには、このファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-104">uses this file to manage data tracking in BizTalk Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="ccedb-105">定義ファイルは、XML ファイル (Tracking.xml) を[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]でインストール、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAMTracking フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ccedb-105">The definition file is an XML file (Tracking.xml) that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] setup installs in the \<*drive*\>:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAMTracking folder.</span></span> <span data-ttu-id="ccedb-106">通常は、Tracking.xml で定義されたアクティビティで十分に目的を達成できます。</span><span class="sxs-lookup"><span data-stu-id="ccedb-106">The activities defined in Tracking.xml may be sufficient for your purposes.</span></span>  
  
 <span data-ttu-id="ccedb-107">追跡アクティビティ、ビュー、およびテーブルの詳細については、次を参照してください。[拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-107">For more information about the tracking activities, views, and tables, see [Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).</span></span> <span data-ttu-id="ccedb-108">BAM の詳細については、"ビジネス アクティビティ監視 (BAM)"で BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccedb-108">For more information about BAM, see "Business Activity Monitoring (BAM)" in BizTalk Server Help.</span></span>  
  
## <a name="managing-tracking-views"></a><span data-ttu-id="ccedb-109">追跡ビューの管理</span><span class="sxs-lookup"><span data-stu-id="ccedb-109">Managing Tracking Views</span></span>  
 <span data-ttu-id="ccedb-110">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] による追跡中は BizTalk 追跡プロファイル エディターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ccedb-110">You do not use the BizTalk Tracking Profile Editor with [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] tracking.</span></span> <span data-ttu-id="ccedb-111">追跡ポイントはカスタマイズできないため、アクティビティの定義を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="ccedb-111">The tracking points are not customizable; do not change activity definitions.</span></span> <span data-ttu-id="ccedb-112">ただし、BAM ビューと展開の管理は可能です。</span><span class="sxs-lookup"><span data-stu-id="ccedb-112">However, you can manage BAM views and deployment.</span></span> <span data-ttu-id="ccedb-113">これを行うには、変更する、[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシート (Tracking.xls) を[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]でインストール、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk 2013 Accelerator for してBAMTracking フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="ccedb-113">To do so, you modify an [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet (Tracking.xls) that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] setup installs in the \<*drive*\>:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking folder.</span></span> <span data-ttu-id="ccedb-114">詳細については、「追跡ビューの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccedb-114">For more information, see "Managing Tracking Views" below.</span></span>  
  
 <span data-ttu-id="ccedb-115">Tracking.xml に定義されているビューでニーズが満たされない場合は、次のように、BAM で追跡する情報についての別のビューを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="ccedb-115">If the views defined in Tracking.xml are not sufficient for your needs, you can define different views of the information tracked in BAM as follows.</span></span>  
  
#### <a name="to-create-different-tracking-views"></a><span data-ttu-id="ccedb-116">別の追跡ビューを作成するには</span><span class="sxs-lookup"><span data-stu-id="ccedb-116">To create different tracking views</span></span>  
  
1. <span data-ttu-id="ccedb-117">**[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccedb-117">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="ccedb-118">入力**cmd**のクリックして実行 ダイアログ ボックスでは、開いているテキスト ボックスに**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-118">Enter **cmd** in the Open text box of the Run dialog box, and then click **OK**.</span></span> <span data-ttu-id="ccedb-119">コマンド ライン ダイアログ ボックスで、tracking.xml の展開を解除し、をクリックするには、次のコードを入力します**OK**:。</span><span class="sxs-lookup"><span data-stu-id="ccedb-119">In the command line dialog box, enter the following code to undeploy tracking.xml, then click **OK**:</span></span>  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
2. <span data-ttu-id="ccedb-120">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動 *\<ドライブ\>* : \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM 追跡します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-120">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *\<drive\>*:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM Tracking.</span></span> <span data-ttu-id="ccedb-121">Tracking.xls をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccedb-121">Double-click Tracking.xls.</span></span>  
  
3. <span data-ttu-id="ccedb-122">ビジネス アクティビティ監視に新しいビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-122">Create a new view in Business Activity Monitoring.</span></span> <span data-ttu-id="ccedb-123">これを行う方法については、BizTalk Server ヘルプの「ビジネス アクティビティ監視の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccedb-123">For information about how to do so, see "Managing Business Activity Monitoring" in BizTalk Server Help.</span></span>  
  
4. <span data-ttu-id="ccedb-124">クリックして**BAM**、 をクリックし、 **XML のエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-124">Click **BAM**, and then click **Export XML**.</span></span> <span data-ttu-id="ccedb-125">目的の場所に移動、(Tracking.xml 以外)、ファイル名を入力し、クリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-125">Move to the desired location, enter a file name (other than Tracking.xml), and then click **Save**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="ccedb-126">追跡 XLS ファイルに新しい追跡ビューを定義してこのファイルから XML ファイルをエクスポートすると、一部のフィールド名が少し変更されます。</span><span class="sxs-lookup"><span data-stu-id="ccedb-126">When you define new tracking views in a tracking XLS file, and export an XML file from the tracking XLS file, some of the new field names may be slightly modified.</span></span> <span data-ttu-id="ccedb-127">カスタマイズした追跡 XML ファイルのフィールドを、BTARN セットアップによってインストールされた標準の Tracking.xml のフィールドと照合して、それらのフィールド名を修正します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-127">Correct this by verifying the fields in your customized tracking XML file against the standard tracking.xml field installed by BTARN setup.</span></span>  
  
5. <span data-ttu-id="ccedb-128">新しい追跡 XML ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-128">Deploy the new tracking XML file.</span></span> <span data-ttu-id="ccedb-129">これを行うには、次のようにクリックします。**開始**、 をクリックし、**実行**します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-129">To do so, click **Start**, and then click **Run**.</span></span> <span data-ttu-id="ccedb-130">入力**cmd**のクリックして実行 ダイアログ ボックスでは、開いているテキスト ボックスに**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-130">Enter **cmd** in the Open text box of the Run dialog box, and then click **OK**.</span></span> <span data-ttu-id="ccedb-131">コマンド ライン ダイアログ ボックスで、新しい追跡ファイルを展開し、をクリックするには、次のコードを入力します。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ccedb-131">In the command line dialog box, enter the following code to deploy your new tracking file, then click **OK**.</span></span> <span data-ttu-id="ccedb-132">既定の Tracking.xml ファイルを上書きしないようにするため、追跡 XML ファイルの名前を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ccedb-132">It is recommended that you rename the tracking XML file so that you do not overwrite the default tracking.xml file.</span></span>  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
   <span data-ttu-id="ccedb-133">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] データベースに格納されているため、BAM で追跡される情報には、メッセージの内容は含まれません。</span><span class="sxs-lookup"><span data-stu-id="ccedb-133">The information tracked in BAM does not include the message content, because that is stored in a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] database.</span></span>  
  
   <span data-ttu-id="ccedb-134">ビジネス アクティビティ監視管理ユーティリティを使用すると、BAM 追跡の展開を管理できます。</span><span class="sxs-lookup"><span data-stu-id="ccedb-134">You can manage deployment of BAM tracking by using the Business Activity Monitoring Management Utility.</span></span> <span data-ttu-id="ccedb-135">このユーティリティの詳細については、「を使用して、ビジネス アクティビティ監視管理ユーティリティ」BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccedb-135">For more information about this utility, see "Using the Business Activity Monitoring Management Utility" in BizTalk Server Help.</span></span>  
  
## <a name="activity-fields"></a><span data-ttu-id="ccedb-136">アクティビティ フィールド</span><span class="sxs-lookup"><span data-stu-id="ccedb-136">Activity Fields</span></span>  
 <span data-ttu-id="ccedb-137">アクティビティ定義ファイルには、次のようなメッセージ アクティビティ フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="ccedb-137">The fields of the message activity in the activity definition file are the following:</span></span>  
  
- <span data-ttu-id="ccedb-138">ActivityName</span><span class="sxs-lookup"><span data-stu-id="ccedb-138">ActivityName</span></span>  
  
- <span data-ttu-id="ccedb-139">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="ccedb-139">Category</span></span>  
  
- <span data-ttu-id="ccedb-140">ContentKey</span><span class="sxs-lookup"><span data-stu-id="ccedb-140">ContentKey</span></span>  
  
- <span data-ttu-id="ccedb-141">DestinationPartyName</span><span class="sxs-lookup"><span data-stu-id="ccedb-141">DestinationPartyName</span></span>  
  
- <span data-ttu-id="ccedb-142">ErrorDescription</span><span class="sxs-lookup"><span data-stu-id="ccedb-142">ErrorDescription</span></span>  
  
- <span data-ttu-id="ccedb-143">HasError</span><span class="sxs-lookup"><span data-stu-id="ccedb-143">HasError</span></span>  
  
- <span data-ttu-id="ccedb-144">InReplyToMessageID</span><span class="sxs-lookup"><span data-stu-id="ccedb-144">InReplyToMessageID</span></span>  
  
- <span data-ttu-id="ccedb-145">IsReceived</span><span class="sxs-lookup"><span data-stu-id="ccedb-145">IsReceived</span></span>  
  
- <span data-ttu-id="ccedb-146">MessageTrackingID</span><span class="sxs-lookup"><span data-stu-id="ccedb-146">MessageTrackingID</span></span>  
  
- <span data-ttu-id="ccedb-147">NoFPipInstance</span><span class="sxs-lookup"><span data-stu-id="ccedb-147">NoFPipInstance</span></span>  
  
- <span data-ttu-id="ccedb-148">PipCode</span><span class="sxs-lookup"><span data-stu-id="ccedb-148">PipCode</span></span>  
  
- <span data-ttu-id="ccedb-149">PipInstanceID</span><span class="sxs-lookup"><span data-stu-id="ccedb-149">PipInstanceID</span></span>  
  
- <span data-ttu-id="ccedb-150">PiPVersion</span><span class="sxs-lookup"><span data-stu-id="ccedb-150">PiPVersion</span></span>  
  
- <span data-ttu-id="ccedb-151">SourcePartName</span><span class="sxs-lookup"><span data-stu-id="ccedb-151">SourcePartName</span></span>  
  
- <span data-ttu-id="ccedb-152">Timestamp</span><span class="sxs-lookup"><span data-stu-id="ccedb-152">Timestamp</span></span>  
  
  <span data-ttu-id="ccedb-153">アクティビティ定義ファイルには、次のようなプロセス アクティビティ フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="ccedb-153">The fields of the process activity in the activity definition file are the following:</span></span>  
  
- <span data-ttu-id="ccedb-154">EndTime</span><span class="sxs-lookup"><span data-stu-id="ccedb-154">EndTime</span></span>  
  
- <span data-ttu-id="ccedb-155">InitiatorPartyName</span><span class="sxs-lookup"><span data-stu-id="ccedb-155">InitiatorPartyName</span></span>  
  
- <span data-ttu-id="ccedb-156">IsInitiatorRole</span><span class="sxs-lookup"><span data-stu-id="ccedb-156">IsInitiatorRole</span></span>  
  
- <span data-ttu-id="ccedb-157">PipCode</span><span class="sxs-lookup"><span data-stu-id="ccedb-157">PipCode</span></span>  
  
- <span data-ttu-id="ccedb-158">PipInstanceID</span><span class="sxs-lookup"><span data-stu-id="ccedb-158">PipInstanceID</span></span>  
  
- <span data-ttu-id="ccedb-159">PipName</span><span class="sxs-lookup"><span data-stu-id="ccedb-159">PipName</span></span>  
  
- <span data-ttu-id="ccedb-160">PipVersion</span><span class="sxs-lookup"><span data-stu-id="ccedb-160">PipVersion</span></span>  
  
- <span data-ttu-id="ccedb-161">ResponderPartyName</span><span class="sxs-lookup"><span data-stu-id="ccedb-161">ResponderPartyName</span></span>  
  
- <span data-ttu-id="ccedb-162">StartTime</span><span class="sxs-lookup"><span data-stu-id="ccedb-162">StartTime</span></span>  
  
- <span data-ttu-id="ccedb-163">状態</span><span class="sxs-lookup"><span data-stu-id="ccedb-163">Status</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccedb-164">参照</span><span class="sxs-lookup"><span data-stu-id="ccedb-164">See Also</span></span>  
 <span data-ttu-id="ccedb-165">[拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="ccedb-165">[Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span></span>  
 [<span data-ttu-id="ccedb-166">構成、証明書、データベース、セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="ccedb-166">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)
---
title: バインド ファイルを使用して、インポートまたはエクスポートする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9a2a82a-f8d4-4ec2-b8c1-be6cda3f993a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ed0f50d6a6d841169b16f3f3ffd485ee345aeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990595"
---
# <a name="use-binding-files-to-import-or-export"></a><span data-ttu-id="d8c4e-102">バインド ファイルを使用して、インポートまたはエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="d8c4e-102">Use binding files to import or export</span></span>

<span data-ttu-id="d8c4e-103">以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]、エクスポートおよびバインド ファイルをインポートすることができます、**パーティ**と**契約**レベル。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-103">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can export and import binding files at the **Parties** and **Agreement** levels.</span></span> <span data-ttu-id="d8c4e-104">以前のバージョンの BizTalk をエクスポートするアプリケーション レベルで説明されています。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-104">For previous BizTalk versions, you export at the application level, as described at:</span></span> 

* [<span data-ttu-id="d8c4e-105">EDI AS2 ソリューションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="d8c4e-105">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="d8c4e-106">Edi-as2 ソリューションのバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="d8c4e-106">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

<span data-ttu-id="d8c4e-107">このトピックでは、インポートする方法を説明し、パーティ、プロファイル、アグリーメント、フォールバックの設定および詳細を使用してエクスポート[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]と BTSTask します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-107">This topic shows you how to import and exports parties, their profiles, agreements, fallback settings, and more using [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] and BTSTask.</span></span> 

## <a name="overview"></a><span data-ttu-id="d8c4e-108">概要</span><span class="sxs-lookup"><span data-stu-id="d8c4e-108">Overview</span></span>

<span data-ttu-id="d8c4e-109">インポートおよびエクスポート機能をいくつか挙げます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-109">Some of the import and export features include:</span></span>

* <span data-ttu-id="d8c4e-110">パーティ、ビジネス プロファイル、およびアグリーメントを XML バインド ファイルからインポートします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-110">Import parties, business profiles, and agreements from an XML binding file</span></span>
* <span data-ttu-id="d8c4e-111">パーティ、ビジネス プロファイル、契約、および EDI フォールバックの設定を XML バインド ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-111">Export parties, business profiles, agreements, and EDI fallback settings to an XML binding file</span></span>
* <span data-ttu-id="d8c4e-112">バインド ファイルをインポートするときに、パーティ、またはフォールバックの設定をインポートしない選択したことができます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-112">When importing a binding file, you can chose to not import the parties, or the fallback settings</span></span>
* <span data-ttu-id="d8c4e-113">パーティ レベルでインポートすると、関係者と、バインド ファイル内の契約がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-113">When importing at the Parties-level, only the parties and agreements within the binding file are imported</span></span>
* <span data-ttu-id="d8c4e-114">特定のパーティを同じのバインド ファイルにエクスポートしもこれらのパーティに関連付けられているすべての契約をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-114">Export specific parties to the same binding file, and choose to also export all the agreements associated with those parties</span></span>
* <span data-ttu-id="d8c4e-115">アプリケーション バインドのインポート ウィザードを使用して、追跡の設定をインポートまたはパーティを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-115">The application import binding wizard lets you choose to import the tracking settings, or exclude the parties.</span></span>
* <span data-ttu-id="d8c4e-116">BTSTask が含まれています、`ImportParties`と`ExportParties`コマンド</span><span class="sxs-lookup"><span data-stu-id="d8c4e-116">BTSTask includes the `ImportParties` and `ExportParties` commands</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d8c4e-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="d8c4e-117">Prerequisites</span></span>

* <span data-ttu-id="d8c4e-118">メンバーであるアカウントでログオンする必要があります、* * BizTalk Server 管理者 * * グループ。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-118">You must be logged on with an account that is a member of the** BizTalk Server Administrators** group.</span></span> <span data-ttu-id="d8c4e-119">参照してください[を展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-119">See [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  

* <span data-ttu-id="d8c4e-120">参照を追加する必要があります、 **BizTalk EDI アプリケーション**を BizTalk アプリケーションを EDI アプリケーションとして使用されるからです。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-120">You must have added a reference to the **BizTalk EDI Application** from a BizTalk application that will be used as an EDI application.</span></span> <span data-ttu-id="d8c4e-121">参照してください[構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-121">See [Post-configuration steps](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>

## <a name="import-or-export-all-the-trading-partners"></a><span data-ttu-id="d8c4e-122">インポートまたはエクスポートするすべての取引</span><span class="sxs-lookup"><span data-stu-id="d8c4e-122">Import or export all the trading partners</span></span>
1. <span data-ttu-id="d8c4e-123">開いている**[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**、BizTalk グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-123">Open **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, and expand the BizTalk group.</span></span>
2. <span data-ttu-id="d8c4e-124">右クリック**パーティ**、選び**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-124">Right-click **Parties**, and select **Export**.</span></span> 

    <span data-ttu-id="d8c4e-125">エクスポートするとき、**パーティ**-レベル、エクスポートするすべての取引先パートナーです。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-125">When you export at the **parties**-level, you are exporting all the trading partners.</span></span> <span data-ttu-id="d8c4e-126">ビジネス プロファイル、および XML ファイルに契約を含む取引で使用されるすべてのものもエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-126">This also exports everything used by the trading partners, including business profiles, and agreements into an XML file.</span></span> 

3. <span data-ttu-id="d8c4e-127">右クリックして**パーティ**を選択します**インポート**バインディングの XML ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-127">Right-click **Parties**, select **Import**, and select the binding XML file.</span></span> 

      <span data-ttu-id="d8c4e-128">**を除外するパーティ**、または**EDI フォールバックの設定を除外する**インポートされないようにします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-128">Choose to **Exclude Parties**, or **Exclude EDI Fallback Settings** so they are not imported.</span></span> <span data-ttu-id="d8c4e-129">それ以外の場合、バインド ファイル内のすべてが、インポート、取引先パートナー、ビジネス プロファイル、アグリーメントなど。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-129">Otherwise, everything in the binding file is imported, including the trading partners, business profiles, and agreements.</span></span>     

### <a name="btstask-example"></a><span data-ttu-id="d8c4e-130">BTSTask の使用例</span><span class="sxs-lookup"><span data-stu-id="d8c4e-130">BTSTask example</span></span>

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

<span data-ttu-id="d8c4e-131">参照してください[ImportParties コマンド](../core/importparties-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-131">See [ImportParties command](../core/importparties-command.md).</span></span>

    
## <a name="export-individual-partners"></a><span data-ttu-id="d8c4e-132">個々 のパートナーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-132">Export individual partners</span></span>
1. <span data-ttu-id="d8c4e-133">**[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** **パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-133">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, select **Parties**.</span></span>
2. <span data-ttu-id="d8c4e-134">**パーティとビジネス プロファイル**ウィンドウで、パーティを右クリックし、選択**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-134">In the **Parties and business profiles** pane, right-click a party, and select **Export**.</span></span>

    <span data-ttu-id="d8c4e-135">特定のパーティをエクスポートするときに、すべてのパーティとパーティで使用されるすべての契約をエクスポートするかの選択肢が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-135">When you export a specific party, you are given the choice to export all the parties, and all the agreements used by that party.</span></span> <span data-ttu-id="d8c4e-136">オフにすることができます**選択したパーティーと、選択したパーティーのすべての契約をエクスポート**のみを選択するパーティをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-136">You can uncheck **Export selected parties and all the agreements within the selected parties** to only export the party you select.</span></span>

3. <span data-ttu-id="d8c4e-137">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-137">Select **OK**.</span></span> 

> [!TIP]
> <span data-ttu-id="d8c4e-138">**パーティとビジネス プロファイル**ウィンドウで、使用することも、 **CTRL**と**Shift**キーの一覧で複数のパーティを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-138">In the **Parties and business profiles** pane, you can also use the **CTRL** and **Shift** keys to select multiple parties in the list.</span></span> <span data-ttu-id="d8c4e-139">同じバインド ファイルに、選択したパーティのすべてのエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-139">All of the parties you select export into the same binding file.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="d8c4e-140">BTSTask の使用例</span><span class="sxs-lookup"><span data-stu-id="d8c4e-140">BTSTask example</span></span>

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

<span data-ttu-id="d8c4e-141">参照してください[ExportParties コマンド](../core/exportparties-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-141">See [ExportParties command](../core/exportparties-command.md).</span></span>


## <a name="import-application-binding-file"></a><span data-ttu-id="d8c4e-142">アプリケーションのバインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="d8c4e-142">Import application binding file</span></span>

<span data-ttu-id="d8c4e-143">アプリケーション レベルでは、EDI および AS2 パーティにバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-143">At the application-level, you can import a binding file with EDI and AS2 parties.</span></span> 

1. <span data-ttu-id="d8c4e-144">**[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**、展開**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="d8c4e-144">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, expand **Applications**</span></span>
2. <span data-ttu-id="d8c4e-145">アプリケーションを右クリックして**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-145">Right-click your application, and select **Import**.</span></span>
3. <span data-ttu-id="d8c4e-146">**追跡設定をインポート**と**除外パーティ**オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-146">**Import Tracking Settings** and **Exclude Parties** options are available.</span></span> <span data-ttu-id="d8c4e-147">これらのオプションを使用して、既存の追跡設定をインポートまたはバインド ファイル内で EDI および AS2 パーティの除外を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-147">Using these options, you can choose to import any existing tracking settings, or exclude any EDI/AS2 parties within the binding file.</span></span>

    | <span data-ttu-id="d8c4e-148">設定</span><span class="sxs-lookup"><span data-stu-id="d8c4e-148">Setting</span></span> | <span data-ttu-id="d8c4e-149">詳細</span><span class="sxs-lookup"><span data-stu-id="d8c4e-149">Details</span></span> |
    |---|---|
    |<span data-ttu-id="d8c4e-150">**追跡設定をインポートします。**</span><span class="sxs-lookup"><span data-stu-id="d8c4e-150">**Import Tracking Settings**</span></span> | <span data-ttu-id="d8c4e-151">メッセージ本文の追跡、およびイベントの追跡など、アプリケーション内でさまざまな成果物に有効になっている追跡設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-151">Imports the tracking settings enabled on the different artifacts within the application, such as track message bodies, and track events.</span></span> <br/><br/><span data-ttu-id="d8c4e-152">下位互換性を確保するのには、既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-152">Enabled by default to ensure backwards-compatibility.</span></span> |
    | <span data-ttu-id="d8c4e-153">**パーティーを除外します。**</span><span class="sxs-lookup"><span data-stu-id="d8c4e-153">**Exclude Parties**</span></span>|<span data-ttu-id="d8c4e-154">いないインポートのパーティ、プロファイル、およびアグリーメントは、ファイル内に存在します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-154">Does not import parties, profiles, and agreements that existing within the file.</span></span> <br/><br/><span data-ttu-id="d8c4e-155">既定では下位互換性を確保するのには無効です。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-155">Disabled by default to ensure backwards-compatibility.</span></span>|

   > [!IMPORTANT]
   > <span data-ttu-id="d8c4e-156">グローバル追跡設定を上書き**追跡設定のインポート**します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-156">The global tracking settings override **Import Tracking Settings**.</span></span> <span data-ttu-id="d8c4e-157">したがって、グローバル追跡を無効にした場合レベル、任意の場合でも、追跡の設定はインポートされません**追跡設定のインポート**がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-157">So if you've disabled tracking at the global level, any tracking settings are not imported, even if **Import Tracking Settings** is checked.</span></span>
   > 
   > <span data-ttu-id="d8c4e-158">**BizTalk 設定ダッシュ ボードの [グループ] ページ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]について説明します、**追跡設定のインポートを許可する**グローバル設定です。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-158">**BizTalk Settings Dashboard, Group Page** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explains the **Allow import of tracking settings** global setting.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="d8c4e-159">BTSTask の使用例</span><span class="sxs-lookup"><span data-stu-id="d8c4e-159">BTSTask example</span></span>

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

<span data-ttu-id="d8c4e-160">参照してください[ImportBindings コマンド](../core/importbindings-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-160">See [ImportBindings command](../core/importbindings-command.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d8c4e-161">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d8c4e-161">In this section</span></span>
<span data-ttu-id="d8c4e-162">インポートまたはエクスポート前のバージョンの BizTalk での EDI および AS2 バインド ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8c4e-162">To import or export EDI and AS2 binding files on previous BizTalk versions, see:</span></span> 

* [<span data-ttu-id="d8c4e-163">EDI AS2 ソリューションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="d8c4e-163">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="d8c4e-164">Edi-as2 ソリューションのバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="d8c4e-164">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

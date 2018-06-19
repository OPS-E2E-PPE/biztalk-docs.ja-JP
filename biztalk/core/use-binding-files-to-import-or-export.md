---
title: インポートまたはエクスポートするバインド ファイルを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: e3707726eb9e8e77e0536f36700fe098d83ad414
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22288274"
---
# <a name="use-binding-files-to-import-or-export"></a><span data-ttu-id="8153e-102">バインド ファイルを使用して、インポートまたはエクスポート</span><span class="sxs-lookup"><span data-stu-id="8153e-102">Use binding files to import or export</span></span>

<span data-ttu-id="8153e-103">以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]、エクスポートし、バインド ファイルをインポートすることができます、**パーティ**と**アグリーメント**レベル。</span><span class="sxs-lookup"><span data-stu-id="8153e-103">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can export and import binding files at the **Parties** and **Agreement** levels.</span></span> <span data-ttu-id="8153e-104">以前のバージョンの BizTalk にエクスポートするアプリケーション レベルで」の説明に従って。</span><span class="sxs-lookup"><span data-stu-id="8153e-104">For previous BizTalk versions, you export at the application level, as described at:</span></span> 

* [<span data-ttu-id="8153e-105">EDI AS2 ソリューションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="8153e-105">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="8153e-106">EDI AS2 ソリューションのバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="8153e-106">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

<span data-ttu-id="8153e-107">このトピックの内容をインポートする方法を示し、パーティ、自分のプロファイル、アグリーメント、フォールバックの設定と詳細を使用してエクスポート[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]と BTSTask です。</span><span class="sxs-lookup"><span data-stu-id="8153e-107">This topic shows you how to import and exports parties, their profiles, agreements, fallback settings, and more using [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] and BTSTask.</span></span> 

## <a name="overview"></a><span data-ttu-id="8153e-108">概要</span><span class="sxs-lookup"><span data-stu-id="8153e-108">Overview</span></span>

<span data-ttu-id="8153e-109">インポートおよびエクスポート機能があります。</span><span class="sxs-lookup"><span data-stu-id="8153e-109">Some of the import and export features include:</span></span>

* <span data-ttu-id="8153e-110">パーティ、ビジネス プロファイル、およびアグリーメントを XML バインド ファイルからインポートします。</span><span class="sxs-lookup"><span data-stu-id="8153e-110">Import parties, business profiles, and agreements from an XML binding file</span></span>
* <span data-ttu-id="8153e-111">パーティ、ビジネス プロファイル、アグリーメント、および EDI フォールバックの設定を XML バインド ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8153e-111">Export parties, business profiles, agreements, and EDI fallback settings to an XML binding file</span></span>
* <span data-ttu-id="8153e-112">バインド ファイルをインポートするときに、パーティまたはフォールバックの設定をインポートしない選択できます。</span><span class="sxs-lookup"><span data-stu-id="8153e-112">When importing a binding file, you can chose to not import the parties, or the fallback settings</span></span>
* <span data-ttu-id="8153e-113">インポートする場合はパーティ レベルで、パーティとアグリーメント、バインド ファイル内のみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8153e-113">When importing at the Parties-level, only the parties and agreements within the binding file are imported</span></span>
* <span data-ttu-id="8153e-114">特定のパーティを同じバインド ファイルにエクスポートし、またそのパーティに関連付けられているすべての契約書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8153e-114">Export specific parties to the same binding file, and choose to also export all the agreements associated with those parties</span></span>
* <span data-ttu-id="8153e-115">アプリケーションのインポート バインド ウィザードを使用して、追跡設定をインポートするか、パーティを除外するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8153e-115">The application import binding wizard lets you choose to import the tracking settings, or exclude the parties.</span></span>
* <span data-ttu-id="8153e-116">BTSTask を含む、`ImportParties`と`ExportParties`コマンド</span><span class="sxs-lookup"><span data-stu-id="8153e-116">BTSTask includes the `ImportParties` and `ExportParties` commands</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8153e-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="8153e-117">Prerequisites</span></span>

* <span data-ttu-id="8153e-118">メンバーであるアカウントでログオンする必要があります、* * BizTalk Server 管理者 * * グループ。</span><span class="sxs-lookup"><span data-stu-id="8153e-118">You must be logged on with an account that is a member of the** BizTalk Server Administrators** group.</span></span> <span data-ttu-id="8153e-119">参照してください[を展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="8153e-119">See [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  

* <span data-ttu-id="8153e-120">参照を追加する必要があります、 **BizTalk EDI アプリケーション** EDI アプリケーションとして使用される BizTalk アプリケーションからです。</span><span class="sxs-lookup"><span data-stu-id="8153e-120">You must have added a reference to the **BizTalk EDI Application** from a BizTalk application that will be used as an EDI application.</span></span> <span data-ttu-id="8153e-121">参照してください[後の構成手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)です。</span><span class="sxs-lookup"><span data-stu-id="8153e-121">See [Post-configuration steps](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>

## <a name="import-or-export-all-the-trading-partners"></a><span data-ttu-id="8153e-122">インポートまたはエクスポートするすべての取引先</span><span class="sxs-lookup"><span data-stu-id="8153e-122">Import or export all the trading partners</span></span>
1. <span data-ttu-id="8153e-123">開いている**[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**、BizTalk グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="8153e-123">Open **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, and expand the BizTalk group.</span></span>
2. <span data-ttu-id="8153e-124">右クリック**パーティ**を選択して**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="8153e-124">Right-click **Parties**, and select **Export**.</span></span> 

    <span data-ttu-id="8153e-125">エクスポートするとき、**パーティ**-レベル、エクスポートするすべての取引先。</span><span class="sxs-lookup"><span data-stu-id="8153e-125">When you export at the **parties**-level, you are exporting all the trading partners.</span></span> <span data-ttu-id="8153e-126">ビジネス プロファイル、および XML ファイルにアグリーメントを含む、取引先で使用されるすべてのものもエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8153e-126">This also exports everything used by the trading partners, including business profiles, and agreements into an XML file.</span></span> 

3. <span data-ttu-id="8153e-127">右クリックし **パーティ**  **インポート** バインディングの XML ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8153e-127">Right-click **Parties**, select **Import**, and select the binding XML file.</span></span> 

      <span data-ttu-id="8153e-128">選択**除外パーティ**、または**EDI フォールバックの設定を除外する**インポートされないようにします。</span><span class="sxs-lookup"><span data-stu-id="8153e-128">Choose to **Exclude Parties**, or **Exclude EDI Fallback Settings** so they are not imported.</span></span> <span data-ttu-id="8153e-129">それ以外の場合、バインド ファイル内のすべてのインポートされると、取引先、ビジネス プロファイル、およびアグリーメントを含むです。</span><span class="sxs-lookup"><span data-stu-id="8153e-129">Otherwise, everything in the binding file is imported, including the trading partners, business profiles, and agreements.</span></span>     

### <a name="btstask-example"></a><span data-ttu-id="8153e-130">BTSTask の使用例</span><span class="sxs-lookup"><span data-stu-id="8153e-130">BTSTask example</span></span>

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

<span data-ttu-id="8153e-131">参照してください[ImportParties コマンド](../core/importparties-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="8153e-131">See [ImportParties command](../core/importparties-command.md).</span></span>

    
## <a name="export-individual-partners"></a><span data-ttu-id="8153e-132">個々 のパートナーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8153e-132">Export individual partners</span></span>
1. <span data-ttu-id="8153e-133"> **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** **パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="8153e-133">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, select **Parties**.</span></span>
2. <span data-ttu-id="8153e-134">**パーティとビジネス プロファイル** ウィンドウでは、パーティを右クリックし、選択**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="8153e-134">In the **Parties and business profiles** pane, right-click a party, and select **Export**.</span></span>

    <span data-ttu-id="8153e-135">特定のパーティをエクスポートすると、すべてのパーティとそのパーティで使用されるすべての契約書をエクスポートする選択肢が与えられます。</span><span class="sxs-lookup"><span data-stu-id="8153e-135">When you export a specific party, you are given the choice to export all the parties, and all the agreements used by that party.</span></span> <span data-ttu-id="8153e-136">ボックスをオフに**選択した関係者と、選択したパーティ内のすべての契約エクスポート**のみを選択するパーティをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8153e-136">You can uncheck **Export selected parties and all the agreements within the selected parties** to only export the party you select.</span></span>

3. <span data-ttu-id="8153e-137">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8153e-137">Select **OK**.</span></span> 

> [!TIP]
> <span data-ttu-id="8153e-138">**パーティとビジネス プロファイル** ウィンドウで、使用することも、 **ctrl キーを押し**と**shift キーを押し**キーを一覧で複数のパーティを選択します。</span><span class="sxs-lookup"><span data-stu-id="8153e-138">In the **Parties and business profiles** pane, you can also use the **CTRL** and **Shift** keys to select multiple parties in the list.</span></span> <span data-ttu-id="8153e-139">同じバインド ファイルにエクスポートすべてのパーティを選択します。</span><span class="sxs-lookup"><span data-stu-id="8153e-139">All of the parties you select export into the same binding file.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="8153e-140">BTSTask の使用例</span><span class="sxs-lookup"><span data-stu-id="8153e-140">BTSTask example</span></span>

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

<span data-ttu-id="8153e-141">参照してください[ExportParties コマンド](../core/exportparties-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="8153e-141">See [ExportParties command](../core/exportparties-command.md).</span></span>


## <a name="import-application-binding-file"></a><span data-ttu-id="8153e-142">アプリケーションのバインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="8153e-142">Import application binding file</span></span>

<span data-ttu-id="8153e-143">アプリケーション レベルでは、EDI および AS2 パーティにバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="8153e-143">At the application-level, you can import a binding file with EDI and AS2 parties.</span></span> 

1. <span data-ttu-id="8153e-144">**[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**、展開**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="8153e-144">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, expand **Applications**</span></span>
2. <span data-ttu-id="8153e-145">アプリケーションを右クリックし **インポート**です。</span><span class="sxs-lookup"><span data-stu-id="8153e-145">Right-click your application, and select **Import**.</span></span>
3. <span data-ttu-id="8153e-146">**追跡の設定をインポート**と**除外パーティ**オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8153e-146">**Import Tracking Settings** and **Exclude Parties** options are available.</span></span> <span data-ttu-id="8153e-147">これらのオプションを使用して、既存の追跡設定をインポートするか、バインド ファイル内の任意の EDI および AS2 パーティの除外を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8153e-147">Using these options, you can choose to import any existing tracking settings, or exclude any EDI/AS2 parties within the binding file.</span></span>

    | <span data-ttu-id="8153e-148">設定</span><span class="sxs-lookup"><span data-stu-id="8153e-148">Setting</span></span> | <span data-ttu-id="8153e-149">詳細</span><span class="sxs-lookup"><span data-stu-id="8153e-149">Details</span></span> |
    |---|---|
    |<span data-ttu-id="8153e-150">**追跡設定をインポートします。**</span><span class="sxs-lookup"><span data-stu-id="8153e-150">**Import Tracking Settings**</span></span> | <span data-ttu-id="8153e-151">メッセージ本文の追跡、およびイベントの追跡など、アプリケーション内の各アイテムに有効になっている追跡の設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="8153e-151">Imports the tracking settings enabled on the different artifacts within the application, such as track message bodies, and track events.</span></span> <br/><br/><span data-ttu-id="8153e-152">後方互換性を確保するのには、既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="8153e-152">Enabled by default to ensure backwards-compatibility.</span></span> |
    | <span data-ttu-id="8153e-153">**パーティを除外します。**</span><span class="sxs-lookup"><span data-stu-id="8153e-153">**Exclude Parties**</span></span>|<span data-ttu-id="8153e-154">ファイル内で既存いないインポート パーティ、プロファイル、およびアグリーメントでは。</span><span class="sxs-lookup"><span data-stu-id="8153e-154">Does not import parties, profiles, and agreements that existing within the file.</span></span> <br/><br/><span data-ttu-id="8153e-155">既定では下位互換性を確保するのには無効です。</span><span class="sxs-lookup"><span data-stu-id="8153e-155">Disabled by default to ensure backwards-compatibility.</span></span>|

     > [!IMPORTANT] 
     > <span data-ttu-id="8153e-156">グローバル追跡の設定をオーバーライド**追跡設定をインポート**です。</span><span class="sxs-lookup"><span data-stu-id="8153e-156">The global tracking settings override **Import Tracking Settings**.</span></span> <span data-ttu-id="8153e-157">したがって、グローバル追跡を無効にした場合レベルに、追跡の設定がインポートされていない場合でも、**追跡設定をインポート**がチェックします。</span><span class="sxs-lookup"><span data-stu-id="8153e-157">So if you've disabled tracking at the global level, any tracking settings are not imported, even if **Import Tracking Settings** is checked.</span></span>
     > 
     > <span data-ttu-id="8153e-158">**BizTalk 設定ダッシュ ボード、グループのページ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]について説明します、**追跡設定のインポートを許可する**グローバル設定。</span><span class="sxs-lookup"><span data-stu-id="8153e-158">**BizTalk Settings Dashboard, Group Page** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explains the **Allow import of tracking settings** global setting.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="8153e-159">BTSTask の使用例</span><span class="sxs-lookup"><span data-stu-id="8153e-159">BTSTask example</span></span>

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

<span data-ttu-id="8153e-160">参照してください[ImportBindings コマンド](../core/importbindings-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="8153e-160">See [ImportBindings command](../core/importbindings-command.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8153e-161">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8153e-161">In this section</span></span>
<span data-ttu-id="8153e-162">インポートまたはエクスポートの以前のバージョンの BizTalk の EDI および AS2 バインド ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8153e-162">To import or export EDI and AS2 binding files on previous BizTalk versions, see:</span></span> 

* [<span data-ttu-id="8153e-163">EDI AS2 ソリューションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="8153e-163">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="8153e-164">EDI AS2 ソリューションのバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="8153e-164">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

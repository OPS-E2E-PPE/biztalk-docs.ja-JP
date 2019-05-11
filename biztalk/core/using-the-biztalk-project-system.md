---
title: BizTalk プロジェクト システムの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, opening
- BizTalk Mapper, opening
- Orchestration Designer, opening
- Pipeline Designer, opening
ms.assetid: a28c715e-128c-463a-b421-9b3efe76a530
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2401048d928a628a4dd4063d6a3e207c78e2155f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320888"
---
# <a name="using-the-biztalk-project-system"></a><span data-ttu-id="5036b-102">BizTalk プロジェクト システムの使用</span><span class="sxs-lookup"><span data-stu-id="5036b-102">Using the BizTalk Project System</span></span>
<span data-ttu-id="5036b-103">BizTalk プロジェクト システムを使用して、作成、整理、および microsoft BizTalk ソリューションを構成する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="5036b-103">You can use the BizTalk project system to create, organize, and configure BizTalk solutions in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="5036b-104">トピックと、このセクションの手順では、BizTalk プロジェクト システムを使用してさまざまなタスクを実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5036b-104">The topics and procedures in this section describe how to perform various tasks by using the BizTalk project system.</span></span>  
  
 <span data-ttu-id="5036b-105">BizTalk Server プロジェクト システムでは、同じプロジェクト管理の原則と他の Microsoft Build Engine (MSBuild) プロジェクトで使用するプロシージャ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5036b-105">The BizTalk Server project system uses the same project management principles and procedures that you use with other Microsoft Build Engine (MSBuild) projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="5036b-106">このセクションでは、Microsoft で実行するアプリケーションを作成するときに使用する一般的な手順をについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5036b-106">This section details common procedures that you might use when creating an application that runs on Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5036b-107">MSBuild の詳細については、MSBuild のリファレンス セクションを参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-107">For more information about MSBuild, see the MSBuild reference section in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="5036b-108">使用しての詳細については、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境の「管理ソリューション、プロジェクト、およびファイル」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[ http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-108">For more information about using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment, see "Managing Solutions, Projects, and Files" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx).</span></span>  
  
 <span data-ttu-id="5036b-109">BizTalk プロジェクト システム設計環境を次に示します、**新しいプロジェクト**ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5036b-109">The following figure shows the BizTalk project system design environment with the **New Project** dialog box open.</span></span>  
  
 <span data-ttu-id="5036b-110">![プロジェクト システム](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span><span class="sxs-lookup"><span data-stu-id="5036b-110">![Project Systems](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span></span>  
<span data-ttu-id="5036b-111">プロジェクト システム設計環境を示しています。</span><span class="sxs-lookup"><span data-stu-id="5036b-111">Depicts the Project System Design Environment</span></span>  
  
### <a name="to-open-biztalk-editor"></a><span data-ttu-id="5036b-112">BizTalk エディターを開く</span><span class="sxs-lookup"><span data-stu-id="5036b-112">To open BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="5036b-113">ソリューション エクスプ ローラーでスキーマをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5036b-113">In Solution Explorer, click a schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5036b-114">BizTalk エディターを開くには、まずスキーマを作成または、以前に作成したスキーマを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5036b-114">To open BizTalk Editor, you must first create a schema or open a previously created schema.</span></span> <span data-ttu-id="5036b-115">スキーマを作成する方法の詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-115">For information about creating a schema, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="5036b-116">参照してください[プロジェクト項目の追加](../core/adding-project-items.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-116">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="5036b-117">**ビュー**  メニューのをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5036b-117">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="5036b-118">- または -</span><span class="sxs-lookup"><span data-stu-id="5036b-118">—Or—</span></span>  
  
     <span data-ttu-id="5036b-119">スキーマを右クリックし、をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5036b-119">Right-click the schema, and then click **Open**.</span></span>  
  
     <span data-ttu-id="5036b-120">- または -</span><span class="sxs-lookup"><span data-stu-id="5036b-120">—Or—</span></span>  
  
     <span data-ttu-id="5036b-121">スキーマをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5036b-121">Double-click the schema.</span></span>  
  
     <span data-ttu-id="5036b-122">選択したスキーマが BizTalk エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="5036b-122">The selected schema opens in BizTalk Editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5036b-123">スキーマを作成するには、プロジェクトを開いてが必要です。</span><span class="sxs-lookup"><span data-stu-id="5036b-123">To create a schema, you must have a project open.</span></span> <span data-ttu-id="5036b-124">プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-124">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="5036b-125">項目をプロジェクトに追加する方法の詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-125">For information about adding items to a project, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="5036b-126">参照してください[プロジェクト項目の追加](../core/adding-project-items.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-126">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
### <a name="to-open-biztalk-mapper"></a><span data-ttu-id="5036b-127">BizTalk マッパーを開く</span><span class="sxs-lookup"><span data-stu-id="5036b-127">To open BizTalk Mapper</span></span>  
  
1.  <span data-ttu-id="5036b-128">ソリューション エクスプ ローラーでマップをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5036b-128">In Solution Explorer, click a map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5036b-129">BizTalk マッパーを開くには、まずマップを作成するか、以前に作成したマップを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5036b-129">To open BizTalk Mapper, you must first create a map or open a previously created map.</span></span> <span data-ttu-id="5036b-130">マップを作成する方法の詳細については、次を参照してください。[新しいマップを作成する方法](../core/how-to-create-new-maps.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-130">For information about creating a map, see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span> <span data-ttu-id="5036b-131">参照してください[プロジェクト項目の追加](../core/adding-project-items.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-131">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="5036b-132">**ビュー**  メニューのをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5036b-132">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="5036b-133">- または -</span><span class="sxs-lookup"><span data-stu-id="5036b-133">—Or—</span></span>  
  
     <span data-ttu-id="5036b-134">クリックして、マップを右クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5036b-134">Right-click the map, and then click **Open**.</span></span>  
  
     <span data-ttu-id="5036b-135">- または -</span><span class="sxs-lookup"><span data-stu-id="5036b-135">—Or—</span></span>  
  
     <span data-ttu-id="5036b-136">マップをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5036b-136">Double-click a map.</span></span>  
  
     <span data-ttu-id="5036b-137">選択したマップは、BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="5036b-137">The selected map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5036b-138">マップを作成するには、プロジェクトを開いてが必要です。</span><span class="sxs-lookup"><span data-stu-id="5036b-138">To create a map, you must have a project open.</span></span> <span data-ttu-id="5036b-139">プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-139">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="5036b-140">項目をプロジェクトに追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-140">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="5036b-141">参照してください[新しいマップを作成する方法](../core/how-to-create-new-maps.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-141">Also see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span>  
  
### <a name="to-open-orchestration-designer"></a><span data-ttu-id="5036b-142">オーケストレーション デザイナーを開く</span><span class="sxs-lookup"><span data-stu-id="5036b-142">To open Orchestration Designer</span></span>  
  
1.  <span data-ttu-id="5036b-143">ソリューション エクスプ ローラーで、オーケストレーション (.odx) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5036b-143">In Solution Explorer, click an orchestration (.odx).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5036b-144">オーケストレーション デザイナーを開くには、最初にオーケストレーションを作成するか、以前に作成したオーケストレーションを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5036b-144">To open Orchestration Designer, you must first create an orchestration or open a previously created orchestration.</span></span> <span data-ttu-id="5036b-145">オーケストレーションを作成する方法については、次を参照してください。[オーケストレーション デザイナーを使用して](../core/working-in-orchestration-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-145">For information about how to create an orchestration, see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
2.  <span data-ttu-id="5036b-146">**ビュー**  メニューのをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5036b-146">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="5036b-147">- または -</span><span class="sxs-lookup"><span data-stu-id="5036b-147">—Or—</span></span>  
  
     <span data-ttu-id="5036b-148">クリックして、オーケストレーションを右クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5036b-148">Right-click the orchestration, and then click **Open**.</span></span>  
  
     <span data-ttu-id="5036b-149">- または -</span><span class="sxs-lookup"><span data-stu-id="5036b-149">—Or—</span></span>  
  
     <span data-ttu-id="5036b-150">オーケストレーションをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5036b-150">Double-click the orchestration.</span></span>  
  
     <span data-ttu-id="5036b-151">オーケストレーション デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="5036b-151">Orchestration Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5036b-152">オーケストレーションを作成するには、プロジェクトを開いてが必要です。</span><span class="sxs-lookup"><span data-stu-id="5036b-152">To create an orchestration, you must have a project open.</span></span> <span data-ttu-id="5036b-153">プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-153">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="5036b-154">項目をプロジェクトに追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-154">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="5036b-155">参照してください[オーケストレーション デザイナーを使用して](../core/working-in-orchestration-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-155">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
### <a name="to-open-pipeline-designer"></a><span data-ttu-id="5036b-156">パイプライン デザイナーを開く</span><span class="sxs-lookup"><span data-stu-id="5036b-156">To open Pipeline Designer</span></span>  
  
1.  <span data-ttu-id="5036b-157">ソリューション エクスプ ローラーでは、パイプラインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5036b-157">In Solution Explorer, click a pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5036b-158">パイプライン デザイナーを開くには、最初にパイプラインを作成するか、以前に作成したパイプラインを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5036b-158">To open Pipeline Designer, you must first create a pipeline or open a previously created pipeline.</span></span> <span data-ttu-id="5036b-159">パイプラインを作成する方法については、次を参照してください。[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-159">For information about how to create a pipeline, see [How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md).</span></span>  
  
2.  <span data-ttu-id="5036b-160">**ビュー**  メニューのをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5036b-160">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="5036b-161">- または -</span><span class="sxs-lookup"><span data-stu-id="5036b-161">—Or—</span></span>  
  
     <span data-ttu-id="5036b-162">パイプラインを右クリックし、をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5036b-162">Right-click the pipeline, and then click **Open**.</span></span>  
  
     <span data-ttu-id="5036b-163">- または -</span><span class="sxs-lookup"><span data-stu-id="5036b-163">—Or—</span></span>  
  
     <span data-ttu-id="5036b-164">パイプラインをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5036b-164">Double-click the pipeline.</span></span>  
  
     <span data-ttu-id="5036b-165">パイプライン デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="5036b-165">Pipeline Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5036b-166">パイプラインを作成するには、プロジェクトを開いてが必要です。</span><span class="sxs-lookup"><span data-stu-id="5036b-166">To create a pipeline, you must have a project open.</span></span> <span data-ttu-id="5036b-167">プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-167">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="5036b-168">項目をプロジェクトに追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-168">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="5036b-169">参照してください[オーケストレーション デザイナーを使用して](../core/working-in-orchestration-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="5036b-169">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5036b-170">参照</span><span class="sxs-lookup"><span data-stu-id="5036b-170">See Also</span></span>  
 <span data-ttu-id="5036b-171">[オーケストレーション デザイナーを使用してオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="5036b-171">[Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md) </span></span>  
 <span data-ttu-id="5036b-172">[パイプライン デザイナーの使用](../core/using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="5036b-172">[Using Pipeline Designer](../core/using-pipeline-designer.md) </span></span>  
 <span data-ttu-id="5036b-173">[ビジネス ルール作成ツールの Windows](../core/windows-of-the-business-rule-composer.md) </span><span class="sxs-lookup"><span data-stu-id="5036b-173">[Windows of the Business Rule Composer](../core/windows-of-the-business-rule-composer.md) </span></span>  
 <span data-ttu-id="5036b-174">[BizTalk エディターを使用してください。](../core/using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="5036b-174">[Using BizTalk Editor](../core/using-biztalk-editor.md) </span></span>  
 <span data-ttu-id="5036b-175">[BizTalk マッパーの使用](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="5036b-175">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="5036b-176">開発ツール</span><span class="sxs-lookup"><span data-stu-id="5036b-176">Developer Tools</span></span>](../core/developer-tools.md)
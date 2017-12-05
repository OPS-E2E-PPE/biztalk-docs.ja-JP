---
title: "BizTalk プロジェクト システムの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, opening
- BizTalk Mapper, opening
- Orchestration Designer, opening
- Pipeline Designer, opening
ms.assetid: a28c715e-128c-463a-b421-9b3efe76a530
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5b8c3a83d75219b9e52fd2ab13124480d772832
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="using-the-biztalk-project-system"></a><span data-ttu-id="70344-102">BizTalk プロジェクト システムの使用</span><span class="sxs-lookup"><span data-stu-id="70344-102">Using the BizTalk Project System</span></span>
<span data-ttu-id="70344-103">BizTalk プロジェクト システムを使用すると、BizTalk ソリューションを Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境で作成、編成、および構成できます。</span><span class="sxs-lookup"><span data-stu-id="70344-103">You can use the BizTalk project system to create, organize, and configure BizTalk solutions in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="70344-104">このセクションの各トピックおよび手順では、BizTalk プロジェクト システムを使用して、さまざまな作業を行う方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="70344-104">The topics and procedures in this section describe how to perform various tasks by using the BizTalk project system.</span></span>  
  
 <span data-ttu-id="70344-105">BizTalk Server プロジェクト システムでは、同じプロジェクト管理の原則と内の他の Microsoft Build Engine (MSBuild) プロジェクトで使用するプロシージャ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="70344-105">The BizTalk Server project system uses the same project management principles and procedures that you use with other Microsoft Build Engine (MSBuild) projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="70344-106">このセクションでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で動作するアプリケーションの作成で行われる共通の作業手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="70344-106">This section details common procedures that you might use when creating an application that runs on Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="70344-107">MSBuild の詳細については、MSBuild のリファレンス セクションを参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)です。</span><span class="sxs-lookup"><span data-stu-id="70344-107">For more information about MSBuild, see the MSBuild reference section in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="70344-108">使用しての詳細については、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境では、「管理ソリューション、プロジェクト、およびファイル」を参照して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="70344-108">For more information about using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment, see "Managing Solutions, Projects, and Files" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx).</span></span>  
  
 <span data-ttu-id="70344-109">次の図は、BizTalk プロジェクト システム設計環境で、**新しいプロジェクト**ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70344-109">The following figure shows the BizTalk project system design environment with the **New Project** dialog box open.</span></span>  
  
 <span data-ttu-id="70344-110">![プロジェクト システム](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span><span class="sxs-lookup"><span data-stu-id="70344-110">![Project Systems](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span></span>  
<span data-ttu-id="70344-111">プロジェクト システム設計環境を示しています。</span><span class="sxs-lookup"><span data-stu-id="70344-111">Depicts the Project System Design Environment</span></span>  
  
### <a name="to-open-biztalk-editor"></a><span data-ttu-id="70344-112">BizTalk エディターを開くには</span><span class="sxs-lookup"><span data-stu-id="70344-112">To open BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="70344-113">ソリューション エクスプローラーで、スキーマをクリックします。</span><span class="sxs-lookup"><span data-stu-id="70344-113">In Solution Explorer, click a schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70344-114">BizTalk エディターを開くには、最初にスキーマを作成するか、既存のスキーマを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="70344-114">To open BizTalk Editor, you must first create a schema or open a previously created schema.</span></span> <span data-ttu-id="70344-115">スキーマを作成する方法の詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-115">For information about creating a schema, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="70344-116">参照してください[プロジェクト項目の追加](../core/adding-project-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-116">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="70344-117">**ビュー**  メニューのをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="70344-117">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="70344-118">- または -</span><span class="sxs-lookup"><span data-stu-id="70344-118">—Or—</span></span>  
  
     <span data-ttu-id="70344-119">スキーマを右クリックし、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="70344-119">Right-click the schema, and then click **Open**.</span></span>  
  
     <span data-ttu-id="70344-120">- または -</span><span class="sxs-lookup"><span data-stu-id="70344-120">—Or—</span></span>  
  
     <span data-ttu-id="70344-121">スキーマをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="70344-121">Double-click the schema.</span></span>  
  
     <span data-ttu-id="70344-122">選択されたスキーマが BizTalk エディターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="70344-122">The selected schema opens in BizTalk Editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70344-123">スキーマを作成するには、プロジェクトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="70344-123">To create a schema, you must have a project open.</span></span> <span data-ttu-id="70344-124">プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-124">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="70344-125">プロジェクトに項目を追加する方法の詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-125">For information about adding items to a project, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="70344-126">参照してください[プロジェクト項目の追加](../core/adding-project-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-126">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
### <a name="to-open-biztalk-mapper"></a><span data-ttu-id="70344-127">BizTalk マッパーを開くには</span><span class="sxs-lookup"><span data-stu-id="70344-127">To open BizTalk Mapper</span></span>  
  
1.  <span data-ttu-id="70344-128">ソリューション エクスプローラーで、マップをクリックします。</span><span class="sxs-lookup"><span data-stu-id="70344-128">In Solution Explorer, click a map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70344-129">BizTalk マッパーを開くには、最初にマップを作成するか、既存のマップを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="70344-129">To open BizTalk Mapper, you must first create a map or open a previously created map.</span></span> <span data-ttu-id="70344-130">マップを作成する方法の詳細については、次を参照してください。[新しいマップを作成する方法](../core/how-to-create-new-maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-130">For information about creating a map, see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span> <span data-ttu-id="70344-131">参照してください[プロジェクト項目の追加](../core/adding-project-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-131">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="70344-132">**ビュー**  メニューのをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="70344-132">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="70344-133">- または -</span><span class="sxs-lookup"><span data-stu-id="70344-133">—Or—</span></span>  
  
     <span data-ttu-id="70344-134">マップを右クリックし、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="70344-134">Right-click the map, and then click **Open**.</span></span>  
  
     <span data-ttu-id="70344-135">- または -</span><span class="sxs-lookup"><span data-stu-id="70344-135">—Or—</span></span>  
  
     <span data-ttu-id="70344-136">マップをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="70344-136">Double-click a map.</span></span>  
  
     <span data-ttu-id="70344-137">選択されたマップが BizTalk マッパーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="70344-137">The selected map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70344-138">マップを作成するには、プロジェクトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="70344-138">To create a map, you must have a project open.</span></span> <span data-ttu-id="70344-139">プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-139">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="70344-140">プロジェクトに項目を追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-140">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="70344-141">参照してください[新しいマップを作成する方法](../core/how-to-create-new-maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-141">Also see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span>  
  
### <a name="to-open-orchestration-designer"></a><span data-ttu-id="70344-142">オーケストレーション デザイナーを開くには</span><span class="sxs-lookup"><span data-stu-id="70344-142">To open Orchestration Designer</span></span>  
  
1.  <span data-ttu-id="70344-143">ソリューション エクスプローラーで、オーケストレーション (.odx) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70344-143">In Solution Explorer, click an orchestration (.odx).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70344-144">オーケストレーション デザイナーを開くには、最初にオーケストレーションを作成するか、既存のオーケストレーションを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="70344-144">To open Orchestration Designer, you must first create an orchestration or open a previously created orchestration.</span></span> <span data-ttu-id="70344-145">オーケストレーションを作成する方法については、次を参照してください。[オーケストレーション デザイナーでの作業](../core/working-in-orchestration-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-145">For information about how to create an orchestration, see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
2.  <span data-ttu-id="70344-146">**ビュー**  メニューのをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="70344-146">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="70344-147">- または -</span><span class="sxs-lookup"><span data-stu-id="70344-147">—Or—</span></span>  
  
     <span data-ttu-id="70344-148">オーケストレーションを右クリックし、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="70344-148">Right-click the orchestration, and then click **Open**.</span></span>  
  
     <span data-ttu-id="70344-149">- または -</span><span class="sxs-lookup"><span data-stu-id="70344-149">—Or—</span></span>  
  
     <span data-ttu-id="70344-150">オーケストレーションをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="70344-150">Double-click the orchestration.</span></span>  
  
     <span data-ttu-id="70344-151">オーケストレーション デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="70344-151">Orchestration Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70344-152">オーケストレーションを作成するには、プロジェクトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="70344-152">To create an orchestration, you must have a project open.</span></span> <span data-ttu-id="70344-153">プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-153">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="70344-154">プロジェクトに項目を追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-154">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="70344-155">参照してください[オーケストレーション デザイナーでの作業](../core/working-in-orchestration-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-155">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
### <a name="to-open-pipeline-designer"></a><span data-ttu-id="70344-156">パイプライン デザイナーを開くには</span><span class="sxs-lookup"><span data-stu-id="70344-156">To open Pipeline Designer</span></span>  
  
1.  <span data-ttu-id="70344-157">ソリューション エクスプローラーで、パイプラインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="70344-157">In Solution Explorer, click a pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70344-158">パイプライン デザイナーを開くには、最初にパイプラインを作成するか、既存のパイプラインを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="70344-158">To open Pipeline Designer, you must first create a pipeline or open a previously created pipeline.</span></span> <span data-ttu-id="70344-159">パイプラインを作成する方法については、次を参照してください。[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-159">For information about how to create a pipeline, see [How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md).</span></span>  
  
2.  <span data-ttu-id="70344-160">**ビュー**  メニューのをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="70344-160">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="70344-161">- または -</span><span class="sxs-lookup"><span data-stu-id="70344-161">—Or—</span></span>  
  
     <span data-ttu-id="70344-162">パイプラインを右クリックし、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="70344-162">Right-click the pipeline, and then click **Open**.</span></span>  
  
     <span data-ttu-id="70344-163">- または -</span><span class="sxs-lookup"><span data-stu-id="70344-163">—Or—</span></span>  
  
     <span data-ttu-id="70344-164">パイプラインをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="70344-164">Double-click the pipeline.</span></span>  
  
     <span data-ttu-id="70344-165">パイプライン デザイナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70344-165">Pipeline Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70344-166">パイプラインを作成するには、プロジェクトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="70344-166">To create a pipeline, you must have a project open.</span></span> <span data-ttu-id="70344-167">プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-167">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="70344-168">プロジェクトに項目を追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-168">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="70344-169">参照してください[オーケストレーション デザイナーでの作業](../core/working-in-orchestration-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="70344-169">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70344-170">参照</span><span class="sxs-lookup"><span data-stu-id="70344-170">See Also</span></span>  
 <span data-ttu-id="70344-171">[オーケストレーション デザイナーを使用してオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="70344-171">[Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md) </span></span>  
 <span data-ttu-id="70344-172">[パイプライン デザイナーの使用](../core/using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="70344-172">[Using Pipeline Designer](../core/using-pipeline-designer.md) </span></span>  
 <span data-ttu-id="70344-173">[ビジネス ルール作成ツールの Windows](../core/windows-of-the-business-rule-composer.md) </span><span class="sxs-lookup"><span data-stu-id="70344-173">[Windows of the Business Rule Composer](../core/windows-of-the-business-rule-composer.md) </span></span>  
 <span data-ttu-id="70344-174">[BizTalk エディターの使用](../core/using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="70344-174">[Using BizTalk Editor](../core/using-biztalk-editor.md) </span></span>  
 <span data-ttu-id="70344-175">[BizTalk マッパーの使用](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="70344-175">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="70344-176">開発ツール</span><span class="sxs-lookup"><span data-stu-id="70344-176">Developer Tools</span></span>](../core/developer-tools.md)
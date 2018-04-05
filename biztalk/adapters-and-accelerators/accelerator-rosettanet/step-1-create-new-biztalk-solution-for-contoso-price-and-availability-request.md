---
title: '手順 1: Contoso Price and Availability Request の新しい BizTalk ソリューションの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating solutions
ms.assetid: e323ce26-2031-4293-95bd-a3bf02e535a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee09981b11be8892eefe8d73d526e5712145c9c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-creating-a-new-biztalk-solution-for-the-contoso-price-and-availability-request"></a><span data-ttu-id="f7df2-102">手順 1: Contoso Price and Availability Request の新しい BizTalk ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="f7df2-102">Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request</span></span>
<span data-ttu-id="f7df2-103">この手順で作成、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Contoso Price and Availability Request プロジェクトのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="f7df2-103">In this step, you create a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] solution for the Contoso Price and Availability Request project.</span></span> <span data-ttu-id="f7df2-104">このプロジェクトには、3A2 Price and Availability メッセージの要求および応答のための、スキーマとマップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7df2-104">This project will contain the schemas and maps for the requests and responses for the 3A2 Price and Availability messages.</span></span>  
  
### <a name="to-create-a-blank-solution"></a><span data-ttu-id="f7df2-105">空のソリューションを作成するには</span><span class="sxs-lookup"><span data-stu-id="f7df2-105">To create a blank solution</span></span>  
  
1.  <span data-ttu-id="f7df2-106">開始**Microsoft Visual Studio 2012**です。</span><span class="sxs-lookup"><span data-stu-id="f7df2-106">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="f7df2-107">**[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7df2-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="f7df2-108">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**その他のプロジェクトの種類**select、 **Visual Studio ソリューション**、し、[、 **テンプレート**セクションで、**空のソリューション**です。</span><span class="sxs-lookup"><span data-stu-id="f7df2-108">In the New Project dialog box, in the **Project Types** section, expand **Other Project Types**, select **Visual Studio Solutions**, and then in the **Templates** section, select **Blank Solution**.</span></span>  
  
4.  <span data-ttu-id="f7df2-109">**名前**ボックスに、入力**Contoso**ソリューション名、およびクリックとして**[ok]**新しいソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7df2-109">In the **Name** box, type **Contoso** as the solution name, and then click **OK** to open the new solution.</span></span>  
  
### <a name="to-create-the-price-and-availability-project"></a><span data-ttu-id="f7df2-110">Price and Availability プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="f7df2-110">To create the Price and Availability project</span></span>  
  
1.  <span data-ttu-id="f7df2-111">Visual Studio での**ファイル** メニューのをポイント**新規**、順にクリック**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="f7df2-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="f7df2-112">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、 **BizTalk プロジェクト**、し、[、**テンプレート**セクションで、**空の BizTalkサーバー プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="f7df2-112">In the New Project dialog box, in the **Project Types** section, select **BizTalk Projects**, and then in the **Templates** section, select **Empty BizTalk Server Project**.</span></span>  
  
3.  <span data-ttu-id="f7df2-113">**名前**ボックスに、入力**ContosoPriceAndAvailability**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="f7df2-113">In the **Name** box, type **ContosoPriceAndAvailability** as the project name.</span></span> <span data-ttu-id="f7df2-114">**ソリューション****ソリューションに追加**です。</span><span class="sxs-lookup"><span data-stu-id="f7df2-114">For **Solution**, select **Add to Solution**.</span></span> <span data-ttu-id="f7df2-115">をクリックして**OK**新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7df2-115">Click **OK** to open the new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7df2-116">参照</span><span class="sxs-lookup"><span data-stu-id="f7df2-116">See Also</span></span>  
 [<span data-ttu-id="f7df2-117">手順 2: Price and Availability プロジェクトの BizTalk エディターを使用して用の Contoso LOB アプリケーション スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="f7df2-117">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-contoso-lob-application-schema-for-price-and-availability.md)
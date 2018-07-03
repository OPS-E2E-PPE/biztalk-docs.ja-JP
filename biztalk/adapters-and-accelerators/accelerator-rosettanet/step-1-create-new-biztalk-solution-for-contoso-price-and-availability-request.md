---
title: '手順 1: Contoso Price and Availability Request の新しい BizTalk ソリューションの作成 |Microsoft Docs'
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
ms.openlocfilehash: a4d48087411241f6ba26b55d4b20f6dce6a255e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971579"
---
# <a name="step-1-creating-a-new-biztalk-solution-for-the-contoso-price-and-availability-request"></a><span data-ttu-id="3ae53-102">手順 1: Contoso Price and Availability Request の新しい BizTalk ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ae53-102">Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request</span></span>
<span data-ttu-id="3ae53-103">この手順で Microsoft を作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Contoso Price and Availability Request プロジェクトのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="3ae53-103">In this step, you create a Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] solution for the Contoso Price and Availability Request project.</span></span> <span data-ttu-id="3ae53-104">このプロジェクトには、3A2 Price and Availability メッセージの要求および応答のための、スキーマとマップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ae53-104">This project will contain the schemas and maps for the requests and responses for the 3A2 Price and Availability messages.</span></span>  
  
### <a name="to-create-a-blank-solution"></a><span data-ttu-id="3ae53-105">空のソリューションを作成するには</span><span class="sxs-lookup"><span data-stu-id="3ae53-105">To create a blank solution</span></span>  
  
1.  <span data-ttu-id="3ae53-106">開始**Microsoft Visual Studio 2012**します。</span><span class="sxs-lookup"><span data-stu-id="3ae53-106">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="3ae53-107">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ae53-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="3ae53-108">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**その他のプロジェクトの種類**を選択します**Visual Studio ソリューション**、し、 **テンプレート**セクションで、**空のソリューション**します。</span><span class="sxs-lookup"><span data-stu-id="3ae53-108">In the New Project dialog box, in the **Project Types** section, expand **Other Project Types**, select **Visual Studio Solutions**, and then in the **Templates** section, select **Blank Solution**.</span></span>  
  
4.  <span data-ttu-id="3ae53-109">**名前**ボックスに「 **Contoso**としてソリューション名 をクリック**ok**を新しいソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ae53-109">In the **Name** box, type **Contoso** as the solution name, and then click **OK** to open the new solution.</span></span>  
  
### <a name="to-create-the-price-and-availability-project"></a><span data-ttu-id="3ae53-110">Price and Availability プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3ae53-110">To create the Price and Availability project</span></span>  
  
1.  <span data-ttu-id="3ae53-111">Visual Studio での**ファイル**メニューで、**新規**、順にクリックします**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="3ae53-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="3ae53-112">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**セクションで、 **BizTalk プロジェクト**、し、**テンプレート**セクションで、**空の BizTalkサーバー プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="3ae53-112">In the New Project dialog box, in the **Project Types** section, select **BizTalk Projects**, and then in the **Templates** section, select **Empty BizTalk Server Project**.</span></span>  
  
3.  <span data-ttu-id="3ae53-113">**名前**ボックスに「 **ContosoPriceAndAvailability**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="3ae53-113">In the **Name** box, type **ContosoPriceAndAvailability** as the project name.</span></span> <span data-ttu-id="3ae53-114">**ソリューション**、**ソリューションに追加**します。</span><span class="sxs-lookup"><span data-stu-id="3ae53-114">For **Solution**, select **Add to Solution**.</span></span> <span data-ttu-id="3ae53-115">をクリックして**OK**を新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ae53-115">Click **OK** to open the new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae53-116">参照</span><span class="sxs-lookup"><span data-stu-id="3ae53-116">See Also</span></span>  
 [<span data-ttu-id="3ae53-117">手順 2: BizTalk エディターを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="3ae53-117">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-contoso-lob-application-schema-for-price-and-availability.md)
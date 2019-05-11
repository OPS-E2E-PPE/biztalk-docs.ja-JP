---
title: チュートリアル 1:SharePoint サイト上の Siebel システムからのデータ表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dd06f75-75d1-4fad-8f34-51c97c7790e3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a12ab4e672851389c794267c9f34f88d8f393039
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370398"
---
# <a name="tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site"></a><span data-ttu-id="c7edd-102">チュートリアル 1:SharePoint サイト上の Siebel システムからのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="c7edd-102">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>
<span data-ttu-id="c7edd-103">このチュートリアルを使用して詳細な手順では、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] SharePoint ポータルで Siebel システムからビジネス データを表示する Microsoft Office SharePoint Server とします。</span><span class="sxs-lookup"><span data-stu-id="c7edd-103">This tutorial provides detailed instructions on using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server to present business data from a Siebel system on a SharePoint portal.</span></span> <span data-ttu-id="c7edd-104">使用する方法を示すために、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Office SharePoint server、Siebel リポジトリを使用して顧客アカウントの一覧を取得する、Office SharePoint Server で、アプリケーションを作成、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c7edd-104">To demonstrate how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Office SharePoint Server, we create an application in Office SharePoint Server to retrieve a list of customer accounts from the Siebel repository using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="c7edd-105">Siebel システムからこの情報を抽出、例では、クエリ メソッドを呼び出し、**アカウント**ビジネス コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="c7edd-105">To extract this information from the Siebel system, the example invokes the Query method on the **Account** business components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7edd-106">このチュートリアルで前を使用するためのすべての前提条件がインストールされているを確認します、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Office SharePoint Server の使用。</span><span class="sxs-lookup"><span data-stu-id="c7edd-106">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Office SharePoint Server.</span></span> <span data-ttu-id="c7edd-107">前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]通常にインストールされて、インストール ガイド\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。</span><span class="sxs-lookup"><span data-stu-id="c7edd-107">For more information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at \<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7edd-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c7edd-108">In This Section</span></span>  
  
-   [<span data-ttu-id="c7edd-109">ステップ 1: Siebel ビジネス コンポーネント操作を WCF サービスとして公開する</span><span class="sxs-lookup"><span data-stu-id="c7edd-109">Step 1: Publish the Siebel Business Component Operations as a WCF Service</span></span>](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)  
  
-   [<span data-ttu-id="c7edd-110">手順 2:Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="c7edd-110">Step 2: Create an Application Definition File for Siebel Business Component Operations</span></span>](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)  
  
-   [<span data-ttu-id="c7edd-111">ステップ 3:Siebel からデータを取得するための SharePoint アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="c7edd-111">Step 3: Create a SharePoint Application to Retrieve Data from Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)  
  
-  [<span data-ttu-id="c7edd-112">手順 4:SharePoint アプリケーションをテストする</span><span class="sxs-lookup"><span data-stu-id="c7edd-112">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7edd-113">参照</span><span class="sxs-lookup"><span data-stu-id="c7edd-113">See Also</span></span>  
 [<span data-ttu-id="c7edd-114">Siebel アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="c7edd-114">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)
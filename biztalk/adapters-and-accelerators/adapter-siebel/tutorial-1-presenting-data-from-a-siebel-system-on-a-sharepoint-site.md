---
title: "チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd06f75-75d1-4fad-8f34-51c97c7790e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7f31de42694cfa81a800d63f1c1d77ffff0bbaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site"></a><span data-ttu-id="5aa42-102">チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示</span><span class="sxs-lookup"><span data-stu-id="5aa42-102">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>
<span data-ttu-id="5aa42-103">このチュートリアルを使用して詳細な手順を説明する、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Microsoft Office SharePoint Server、Siebel システムからデータをビジネス SharePoint ポータルを表示するとします。</span><span class="sxs-lookup"><span data-stu-id="5aa42-103">This tutorial provides detailed instructions on using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server to present business data from a Siebel system on a SharePoint portal.</span></span> <span data-ttu-id="5aa42-104">使用する方法を示すために、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Office SharePoint Server と Siebel リポジトリを使用して、お客様のアカウントの一覧を取得する、Office SharePoint Server でアプリケーションを作成お、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5aa42-104">To demonstrate how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Office SharePoint Server, we create an application in Office SharePoint Server to retrieve a list of customer accounts from the Siebel repository using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="5aa42-105">Siebel システムからこの情報を抽出、例では、上、クエリ メソッドを呼び出し、**アカウント**ビジネス コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="5aa42-105">To extract this information from the Siebel system, the example invokes the Query method on the **Account** business components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5aa42-106">チュートリアルの前を使用するためのすべての前提条件がインストールされていることを確認してください、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Office SharePoint Server とします。</span><span class="sxs-lookup"><span data-stu-id="5aa42-106">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Office SharePoint Server.</span></span> <span data-ttu-id="5aa42-107">前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイド 』 に通常インストール\<インストール ドライブ >: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。</span><span class="sxs-lookup"><span data-stu-id="5aa42-107">For more information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at \<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5aa42-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5aa42-108">In This Section</span></span>  
  
-   [<span data-ttu-id="5aa42-109">手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="5aa42-109">Step 1: Publish the Siebel Business Component Operations as a WCF Service</span></span>](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)  
  
-   [<span data-ttu-id="5aa42-110">手順 2: Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5aa42-110">Step 2: Create an Application Definition File for Siebel Business Component Operations</span></span>](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)  
  
-   [<span data-ttu-id="5aa42-111">手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5aa42-111">Step 3: Create a SharePoint Application to Retrieve Data from Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)  
  
-  [<span data-ttu-id="5aa42-112">手順 4: SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="5aa42-112">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="5aa42-113">参照</span><span class="sxs-lookup"><span data-stu-id="5aa42-113">See Also</span></span>  
 [<span data-ttu-id="5aa42-114">Siebel アダプタ チュートリアル</span><span class="sxs-lookup"><span data-stu-id="5aa42-114">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)
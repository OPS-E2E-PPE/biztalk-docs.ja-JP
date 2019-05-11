---
title: チュートリアル 1:SharePoint サイト上の SAP システムからのデータ表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MOSS, creating an application in
- Microsoft Office SharePoint Server
- MOSS
- Microsoft Office SharePoint Server, creating an application in
ms.assetid: 6e31c365-446c-4fe1-8538-fa6c869eed63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5365f75982677124e8cd529ffa78b76c66dd2358
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372398"
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a><span data-ttu-id="ea0e0-102">チュートリアル 1:SharePoint サイト上の SAP システムからデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-102">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>
<span data-ttu-id="ea0e0-103">このチュートリアルを使用して詳細な手順では、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SharePoint ポータルでの SAP システムからビジネス データを表示する Microsoft Office SharePoint Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-103">This tutorial provides detailed instructions on using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft Office SharePoint Server to present business data from an SAP system on a SharePoint portal.</span></span> <span data-ttu-id="ea0e0-104">使用する方法を示すために、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Office SharePoint server では、ビジネスでの 2 つの最も一般的なエンティティ検討してください: 顧客および販売注文します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-104">To demonstrate how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Office SharePoint Server, consider the two most common entities in any business: customers and sales orders.</span></span> <span data-ttu-id="ea0e0-105">この例では、Office SharePoint Server を使用して、アプリケーションを作成、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-105">In this example, an application is created in Office SharePoint Server, which uses the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to do the following:</span></span>  
  
- <span data-ttu-id="ea0e0-106">検索文字列に基づいて、SAP システムから顧客の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-106">Retrieve a list of customers from the SAP system based on a search string.</span></span>  
  
- <span data-ttu-id="ea0e0-107">顧客の一覧と表示の詳細から顧客を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-107">Select a customer from the list and present details for the customer.</span></span>  
  
- <span data-ttu-id="ea0e0-108">選択した顧客の販売注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-108">Retrieve the sales orders for the selected customer.</span></span>  
  
  <span data-ttu-id="ea0e0-109">SAP システムから顧客データを抽出するには、SD_RFC_CUSTOMER_GET RFC を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-109">To extract customer data from an SAP system, the example uses the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="ea0e0-110">特定の顧客の販売注文に関する情報を抽出するには、BAPI_SALESORDER_GETLIST RFC を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-110">To extract information about sales orders for a specific customer, it uses the BAPI_SALESORDER_GETLIST RFC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea0e0-111">SAP システムの一部のバージョンでは、SD_RFC_CUSTOMER_GET ではなく RFC_CUSTOMER_GET RFC を公開します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-111">Some versions of the SAP system expose an RFC_CUSTOMER_GET RFC instead of SD_RFC_CUSTOMER_GET.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="ea0e0-112">このチュートリアルで前を使用するためのすべての前提条件がインストールされているを確認します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Office SharePoint Server の使用。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-112">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Office SharePoint Server.</span></span> <span data-ttu-id="ea0e0-113">前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイド、通常は c:/プログラム ファイルまたは Microsoft にインストールされている [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] /文書化します。</span><span class="sxs-lookup"><span data-stu-id="ea0e0-113">For more information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at C:/Program Files/Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]/Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea0e0-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ea0e0-114">In This Section</span></span>  
  
-   [<span data-ttu-id="ea0e0-115">ステップ 1: SAP アイテムを WCF サービスとして公開する</span><span class="sxs-lookup"><span data-stu-id="ea0e0-115">Step 1: Publish the SAP Artifacts as a WCF Service</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [<span data-ttu-id="ea0e0-116">手順 2:SAP アイテム用のアプリケーション定義ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="ea0e0-116">Step 2: Create an Application Definition File for the SAP Artifacts</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [<span data-ttu-id="ea0e0-117">ステップ 3:SAP からデータを取得するための SharePoint アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="ea0e0-117">Step 3: Create a SharePoint Application to Retrieve Data from SAP</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [<span data-ttu-id="ea0e0-118">手順 4:SharePoint アプリケーションをテストする</span><span class="sxs-lookup"><span data-stu-id="ea0e0-118">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea0e0-119">参照</span><span class="sxs-lookup"><span data-stu-id="ea0e0-119">See Also</span></span>  
 [<span data-ttu-id="ea0e0-120">SAP アダプター チュートリアル</span><span class="sxs-lookup"><span data-stu-id="ea0e0-120">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)
---
title: 'チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示 |Microsoft ドキュメント'
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
ms.openlocfilehash: cdc3ea5e41600aebcef1fda933735c418dec78c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217426"
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a><span data-ttu-id="1b72f-102">チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示</span><span class="sxs-lookup"><span data-stu-id="1b72f-102">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>
<span data-ttu-id="1b72f-103">このチュートリアルを使用して詳細な手順を説明する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Microsoft Office SharePoint Server、SharePoint portal に SAP システムからビジネス データを表示するとします。</span><span class="sxs-lookup"><span data-stu-id="1b72f-103">This tutorial provides detailed instructions on using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft Office SharePoint Server to present business data from an SAP system on a SharePoint portal.</span></span> <span data-ttu-id="1b72f-104">使用する方法を示すために、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Office SharePoint Server と、あらゆるビジネスで 2 つの最も一般的なエンティティを考慮します: 顧客および販売注文します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-104">To demonstrate how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Office SharePoint Server, consider the two most common entities in any business: customers and sales orders.</span></span> <span data-ttu-id="1b72f-105">Office SharePoint server を使用してアプリケーションを作成するこの例では、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を次を行うには。</span><span class="sxs-lookup"><span data-stu-id="1b72f-105">In this example, an application is created in Office SharePoint Server, which uses the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to do the following:</span></span>  
  
-   <span data-ttu-id="1b72f-106">検索文字列に基づき、SAP システムから顧客の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-106">Retrieve a list of customers from the SAP system based on a search string.</span></span>  
  
-   <span data-ttu-id="1b72f-107">顧客のリストと存在詳細から顧客を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-107">Select a customer from the list and present details for the customer.</span></span>  
  
-   <span data-ttu-id="1b72f-108">選択した顧客の販売注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-108">Retrieve the sales orders for the selected customer.</span></span>  
  
 <span data-ttu-id="1b72f-109">SAP システムから顧客データを抽出するには、SD_RFC_CUSTOMER_GET RFC を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-109">To extract customer data from an SAP system, the example uses the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="1b72f-110">特定の顧客の販売注文に関する情報を抽出するには、BAPI_SALESORDER_GETLIST RFC を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-110">To extract information about sales orders for a specific customer, it uses the BAPI_SALESORDER_GETLIST RFC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b72f-111">SAP システムのバージョンによっては、SD_RFC_CUSTOMER_GET ではなく RFC_CUSTOMER_GET RFC を公開します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-111">Some versions of the SAP system expose an RFC_CUSTOMER_GET RFC instead of SD_RFC_CUSTOMER_GET.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b72f-112">チュートリアルの前を使用するためのすべての前提条件がインストールされていることを確認してください、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Office SharePoint Server とします。</span><span class="sxs-lookup"><span data-stu-id="1b72f-112">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Office SharePoint Server.</span></span> <span data-ttu-id="1b72f-113">前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]通常 c:/program ファイルまたは Microsoft にインストールされているインストール ガイド[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]ドキュメント/です。</span><span class="sxs-lookup"><span data-stu-id="1b72f-113">For more information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at C:/Program Files/Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]/Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b72f-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1b72f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="1b72f-115">手順 1: WCF サービスとして SAP アイテムを公開します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-115">Step 1: Publish the SAP Artifacts as a WCF Service</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [<span data-ttu-id="1b72f-116">手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-116">Step 2: Create an Application Definition File for the SAP Artifacts</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [<span data-ttu-id="1b72f-117">手順 3: SAP からデータを取得する SharePoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b72f-117">Step 3: Create a SharePoint Application to Retrieve Data from SAP</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [<span data-ttu-id="1b72f-118">手順 4: SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="1b72f-118">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a><span data-ttu-id="1b72f-119">参照</span><span class="sxs-lookup"><span data-stu-id="1b72f-119">See Also</span></span>  
 [<span data-ttu-id="1b72f-120">SAP アダプタ チュートリアル</span><span class="sxs-lookup"><span data-stu-id="1b72f-120">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)
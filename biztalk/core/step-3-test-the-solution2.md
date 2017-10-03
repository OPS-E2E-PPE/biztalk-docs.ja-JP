---
title: "手順 3: テストのソリューション 2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30dbc7c9-3c5f-4953-b26f-5c41141c22ad
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0e484a9f6af788775ec4ae7309965327378267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-solution"></a><span data-ttu-id="dbedb-102">手順 3: ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="dbedb-102">Step 3: Test the Solution</span></span>
<span data-ttu-id="dbedb-103">![手順 3 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="dbedb-103">![Step 3 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="dbedb-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="dbedb-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="dbedb-105">**目標:** EAI ソリューションでメッセージをどのように処理するかをテストするこの手順でします。</span><span class="sxs-lookup"><span data-stu-id="dbedb-105">**Objective:** In this step, you test how the EAI solution processes messages.</span></span>  
  
 <span data-ttu-id="dbedb-106">**目的:**この手順では、EAIProcess オーケストレーションでメッセージが正しく処理されているチェックします。</span><span class="sxs-lookup"><span data-stu-id="dbedb-106">**Purpose:** In this step, you check that the EAIProcess orchestration processes messages correctly.</span></span> <span data-ttu-id="dbedb-107">EAI アプリケーションに指定されている受信場所にサンプル メッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="dbedb-107">You do this by dropping sample messages into the receive location specified for the EAI application.</span></span> <span data-ttu-id="dbedb-108">EAI ソリューションが適切に機能している場合、倉庫から EAIProcess オーケストレーションへのメッセージで要求される項目数が 500 を超えると、オーケストレーションでは要求拒否メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dbedb-108">If the EAI solution is working properly, if the EAIProcess orchestration receives a message from the warehouse requesting more than 500 items, the orchestration generates a decline request message.</span></span> <span data-ttu-id="dbedb-109">倉庫から EAIProcess オーケストレーションへのメッセージで要求される項目数が 500 以下であれば、メッセージは ERP システムに渡されます。</span><span class="sxs-lookup"><span data-stu-id="dbedb-109">If the EAIProcess orchestration receives a message from the warehouse requesting fewer than 500 items, the orchestration passes the message on to the ERP system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dbedb-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="dbedb-110">Prerequisites</span></span>  
 <span data-ttu-id="dbedb-111">この手順を開始する前に行う必要があります[手順 2: 構成し、アプリケーションを起動](../core/step-2-configure-and-start-the-application1.md)です。</span><span class="sxs-lookup"><span data-stu-id="dbedb-111">Before you begin this step you must complete [Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="dbedb-112">手順</span><span class="sxs-lookup"><span data-stu-id="dbedb-112">Procedures</span></span>  
  
#### <a name="to-test-the-eai-solution"></a><span data-ttu-id="dbedb-113">EAI ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dbedb-113">To test the EAI solution</span></span>  
  
1.  <span data-ttu-id="dbedb-114">Windows エクスプ ローラーを開きに移動**C:\BTSTutorials\WareHouse**です。</span><span class="sxs-lookup"><span data-stu-id="dbedb-114">Open Windows Explorer, and navigate to **C:\BTSTutorials\WareHouse**.</span></span>  <span data-ttu-id="dbedb-115">このフォルダーは、チュートリアル ファイルのインストールによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="dbedb-115">This folder is created by installing the tutorial files.</span></span>  
  
2.  <span data-ttu-id="dbedb-116">コピー **RequestInstance.XML**貼り付けます**C:\BTSTutorials\WareHouse\Request**です。</span><span class="sxs-lookup"><span data-stu-id="dbedb-116">Copy **RequestInstance.XML** and paste it into **C:\BTSTutorials\WareHouse\Request**.</span></span>  
  
3.  <span data-ttu-id="dbedb-117">ファイルが消え、ときに確認**C:\BTSTutorials\ERP\Request**です。</span><span class="sxs-lookup"><span data-stu-id="dbedb-117">When the file disappears, check **C:\BTSTutorials\ERP\Request**.</span></span>  
  
4.  <span data-ttu-id="dbedb-118">Windows エクスプ ローラーに移動**C:\BTSTutorials\WareHouse**です。</span><span class="sxs-lookup"><span data-stu-id="dbedb-118">In Windows Explorer, navigate to **C:\BTSTutorials\WareHouse**.</span></span>  
  
5.  <span data-ttu-id="dbedb-119">コピー **RequestInstance (制限) を超えています。XML**貼り付けます**C:\BTSTutorials\WareHouse\Request**です。</span><span class="sxs-lookup"><span data-stu-id="dbedb-119">Copy **RequestInstance(Over Limit).XML** and paste it into **C:\BTSTutorials\WareHouse\Request**.</span></span>  
  
6.  <span data-ttu-id="dbedb-120">ファイルが消え、ときに確認**C:\BTSTutorials\WareHouse\RequestDecline**です。</span><span class="sxs-lookup"><span data-stu-id="dbedb-120">When the file disappears, check **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="dbedb-121">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="dbedb-121">What did I just do?</span></span>  
 <span data-ttu-id="dbedb-122">このステップでは、サンプル メッセージを EAI アプリケーションの受信場所に格納し、EAI ソリューションをテストしました。</span><span class="sxs-lookup"><span data-stu-id="dbedb-122">You tested the EAI solution by placing sample messages in the receive location for the EAI application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbedb-123">参照</span><span class="sxs-lookup"><span data-stu-id="dbedb-123">See Also</span></span>  
 <span data-ttu-id="dbedb-124">[手順 1: 配置プロジェクト](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="dbedb-124">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="dbedb-125">手順 2: を構成し、アプリケーションを起動</span><span class="sxs-lookup"><span data-stu-id="dbedb-125">Step 2: Configure and Start the Application</span></span>](../core/step-2-configure-and-start-the-application1.md)
---
title: 手順 3:テスト、Solution2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30dbc7c9-3c5f-4953-b26f-5c41141c22ad
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e585019df8d6aa13374bb5648d37b10273d99cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392638"
---
# <a name="step-3-test-the-solution"></a><span data-ttu-id="5f84a-102">手順 3:ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="5f84a-102">Step 3: Test the Solution</span></span>
<span data-ttu-id="5f84a-103">![ステップ 3/3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="5f84a-103">![Step 3 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="5f84a-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="5f84a-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="5f84a-105">**目標:** この手順では、EAI ソリューションでのメッセージの処理方法をテストします。</span><span class="sxs-lookup"><span data-stu-id="5f84a-105">**Objective:** In this step, you test how the EAI solution processes messages.</span></span>  
  
 <span data-ttu-id="5f84a-106">**目的:** この手順では、EAIProcess オーケストレーションがメッセージを正しく処理することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-106">**Purpose:** In this step, you check that the EAIProcess orchestration processes messages correctly.</span></span> <span data-ttu-id="5f84a-107">EAI アプリケーションに指定された受信場所にサンプル メッセージを削除しています。 これを行います。</span><span class="sxs-lookup"><span data-stu-id="5f84a-107">You do this by dropping sample messages into the receive location specified for the EAI application.</span></span> <span data-ttu-id="5f84a-108">500 個を超える項目、倉庫から EAIProcess オーケストレーションがメッセージを受信する場合、EAI ソリューションは、適切に動作は、オーケストレーションは、要求拒否メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-108">If the EAI solution is working properly, if the EAIProcess orchestration receives a message from the warehouse requesting more than 500 items, the orchestration generates a decline request message.</span></span> <span data-ttu-id="5f84a-109">では、EAIProcess オーケストレーションでは、500 未満の項目を要求するウェアハウスからメッセージを受信した場合、オーケストレーションは、メッセージを ERP システムを渡します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-109">If the EAIProcess orchestration receives a message from the warehouse requesting fewer than 500 items, the orchestration passes the message on to the ERP system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5f84a-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="5f84a-110">Prerequisites</span></span>  
 <span data-ttu-id="5f84a-111">この手順を開始する前に行う必要があります[手順 2。構成し、アプリケーションを起動](../core/step-2-configure-and-start-the-application1.md)します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-111">Before you begin this step you must complete [Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="5f84a-112">手順</span><span class="sxs-lookup"><span data-stu-id="5f84a-112">Procedures</span></span>  
  
#### <a name="to-test-the-eai-solution"></a><span data-ttu-id="5f84a-113">EAI ソリューションをテストするには</span><span class="sxs-lookup"><span data-stu-id="5f84a-113">To test the EAI solution</span></span>  
  
1.  <span data-ttu-id="5f84a-114">Windows エクスプ ローラーを開きに移動します**C:\BTSTutorials\WareHouse**します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-114">Open Windows Explorer, and navigate to **C:\BTSTutorials\WareHouse**.</span></span>  <span data-ttu-id="5f84a-115">このフォルダーは、チュートリアル ファイルをインストールすることによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f84a-115">This folder is created by installing the tutorial files.</span></span>  
  
2.  <span data-ttu-id="5f84a-116">コピー **RequestInstance.XML**貼り付けます**C:\BTSTutorials\WareHouse\Request**します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-116">Copy **RequestInstance.XML** and paste it into **C:\BTSTutorials\WareHouse\Request**.</span></span>  
  
3.  <span data-ttu-id="5f84a-117">ファイルが、確認**C:\BTSTutorials\ERP\Request**します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-117">When the file disappears, check **C:\BTSTutorials\ERP\Request**.</span></span>  
  
4.  <span data-ttu-id="5f84a-118">Windows エクスプ ローラーに移動します。 **C:\BTSTutorials\WareHouse**します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-118">In Windows Explorer, navigate to **C:\BTSTutorials\WareHouse**.</span></span>  
  
5.  <span data-ttu-id="5f84a-119">コピー **RequestInstance (上限) を超えています。XML**貼り付けます**C:\BTSTutorials\WareHouse\Request**します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-119">Copy **RequestInstance(Over Limit).XML** and paste it into **C:\BTSTutorials\WareHouse\Request**.</span></span>  
  
6.  <span data-ttu-id="5f84a-120">ファイルが、確認**C:\BTSTutorials\WareHouse\RequestDecline**します。</span><span class="sxs-lookup"><span data-stu-id="5f84a-120">When the file disappears, check **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="5f84a-121">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="5f84a-121">What did I just do?</span></span>  
 <span data-ttu-id="5f84a-122">EAI アプリケーションの受信場所にサンプル メッセージを配置することで、EAI ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="5f84a-122">You tested the EAI solution by placing sample messages in the receive location for the EAI application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f84a-123">参照</span><span class="sxs-lookup"><span data-stu-id="5f84a-123">See Also</span></span>  
 <span data-ttu-id="5f84a-124">[ステップ 1: プロジェクトを配置します。](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="5f84a-124">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="5f84a-125">手順 2:アプリケーションの構成と開始</span><span class="sxs-lookup"><span data-stu-id="5f84a-125">Step 2: Configure and Start the Application</span></span>](../core/step-2-configure-and-start-the-application1.md)
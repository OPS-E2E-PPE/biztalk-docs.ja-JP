---
title: BizTalk Server Projects1 にスキーマのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70eff140259cd7cf815e8e05125f9ade78bf5493
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982363"
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="09d5b-102">BizTalk Server プロジェクトへのスキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="09d5b-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="09d5b-103">ここでは、BizTalk Server プロジェクトにスキーマをインポートする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-103">The following information describes how to import schemas into a BizTalk Server project.</span></span>  
  
## <a name="importing-schemas"></a><span data-ttu-id="09d5b-104">スキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="09d5b-104">Importing Schemas</span></span>  
  
#### <a name="to-import-schemas"></a><span data-ttu-id="09d5b-105">スキーマをインポートするには</span><span class="sxs-lookup"><span data-stu-id="09d5b-105">To import schemas</span></span>  
  
1. <span data-ttu-id="09d5b-106">ソリューション エクスプ ローラーでプロジェクトを右クリックして**追加**、選び**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-106">In Solution Explorer, right-click the project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
2. <span data-ttu-id="09d5b-107">をクリックして**アダプタの追加**、し、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-107">Click **Add adapter**, and then select **Open**.</span></span>  
  
3. <span data-ttu-id="09d5b-108">アダプターを選択して<strong>、j. d.Edwards OneWorld XE</strong>します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-108">Select the adapter<strong>, J.D. Edwards OneWorld XE</strong>.</span></span>  
  
4. <span data-ttu-id="09d5b-109">ボックスの一覧で、ポートを選択します。 **[SSOSendToJD Edwards OneWorld XE**、] をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="09d5b-109">In the drop-down list, select the port **SSOSendToJD Edwards OneWorld XE**, and then click **Next**.</span></span>  
  
    <span data-ttu-id="09d5b-110">MyJ.D します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-110">The myJ.D.</span></span> <span data-ttu-id="09d5b-111">Edwards OneWorld XESSO 論理システムが (この論理システムは、によりで作成されましたブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d5b-111">Edwards OneWorld XESSO logical system appears in the browser (this logical system was created with the SSOSendToJ.D.</span></span> <span data-ttu-id="09d5b-112">Edwards OneWorld XE ポート)。</span><span class="sxs-lookup"><span data-stu-id="09d5b-112">Edwards OneWorld XE port).</span></span>  
  
5. <span data-ttu-id="09d5b-113">展開**myJ.D します。Edwards OneWorld XESSO**します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-113">Expand **myJ.D. Edwards OneWorld XESSO**.</span></span>  
  
6. <span data-ttu-id="09d5b-114">アイテムを移動 (またはドラッグするだけで) 矢印アイコンをクリックして、**送信**ウィンドウ、およびクリック**OK**。</span><span class="sxs-lookup"><span data-stu-id="09d5b-114">Click the arrow icon to move the item (or simply drag it) into the **Transmit** window, and then click **OK**.</span></span>  
  
    <span data-ttu-id="09d5b-115">SSOSchedule プロジェクトにスキーマが追加されます。</span><span class="sxs-lookup"><span data-stu-id="09d5b-115">The schemas are added to the SSOSchedule project.</span></span>  
  
7. <span data-ttu-id="09d5b-116">ソリューション エクスプ ローラーで、 **SSOSchedule プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-116">In Solution Explorer, expand **SSOSchedule project**.</span></span>  
  
8. <span data-ttu-id="09d5b-117">右クリック**BizTalk orchestration.odx**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-117">Right-click **BizTalk orchestration.odx**, and then click **Delete**.</span></span>  
  
9. <span data-ttu-id="09d5b-118">ソリューション エクスプ ローラーでダブルクリック**GetList.odx**オーケストレーションを検査します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-118">In Solution Explorer, double-click **GetList.odx** to inspect the orchestration.</span></span>  
  
## <a name="orchestration-types---port-types"></a><span data-ttu-id="09d5b-119">オーケストレーションの種類 - ポートの種類</span><span class="sxs-lookup"><span data-stu-id="09d5b-119">Orchestration Types - Port Types</span></span>  
  
-   <span data-ttu-id="09d5b-120">**PortTypeIn/で/要求:** SSOSchedule.myJ.D します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-120">**PortTypeIn/In/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="09d5b-121">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="09d5b-121">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="09d5b-122">**PortTypeOut/アウト/応答:** SSOSchedule.myJ.D します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-122">**PortTypeOut/Out/response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="09d5b-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="09d5b-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
-   <span data-ttu-id="09d5b-124">**PortTypeInOut/InOut/要求:** SSOSchedule.myJ.D します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-124">**PortTypeInOut/InOut/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="09d5b-125">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="09d5b-125">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="09d5b-126">**PortTypeInOut/InOut/応答:** SSOSchedule.myJ.D します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-126">**PortTypeInOut/InOut/Response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="09d5b-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="09d5b-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="orchestration-variables---messages"></a><span data-ttu-id="09d5b-128">オーケストレーション変数 - メッセージ</span><span class="sxs-lookup"><span data-stu-id="09d5b-128">Orchestration Variables - Messages</span></span>  
  
-   <span data-ttu-id="09d5b-129">**MessageIn:** SSOSchedule.myJ.D します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-129">**MessageIn:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="09d5b-130">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="09d5b-130">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="09d5b-131">**MessageOut:** SSOSchedule.myJ.D します。</span><span class="sxs-lookup"><span data-stu-id="09d5b-131">**MessageOut:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="09d5b-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="09d5b-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d5b-133">参照</span><span class="sxs-lookup"><span data-stu-id="09d5b-133">See Also</span></span>  
 [<span data-ttu-id="09d5b-134">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="09d5b-134">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)
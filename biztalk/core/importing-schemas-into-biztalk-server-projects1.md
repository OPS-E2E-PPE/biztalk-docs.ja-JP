---
title: "BizTalk Server Projects1 へのスキーマのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c0e67ef4e47b62e0381d882739b2fdc012ba621
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="55c57-102">BizTalk Server プロジェクトへのスキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="55c57-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="55c57-103">ここでは、BizTalk Server プロジェクトにスキーマをインポートする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="55c57-103">The following information describes how to import schemas into a BizTalk Server project.</span></span>  
  
## <a name="importing-schemas"></a><span data-ttu-id="55c57-104">スキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="55c57-104">Importing Schemas</span></span>  
  
#### <a name="to-import-schemas"></a><span data-ttu-id="55c57-105">スキーマをインポートするには</span><span class="sxs-lookup"><span data-stu-id="55c57-105">To import schemas</span></span>  
  
1.  <span data-ttu-id="55c57-106">ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**を選択して**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="55c57-106">In Solution Explorer, right-click the project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="55c57-107">をクリックして**アダプタの追加**、し、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="55c57-107">Click **Add adapter**, and then select **Open**.</span></span>  
  
3.  <span data-ttu-id="55c57-108">アダプターを選択して**、j. d.Edwards OneWorld XE**です。</span><span class="sxs-lookup"><span data-stu-id="55c57-108">Select the adapter**, J.D. Edwards OneWorld XE**.</span></span>  
  
4.  <span data-ttu-id="55c57-109">ドロップダウン リストで、ポートを選択**SSOSendToJD Edwards OneWorld XE**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="55c57-109">In the drop-down list, select the port **SSOSendToJD Edwards OneWorld XE**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="55c57-110">MyJ.D です。</span><span class="sxs-lookup"><span data-stu-id="55c57-110">The myJ.D.</span></span> <span data-ttu-id="55c57-111">Edwards OneWorld XESSO 論理システムが (この論理システムは、SSOSendToJ.D で作成されましたブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="55c57-111">Edwards OneWorld XESSO logical system appears in the browser (this logical system was created with the SSOSendToJ.D.</span></span> <span data-ttu-id="55c57-112">Edwards OneWorld XE ポート)。</span><span class="sxs-lookup"><span data-stu-id="55c57-112">Edwards OneWorld XE port).</span></span>  
  
5.  <span data-ttu-id="55c57-113">展開**myJ.D です。Edwards OneWorld XESSO**です。</span><span class="sxs-lookup"><span data-stu-id="55c57-113">Expand **myJ.D. Edwards OneWorld XESSO**.</span></span>  
  
6.  <span data-ttu-id="55c57-114">項目へ移動します (またはドラッグ) にある矢印アイコンをクリックして、**送信**ウィンドウ、およびクリック**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="55c57-114">Click the arrow icon to move the item (or simply drag it) into the **Transmit** window, and then click **OK**.</span></span>  
  
     <span data-ttu-id="55c57-115">SSOSchedule プロジェクトにスキーマが追加されます。</span><span class="sxs-lookup"><span data-stu-id="55c57-115">The schemas are added to the SSOSchedule project.</span></span>  
  
7.  <span data-ttu-id="55c57-116">ソリューション エクスプ ローラーで、 **SSOSchedule プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="55c57-116">In Solution Explorer, expand **SSOSchedule project**.</span></span>  
  
8.  <span data-ttu-id="55c57-117">右クリック**BizTalk orchestration.odx**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="55c57-117">Right-click **BizTalk orchestration.odx**, and then click **Delete**.</span></span>  
  
9. <span data-ttu-id="55c57-118">ソリューション エクスプ ローラーで、 **GetList.odx**をオーケストレーションを検査します。</span><span class="sxs-lookup"><span data-stu-id="55c57-118">In Solution Explorer, double-click **GetList.odx** to inspect the orchestration.</span></span>  
  
## <a name="orchestration-types---port-types"></a><span data-ttu-id="55c57-119">オーケストレーションの種類 - ポートの種類</span><span class="sxs-lookup"><span data-stu-id="55c57-119">Orchestration Types - Port Types</span></span>  
  
-   <span data-ttu-id="55c57-120">**PortTypeIn/で/要求:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="55c57-120">**PortTypeIn/In/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="55c57-121">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="55c57-121">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="55c57-122">**PortTypeOut/アウト/応答:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="55c57-122">**PortTypeOut/Out/response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="55c57-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="55c57-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
-   <span data-ttu-id="55c57-124">**PortTypeInOut/InOut/要求:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="55c57-124">**PortTypeInOut/InOut/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="55c57-125">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="55c57-125">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="55c57-126">**PortTypeInOut/InOut/応答:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="55c57-126">**PortTypeInOut/InOut/Response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="55c57-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="55c57-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="orchestration-variables---messages"></a><span data-ttu-id="55c57-128">オーケストレーション変数 - メッセージ</span><span class="sxs-lookup"><span data-stu-id="55c57-128">Orchestration Variables - Messages</span></span>  
  
-   <span data-ttu-id="55c57-129">**MessageIn:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="55c57-129">**MessageIn:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="55c57-130">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="55c57-130">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="55c57-131">**MessageOut:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="55c57-131">**MessageOut:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="55c57-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="55c57-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c57-133">参照</span><span class="sxs-lookup"><span data-stu-id="55c57-133">See Also</span></span>  
 [<span data-ttu-id="55c57-134">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="55c57-134">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)
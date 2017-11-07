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
ms.openlocfilehash: 719679dffa5bcffdeddcbcd889f847f147a705b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="11292-102">BizTalk Server プロジェクトへのスキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="11292-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="11292-103">ここでは、BizTalk Server プロジェクトにスキーマをインポートする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="11292-103">The following information describes how to import schemas into a BizTalk Server project.</span></span>  
  
## <a name="importing-schemas"></a><span data-ttu-id="11292-104">スキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="11292-104">Importing Schemas</span></span>  
  
#### <a name="to-import-schemas"></a><span data-ttu-id="11292-105">スキーマをインポートするには</span><span class="sxs-lookup"><span data-stu-id="11292-105">To import schemas</span></span>  
  
1.  <span data-ttu-id="11292-106">ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**を選択して**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="11292-106">In Solution Explorer, right-click the project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="11292-107">をクリックして**アダプタの追加**、し、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="11292-107">Click **Add adapter**, and then select **Open**.</span></span>  
  
3.  <span data-ttu-id="11292-108">アダプターを選択して**、j. d.Edwards OneWorld XE**です。</span><span class="sxs-lookup"><span data-stu-id="11292-108">Select the adapter**, J.D. Edwards OneWorld XE**.</span></span>  
  
4.  <span data-ttu-id="11292-109">ドロップダウン リストで、ポートを選択**SSOSendToJD Edwards OneWorld XE**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="11292-109">In the drop-down list, select the port **SSOSendToJD Edwards OneWorld XE**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="11292-110">MyJ.D です。</span><span class="sxs-lookup"><span data-stu-id="11292-110">The myJ.D.</span></span> <span data-ttu-id="11292-111">Edwards OneWorld XESSO 論理システムが (この論理システムは、SSOSendToJ.D で作成されましたブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="11292-111">Edwards OneWorld XESSO logical system appears in the browser (this logical system was created with the SSOSendToJ.D.</span></span> <span data-ttu-id="11292-112">Edwards OneWorld XE ポート)。</span><span class="sxs-lookup"><span data-stu-id="11292-112">Edwards OneWorld XE port).</span></span>  
  
5.  <span data-ttu-id="11292-113">展開**myJ.D です。Edwards OneWorld XESSO**です。</span><span class="sxs-lookup"><span data-stu-id="11292-113">Expand **myJ.D. Edwards OneWorld XESSO**.</span></span>  
  
6.  <span data-ttu-id="11292-114">項目へ移動します (またはドラッグ) にある矢印アイコンをクリックして、**送信**ウィンドウ、およびクリック**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="11292-114">Click the arrow icon to move the item (or simply drag it) into the **Transmit** window, and then click **OK**.</span></span>  
  
     <span data-ttu-id="11292-115">SSOSchedule プロジェクトにスキーマが追加されます。</span><span class="sxs-lookup"><span data-stu-id="11292-115">The schemas are added to the SSOSchedule project.</span></span>  
  
7.  <span data-ttu-id="11292-116">ソリューション エクスプ ローラーで、 **SSOSchedule プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="11292-116">In Solution Explorer, expand **SSOSchedule project**.</span></span>  
  
8.  <span data-ttu-id="11292-117">右クリック**BizTalk orchestration.odx**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="11292-117">Right-click **BizTalk orchestration.odx**, and then click **Delete**.</span></span>  
  
9. <span data-ttu-id="11292-118">ソリューション エクスプ ローラーで、 **GetList.odx**をオーケストレーションを検査します。</span><span class="sxs-lookup"><span data-stu-id="11292-118">In Solution Explorer, double-click **GetList.odx** to inspect the orchestration.</span></span>  
  
## <a name="orchestration-types---port-types"></a><span data-ttu-id="11292-119">オーケストレーションの種類 - ポートの種類</span><span class="sxs-lookup"><span data-stu-id="11292-119">Orchestration Types - Port Types</span></span>  
  
-   <span data-ttu-id="11292-120">**PortTypeIn/で/要求:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="11292-120">**PortTypeIn/In/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="11292-121">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="11292-121">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="11292-122">**PortTypeOut/アウト/応答:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="11292-122">**PortTypeOut/Out/response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="11292-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="11292-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
-   <span data-ttu-id="11292-124">**PortTypeInOut/InOut/要求:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="11292-124">**PortTypeInOut/InOut/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="11292-125">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="11292-125">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="11292-126">**PortTypeInOut/InOut/応答:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="11292-126">**PortTypeInOut/InOut/Response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="11292-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="11292-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="orchestration-variables---messages"></a><span data-ttu-id="11292-128">オーケストレーション変数 - メッセージ</span><span class="sxs-lookup"><span data-stu-id="11292-128">Orchestration Variables - Messages</span></span>  
  
-   <span data-ttu-id="11292-129">**MessageIn:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="11292-129">**MessageIn:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="11292-130">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="11292-130">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="11292-131">**MessageOut:** SSOSchedule.myJ.D です。</span><span class="sxs-lookup"><span data-stu-id="11292-131">**MessageOut:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="11292-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="11292-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11292-133">参照</span><span class="sxs-lookup"><span data-stu-id="11292-133">See Also</span></span>  
 [<span data-ttu-id="11292-134">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="11292-134">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)
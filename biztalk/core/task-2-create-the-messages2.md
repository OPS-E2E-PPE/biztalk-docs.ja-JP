---
title: タスク 2:作成、Messages2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2db67595-bcb6-455b-ad81-07b4426b7ea4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfbed288824fffc6e1fa1651dcbfef717de74cf9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399253"
---
# <a name="task-2-create-the-messages"></a><span data-ttu-id="1fc63-102">タスク 2:メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fc63-102">Task 2: Create the Messages</span></span>
<span data-ttu-id="1fc63-103">オーケストレーションで使用される、次のメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fc63-103">Create the following Messages, which will be used in the orchestration.</span></span>  
  
### <a name="to-create-the-messages"></a><span data-ttu-id="1fc63-104">メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="1fc63-104">To create the messages</span></span>  
  
1.  <span data-ttu-id="1fc63-105">右クリックして**メッセージ**、し、**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="1fc63-105">Right-click **Message**, and then select **New Message**.</span></span>  
  
2.  <span data-ttu-id="1fc63-106">識別子とメッセージの種類は、次を入力 > スキーマとメッセージごとに表示された一覧からタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fc63-106">Fill in the following for the Identifier and the Message Type>Schema and select the type from the displayed list for each message.</span></span>  
  
    |<span data-ttu-id="1fc63-107">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="1fc63-107">Identifier</span></span>|<span data-ttu-id="1fc63-108">メッセージの種類 > スキーマ</span><span class="sxs-lookup"><span data-stu-id="1fc63-108">Message Type > Schema</span></span>|  
    |----------------|----------------------------|  
    |<span data-ttu-id="1fc63-109">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-109">BeginDocMsg</span></span>|<span data-ttu-id="1fc63-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="1fc63-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="1fc63-111">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-111">BeginDocResponseMsg</span></span>|<span data-ttu-id="1fc63-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="1fc63-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span></span>|  
    |<span data-ttu-id="1fc63-113">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-113">BeginDocSessionMsg</span></span>|<span data-ttu-id="1fc63-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="1fc63-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="1fc63-115">EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-115">EditLineMsg</span></span>|<span data-ttu-id="1fc63-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="1fc63-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="1fc63-117">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-117">EditLineResponseMsg</span></span>|<span data-ttu-id="1fc63-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span><span class="sxs-lookup"><span data-stu-id="1fc63-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span></span>|  
    |<span data-ttu-id="1fc63-119">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-119">EditLineSessionMsg</span></span>|<span data-ttu-id="1fc63-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="1fc63-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="1fc63-121">EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-121">EndDocMsg</span></span>|<span data-ttu-id="1fc63-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="1fc63-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
    |<span data-ttu-id="1fc63-123">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-123">EndDocResponseMsg</span></span>|<span data-ttu-id="1fc63-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="1fc63-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span></span>|  
    |<span data-ttu-id="1fc63-125">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1fc63-125">EndDocSessionMsg</span></span>|<span data-ttu-id="1fc63-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="1fc63-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fc63-127">参照</span><span class="sxs-lookup"><span data-stu-id="1fc63-127">See Also</span></span>  
 <span data-ttu-id="1fc63-128">[タスク 1:ポートを作成します。](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="1fc63-128">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="1fc63-129">[タスク 3:受信図形と送信の構成](../core/task-3-configure-the-send-and-receive-shapes2.md) </span><span class="sxs-lookup"><span data-stu-id="1fc63-129">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes2.md) </span></span>  
 <span data-ttu-id="1fc63-130">[タスク 4:メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="1fc63-130">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 [<span data-ttu-id="1fc63-131">タスク 5:変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="1fc63-131">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)
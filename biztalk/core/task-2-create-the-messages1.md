---
title: 'タスク 2: 作成、Messages1 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df908ea0-b3be-47e6-99ba-4122cb1db561
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e326662737919e325f95d82b86aa8824e4e3a06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278850"
---
# <a name="task-2-create-the-messages"></a><span data-ttu-id="97d80-102">タスク 2: メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="97d80-102">Task 2: Create the Messages</span></span>
<span data-ttu-id="97d80-103">次のメッセージを作成します。これらのメッセージはオーケストレーションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="97d80-103">Create the following Messages, they will be used in the orchestration.</span></span>  
  
### <a name="to-create-the-messages"></a><span data-ttu-id="97d80-104">メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="97d80-104">To create the messages</span></span>  
  
1.  <span data-ttu-id="97d80-105">右クリック**メッセージ**、し、**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="97d80-105">Right-click **Message**, and then select **New Message**.</span></span>  
  
2.  <span data-ttu-id="97d80-106">[識別子] および [メッセージの種類] >&lt;a&gt;</ph>[スキーマ] に以下を入力し、各メッセージに対し表示される一覧から種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="97d80-106">Fill in the following for the Identifier and the Message Type>Schema and select the type from the displayed list for each message.</span></span>  
  
    |<span data-ttu-id="97d80-107">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="97d80-107">Identifier</span></span>|<span data-ttu-id="97d80-108">メッセージの種類 > スキーマ</span><span class="sxs-lookup"><span data-stu-id="97d80-108">Message Type>Schema</span></span>|  
    |----------------|--------------------------|  
    |<span data-ttu-id="97d80-109">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-109">BeginDocMsg</span></span>|<span data-ttu-id="97d80-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="97d80-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="97d80-111">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-111">BeginDocResponseMsg</span></span>|<span data-ttu-id="97d80-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="97d80-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span></span>|  
    |<span data-ttu-id="97d80-113">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-113">BeginDocSessionMsg</span></span>|<span data-ttu-id="97d80-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="97d80-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="97d80-115">EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-115">EditLineMsg</span></span>|<span data-ttu-id="97d80-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="97d80-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="97d80-117">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-117">EditLineResponseMsg</span></span>|<span data-ttu-id="97d80-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span><span class="sxs-lookup"><span data-stu-id="97d80-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span></span>|  
    |<span data-ttu-id="97d80-119">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-119">EditLineSessionMsg</span></span>|<span data-ttu-id="97d80-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="97d80-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="97d80-121">EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-121">EndDocMsg</span></span>|<span data-ttu-id="97d80-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="97d80-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
    |<span data-ttu-id="97d80-123">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-123">EndDocResponseMsg</span></span>|<span data-ttu-id="97d80-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="97d80-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span></span>|  
    |<span data-ttu-id="97d80-125">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="97d80-125">EndDocSessionMsg</span></span>|<span data-ttu-id="97d80-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="97d80-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97d80-127">参照</span><span class="sxs-lookup"><span data-stu-id="97d80-127">See Also</span></span>  
 <span data-ttu-id="97d80-128">[タスク 1: ポートを作成します。](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="97d80-128">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="97d80-129">[タスク 3: 送信、受信図形と構成](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="97d80-129">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 <span data-ttu-id="97d80-130">[タスク 4: メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="97d80-130">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape2.md) </span></span>  
 [<span data-ttu-id="97d80-131">タスク 5: 変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="97d80-131">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)
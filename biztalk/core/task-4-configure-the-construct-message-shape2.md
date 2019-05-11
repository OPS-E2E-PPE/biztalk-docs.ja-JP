---
title: タスク 4:コンス トラクターのメッセージ Shape2 の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43a7b912-0293-41be-b992-309eca550801
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47251eb4d9011c2c0221af75e7190abe2487a440
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399230"
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="add13-102">タスク 4:メッセージの構築図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="add13-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="add13-103">メッセージの構築では、開始、編集、およびドキュメントの終了コードの手順でメッセージの割り当てを保持します。</span><span class="sxs-lookup"><span data-stu-id="add13-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="add13-104">メッセージの構築図形を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="add13-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="add13-105">メッセージの構築図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="add13-105">To configure the Construct Message shape</span></span>  
  
1. <span data-ttu-id="add13-106">メッセージの構築図形 receivebegindoc] と [をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="add13-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
   -   <span data-ttu-id="add13-107">**構築メッセージ:** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="add13-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
   -   <span data-ttu-id="add13-108">**名:** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="add13-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
   1.  <span data-ttu-id="add13-109">新しいメッセージを作成するオーケストレーションにメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="add13-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="add13-110">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="add13-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="add13-111">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="add13-111">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="add13-112">たとえば、コードに入力します。</span><span class="sxs-lookup"><span data-stu-id="add13-112">Type in your code, for example:</span></span>  
  
   ```  
   BeginDocSessionMsg = BeginDocMsg;  
   BeginDocSessionMsg(JDE.ReserveSession) = true;  
   BeginDocSessionMsg(JDE.SessionID) = 0;  
   ```  
  
    <span data-ttu-id="add13-113">これにより、セッションを開始するアダプター。</span><span class="sxs-lookup"><span data-stu-id="add13-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="add13-114">SessionID は 0 として初期化されますが、ID を j. d. によって割り当てられますが、応答が返される</span><span class="sxs-lookup"><span data-stu-id="add13-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="add13-115">Edwards OneWorld サーバー。</span><span class="sxs-lookup"><span data-stu-id="add13-115">Edwards OneWorld Server.</span></span>  
  
    <span data-ttu-id="add13-116">![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")</span><span class="sxs-lookup"><span data-stu-id="add13-116">![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")</span></span>  
  
2. <span data-ttu-id="add13-117">SendEditLine する前にメッセージの構築をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="add13-117">Drag a Construct Message before SendEditLine.</span></span>  
  
   - <span data-ttu-id="add13-118">**構築メッセージ:** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="add13-118">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
   - <span data-ttu-id="add13-119">**名:** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="add13-119">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     <span data-ttu-id="add13-120">![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")</span><span class="sxs-lookup"><span data-stu-id="add13-120">![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")</span></span>  
  
   1.  <span data-ttu-id="add13-121">新しいメッセージを作成するオーケストレーションにメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="add13-121">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="add13-122">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="add13-122">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="add13-123">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="add13-123">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="add13-124">たとえば、コードに入力します。</span><span class="sxs-lookup"><span data-stu-id="add13-124">Type in your code, for example:</span></span>  
  
   ```  
   EditLineSessionMsg = EditLineMsg;  
   EditLineSessionMsg(JDE.ReserveSession) = true;  
   EditLineSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
    <span data-ttu-id="add13-125">![](../core/media/jde-editline-editor.gif "JDE_editline_editor")</span><span class="sxs-lookup"><span data-stu-id="add13-125">![](../core/media/jde-editline-editor.gif "JDE_editline_editor")</span></span>  
  
3. <span data-ttu-id="add13-126">SendEndDoc する前にメッセージの構築をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="add13-126">Drag a Construct Message before SendEndDoc.</span></span>  
  
   -   <span data-ttu-id="add13-127">**構築メッセージ:** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="add13-127">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
   -   <span data-ttu-id="add13-128">**名:** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="add13-128">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
   1.  <span data-ttu-id="add13-129">新しいメッセージを作成するオーケストレーションにメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="add13-129">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="add13-130">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="add13-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="add13-131">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="add13-131">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="add13-132">たとえば、コードに入力します。</span><span class="sxs-lookup"><span data-stu-id="add13-132">Type in your code, for example:</span></span>  
  
   ```  
   EndDocSessionMsg = EndDocMsg;  
   EndDocSessionMsg(JDE.ReserveSession) = false;  
   EndDocSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="add13-133">参照</span><span class="sxs-lookup"><span data-stu-id="add13-133">See Also</span></span>  
 <span data-ttu-id="add13-134">[タスク 1:ポートを作成します。](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="add13-134">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="add13-135">[タスク 2:メッセージを作成します。](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="add13-135">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="add13-136">[タスク 3:受信図形と送信の構成](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="add13-136">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="add13-137">タスク 5:変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="add13-137">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)
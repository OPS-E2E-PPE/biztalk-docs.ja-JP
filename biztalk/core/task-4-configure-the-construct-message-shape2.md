---
title: 'タスク 4: 構成のコンストラクトのメッセージ Shape2 |Microsoft Docs'
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
ms.openlocfilehash: 67c9e667248150a705841d0947bfb0cb3799a516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012699"
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="8151f-102">タスク 4: メッセージの構築図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="8151f-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="8151f-103">メッセージの構築には、メッセージの割り当てと共に、ドキュメントの開始、編集、および終了の各コードに関する指示が格納されます。</span><span class="sxs-lookup"><span data-stu-id="8151f-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="8151f-104">メッセージの構築図形を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8151f-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="8151f-105">メッセージの構築図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="8151f-105">To configure the Construct Message shape</span></span>  
  
1. <span data-ttu-id="8151f-106">メッセージの構築図形を [ReceiveBeginDoc] と [SendBeginDoc] の間にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8151f-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
   -   <span data-ttu-id="8151f-107">**構築メッセージ:** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="8151f-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
   -   <span data-ttu-id="8151f-108">**名前:** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="8151f-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
   1.  <span data-ttu-id="8151f-109">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8151f-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="8151f-110">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8151f-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="8151f-111">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8151f-111">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="8151f-112">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8151f-112">Type in your code, for example:</span></span>  
  
   ```  
   BeginDocSessionMsg = BeginDocMsg;  
   BeginDocSessionMsg(JDE.ReserveSession) = true;  
   BeginDocSessionMsg(JDE.SessionID) = 0;  
   ```  
  
    <span data-ttu-id="8151f-113">これにより、セッションを開始するようにアダプタに指示できます。</span><span class="sxs-lookup"><span data-stu-id="8151f-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="8151f-114">SessionID は 0 として初期化されますが、ID を j. d. によって割り当てられますが、応答が返される</span><span class="sxs-lookup"><span data-stu-id="8151f-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="8151f-115">Edwards OneWorld サーバー。</span><span class="sxs-lookup"><span data-stu-id="8151f-115">Edwards OneWorld Server.</span></span>  
  
    <span data-ttu-id="8151f-116">![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")</span><span class="sxs-lookup"><span data-stu-id="8151f-116">![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")</span></span>  
  
2. <span data-ttu-id="8151f-117">メッセージの構築図形を [SendEditLine] の前にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8151f-117">Drag a Construct Message before SendEditLine.</span></span>  
  
   - <span data-ttu-id="8151f-118">**構築メッセージ:** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="8151f-118">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
   - <span data-ttu-id="8151f-119">**名前:** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="8151f-119">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     <span data-ttu-id="8151f-120">![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")</span><span class="sxs-lookup"><span data-stu-id="8151f-120">![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")</span></span>  
  
   1.  <span data-ttu-id="8151f-121">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8151f-121">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="8151f-122">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8151f-122">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="8151f-123">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8151f-123">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="8151f-124">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8151f-124">Type in your code, for example:</span></span>  
  
   ```  
   EditLineSessionMsg = EditLineMsg;  
   EditLineSessionMsg(JDE.ReserveSession) = true;  
   EditLineSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
    <span data-ttu-id="8151f-125">![](../core/media/jde-editline-editor.gif "JDE_editline_editor")</span><span class="sxs-lookup"><span data-stu-id="8151f-125">![](../core/media/jde-editline-editor.gif "JDE_editline_editor")</span></span>  
  
3. <span data-ttu-id="8151f-126">メッセージの構築図形を [SendEndDoc] の前にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8151f-126">Drag a Construct Message before SendEndDoc.</span></span>  
  
   -   <span data-ttu-id="8151f-127">**構築メッセージ:** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="8151f-127">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
   -   <span data-ttu-id="8151f-128">**名前:** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="8151f-128">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
   1.  <span data-ttu-id="8151f-129">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8151f-129">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="8151f-130">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8151f-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="8151f-131">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8151f-131">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="8151f-132">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8151f-132">Type in your code, for example:</span></span>  
  
   ```  
   EndDocSessionMsg = EndDocMsg;  
   EndDocSessionMsg(JDE.ReserveSession) = false;  
   EndDocSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="8151f-133">参照</span><span class="sxs-lookup"><span data-stu-id="8151f-133">See Also</span></span>  
 <span data-ttu-id="8151f-134">[タスク 1: ポートを作成します。](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="8151f-134">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="8151f-135">[タスク 2: メッセージを作成します。](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="8151f-135">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="8151f-136">[タスク 3: 構成、送信と受信図形](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="8151f-136">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="8151f-137">タスク 5: 変換図形の構成</span><span class="sxs-lookup"><span data-stu-id="8151f-137">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)
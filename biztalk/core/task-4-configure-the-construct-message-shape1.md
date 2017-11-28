---
title: "タスク 4: 構成コンストラクト メッセージ Shape1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3e66a9d-c549-42d0-849b-9e1744056429
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f781e03f83223f7d82628ee9c01728a0754b149f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="643e1-102">タスク 4: メッセージの構築図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="643e1-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="643e1-103">メッセージの構築には、メッセージの割り当てと共に、ドキュメントの開始、編集、および終了の各コードに関する指示が格納されます。</span><span class="sxs-lookup"><span data-stu-id="643e1-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="643e1-104">メッセージの構築図形を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="643e1-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="643e1-105">メッセージの構築図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="643e1-105">To configure the Construct Message shape</span></span>  
  
1.  <span data-ttu-id="643e1-106">メッセージの構築図形を [ReceiveBeginDoc] と [SendBeginDoc] の間にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="643e1-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
    -   <span data-ttu-id="643e1-107">**構築メッセージ:** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="643e1-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="643e1-108">**[名前]:** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="643e1-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="643e1-109">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="643e1-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="643e1-110">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="643e1-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="643e1-111">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="643e1-111">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="643e1-112">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="643e1-112">Type in your code, for example:</span></span>  
  
        ```  
        BeginDocSessionMsg = BeginDocMsg;  
        BeginDocSessionMsg(JDE.ReserveSession) = true;  
        BeginDocSessionMsg(JDE.SessionID) = 0;  
        ```  
  
         <span data-ttu-id="643e1-113">これにより、セッションを開始するようにアダプタに指示できます。</span><span class="sxs-lookup"><span data-stu-id="643e1-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="643e1-114">SessionID は 0 として初期化されますが、応答が返さ ID はで割り当てられます、j. d.</span><span class="sxs-lookup"><span data-stu-id="643e1-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="643e1-115">Edwards EnterpriseOne サーバー。</span><span class="sxs-lookup"><span data-stu-id="643e1-115">Edwards EnterpriseOne Server.</span></span>  
  
     <span data-ttu-id="643e1-116">![メッセージ式エディター](../core/media/message-expression-editor.gif "message_expression_editor")</span><span class="sxs-lookup"><span data-stu-id="643e1-116">![Message Expression Editor](../core/media/message-expression-editor.gif "message_expression_editor")</span></span>  
  
2.  <span data-ttu-id="643e1-117">メッセージの構築図形を [SendEditLine] の前にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="643e1-117">Drag a Construct Message before SendEditLine.</span></span>  
  
    -   <span data-ttu-id="643e1-118">**構築メッセージ:** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="643e1-118">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
    -   <span data-ttu-id="643e1-119">**[名前]:** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="643e1-119">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     <span data-ttu-id="643e1-120">![編集行を送信](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")</span><span class="sxs-lookup"><span data-stu-id="643e1-120">![Send Edit Line](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")</span></span>  
  
    1.  <span data-ttu-id="643e1-121">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="643e1-121">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="643e1-122">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="643e1-122">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="643e1-123">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="643e1-123">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="643e1-124">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="643e1-124">Type in your code, for example:</span></span>  
  
        ```  
        EditLineSessionMsg = EditLineMsg;  
        EditLineSessionMsg(JDE.ReserveSession) = true;  
        EditLineSessionMsg(JDE.SessionID) =  
        BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
     <span data-ttu-id="643e1-125">![編集行エディター](../core/media/editline-editor.gif "editline_editor")</span><span class="sxs-lookup"><span data-stu-id="643e1-125">![Edit Line Editor](../core/media/editline-editor.gif "editline_editor")</span></span>  
  
3.  <span data-ttu-id="643e1-126">SendEndDoc の前にメッセージの構築図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="643e1-126">Drag a Construct Message shape before SendEndDoc.</span></span>  
  
    -   <span data-ttu-id="643e1-127">**構築メッセージ:** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="643e1-127">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="643e1-128">**[名前]:** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="643e1-128">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="643e1-129">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="643e1-129">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="643e1-130">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="643e1-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="643e1-131">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="643e1-131">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="643e1-132">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="643e1-132">Type in your code, for example:</span></span>  
  
        ```  
        EndDocSessionMsg = EndDocMsg;  
        EndDocSessionMsg(JDE.ReserveSession) = false;  
        EndDocSessionMsg(JDE.SessionID) =  
           BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="643e1-133">参照</span><span class="sxs-lookup"><span data-stu-id="643e1-133">See Also</span></span>  
 <span data-ttu-id="643e1-134">[タスク 1: ポートを作成します。](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="643e1-134">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="643e1-135">[タスク 2: メッセージを作成します。](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="643e1-135">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="643e1-136">[タスク 3: 送信、受信図形と構成](../core/task-3-configure-the-send-and-receive-shapes2.md) </span><span class="sxs-lookup"><span data-stu-id="643e1-136">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes2.md) </span></span>  
 [<span data-ttu-id="643e1-137">タスク 5: 変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="643e1-137">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)
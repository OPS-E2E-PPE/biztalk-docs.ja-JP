---
title: 'タスク 4: 構成コンストラクト メッセージ Shape2 |Microsoft ドキュメント'
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
ms.openlocfilehash: 6616fec48eb0915527a95f94992e4bda838e9d37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279042"
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="1a6c9-102">タスク 4: メッセージの構築図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="1a6c9-103">メッセージの構築には、メッセージの割り当てと共に、ドキュメントの開始、編集、および終了の各コードに関する指示が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="1a6c9-104">メッセージの構築図形を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="1a6c9-105">メッセージの構築図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="1a6c9-105">To configure the Construct Message shape</span></span>  
  
1.  <span data-ttu-id="1a6c9-106">メッセージの構築図形を [ReceiveBeginDoc] と [SendBeginDoc] の間にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
    -   <span data-ttu-id="1a6c9-107">**構築メッセージ:** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1a6c9-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="1a6c9-108">**[名前]:** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="1a6c9-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="1a6c9-109">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="1a6c9-110">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="1a6c9-111">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-111">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="1a6c9-112">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-112">Type in your code, for example:</span></span>  
  
    ```  
    BeginDocSessionMsg = BeginDocMsg;  
    BeginDocSessionMsg(JDE.ReserveSession) = true;  
    BeginDocSessionMsg(JDE.SessionID) = 0;  
    ```  
  
     <span data-ttu-id="1a6c9-113">これにより、セッションを開始するようにアダプタに指示できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="1a6c9-114">SessionID は 0 として初期化されますが、応答が返さ ID はで割り当てられます、j. d.</span><span class="sxs-lookup"><span data-stu-id="1a6c9-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="1a6c9-115">Edwards OneWorld サーバー。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-115">Edwards OneWorld Server.</span></span>  
  
     ![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")  
  
2.  <span data-ttu-id="1a6c9-116">メッセージの構築図形を [SendEditLine] の前にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-116">Drag a Construct Message before SendEditLine.</span></span>  
  
    -   <span data-ttu-id="1a6c9-117">**構築メッセージ:** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1a6c9-117">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
    -   <span data-ttu-id="1a6c9-118">**[名前]:** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="1a6c9-118">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     ![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")  
  
    1.  <span data-ttu-id="1a6c9-119">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-119">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="1a6c9-120">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-120">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="1a6c9-121">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-121">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="1a6c9-122">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-122">Type in your code, for example:</span></span>  
  
    ```  
    EditLineSessionMsg = EditLineMsg;  
    EditLineSessionMsg(JDE.ReserveSession) = true;  
    EditLineSessionMsg(JDE.SessionID) =  
       BeginDocResponseMsg(JDE.SessionID);  
    ```  
  
     ![](../core/media/jde-editline-editor.gif "JDE_editline_editor")  
  
3.  <span data-ttu-id="1a6c9-123">メッセージの構築図形を [SendEndDoc] の前にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-123">Drag a Construct Message before SendEndDoc.</span></span>  
  
    -   <span data-ttu-id="1a6c9-124">**構築メッセージ:** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1a6c9-124">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="1a6c9-125">**[名前]:** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="1a6c9-125">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="1a6c9-126">新規メッセージを作成するオーケストレーション内にメッセージの割り当て図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-126">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="1a6c9-127">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-127">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="1a6c9-128">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-128">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="1a6c9-129">コードを入力します。コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-129">Type in your code, for example:</span></span>  
  
    ```  
    EndDocSessionMsg = EndDocMsg;  
    EndDocSessionMsg(JDE.ReserveSession) = false;  
    EndDocSessionMsg(JDE.SessionID) =  
       BeginDocResponseMsg(JDE.SessionID);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1a6c9-130">参照</span><span class="sxs-lookup"><span data-stu-id="1a6c9-130">See Also</span></span>  
 <span data-ttu-id="1a6c9-131">[タスク 1: ポートを作成します。](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="1a6c9-131">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="1a6c9-132">[タスク 2: メッセージを作成します。](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="1a6c9-132">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="1a6c9-133">[タスク 3: 送信、受信図形と構成](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="1a6c9-133">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="1a6c9-134">タスク 5: 変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="1a6c9-134">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)
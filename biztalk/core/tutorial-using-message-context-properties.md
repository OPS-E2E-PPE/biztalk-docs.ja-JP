---
title: チュートリアル:TIBCO EMS メッセージ コンテキスト プロパティの使用 |Microsoft Docs
description: BizTalk Server のオーケストレーションで TIBCO Enterprise Message Service メッセージ記述子フィールドを使用するステップ バイ ステップ ガイド
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef7ce23a38c528b3dc7e3d0a3d98c39412e9c175
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393849"
---
# <a name="tutorial-use-tibco-ems-message-descriptors"></a><span data-ttu-id="60631-103">チュートリアル:TIBCO EMS メッセージ記述子を使用します。</span><span class="sxs-lookup"><span data-stu-id="60631-103">Tutorial: Use TIBCO EMS message descriptors</span></span>

## <a name="overview"></a><span data-ttu-id="60631-104">概要</span><span class="sxs-lookup"><span data-stu-id="60631-104">Overview</span></span>
<span data-ttu-id="60631-105">このチュートリアルでは、BizTalk Server コンテキスト プロパティを使用して、オーケストレーションで TIBCO Enterprise Message Service (EMS) のメッセージ記述子フィールドを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="60631-105">This tutorial demonstrates how to use BizTalk Server context properties to set TIBCO Enterprise Message Service (EMS) message descriptor fields in your orchestration.</span></span> <span data-ttu-id="60631-106">このチュートリアルでは、受信ポートからメッセージを受信し、TIBCO Enterprise Message Service for Microsoft BizTalk アダプターにバインドされた送信ポートにメッセージを送信するオーケストレーションがあることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="60631-106">The tutorial assumes that you have an orchestration that receives a message from a receive port and sends the message to a send port bound to Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
 <span data-ttu-id="60631-107">次の手順では、TibcoEMS.Priority コンテキスト プロパティの値を変更することで、TIBCO EMS メッセージの優先度を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="60631-107">The following procedure demonstrates how to change the priority of the TIBCO EMS message by changing the value of the TibcoEMS.Priority context property.</span></span> <span data-ttu-id="60631-108">BizTalk Server で、メッセージは変更できません。</span><span class="sxs-lookup"><span data-stu-id="60631-108">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="60631-109">そのため、プロパティ値を変更するには、作成および、新しいメッセージを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60631-109">Therefore, to change a property value, you must create and modify a new message.</span></span> <span data-ttu-id="60631-110">作成し、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="60631-110">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span> <span data-ttu-id="60631-111">最初に、ただし、する必要があります、スキーマ DLL を参照、TIBCO EMS プロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="60631-111">First, however, you must reference the schema DLL to gain access to the TIBCO EMS properties.</span></span>  
  
## <a name="reference-the-schema-dll"></a><span data-ttu-id="60631-112">スキーマ DLL を参照します。</span><span class="sxs-lookup"><span data-stu-id="60631-112">Reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="60631-113">Visual Studio で、BizTalk Server プロジェクトを開くし、開く**ソリューション エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="60631-113">In Visual Studio, open your BizTalk Server project, and open **Solution Explorer** .</span></span>  
  
2.  <span data-ttu-id="60631-114">右クリック**参照**、選び**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="60631-114">Right-click **References**, and select **Add Reference**.</span></span>  
  
     <span data-ttu-id="60631-115">**[参照の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60631-115">The **Add Reference** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="60631-116">をクリックして、**参照**タブ。</span><span class="sxs-lookup"><span data-stu-id="60631-116">Click the **Browse** tab.</span></span>  
  
     <span data-ttu-id="60631-117">**コンポーネントの選択** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60631-117">The **Select Component** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="60631-118">検索 **\<TIBCO EMS_Adapter_installation_directory\>\bin**、し、 **Microsoft.Adapters.TibcoEMSProperties.dll**します。</span><span class="sxs-lookup"><span data-stu-id="60631-118">Locate **\<TIBCO EMS_Adapter_installation_directory\>\bin**, and then select **Microsoft.Adapters.TibcoEMSProperties.dll**.</span></span>  
  
5.  <span data-ttu-id="60631-119">**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60631-119">Click **Open**.</span></span>  
  
     <span data-ttu-id="60631-120">DLL が表示されます、**選択されたコンポーネント**で、**参照の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="60631-120">The DLL appears in the **Selected Components** in the **Add Reference** dialog box.</span></span>  
  
6.  <span data-ttu-id="60631-121">クリックして**OK**し、オーケストレーション デザイナにアクセスするオーケストレーションをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="60631-121">Click **OK** and then double-click your orchestration to access the Orchestration Designer.</span></span>  
  
7.  <span data-ttu-id="60631-122">**ビュー**メニューで、**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="60631-122">On the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
8.  <span data-ttu-id="60631-123">オーケストレーション ビューで右クリックして**メッセージ**選択と**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="60631-123">In the Orchestration view, right-click **Messages** and select **New Message**.</span></span>  
  
9. <span data-ttu-id="60631-124">新しいメッセージのプロパティを編集し、割り当てる、**メッセージの種類**します。</span><span class="sxs-lookup"><span data-stu-id="60631-124">Edit your new message properties and assign a **Message Type**.</span></span>  
  
     <span data-ttu-id="60631-125">Message_1 を Message_2 に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="60631-125">You will assign Message_1 to Message_2.</span></span> <span data-ttu-id="60631-126">そのため、メッセージの両方に同じメッセージの種類を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="60631-126">Therefore, you must assign the same message type to both messages.</span></span>  
  
10. <span data-ttu-id="60631-127">**[表示]** メニューの **[ツールボックス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60631-127">On the **View** menu, click **Toolbox**.</span></span>  
  
11. <span data-ttu-id="60631-128">ドラッグ、**メッセージの割り当て**図形に新しいメッセージを作成するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="60631-128">Drag a **Message Assignment** shape onto your orchestration where you want to create a new message.</span></span>  
  
12. <span data-ttu-id="60631-129">外側の ConstructMessage_1 図形を編集しで、新しいメッセージ Message_2 を選択、**構築メッセージ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="60631-129">Edit the outer ConstructMessage_1 shape and select your new message, Message_2, in the **Constructed Messages** property.</span></span>  
  
13. <span data-ttu-id="60631-130">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="60631-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
     <span data-ttu-id="60631-131">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60631-131">The BizTalk Expression Editor appears.</span></span>  
  
14. <span data-ttu-id="60631-132">BizTalk 式エディターでは、コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="60631-132">In the BizTalk Expression Editor, type your code.</span></span>  
  
15. <span data-ttu-id="60631-133">まず、既存のメッセージをコピーし、メッセージ コンテキスト プロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="60631-133">First copy an existing message and then assign values to message context properties.</span></span>  
  
     <span data-ttu-id="60631-134">構文は`Message(property) = value;`します。</span><span class="sxs-lookup"><span data-stu-id="60631-134">The syntax is `Message(property) = value;`.</span></span> <span data-ttu-id="60631-135">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="60631-135">For example:</span></span>  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     <span data-ttu-id="60631-136">カスタム メッセージで使用できるサポートされているプロパティの一覧については、TIBCO EMS を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60631-136">See TIBCO EMS for a list of supported properties that you can use in your custom message.</span></span>  
  
16. <span data-ttu-id="60631-137">クリックして**OK** BizTalk 式エディターを終了し、コードを保存します。</span><span class="sxs-lookup"><span data-stu-id="60631-137">Click **OK** to close the BizTalk Expression Editor and save your code.</span></span>  
  
17. <span data-ttu-id="60631-138">送信図形をクリックし、割り当てる、**メッセージ**する**Message_2**します。</span><span class="sxs-lookup"><span data-stu-id="60631-138">Click the Send shape and assign the **Message** to be **Message_2**.</span></span>  
  
18. <span data-ttu-id="60631-139">メッセージ フローの残りの部分で図形を適切なメッセージで動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="60631-139">Verify that the shapes in the rest of the message flow operate on the appropriate message.</span></span>  
  
19. <span data-ttu-id="60631-140">ソリューション エクスプ ローラーでプロジェクトを右クリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="60631-140">Right-click your project in Solution Explorer, and select **Build**.</span></span>  
  
20. <span data-ttu-id="60631-141">プロジェクトを右クリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="60631-141">Right-click your project and select **Deploy**.</span></span>  
  
21. <span data-ttu-id="60631-142">選択**バインド**、**参加**、および**開始**オーケストレーションをテストする BizTalk エクスプ ローラーでします。</span><span class="sxs-lookup"><span data-stu-id="60631-142">Select **Bind**, **Enlist**, and **Start** in the BizTalk Explorer to test your orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60631-143">参照</span><span class="sxs-lookup"><span data-stu-id="60631-143">See Also</span></span>  
[<span data-ttu-id="60631-144">TIBCO EMS メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="60631-144">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)
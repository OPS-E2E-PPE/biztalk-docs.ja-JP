---
title: "チュートリアル: メッセージ コンテキスト プロパティの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, changing priority
- message context properties, tutorial
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f122215baa5660294e159e4f1d6967a2df5ba9b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-message-context-properties"></a><span data-ttu-id="02061-102">チュートリアル: メッセージ コンテキスト プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="02061-102">Tutorial: Using Message Context Properties</span></span>
<span data-ttu-id="02061-103">このチュートリアルでは、BizTalk Server コンテキスト プロパティを使用して、オーケストレーションで TIBCO Enterprise Message Service (EMS) のメッセージ記述子フィールドを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02061-103">This tutorial demonstrates how to use BizTalk Server context properties to set TIBCO Enterprise Message Service (EMS) message descriptor fields in your orchestration.</span></span> <span data-ttu-id="02061-104">このチュートリアルでは、受信ポートからメッセージを受信し、Microsoft BizTalk Adapter for TIBCO Enterprise Message Service にバインドされた送信ポートにそのメッセージを送信するオーケストレーションがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="02061-104">The tutorial assumes that you have an orchestration that receives a message from a receive port and sends the message to a send port bound to Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
 <span data-ttu-id="02061-105">次の手順では、TibcoEMS.Priority コンテキスト プロパティの値を変更することで、TIBCO EMS メッセージの優先度を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02061-105">The following procedure demonstrates how to change the priority of the TIBCO EMS message by changing the value of the TibcoEMS.Priority context property.</span></span> <span data-ttu-id="02061-106">BizTalk Server では、メッセージを変更できません。</span><span class="sxs-lookup"><span data-stu-id="02061-106">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="02061-107">そのため、プロパティ値を変更するには、作成および、新しいメッセージを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02061-107">Therefore, to change a property value, you must create and modify a new message.</span></span> <span data-ttu-id="02061-108">作成して、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="02061-108">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span> <span data-ttu-id="02061-109">ただし、TIBCO EMS プロパティにアクセスできるようにするために、最初にスキーマ DLL を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02061-109">First, however, you must reference the schema DLL to gain access to the TIBCO EMS properties.</span></span>  
  
### <a name="to-reference-the-schema-dll"></a><span data-ttu-id="02061-110">スキーマ DLL を参照するには</span><span class="sxs-lookup"><span data-stu-id="02061-110">To reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="02061-111">開いている**ソリューション エクスプ ローラー** Visual Studio でします。</span><span class="sxs-lookup"><span data-stu-id="02061-111">Open **Solution Explorer** in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="02061-112">右クリック**参照**を選択して**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="02061-112">Right-click **References**, and select **Add Reference**.</span></span>  
  
     <span data-ttu-id="02061-113">**[参照の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02061-113">The **Add Reference** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="02061-114">クリックして、**参照**タブです。</span><span class="sxs-lookup"><span data-stu-id="02061-114">Click the **Browse** tab.</span></span>  
  
     <span data-ttu-id="02061-115">**コンポーネントの選択** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02061-115">The **Select Component** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="02061-116">検索 **\<TIBCO EMS_Adapter_installation_directory > \bin**、し、 **Microsoft.Adapters.TibcoEMSProperties.dll**です。</span><span class="sxs-lookup"><span data-stu-id="02061-116">Locate **\<TIBCO EMS_Adapter_installation_directory>\bin**, and then select **Microsoft.Adapters.TibcoEMSProperties.dll**.</span></span>  
  
5.  <span data-ttu-id="02061-117">**[開く]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02061-117">Click **Open**.</span></span>  
  
     <span data-ttu-id="02061-118">DLL が表示されます、**選択されたコンポーネント**で、**参照の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="02061-118">The DLL appears in the **Selected Components** in the **Add Reference** dialog box.</span></span>  
  
6.  <span data-ttu-id="02061-119">をクリックして**OK**し、オーケストレーションをダブルクリックして、オーケストレーション デザイナにアクセスするとします。</span><span class="sxs-lookup"><span data-stu-id="02061-119">Click **OK** and then double-click your orchestration to access the Orchestration Designer.</span></span>  
  
7.  <span data-ttu-id="02061-120">**ビュー**  メニューのをポイント**その他のウィンドウ**、順にクリック**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="02061-120">On the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
8.  <span data-ttu-id="02061-121">オーケストレーション ビューで右クリック**メッセージ**選択**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="02061-121">In the Orchestration view, right-click **Messages** and select **New Message**.</span></span>  
  
9. <span data-ttu-id="02061-122">新しいメッセージ プロパティを編集し、割り当てます、**メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="02061-122">Edit your new message properties and assign a **Message Type**.</span></span>  
  
     <span data-ttu-id="02061-123">Message_1 を Message_2 に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="02061-123">You will assign Message_1 to Message_2.</span></span> <span data-ttu-id="02061-124">したがって、両方のメッセージに同じメッセージの種類を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02061-124">Therefore, you must assign the same message type to both messages.</span></span>  
  
10. <span data-ttu-id="02061-125">**[表示]** メニューの **[ツールボックス]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02061-125">On the **View** menu, click **Toolbox**.</span></span>  
  
11. <span data-ttu-id="02061-126">ドラッグ、**メッセージの割り当て**図形に新しいメッセージを作成するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="02061-126">Drag a **Message Assignment** shape onto your orchestration where you want to create a new message.</span></span>  
  
12. <span data-ttu-id="02061-127">外側の ConstructMessage_1 図形を編集しで、新しいメッセージ Message_2 を選択、**構築メッセージ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="02061-127">Edit the outer ConstructMessage_1 shape and select your new message, Message_2, in the **Constructed Messages** property.</span></span>  
  
13. <span data-ttu-id="02061-128">内側の MessageAssignment_1 図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="02061-128">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
     <span data-ttu-id="02061-129">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02061-129">The BizTalk Expression Editor appears.</span></span>  
  
14. <span data-ttu-id="02061-130">BizTalk 式エディターでは、コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="02061-130">In the BizTalk Expression Editor, type your code.</span></span>  
  
15. <span data-ttu-id="02061-131">まず既存のメッセージをコピーし、メッセージのコンテキスト プロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="02061-131">First copy an existing message and then assign values to message context properties.</span></span>  
  
     <span data-ttu-id="02061-132">構文は `Message(property) = value;` です。</span><span class="sxs-lookup"><span data-stu-id="02061-132">The syntax is `Message(property) = value;`.</span></span> <span data-ttu-id="02061-133">例:</span><span class="sxs-lookup"><span data-stu-id="02061-133">For example:</span></span>  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     <span data-ttu-id="02061-134">カスタム メッセージで使用できる、サポートされているプロパティの一覧については、TIBCO EMS を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02061-134">See TIBCO EMS for a list of supported properties that you can use in your custom message.</span></span>  
  
16. <span data-ttu-id="02061-135">をクリックして**OK**して BizTalk 式エディタを終了し、コードを保存します。</span><span class="sxs-lookup"><span data-stu-id="02061-135">Click **OK** to close the BizTalk Expression Editor and save your code.</span></span>  
  
17. <span data-ttu-id="02061-136">送信図形をクリックし、割り当てる、**メッセージ**する**Message_2**です。</span><span class="sxs-lookup"><span data-stu-id="02061-136">Click the Send shape and assign the **Message** to be **Message_2**.</span></span>  
  
18. <span data-ttu-id="02061-137">メッセージ フローの残りの図形が該当するメッセージで動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="02061-137">Verify that the shapes in the rest of the message flow operate on the appropriate message.</span></span>  
  
19. <span data-ttu-id="02061-138">ソリューション エクスプ ローラーでプロジェクトを右クリックし **ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="02061-138">Right-click your project in Solution Explorer, and select **Build**.</span></span>  
  
20. <span data-ttu-id="02061-139">プロジェクトを右クリックし **展開**です。</span><span class="sxs-lookup"><span data-stu-id="02061-139">Right-click your project and select **Deploy**.</span></span>  
  
21. <span data-ttu-id="02061-140">選択**バインド**、 **Enlist**、および**開始**BizTalk エクスプ ローラーで、オーケストレーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="02061-140">Select **Bind**, **Enlist**, and **Start** in the BizTalk Explorer to test your orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02061-141">参照</span><span class="sxs-lookup"><span data-stu-id="02061-141">See Also</span></span>  
 [<span data-ttu-id="02061-142">メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="02061-142">Message Context Properties</span></span>](../core/message-context-properties2.md)
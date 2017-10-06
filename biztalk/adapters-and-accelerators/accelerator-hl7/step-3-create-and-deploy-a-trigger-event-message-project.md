---
title: "手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトを配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, trigger events
- trigger events
ms.assetid: 5d21a923-fc2c-4d50-b146-daca0aa26e2a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf96bdc546223b68677b642944265c22d2ce4b14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a><span data-ttu-id="c2c52-102">手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="c2c52-102">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>
<span data-ttu-id="c2c52-103">この手順では、トリガーのイベント メッセージのスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2c52-103">In this step, you create the schema for your trigger event message.</span></span> <span data-ttu-id="c2c52-104">たとえば、受付放電して転送システム (ADT) 病院情報システム (HIS) にメッセージを送信する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c2c52-104">For example, you might be the Admissions Discharge and Transfer system (ADT) who sends a message to the Hospital Information System (HIS).</span></span> <span data-ttu-id="c2c52-105">このスキーマに、メッセージの書式を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2c52-105">You need this schema to define the format of your message.</span></span>  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a><span data-ttu-id="c2c52-106">トリガー イベント メッセージのプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="c2c52-106">To create the project for the trigger event message</span></span>  
  
1.  <span data-ttu-id="c2c52-107">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**をクリックし、**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, then click **Project**.</span></span>  
  
2.  <span data-ttu-id="c2c52-108">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、順にクリック**BTAHL7Projects**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-108">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="c2c52-109">テンプレート の  **BTAHL7 の空のプロジェクト**で、**名前**ボックスに、入力**BTAHL7V231Body プロジェクト**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-109">In the Templates section, click **Empty BTAHL7 Project**, in the **Name** box, type **BTAHL7V231Body Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="c2c52-110">ソリューション エクスプ ローラーで、新しいプロジェクトのノードの下を右クリックして**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-110">In Solution Explorer, under the node for your new project, right-click **References**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="c2c52-111">参照の追加 ダイアログ ボックスで、**プロジェクト** タブで、 **BTAHL7V231Common Project1**、 をクリックして**追加**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-111">In the Add Reference dialog box, on the **Projects** tab, select **BTAHL7V231Common Project1**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="step-3a-add-the-schema"></a><span data-ttu-id="c2c52-112">手順 3: スキーマの追加</span><span class="sxs-lookup"><span data-stu-id="c2c52-112">Step 3A: Add the Schema</span></span>  
 <span data-ttu-id="c2c52-113">次の手順を使用して、新しいスキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c2c52-113">Use the following procedure to add the new schema to the project.</span></span>  
  
#### <a name="to-add-the-schema-to-the-project"></a><span data-ttu-id="c2c52-114">スキーマをプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="c2c52-114">To add the schema to the project</span></span>  
  
1.  <span data-ttu-id="c2c52-115">ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body プロジェクト**、をポイント**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="c2c52-115">In Solution Explorer, right-click **BTAHL7V231Body Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="c2c52-116">追加で新しい項目 ダイアログ ボックス、、**カテゴリ**セクションで、展開**BizTalk プロジェクトの項目**、し、 **BTAHL7 スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-116">In the Add New Item dialog box, in the **Categories** section, expand **BizTalk Project Items**, and then select **BTAHL7 Schemas**.</span></span>  
  
3.  <span data-ttu-id="c2c52-117">[テンプレート] セクションをダブルクリックして**BTAHL7 スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-117">In the Templates section, double-click **BTAHL7 Schemas**.</span></span>  
  
4.  <span data-ttu-id="c2c52-118">HL7 スキーマの選択 ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c2c52-118">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="c2c52-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2c52-119">Use this</span></span>|<span data-ttu-id="c2c52-120">目的</span><span class="sxs-lookup"><span data-stu-id="c2c52-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c2c52-121">**Message クラス**</span><span class="sxs-lookup"><span data-stu-id="c2c52-121">**Message Class**</span></span>|<span data-ttu-id="c2c52-122">既定のままにして**V2.X**選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c52-122">Leave the default of **V2.X** selected.</span></span>|  
    |<span data-ttu-id="c2c52-123">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="c2c52-123">**Version**</span></span>|<span data-ttu-id="c2c52-124">選択**2.3.1**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-124">Select **2.3.1**.</span></span>|  
    |<span data-ttu-id="c2c52-125">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="c2c52-125">**Message Type**</span></span>|<span data-ttu-id="c2c52-126">選択**ADT**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-126">Select **ADT**.</span></span>|  
    |<span data-ttu-id="c2c52-127">**トリガー イベント**</span><span class="sxs-lookup"><span data-stu-id="c2c52-127">**Trigger Event**</span></span>|<span data-ttu-id="c2c52-128">選択**A03**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-128">Select **A03**.</span></span>|  
  
5.  <span data-ttu-id="c2c52-129">をクリックして**完了**スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c2c52-129">Click **Finish** to add the schema to the project.</span></span>  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="c2c52-130">手順 3 b: アセンブリに厳密なキーを割り当てると展開</span><span class="sxs-lookup"><span data-stu-id="c2c52-130">Step 3B: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="c2c52-131">アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2c52-131">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="c2c52-132">強力なキーを割り当てるし、アセンブリを展開するには</span><span class="sxs-lookup"><span data-stu-id="c2c52-132">To assign a strong key and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="c2c52-133">ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body プロジェクト**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-133">In Solution Explorer, right-click **BTAHL7V231Body Project**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c2c52-134">プロジェクト プロパティ ページ ページで、をクリックして**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-134">In the Project Property Pages page, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="c2c52-135">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2c52-135">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="c2c52-136">アセンブリ キー ファイル ダイアログ ボックスでを参照\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド チュートリアルをクリックして**key.snk**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-136">In the Assembly Key File dialog box, browse to \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="c2c52-137">プロジェクト プロパティ ページ] ダイアログ ボックスで、[ **OK**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c2c52-137">In the Project Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
6.  <span data-ttu-id="c2c52-138">ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body プロジェクト**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-138">In Solution Explorer right-click **BTAHL7V231Body Project**, and then click **Deploy**.</span></span> <span data-ttu-id="c2c52-139">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="c2c52-139">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2c52-140">展開の成功メッセージが表示されない場合を使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="c2c52-140">If a successful deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="c2c52-141">進みます[手順 4: 作成、ADT を受け入れるための受信ポート ^ MLLP アダプターを使用して ADT システムから A03 メッセージ](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)です。</span><span class="sxs-lookup"><span data-stu-id="c2c52-141">Proceed to [Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md).</span></span>
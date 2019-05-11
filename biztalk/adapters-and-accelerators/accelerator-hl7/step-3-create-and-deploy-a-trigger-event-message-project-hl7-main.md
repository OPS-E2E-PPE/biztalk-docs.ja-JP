---
title: 手順 3:作成してデプロイをトリガー イベント (メッセージ) _hl7_main |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, trigger events
ms.assetid: 90b65ad1-7953-4009-a1eb-1c2a85c7980a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74d78bde972541046e1ae27ddb5a260d2df16fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288351"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-projecthl7main"></a><span data-ttu-id="8372d-102">手順 3:作成および展開のトリガー イベント (メッセージ) の _hl7_main</span><span class="sxs-lookup"><span data-stu-id="8372d-102">Step 3: Create and Deploy a Trigger Event (Message) Project_hl7_main</span></span>
<span data-ttu-id="8372d-103">この手順では、トリガー イベントのメッセージで使用されるスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="8372d-103">In this step, you create the schema used by a trigger event message.</span></span> <span data-ttu-id="8372d-104">たとえば、入学放電と転送システム (ADT) をメッセージを送信病院情報システム (HIS) にします。</span><span class="sxs-lookup"><span data-stu-id="8372d-104">For example, the Admissions Discharge and Transfer system (ADT) that sends a message to the Hospital Information System (HIS).</span></span> <span data-ttu-id="8372d-105">このスキーマを使用するには、メッセージの形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="8372d-105">You use this schema to define the format of your message.</span></span>  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a><span data-ttu-id="8372d-106">トリガー イベントのメッセージのプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="8372d-106">To create the project for the trigger event message</span></span>  
  
1. <span data-ttu-id="8372d-107">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="8372d-108">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、 をクリックし、 **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-108">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="8372d-109">**テンプレート**一覧で、 **BTAHL7 の空のプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-109">In the **Templates** list, click **Empty BTAHL7 Project**.</span></span>  
  
4. <span data-ttu-id="8372d-110">**名前**フィールドに「 **BTAHL7V24Body プロジェクト**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-110">In the **Name** field, type **BTAHL7V24Body Project**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="8372d-111">ソリューション エクスプ ローラーで、新しいノードの下で**BTAHL7V24Body**プロジェクトを右クリックして**参照**、順にクリックします**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-111">In Solution Explorer, under the node for your new **BTAHL7V24Body** project, right-click **References**, and then click **Add Reference**.</span></span>  
  
6. <span data-ttu-id="8372d-112">参照の追加 ダイアログ ボックスで、、**プロジェクト** タブで  **Interrogative_24Schemas**、 をクリックして**追加**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-112">In the Add Reference dialog box, click the **Projects** tab, select **Interrogative_24Schemas**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="step-3a-add-the-schemas"></a><span data-ttu-id="8372d-113">手順 3 a:スキーマを追加します</span><span class="sxs-lookup"><span data-stu-id="8372d-113">Step 3A: Add the Schemas</span></span>  
 <span data-ttu-id="8372d-114">次の手順を使用して、新しいスキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="8372d-114">Use the following procedure to add the new schemas to the project.</span></span>  
  
#### <a name="to-add-the-schemas-to-the-project"></a><span data-ttu-id="8372d-115">スキーマをプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="8372d-115">To add the schemas to the project</span></span>  
  
1.  <span data-ttu-id="8372d-116">ソリューション エクスプ ローラーで右クリック**BTAHL7V24Body プロジェクト**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-116">In Solution Explorer, right-click **BTAHL7V24Body Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="8372d-117">新しい項目の追加 ダイアログ ボックスで、 **BizTalk プロジェクトの項目**、し、ダブルクリック**BTAHL7 スキーマ**右側のペインでします。</span><span class="sxs-lookup"><span data-stu-id="8372d-117">In the Add New Item dialog box, expand **BizTalk Project Items**, and then double-click **BTAHL7 Schemas** in the right pane.</span></span>  
  
3.  <span data-ttu-id="8372d-118">HL7 スキーマの選択 ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8372d-118">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="8372d-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8372d-119">Use this</span></span>|<span data-ttu-id="8372d-120">目的</span><span class="sxs-lookup"><span data-stu-id="8372d-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8372d-121">**Message クラス**</span><span class="sxs-lookup"><span data-stu-id="8372d-121">**Message Class**</span></span>|<span data-ttu-id="8372d-122">保持**V2.X**選択します。</span><span class="sxs-lookup"><span data-stu-id="8372d-122">Keep **V2.X** selected.</span></span>|  
    |<span data-ttu-id="8372d-123">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="8372d-123">**Version**</span></span>|<span data-ttu-id="8372d-124">選択**2.4**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-124">Select **2.4**.</span></span>|  
    |<span data-ttu-id="8372d-125">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="8372d-125">**Message Type**</span></span>|<span data-ttu-id="8372d-126">選択**QRY**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-126">Select **QRY**.</span></span>|  
    |<span data-ttu-id="8372d-127">**トリガー イベント**</span><span class="sxs-lookup"><span data-stu-id="8372d-127">**Trigger Event**</span></span>|<span data-ttu-id="8372d-128">選択**Q01**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-128">Select **Q01**.</span></span>|  
  
4.  <span data-ttu-id="8372d-129">をクリックして**完了**スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="8372d-129">Click **Finish** to add the schema to the project.</span></span>  
  
     <span data-ttu-id="8372d-130">これには、クエリのスキーマ ファイル QRY_Q01_24_GLO_DEF.xsd が作成されます。</span><span class="sxs-lookup"><span data-stu-id="8372d-130">This creates the query schema file QRY_Q01_24_GLO_DEF.xsd.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8372d-131">HL7 スキーマの選択 ダイアログ ボックスを終了しないでください。</span><span class="sxs-lookup"><span data-stu-id="8372d-131">Do not close the HL7 Schema Selector dialog box.</span></span>  
  
5.  <span data-ttu-id="8372d-132">HL7 スキーマの選択 ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8372d-132">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="8372d-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8372d-133">Use this</span></span>|<span data-ttu-id="8372d-134">目的</span><span class="sxs-lookup"><span data-stu-id="8372d-134">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8372d-135">**Message クラス**</span><span class="sxs-lookup"><span data-stu-id="8372d-135">**Message Class**</span></span>|<span data-ttu-id="8372d-136">保持**V2.X**選択します。</span><span class="sxs-lookup"><span data-stu-id="8372d-136">Keep **V2.X** selected.</span></span>|  
    |<span data-ttu-id="8372d-137">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="8372d-137">**Version**</span></span>|<span data-ttu-id="8372d-138">選択**2.4**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-138">Select **2.4**.</span></span>|  
    |<span data-ttu-id="8372d-139">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="8372d-139">**Message Type**</span></span>|<span data-ttu-id="8372d-140">選択**DSR**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-140">Select **DSR**.</span></span>|  
    |<span data-ttu-id="8372d-141">**トリガー イベント**</span><span class="sxs-lookup"><span data-stu-id="8372d-141">**Trigger Event**</span></span>|<span data-ttu-id="8372d-142">選択**Q01**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-142">Select **Q01**.</span></span>|  
  
6.  <span data-ttu-id="8372d-143">をクリックして**完了**スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="8372d-143">Click **Finish** to add the schema to the project.</span></span>  
  
     <span data-ttu-id="8372d-144">これには、応答スキーマ ファイル DSR_Q01_24_GLO_DEF.xsd が作成されます。</span><span class="sxs-lookup"><span data-stu-id="8372d-144">This creates the response schema file DSR_Q01_24_GLO_DEF.xsd.</span></span>  
  
7.  <span data-ttu-id="8372d-145">クリックして**キャンセル**を閉じる、 **HL7 スキーマの選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8372d-145">Click **Cancel** to close the **HL7 Schema Selector** dialog box.</span></span>  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="8372d-146">手順 3 b:アセンブリに厳密なキーを割り当てるとデプロイ</span><span class="sxs-lookup"><span data-stu-id="8372d-146">Step 3B: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="8372d-147">アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="8372d-147">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="8372d-148">強力なキーを割り当てるし、アセンブリを展開するには</span><span class="sxs-lookup"><span data-stu-id="8372d-148">To assign a strong key and deploy the assembly</span></span>  
  
1. <span data-ttu-id="8372d-149">ソリューション エクスプ ローラーで右クリックして**BTAHL7V24Body**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-149">In Solution Explorer, right-click **BTAHL7V24Body** project, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="8372d-150">**BTAHL7V24Body プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-150">In the **BTAHL7V24Body Property Pages** dialog box, click **Assembly**.</span></span>  
  
3. <span data-ttu-id="8372d-151">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8372d-151">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
4. <span data-ttu-id="8372d-152">**アセンブリ キー ファイル** ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative チュートリアルでは、アクセラレータのをクリックして**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-152">In the **Assembly Key File** dialog box, browse to \<*drive*\>:\Program Files\\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="8372d-153">**BTAHL7V24Body プロパティ ページ**ダイアログ ボックスで、をクリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="8372d-153">In the **BTAHL7V24Body Property Pages** dialog box, click **OK** to save your changes.</span></span>  
  
6. <span data-ttu-id="8372d-154">ソリューション エクスプ ローラーで右クリックして**BTAHL7V24Body プロジェクト**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="8372d-154">In Solution Explorer right-click **BTAHL7V24Body Project**, and then click **Deploy**.</span></span> <span data-ttu-id="8372d-155">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="8372d-155">Ensure a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8372d-156">デプロイが成功したメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="8372d-156">If a successful deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
   <span data-ttu-id="8372d-157">続行する[手順 4。作成、受信ポート ADT クエリ メッセージの受け入れの](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="8372d-157">Proceed to [Step 4: Create the Receive Port for Accepting ADT Query Messages](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md).</span></span>
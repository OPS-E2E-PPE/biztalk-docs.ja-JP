---
title: 手順 3:作成し、トリガー イベント (メッセージ) プロジェクトの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, trigger events
- trigger events
ms.assetid: 5d21a923-fc2c-4d50-b146-daca0aa26e2a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 688d71ba78b79e3cfa7571e6e2f9acb9fe8c6fa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288382"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a><span data-ttu-id="afb30-102">手順 3:作成し、トリガー イベント (メッセージ) プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="afb30-102">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>
<span data-ttu-id="afb30-103">この手順では、トリガー イベントのメッセージのスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="afb30-103">In this step, you create the schema for your trigger event message.</span></span> <span data-ttu-id="afb30-104">たとえば、入学放電と転送システム (ADT) 病院に情報システム (HIS) にメッセージを送信する場合があります。</span><span class="sxs-lookup"><span data-stu-id="afb30-104">For example, you might be the Admissions Discharge and Transfer system (ADT) who sends a message to the Hospital Information System (HIS).</span></span> <span data-ttu-id="afb30-105">このスキーマ、メッセージの形式を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afb30-105">You need this schema to define the format of your message.</span></span>  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a><span data-ttu-id="afb30-106">トリガー イベントのメッセージのプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="afb30-106">To create the project for the trigger event message</span></span>  
  
1. <span data-ttu-id="afb30-107">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューで、**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, then click **Project**.</span></span>  
  
2. <span data-ttu-id="afb30-108">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、 をクリックし、 **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-108">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="afb30-109">テンプレート の  **BTAHL7 の空のプロジェクト**で、**名前**ボックスに「 **BTAHL7V231Body プロジェクト**順にクリックします**ok**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-109">In the Templates section, click **Empty BTAHL7 Project**, in the **Name** box, type **BTAHL7V231Body Project**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="afb30-110">ソリューション エクスプ ローラーで、新しいプロジェクトのノードで右クリック**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-110">In Solution Explorer, under the node for your new project, right-click **References**, and then click **Add Reference**.</span></span>  
  
5. <span data-ttu-id="afb30-111">参照の追加 ダイアログ ボックスで、上、**プロジェクト** タブで  **BTAHL7V231Common Project1**、 をクリックして**追加**、順にクリックします**ok**。</span><span class="sxs-lookup"><span data-stu-id="afb30-111">In the Add Reference dialog box, on the **Projects** tab, select **BTAHL7V231Common Project1**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="step-3a-add-the-schema"></a><span data-ttu-id="afb30-112">手順 3 a:スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="afb30-112">Step 3A: Add the Schema</span></span>  
 <span data-ttu-id="afb30-113">新しいスキーマをプロジェクトに追加するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="afb30-113">Use the following procedure to add the new schema to the project.</span></span>  
  
#### <a name="to-add-the-schema-to-the-project"></a><span data-ttu-id="afb30-114">スキーマをプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="afb30-114">To add the schema to the project</span></span>  
  
1.  <span data-ttu-id="afb30-115">ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body プロジェクト**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-115">In Solution Explorer, right-click **BTAHL7V231Body Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="afb30-116">追加新しい項目] ダイアログ ボックスで、**カテゴリ**セクションで、展開**BizTalk プロジェクトの項目**、し、[ **BTAHL7 スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-116">In the Add New Item dialog box, in the **Categories** section, expand **BizTalk Project Items**, and then select **BTAHL7 Schemas**.</span></span>  
  
3.  <span data-ttu-id="afb30-117">ダブルクリックして、[テンプレート] セクションで**BTAHL7 スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-117">In the Templates section, double-click **BTAHL7 Schemas**.</span></span>  
  
4.  <span data-ttu-id="afb30-118">HL7 スキーマの選択 ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="afb30-118">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="afb30-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afb30-119">Use this</span></span>|<span data-ttu-id="afb30-120">目的</span><span class="sxs-lookup"><span data-stu-id="afb30-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="afb30-121">**Message クラス**</span><span class="sxs-lookup"><span data-stu-id="afb30-121">**Message Class**</span></span>|<span data-ttu-id="afb30-122">既定のままに**V2.X**選択します。</span><span class="sxs-lookup"><span data-stu-id="afb30-122">Leave the default of **V2.X** selected.</span></span>|  
    |<span data-ttu-id="afb30-123">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="afb30-123">**Version**</span></span>|<span data-ttu-id="afb30-124">選択**2.3.1**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-124">Select **2.3.1**.</span></span>|  
    |<span data-ttu-id="afb30-125">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="afb30-125">**Message Type**</span></span>|<span data-ttu-id="afb30-126">選択**ADT**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-126">Select **ADT**.</span></span>|  
    |<span data-ttu-id="afb30-127">**トリガー イベント**</span><span class="sxs-lookup"><span data-stu-id="afb30-127">**Trigger Event**</span></span>|<span data-ttu-id="afb30-128">選択**A03**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-128">Select **A03**.</span></span>|  
  
5.  <span data-ttu-id="afb30-129">をクリックして**完了**スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="afb30-129">Click **Finish** to add the schema to the project.</span></span>  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="afb30-130">手順 3 b:アセンブリに厳密なキーを割り当てるとデプロイ</span><span class="sxs-lookup"><span data-stu-id="afb30-130">Step 3B: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="afb30-131">アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="afb30-131">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="afb30-132">強力なキーを割り当てるし、アセンブリを展開するには</span><span class="sxs-lookup"><span data-stu-id="afb30-132">To assign a strong key and deploy the assembly</span></span>  
  
1. <span data-ttu-id="afb30-133">ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Body プロジェクト**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-133">In Solution Explorer, right-click **BTAHL7V231Body Project**, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="afb30-134">プロジェクト プロパティ ページ ページで、次のようにクリックします。**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-134">In the Project Property Pages page, click **Assembly**.</span></span>  
  
3. <span data-ttu-id="afb30-135">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="afb30-135">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
4. <span data-ttu-id="afb30-136">アセンブリ キー ファイル ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド チュートリアルについては、アクセラレータ クリックして**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-136">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="afb30-137">プロジェクト プロパティ ページ] ダイアログ ボックスで、[ **OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="afb30-137">In the Project Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
6. <span data-ttu-id="afb30-138">ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Body プロジェクト**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="afb30-138">In Solution Explorer right-click **BTAHL7V231Body Project**, and then click **Deploy**.</span></span> <span data-ttu-id="afb30-139">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="afb30-139">Ensure a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="afb30-140">デプロイが成功したメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="afb30-140">If a successful deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
   <span data-ttu-id="afb30-141">続行する[手順 4。作成、ADT を受け入れるための受信ポート ^ A03 メッセージ MLLP アダプターを使用して ADT システムから](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)します。</span><span class="sxs-lookup"><span data-stu-id="afb30-141">Proceed to [Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md).</span></span>
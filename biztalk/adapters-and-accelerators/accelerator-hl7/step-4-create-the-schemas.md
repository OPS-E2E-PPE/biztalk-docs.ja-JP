---
title: '手順 4: スキーマの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, schemas
- creating, schemas
- schemas, creating
ms.assetid: 81b1f538-9743-433a-87f9-a423dcb868c8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ce9ea850632327e257909e1c7d4b60117865e46
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961736"
---
# <a name="step-4-create-the-schemas"></a><span data-ttu-id="4f116-102">手順 4: スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f116-102">Step 4: Create the Schemas</span></span>
<span data-ttu-id="4f116-103">この手順で新しいプロジェクトを作成する (**BTAHL7 プロジェクト**) このプロジェクトの成果物を含む: スキーマ、マップ、およびオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="4f116-103">In this step, you create a new project (**BTAHL7 Project**) that contains the artifacts for this project: the schemas, map, and orchestration.</span></span> <span data-ttu-id="4f116-104">スキーマを作成し、(**Doorbell.xsd**) を既存のスキーマを選択して受信の XML でエンコードされたメッセージ (**ADT_A04_22_GLO_DEF.xsd**) HL7 エンコードされたメッセージの送信。</span><span class="sxs-lookup"><span data-stu-id="4f116-104">You then create a schema (**Doorbell.xsd**) for the incoming XML-encoded message, and select an existing schema (**ADT_A04_22_GLO_DEF.xsd**) for the outgoing HL7-encoded message.</span></span> <span data-ttu-id="4f116-105">これらのスキーマを使用して、オーケストレーション内で交換されるメッセージの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="4f116-105">You use these schemas to define the structure of the messages that you exchange within the orchestration.</span></span>  
  
### <a name="to-create-the-schemas"></a><span data-ttu-id="4f116-106">スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="4f116-106">To create the schemas</span></span>  
  
1.  <span data-ttu-id="4f116-107">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f116-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="4f116-108">新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダーをクリックして、 **BTAHL7Projects**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4f116-108">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  
  
3.  <span data-ttu-id="4f116-109">**テンプレート** ウィンドウで、をクリックして**BTAHL7 の空のプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-109">In the **Templates** pane, click **Empty BTAHL7 Project**.</span></span>  
  
4.  <span data-ttu-id="4f116-110">**名前**フィールドに「 **BTAHL7 プロジェクト**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="4f116-110">In the **Name** field, type **BTAHL7 Project** as the project name.</span></span>  
  
5.  <span data-ttu-id="4f116-111">**ソリューション**フィールドで、**ソリューションに追加**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-111">In the **Solution** field, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="4f116-112">**場所**フィールドしていることを確認するには、  **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common**パスです。</span><span class="sxs-lookup"><span data-stu-id="4f116-112">In the **Location** field, verify that **\<*drive*\>:\Tutorial\BTAHL7V22Common** is the path.</span></span>  
  
7.  <span data-ttu-id="4f116-113">をクリックして**OK**新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f116-113">Click **OK** to open the new project.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="4f116-114">ソリューション エクスプ ローラーに新しいプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="4f116-114"> adds a new project to Solution Explorer.</span></span> <span data-ttu-id="4f116-115">プロジェクト フォルダーを追加して内のファイルを作成、 \<*ドライブ*\>: \Tutorial\\**BTAHL7V22Common**プロジェクト フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4f116-115">It also adds the project folder and creates files in the \<*drive*\>:\Tutorial\\**BTAHL7V22Common** Project folder.</span></span>  
  
8.  <span data-ttu-id="4f116-116">ソリューション エクスプ ローラーで右クリックし、 **BTAHL7 プロジェクト**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="4f116-116">In Solution Explorer, right-click the **BTAHL7 Project** project, point to **Add**, and then click **New Item**.</span></span>  
  
9. <span data-ttu-id="4f116-117">新しい項目の追加 - BTAHL7 プロジェクト ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**スキーマ ファイル**、し、、**テンプレート** ウィンドウで、をクリックして**スキーマ**.</span><span class="sxs-lookup"><span data-stu-id="4f116-117">In the Add New Item - BTAHL7 Project dialog box, in the **Categories** pane, click **Schema Files**, and in the **Templates** pane, click **Schema**.</span></span>  
  
10. <span data-ttu-id="4f116-118">**名前**フィールドに「 **Doorbell.xsd**にスキーマの名前。</span><span class="sxs-lookup"><span data-stu-id="4f116-118">In the **Name** field, type **Doorbell.xsd** to name the schema.</span></span>  
  
11. <span data-ttu-id="4f116-119">をクリックして**追加**に空のスキーマを BizTalk エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="4f116-119">Click **Add** to open the blank schema in BizTalk Editor.</span></span>  
  
12. <span data-ttu-id="4f116-120">**\<スキーマ\>** ツリーで、右クリックし、**ルート**ノードをクリックして**の名前を変更**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-120">In the **\<Schema\>** tree, right-click the **Root** node, and then click **Rename**.</span></span>  
  
13. <span data-ttu-id="4f116-121">型**DoorbellRoot**新しい名前は、およびキーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-121">Type **DoorbellRoot** as the new name, and then press **Enter**.</span></span>  
  
14. <span data-ttu-id="4f116-122">右クリックし、 **DoorbellRoot**に**スキーマ ノードの挿入**、クリックして**子フィールド要素**(フィールドごとにこの手順を繰り返して、次のフィールドを追加するには要素)。</span><span class="sxs-lookup"><span data-stu-id="4f116-122">Right-click the **DoorbellRoot** node, point to **Insert Schema Node**, and then click **Child Field Element** to add the following fields (repeat this step for each field element):</span></span>  
  
    -   <span data-ttu-id="4f116-123">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="4f116-123">**FirstName**</span></span>  
  
    -   <span data-ttu-id="4f116-124">**MiddleName**</span><span class="sxs-lookup"><span data-stu-id="4f116-124">**MiddleName**</span></span>  
  
    -   <span data-ttu-id="4f116-125">**LastName**</span><span class="sxs-lookup"><span data-stu-id="4f116-125">**LastName**</span></span>  
  
    -   <span data-ttu-id="4f116-126">**SSN**</span><span class="sxs-lookup"><span data-stu-id="4f116-126">**SSN**</span></span>  
  
15. <span data-ttu-id="4f116-127">ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="4f116-127">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
16. <span data-ttu-id="4f116-128">新しい項目の追加 - BTAHL7 プロジェクト ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**BTAHL7 スキーマ**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-128">In the Add New Item - BTAHL7 Project dialog box, in the **Categories** pane, click **BTAHL7 Schemas**, and then click **Add**.</span></span>  
  
17. <span data-ttu-id="4f116-129">HL7 スキーマの選択 ダイアログ ボックスで、**メッセージ クラス**ボックスで、 **V2.X**、し、、**スキーマの詳細** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4f116-129">In the HL7 Schema Selector dialog box, in the **Message Class** box, select **V2.X**, and in the **Schema Details** pane, do the following:</span></span>  
  
    |<span data-ttu-id="4f116-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f116-130">Use this</span></span>|<span data-ttu-id="4f116-131">目的</span><span class="sxs-lookup"><span data-stu-id="4f116-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4f116-132">**[バージョン]**</span><span class="sxs-lookup"><span data-stu-id="4f116-132">**Version**</span></span>|<span data-ttu-id="4f116-133">HL7 メッセージのバージョン番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f116-133">Select the version number of the HL7 message.</span></span> <span data-ttu-id="4f116-134">このチュートリアルで使用して**2.2**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-134">In this tutorial, use **2.2**.</span></span>|  
    |<span data-ttu-id="4f116-135">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="4f116-135">**Message Type**</span></span>|<span data-ttu-id="4f116-136">HL7 メッセージの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f116-136">Select the type of HL7 message.</span></span> <span data-ttu-id="4f116-137">このチュートリアルで使用して**ADT**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-137">In this tutorial, use **ADT**.</span></span>|  
    |<span data-ttu-id="4f116-138">**トリガー イベント**</span><span class="sxs-lookup"><span data-stu-id="4f116-138">**Trigger Event**</span></span>|<span data-ttu-id="4f116-139">HL7 メッセージのトリガー イベントの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f116-139">Select the Trigger Event value for the HL7 message.</span></span> <span data-ttu-id="4f116-140">このチュートリアルで使用して**A04**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-140">In this tutorial, use **A04**.</span></span>|  
  
18. <span data-ttu-id="4f116-141">をクリックして**完了**ADT_A04_22_GLO_DEF.xsd (登録患者) スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4f116-141">Click **Finish** to add the ADT_A04_22_GLO_DEF.xsd (Register Patient) schema to your project.</span></span> <span data-ttu-id="4f116-142">HL7 スキーマの選択 ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4f116-142">Close the HL7 Schema Selector dialog box.</span></span>  
  
19. <span data-ttu-id="4f116-143">ソリューション エクスプ ローラーで、[ **BTAHL7 プロジェクト**を右クリックして**参照**] をクリックし、**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-143">In Solution Explorer, under **BTAHL7 Project**, right-click **References** and then click **Add Reference**.</span></span>  
  
20. <span data-ttu-id="4f116-144">参照の追加 ダイアログ ボックスで、**プロジェクト** タブで、、 **BTAHL7V22Common**プロジェクトで、をクリックして**追加**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-144">In the Add Reference dialog box, on the **Projects** tab, select the **BTAHL7V22Common** project, click **Add**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f116-145">元のプロジェクトへの参照を追加できるように[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]HL7 スキーマを正しく認識します。</span><span class="sxs-lookup"><span data-stu-id="4f116-145">This adds a reference to the original project so that [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] recognizes the HL7 schemas correctly.</span></span>  
  
21. <span data-ttu-id="4f116-146">ソリューション エクスプ ローラーで、[ **BTAHL7 プロジェクト**を右クリックして**参照**] をクリックし、**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-146">In Solution Explorer, under **BTAHL7 Project**, right-click **References** and then click **Add Reference**.</span></span>  
  
22. <span data-ttu-id="4f116-147">[参照の追加] ダイアログ ボックス、**参照**タブです。**検索対象の**ボックスに移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド チュートリアルのアクセラレータ\Tutorial_BTAHL7Drop\Bin です。</span><span class="sxs-lookup"><span data-stu-id="4f116-147">In the Add Reference dialog box, click the **Browse** tab. In the **Look In** box, move to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop\Bin.</span></span> <span data-ttu-id="4f116-148">をクリックして**Microsoft.Solutions.BTAHL7.HL7Schemas.dll**、 をクリックして**追加**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="4f116-148">Click **Microsoft.Solutions.BTAHL7.HL7Schemas.dll**, click **Add**, and then click **OK**.</span></span>  
  
 <span data-ttu-id="4f116-149">進みます[手順 5: スキーマのプロパティを昇格させる](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f116-149">Proceed to [Step 5: Promote Schema Properties](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f116-150">参照</span><span class="sxs-lookup"><span data-stu-id="4f116-150">See Also</span></span>  
 [<span data-ttu-id="4f116-151">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="4f116-151">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)
---
title: '手順 8: BizTalk マッパーでマップを作成する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, maps
- creating, maps
- maps, creating
- BizTalk Mapper
ms.assetid: 785426c7-5651-48be-b3f4-7f9d8051ba23
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b9edeca21fe9967f816f05d2ceb12ffe5c5ded
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968459"
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a><span data-ttu-id="53f75-102">手順 8: BizTalk マッパーでマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="53f75-102">Step 8: Create a Map with BizTalk Mapper</span></span>
<span data-ttu-id="53f75-103">この手順では、BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="53f75-103">In this step, you use the BizTalk Mapper to create a map.</span></span> <span data-ttu-id="53f75-104">データ (フィールド) に関連付けるリンクを作成するのにドキュメントが拒否された要求のデータに補充要求ドキュメントでこのマップを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="53f75-104">You use this map to create links that associate the data (fields) in a replenishment request document to the data in a request denied document.</span></span>  
  
### <a name="to-create-a-map"></a><span data-ttu-id="53f75-105">マップを作成するには</span><span class="sxs-lookup"><span data-stu-id="53f75-105">To create a map</span></span>  
  
1. <span data-ttu-id="53f75-106">ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="53f75-106">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="53f75-107">**新しい項目の追加** ダイアログ ボックスで、**カテゴリ**ウィンドウで、をクリックして**マップ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="53f75-107">In the **Add New Item** dialog box, in the **Categories** pane, click **Map Files**.</span></span>  
  
3. <span data-ttu-id="53f75-108">**名前**フィールドに「 **DoorbellMap** 、マップの名前をクリックして**追加**を BizTalk マッパーを開始します。</span><span class="sxs-lookup"><span data-stu-id="53f75-108">In the **Name** field, type **DoorbellMap** to name the map, and then click **Add** to start BizTalk Mapper.</span></span>  
  
4. <span data-ttu-id="53f75-109">**送信元スキーマ**ウィンドウ (左側) をクリックします**ソース スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="53f75-109">In the **Source Schema** pane (left side), click **Open Source Schema**.</span></span>  
  
5. <span data-ttu-id="53f75-110">BizTalk 型の選択 ダイアログ ボックスで、 **BTAHL7 プロジェクト**、展開**スキーマ**、 をクリックして**BTAHL7_Project.Doorbell**、順にクリックします**OK**.</span><span class="sxs-lookup"><span data-stu-id="53f75-110">In the BizTalk Type Picker dialog box, expand **BTAHL7 Project**, expand **Schemas**, click **BTAHL7_Project.Doorbell**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="53f75-111">**送信先スキーマ**ウィンドウ (右側) をクリックします**送信先スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="53f75-111">In the **Destination Schema** pane (right side), click **Open Destination Schema**.</span></span>  
  
7. <span data-ttu-id="53f75-112">BizTalk 型の選択で [ **BTAHL7 プロジェクト**、展開**スキーマ**、] をクリックして**BTAHL7Schemas.ADT_A04_22_GLO_DEF**、順にクリックします**OK**.</span><span class="sxs-lookup"><span data-stu-id="53f75-112">In the BizTalk Type Picker, expand **BTAHL7 Project**, expand **Schemas**, click **BTAHL7Schemas.ADT_A04_22_GLO_DEF**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="53f75-113">**送信先スキーマ**ウィンドウ (右側) 展開**ADT_A04_22_GLO_DEF**、展開**PID_PatientIdentification**、展開と**PID.5_PatientName**.</span><span class="sxs-lookup"><span data-stu-id="53f75-113">In the **Destination Schema** pane (right side), expand **ADT_A04_22_GLO_DEF**, expand **PID_PatientIdentification**, and expand **PID.5_PatientName**.</span></span>  
  
9. <span data-ttu-id="53f75-114">**送信元スキーマ**ウィンドウ (左側)、展開**DoorbellRoot**します。</span><span class="sxs-lookup"><span data-stu-id="53f75-114">In the **Source Schema** pane (left side), expand **DoorbellRoot**.</span></span> <span data-ttu-id="53f75-115">ドラッグ、 **LastName**フィールドを**PN_0_FamilyName**フィールドに、**送信先スキーマ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="53f75-115">Drag the **LastName** field to the **PN_0_FamilyName** field in the **Destination Schema** pane.</span></span>  
  
10. <span data-ttu-id="53f75-116">**送信元スキーマ**ウィンドウで、ドラッグ、 **FirstName**フィールドを**PN_1_GivenName**フィールドに、**送信先スキーマ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="53f75-116">In the **Source Schema** pane, drag the **FirstName** field to the **PN_1_GivenName** field in the **Destination Schema** pane.</span></span>  
  
11. <span data-ttu-id="53f75-117">**送信元スキーマ**ウィンドウで、ドラッグ、 **MiddleName**フィールドを**PN_2_MiddleInitialOrName**フィールドに、**送信先スキーマ**ウィンドウ.</span><span class="sxs-lookup"><span data-stu-id="53f75-117">In the **Source Schema** pane, drag the **MiddleName** field to the **PN_2_MiddleInitialOrName** field in the **Destination Schema** pane.</span></span>  
  
12. <span data-ttu-id="53f75-118">**送信先スキーマ**ウィンドウで、展開**PID_3_PatientIdInternalId**します。</span><span class="sxs-lookup"><span data-stu-id="53f75-118">In the **Destination Schema** pane, expand **PID_3_PatientIdInternalId**.</span></span>  
  
13. <span data-ttu-id="53f75-119">**送信元スキーマ**ウィンドウで、ドラッグ、 **SSN**フィールドを**CM_PAT_ID_0_PatientID**で、**送信先スキーマ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="53f75-119">In the **Source Schema** pane, drag the **SSN** field to the **CM_PAT_ID_0_PatientID** in the **Destination Schema** pane.</span></span>  
  
14. <span data-ttu-id="53f75-120">**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="53f75-120">In the **File** menu, click **Save All**.</span></span>  
  
    <span data-ttu-id="53f75-121">一般的なメッセージの強化のシナリオで、患者の情報が見つからない場合は、オーケストレーションで患者レコード データベースへの呼び出しを行うして、不足している情報を追加し、する追加の情報を使用してマッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="53f75-121">In a typical message enrichment scenario, if any patient information were missing, you would make a call to a Patient Records database in your orchestration and add the missing information, then use the additional information to complete the mapping.</span></span> <span data-ttu-id="53f75-122">たとえば、XML ドアベル トリガー イベントの受信メッセージが提供していないために、患者レコードのデータベースから患者の自宅の住所を取得することが。</span><span class="sxs-lookup"><span data-stu-id="53f75-122">For example, you might retrieve the home address of a patient from the Patient Records database, since the inbound XML doorbell trigger event message did not provide it.</span></span>  
  
    <span data-ttu-id="53f75-123">進みます[手順 9: 検証し、マップのプロジェクトをビルド](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="53f75-123">Proceed to [Step 9: Validate and Build the Map Project](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f75-124">参照</span><span class="sxs-lookup"><span data-stu-id="53f75-124">See Also</span></span>  
 [<span data-ttu-id="53f75-125">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="53f75-125">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)
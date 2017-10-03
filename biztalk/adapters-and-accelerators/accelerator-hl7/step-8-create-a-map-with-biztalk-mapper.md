---
title: "手順 8: BizTalk マッパーでマップの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, maps
- creating, maps
- maps, creating
- BizTalk Mapper
ms.assetid: 785426c7-5651-48be-b3f4-7f9d8051ba23
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48e2578211d65ade2a50916e909c87a6fd84bf44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a><span data-ttu-id="08ab8-102">手順 8: BizTalk マッパーでマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="08ab8-102">Step 8: Create a Map with BizTalk Mapper</span></span>
<span data-ttu-id="08ab8-103">このステップでは、BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="08ab8-103">In this step, you use the BizTalk Mapper to create a map.</span></span> <span data-ttu-id="08ab8-104">データ (フィールド) に関連付けているリンクを作成するのにドキュメントを拒否された要求内のデータに補充要求ドキュメントでこのマップを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="08ab8-104">You use this map to create links that associate the data (fields) in a replenishment request document to the data in a request denied document.</span></span>  
  
### <a name="to-create-a-map"></a><span data-ttu-id="08ab8-105">マップを作成するには</span><span class="sxs-lookup"><span data-stu-id="08ab8-105">To create a map</span></span>  
  
1.  <span data-ttu-id="08ab8-106">ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="08ab8-106">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="08ab8-107">**新しい項目の追加** ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**マップ ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="08ab8-107">In the **Add New Item** dialog box, in the **Categories** pane, click **Map Files**.</span></span>  
  
3.  <span data-ttu-id="08ab8-108">**名前**フィールドに「 **DoorbellMap** 、マップの名前を指定し [] をクリックしてする**追加**を BizTalk マッパーを起動します。</span><span class="sxs-lookup"><span data-stu-id="08ab8-108">In the **Name** field, type **DoorbellMap** to name the map, and then click **Add** to start BizTalk Mapper.</span></span>  
  
4.  <span data-ttu-id="08ab8-109">**送信元スキーマ**ウィンドウ (左側) をクリックします**ソース スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="08ab8-109">In the **Source Schema** pane (left side), click **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="08ab8-110">BizTalk 型の選択 ダイアログ ボックスで、展開**BTAHL7 プロジェクト**、展開**スキーマ**、 をクリックして**BTAHL7_Project.Doorbell**、順にクリック**OK**.</span><span class="sxs-lookup"><span data-stu-id="08ab8-110">In the BizTalk Type Picker dialog box, expand **BTAHL7 Project**, expand **Schemas**, click **BTAHL7_Project.Doorbell**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="08ab8-111">**送信先スキーマ**ウィンドウ (右側) をクリックして**送信先スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="08ab8-111">In the **Destination Schema** pane (right side), click **Open Destination Schema**.</span></span>  
  
7.  <span data-ttu-id="08ab8-112">BizTalk 型の選択で、展開**BTAHL7 プロジェクト**、展開**スキーマ**、 をクリックして**BTAHL7Schemas.ADT_A04_22_GLO_DEF**、順にクリック**OK**.</span><span class="sxs-lookup"><span data-stu-id="08ab8-112">In the BizTalk Type Picker, expand **BTAHL7 Project**, expand **Schemas**, click **BTAHL7Schemas.ADT_A04_22_GLO_DEF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="08ab8-113">**送信先スキーマ**ウィンドウ (右側) を展開**ADT_A04_22_GLO_DEF**、展開**PID_PatientIdentification**、展開と**PID.5_PatientName**.</span><span class="sxs-lookup"><span data-stu-id="08ab8-113">In the **Destination Schema** pane (right side), expand **ADT_A04_22_GLO_DEF**, expand **PID_PatientIdentification**, and expand **PID.5_PatientName**.</span></span>  
  
9. <span data-ttu-id="08ab8-114">**送信元スキーマ**ウィンドウ (左側)、展開**DoorbellRoot**です。</span><span class="sxs-lookup"><span data-stu-id="08ab8-114">In the **Source Schema** pane (left side), expand **DoorbellRoot**.</span></span> <span data-ttu-id="08ab8-115">ドラッグ、 **LastName**フィールドを**PN_0_FamilyName**フィールドで、**送信先スキーマ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="08ab8-115">Drag the **LastName** field to the **PN_0_FamilyName** field in the **Destination Schema** pane.</span></span>  
  
10. <span data-ttu-id="08ab8-116">**送信元スキーマ** ウィンドウで、ドラッグ、 **FirstName**フィールドを**PN_1_GivenName**フィールドで、**送信先スキーマ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="08ab8-116">In the **Source Schema** pane, drag the **FirstName** field to the **PN_1_GivenName** field in the **Destination Schema** pane.</span></span>  
  
11. <span data-ttu-id="08ab8-117">**送信元スキーマ** ウィンドウで、ドラッグ、 **MiddleName**フィールドを**PN_2_MiddleInitialOrName**フィールドで、**送信先スキーマ**ペイン.</span><span class="sxs-lookup"><span data-stu-id="08ab8-117">In the **Source Schema** pane, drag the **MiddleName** field to the **PN_2_MiddleInitialOrName** field in the **Destination Schema** pane.</span></span>  
  
12. <span data-ttu-id="08ab8-118">**送信先スキーマ** ウィンドウで、展開**PID_3_PatientIdInternalId**です。</span><span class="sxs-lookup"><span data-stu-id="08ab8-118">In the **Destination Schema** pane, expand **PID_3_PatientIdInternalId**.</span></span>  
  
13. <span data-ttu-id="08ab8-119">**送信元スキーマ** ウィンドウで、ドラッグ、 **SSN**フィールドを**CM_PAT_ID_0_PatientID**で、**送信先スキーマ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="08ab8-119">In the **Source Schema** pane, drag the **SSN** field to the **CM_PAT_ID_0_PatientID** in the **Destination Schema** pane.</span></span>  
  
14. <span data-ttu-id="08ab8-120">**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="08ab8-120">In the **File** menu, click **Save All**.</span></span>  
  
 <span data-ttu-id="08ab8-121">シナリオでは、一般的なメッセージの強化、患者の情報が見つからなかった場合は、オーケストレーションで、患者のレコードのデータベースへの呼び出しを行うして不足している情報を追加し、する追加の情報を使用して、マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="08ab8-121">In a typical message enrichment scenario, if any patient information were missing, you would make a call to a Patient Records database in your orchestration and add the missing information, then use the additional information to complete the mapping.</span></span> <span data-ttu-id="08ab8-122">たとえば、XML ドアベル トリガー イベントの受信メッセージでは提供しませんでしたので患者のレコードのデータベースから患者の自宅の住所を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="08ab8-122">For example, you might retrieve the home address of a patient from the Patient Records database, since the inbound XML doorbell trigger event message did not provide it.</span></span>  
  
 <span data-ttu-id="08ab8-123">進みます[手順 9: 検証し、マップのプロジェクトをビルド](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="08ab8-123">Proceed to [Step 9: Validate and Build the Map Project](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ab8-124">参照</span><span class="sxs-lookup"><span data-stu-id="08ab8-124">See Also</span></span>  
 [<span data-ttu-id="08ab8-125">メッセージの強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="08ab8-125">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)
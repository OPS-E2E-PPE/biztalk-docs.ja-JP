---
title: ビジネス アクティビティを定義する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business activities, creating [Excel add-in]
- monitoring business activities [BAM], creating business activities [Excel add-in]
- monitoring business activities [BAM], Excel add-in
ms.assetid: 305e3718-46b4-45df-bd52-f7ae36621576
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5702d1530926bf4bd0c2ecdc97520f777be3701e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385372"
---
# <a name="how-to-define-a-business-activity"></a><span data-ttu-id="20141-102">ビジネス アクティビティを定義する方法</span><span class="sxs-lookup"><span data-stu-id="20141-102">How to Define a Business Activity</span></span>
<span data-ttu-id="20141-103">レポート用に収集が必要なデータを指定するには、BAM アクティビティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20141-103">To indicate the data you need to collect for reports, you must define a BAM activity.</span></span> <span data-ttu-id="20141-104">アクティビティには、BAM を使用して追跡する重要なマイルストーンとデータ項目の一覧を含めます。BAM Excel アドインを使用し、以下の手順に従ってアクティビティを作成します。</span><span class="sxs-lookup"><span data-stu-id="20141-104">This contains a list of the important milestones and data items you want BAM to track. Use the BAM Excel add-in to create an activity as shown in the following procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20141-105">アクティビティを展開した後は、アクティビティに対して実行できる操作が制限されます。</span><span class="sxs-lookup"><span data-stu-id="20141-105">Once an activity has been deployed, the actions you can take on an activity become restricted.</span></span> <span data-ttu-id="20141-106">特に、アクティビティから項目を削除するには、管理者に依頼して BAM のアクティビティとビュー セット全体を展開解除し、再展開してもらう必要があります。</span><span class="sxs-lookup"><span data-stu-id="20141-106">Specifically, you cannot delete items from an activity unless you are prepared to have your administrator undeploy the entire BAM activity and view sets and then redeploy them.</span></span> <span data-ttu-id="20141-107">このとき、管理者がデータのバックアップと復元を行わないと、データが失われたり、表示できなくなったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="20141-107">This can cause an interruption of visibility and loss of data unless the administrator does a backup and restore of the data.</span></span>  
  
### <a name="to-create-a-business-activity"></a><span data-ttu-id="20141-108">ビジネス アクティビティを作成するには</span><span class="sxs-lookup"><span data-stu-id="20141-108">To create a business activity</span></span>  
  
1.  <span data-ttu-id="20141-109">Microsoft Excel を開きます。</span><span class="sxs-lookup"><span data-stu-id="20141-109">Open Microsoft Excel.</span></span>  
  
2.  <span data-ttu-id="20141-110">メニューの [ツールバー] をクリックして、 **BAM**メニュー項目をクリックします**BAM アクティビティ**します。</span><span class="sxs-lookup"><span data-stu-id="20141-110">On the menu tool bar, click the **BAM** menu item, and click **BAM Activity**.</span></span>  
  
     <span data-ttu-id="20141-111">**ビジネス アクティビティ監視アクティビティ ウィザード**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20141-111">The **Business Activity Monitoring Activity Wizard** appears.</span></span>  
  
3.  <span data-ttu-id="20141-112">クリックして**新しいアクティビティ**します。</span><span class="sxs-lookup"><span data-stu-id="20141-112">Click **New Activity**.</span></span>  
  
     <span data-ttu-id="20141-113">**新しいアクティビティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20141-113">The **New Activity** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="20141-114">アクティビティでは、わかりやすい名前を入力、**アクティビティ名**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="20141-114">Type a descriptive name for the activity in the **Activity Name** text box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20141-115">アクティビティには、少なくとも 1 つのアクティビティ項目が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="20141-115">An activity must contain at least one activity item.</span></span>  
  
#### <a name="to-create-a-new-item"></a><span data-ttu-id="20141-116">新しい項目を作成するには</span><span class="sxs-lookup"><span data-stu-id="20141-116">To create a new item</span></span>  
  
1. <span data-ttu-id="20141-117">クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="20141-117">Click **New Item**.</span></span>  
  
2. <span data-ttu-id="20141-118">**新しいアクティビティ項目** ダイアログ ボックスで、**新しいアクティビティ項目**ボックスに、アクティビティ項目のわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="20141-118">In the **New Activity Item** dialog box, in the **New Activity Item** box, type a descriptive name for the activity item.</span></span>  
  
3. <span data-ttu-id="20141-119">**項目の種類**ドロップダウン メニューでは、この項目の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="20141-119">From the **Item type** drop-down menu, select a type for this item.</span></span> <span data-ttu-id="20141-120">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20141-120">Possible values include:</span></span>  
  
   |<span data-ttu-id="20141-121">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="20141-121">Item type</span></span>|<span data-ttu-id="20141-122">説明</span><span class="sxs-lookup"><span data-stu-id="20141-122">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="20141-123">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="20141-123">Business Milestone</span></span>|<span data-ttu-id="20141-124">日付/時刻値。</span><span class="sxs-lookup"><span data-stu-id="20141-124">A date/time value.</span></span> <span data-ttu-id="20141-125">たとえば、注文書が承認された日付です。</span><span class="sxs-lookup"><span data-stu-id="20141-125">For example, an approval date for a purchase order.</span></span>|  
   |<span data-ttu-id="20141-126">ビジネス データ - テキスト</span><span class="sxs-lookup"><span data-stu-id="20141-126">Business Data – Text</span></span>|<span data-ttu-id="20141-127">任意の英数字の文字列。</span><span class="sxs-lookup"><span data-stu-id="20141-127">A string containing any alphanumeric characters.</span></span> <span data-ttu-id="20141-128">たとえば、出荷先。市区町村、都道府県、郵便コードです。</span><span class="sxs-lookup"><span data-stu-id="20141-128">For example, Ship to: City, State/Province and Zip/Postal code.</span></span>|  
   |<span data-ttu-id="20141-129">ビジネス データ-Integer</span><span class="sxs-lookup"><span data-stu-id="20141-129">Business Data – Integer</span></span>|<span data-ttu-id="20141-130">整数値。</span><span class="sxs-lookup"><span data-stu-id="20141-130">A whole number value.</span></span> <span data-ttu-id="20141-131">たとえば、注文の合計数です。</span><span class="sxs-lookup"><span data-stu-id="20141-131">For example, the total number of purchases.</span></span>|  
   |<span data-ttu-id="20141-132">ビジネス データ - 10 進数</span><span class="sxs-lookup"><span data-stu-id="20141-132">Business Data – Decimal</span></span>|<span data-ttu-id="20141-133">decimal 値です。</span><span class="sxs-lookup"><span data-stu-id="20141-133">A decimal value.</span></span> <span data-ttu-id="20141-134">たとえば、PO の合計金額です。</span><span class="sxs-lookup"><span data-stu-id="20141-134">For example the total dollar amount of the PO.</span></span>|  
  
    <span data-ttu-id="20141-135">"ビジネス データ-Text"を型項目を選択する場合は、文字列の最大文字数を入力する必要があります、**最大長**ボックス。</span><span class="sxs-lookup"><span data-stu-id="20141-135">If you select the item type "Business Data – Text", you must enter the maximum number of characters for the string in the **Maximum length** box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="20141-136">これらの項目の作成の詳細については、Microsoft BizTalk Server チュートリアルの「パートナーの管理とビジネス アクティビティの監視」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20141-136">For more information about creating these items, see "Partner Management and Business Activity Monitoring" in the Microsoft BizTalk Server tutorial.</span></span>  
  
4. <span data-ttu-id="20141-137">手順 1. ～ 3. を繰り返して、このアクティビティに必要な数だけ項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="20141-137">Repeat steps 1 through 3 to add as many items as needed to this activity.</span></span>  
  
5. <span data-ttu-id="20141-138">ビジネス アクティビティ監視アクティビティ ウィザードを完了すると、ビジネス アクティビティ監視ビュー ウィザードが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="20141-138">After you complete the Business Activity Monitoring Activity Wizard, the Business Activity Monitoring View Wizard starts automatically.</span></span>  
  
   <span data-ttu-id="20141-139">詳細については、このウィザードを使用して、次を参照してください。 [BAM ビューを定義する](../core/defining-a-bam-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="20141-139">For more information about using this wizard, see [Defining a BAM View](../core/defining-a-bam-view.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20141-140">参照</span><span class="sxs-lookup"><span data-stu-id="20141-140">See Also</span></span>  
 <span data-ttu-id="20141-141">[BAM ビューの定義](../core/defining-a-bam-view.md) </span><span class="sxs-lookup"><span data-stu-id="20141-141">[Defining a BAM View](../core/defining-a-bam-view.md) </span></span>  
 [<span data-ttu-id="20141-142">Excel でのビジネス アクティビティとビジネス ビューの定義</span><span class="sxs-lookup"><span data-stu-id="20141-142">Defining Business Activities and Views in Excel</span></span>](../core/defining-business-activities-and-views-in-excel.md)
---
title: データベース Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77bc9390-cdb5-42ff-8b28-6265c51c79fc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5c0b1be12176653bba2414e32bdefbd83e9083
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013835"
---
# <a name="database-functoids"></a><span data-ttu-id="1c5da-102">データベース Functoid</span><span class="sxs-lookup"><span data-stu-id="1c5da-102">Database Functoids</span></span>
<span data-ttu-id="1c5da-103">**データベース**functoid は、出力インスタンス メッセージで使用するためのデータベースからデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-103">**Database** functoids extract data from a database for use in an output instance message.</span></span> 

## <a name="overview"></a><span data-ttu-id="1c5da-104">概要</span><span class="sxs-lookup"><span data-stu-id="1c5da-104">Overview</span></span>
<span data-ttu-id="1c5da-105">一覧を次に、**データベース**functoid とその使用方法。</span><span class="sxs-lookup"><span data-stu-id="1c5da-105">The following is a list of the **Database** functoids and how you can use them:</span></span>  

- <span data-ttu-id="1c5da-106">**データベース検索します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-106">**Database Lookup.**</span></span> <span data-ttu-id="1c5da-107">使用して、**データベース検索**functoid をデータベースから情報を抽出し、Microsoft ActiveX データ オブジェクト .NET (ADO.NET) レコード セットとして保存します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-107">Use the **Database Lookup** functoid to extract information from a database and store it as a Microsoft ActiveX Data Objects .NET (ADO.NET) recordset.</span></span> <span data-ttu-id="1c5da-108">この Functoid には、次の順序で 4 つの入力パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="1c5da-108">This functoid requires four input parameters in the following order:</span></span>  

  -   <span data-ttu-id="1c5da-109">参照値</span><span class="sxs-lookup"><span data-stu-id="1c5da-109">A lookup value</span></span>  

  -   <span data-ttu-id="1c5da-110">データベース接続文字列</span><span class="sxs-lookup"><span data-stu-id="1c5da-110">A database connection string</span></span>  

  -   <span data-ttu-id="1c5da-111">テーブル名</span><span class="sxs-lookup"><span data-stu-id="1c5da-111">A table name</span></span>  

  -   <span data-ttu-id="1c5da-112">参照値の列の名前</span><span class="sxs-lookup"><span data-stu-id="1c5da-112">A column name for the lookup value.</span></span>  

- <span data-ttu-id="1c5da-113">**エラーの戻り値。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-113">**Error Return.**</span></span> <span data-ttu-id="1c5da-114">使用して、**エラーを返す**functoid を実行時に行われる、データベース接続エラーなどのエラー情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-114">Use the **Error Return** functoid to capture error information, such as database connection failures, that occur during run time.</span></span> <span data-ttu-id="1c5da-115">この functoid には、1 つの入力パラメーターが必要です: からのリンク、**データベース検索**functoid。</span><span class="sxs-lookup"><span data-stu-id="1c5da-115">This functoid requires one input parameter: a link from the **Database Lookup** functoid.</span></span>  

- <span data-ttu-id="1c5da-116">**メッセージの書式設定します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-116">**Format Message.**</span></span> <span data-ttu-id="1c5da-117">引数の代入によって書式設定とローカライズが行われた文字列が返されます。また場合によっては、ID と値が返されます。</span><span class="sxs-lookup"><span data-stu-id="1c5da-117">Returns a formatted and localized string using argument substitution and, potentially, ID and value cross-referencing.</span></span>  

- <span data-ttu-id="1c5da-118">**アプリケーション ID を取得します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-118">**Get Application ID.**</span></span> <span data-ttu-id="1c5da-119">アプリケーション オブジェクトの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-119">Retrieves an identifier for an application object.</span></span>  

- <span data-ttu-id="1c5da-120">**アプリケーション値を取得します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-120">**Get Application Value.**</span></span> <span data-ttu-id="1c5da-121">アプリケーション値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-121">Retrieves an application value.</span></span>  

- <span data-ttu-id="1c5da-122">**共通 ID を取得します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-122">**Get Common ID.**</span></span> <span data-ttu-id="1c5da-123">共通オブジェクトの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-123">Retrieves an identifier for a common object.</span></span>  

- <span data-ttu-id="1c5da-124">**一般的な値を取得します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-124">**Get Common Value.**</span></span> <span data-ttu-id="1c5da-125">共通値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-125">Retrieves a common value.</span></span>  

- <span data-ttu-id="1c5da-126">**アプリケーション ID を削除します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-126">**Remove Application ID.**</span></span> <span data-ttu-id="1c5da-127">アプリケーション値を削除します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-127">Removes an application value.</span></span>  

- <span data-ttu-id="1c5da-128">**共通 ID を設定します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-128">**Set Common ID.**</span></span> <span data-ttu-id="1c5da-129">共通オブジェクトの識別子を設定して返します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-129">Sets and returns an identifier for a common object.</span></span>  

- <span data-ttu-id="1c5da-130">**値抽出します。**</span><span class="sxs-lookup"><span data-stu-id="1c5da-130">**Value Extractor.**</span></span> <span data-ttu-id="1c5da-131">使用して、**値抽出**functoid によって返されるレコード セット内の指定された列からデータを抽出する、**データベース検索**functoid。</span><span class="sxs-lookup"><span data-stu-id="1c5da-131">Use the **Value Extractor** functoid to extract data from the specified column in a recordset returned by the **Database Lookup** functoid.</span></span> <span data-ttu-id="1c5da-132">この functoid は、2 つの入力パラメーターが必要です: へのリンク、**データベース検索**functoid と列の名前。</span><span class="sxs-lookup"><span data-stu-id="1c5da-132">This functoid requires two input parameters: a link to the **Database Lookup** functoid and a column name.</span></span>  

  <span data-ttu-id="1c5da-133">1 ~ 7、**データベース**functoid —**メッセージの書式設定、アプリケーション ID の取得**、**アプリケーション値の取得**、**共通 ID の取得**、 **共通値の取得**、**アプリケーション ID の削除**、および**共通 ID の設定**— は**CrossReferencing** functoid。</span><span class="sxs-lookup"><span data-stu-id="1c5da-133">Seven of the **Database** functoids— **Format Message, Get Application ID**, **Get Application Value**, **Get Common ID**, **Get Common Value**, **Remove Application ID**, and **Set Common ID**—are **CrossReferencing** functoids.</span></span> <span data-ttu-id="1c5da-134">これらの Functoid は、入力メッセージの ID と値を、出力メッセージで必要とされる ID と値に変換します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-134">These functoids translate IDs and values from an input message into the IDs and values needed in the output message.</span></span> <span data-ttu-id="1c5da-135">詳細については、次を参照してください。**データベース Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-135">For more information, see **Database Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="example"></a><span data-ttu-id="1c5da-136">例</span><span class="sxs-lookup"><span data-stu-id="1c5da-136">Example</span></span>  
 <span data-ttu-id="1c5da-137">次の例では、いくつか使用して、**データベース**functoid。</span><span class="sxs-lookup"><span data-stu-id="1c5da-137">The following example uses some of the **Database** functoids.</span></span> <span data-ttu-id="1c5da-138">この例では、広範な地域に店舗を持つ大規模な小売メーカーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="1c5da-138">Consider a large retail manufacturer with stores spread over a large geographical area.</span></span> <span data-ttu-id="1c5da-139">店舗を追跡するのに本社は各ストアという一意のコードを割り当てます、 **StoreID**します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-139">To keep track of the stores, headquarters assigns each store a unique code called a **StoreID**.</span></span> <span data-ttu-id="1c5da-140">さらに、本社が互いに、次の情報を関連付けます**StoreID**:</span><span class="sxs-lookup"><span data-stu-id="1c5da-140">Additionally, headquarters associates the following information with each **StoreID**:</span></span>  

- <span data-ttu-id="1c5da-141">StoreName</span><span class="sxs-lookup"><span data-stu-id="1c5da-141">StoreName</span></span>  

- <span data-ttu-id="1c5da-142">StoreAddress</span><span class="sxs-lookup"><span data-stu-id="1c5da-142">StoreAddress</span></span>  

- <span data-ttu-id="1c5da-143">City</span><span class="sxs-lookup"><span data-stu-id="1c5da-143">City</span></span>  

- <span data-ttu-id="1c5da-144">PostalCode</span><span class="sxs-lookup"><span data-stu-id="1c5da-144">PostalCode</span></span>  

- <span data-ttu-id="1c5da-145">StorePhoneNumber</span><span class="sxs-lookup"><span data-stu-id="1c5da-145">StorePhoneNumber</span></span>  

- <span data-ttu-id="1c5da-146">StoreManager</span><span class="sxs-lookup"><span data-stu-id="1c5da-146">StoreManager</span></span>  

  <span data-ttu-id="1c5da-147">この情報は、データベースに保存され、定期的に取引先に配布されます。</span><span class="sxs-lookup"><span data-stu-id="1c5da-147">This information is stored in a database and is distributed to trading partners on a regular basis.</span></span> <span data-ttu-id="1c5da-148">メーカー側では、すべての購入が店舗ではなく本社で行われます。</span><span class="sxs-lookup"><span data-stu-id="1c5da-148">For the manufacturer, all purchasing is done by headquarters, not the stores.</span></span> <span data-ttu-id="1c5da-149">本社が取引先に注文書を送る場合、通常、複数の店舗が受け取る商品を 1 つの注文書で処理します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-149">When headquarters sends a purchase order to the trading partners, it is common for multiple stores to receive merchandise ordered through the single purchase order.</span></span> <span data-ttu-id="1c5da-150">商品を受け取る各店舗の名前とアドレス情報を送信する代わりに本社が単純に送信します、 **StoreID**します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-150">Instead of sending name and address information for each store that is to receive merchandise, headquarters simply sends the **StoreID**.</span></span> <span data-ttu-id="1c5da-151">取引先が使用するには、高度な出荷通知には、名前とアドレス情報を挿入する、**データベース**functoid は、出力インスタンス メッセージにこの情報を自動的に挿入します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-151">To insert the name and address information into the advanced ship notice, the trading partner uses the **Database** functoids to automatically insert this information into the output instance message.</span></span> <span data-ttu-id="1c5da-152">次の図は、取引先がマップ内で StoreID の置換を実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1c5da-152">The following figure shows how a trading partner can implement the replacement of the StoreID in a map.</span></span>  

  <span data-ttu-id="1c5da-153">![表示されている別のデータベース functoid をマップします。](../core/media/origdbfunctoids.gif "origdbfunctoids")</span><span class="sxs-lookup"><span data-stu-id="1c5da-153">![Map showing  different database functoids.](../core/media/origdbfunctoids.gif "origdbfunctoids")</span></span>  

  <span data-ttu-id="1c5da-154">この図では、送信元スキーマは受信する注文書を表し、送信先スキーマは詳細な出荷通知を表しています。</span><span class="sxs-lookup"><span data-stu-id="1c5da-154">In the figure, the source schema represents an incoming purchase order; the destination schema represents an advanced ship notice.</span></span> <span data-ttu-id="1c5da-155">**データベース検索**functoid が適切なデータベース テーブルから適切なレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-155">The **Database Lookup** functoid finds the appropriate record from the appropriate database table.</span></span> <span data-ttu-id="1c5da-156">**値抽出**functoid は、参照レコードから適切な列を抽出します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-156">The **Value Extractor** functoids extract the appropriate column from the lookup record.</span></span> <span data-ttu-id="1c5da-157">**エラーを返す**functoid は、実行時にエラー (接続の障害などがある場合は、エラー情報を含む文字列を出力します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-157">The **Error Return** functoid outputs a string containing error information if there are errors (such as connection failures) at run time.</span></span>  

  <span data-ttu-id="1c5da-158">前の例では、最初の入力パラメーターから取得されます、 **StoreID**フィールドは、入力方向の注文書、および残りの 3 つの入力パラメーターが定数で構成されている、**構成\<Functoid\> Functoid**の ダイアログ ボックス、**データベース検索**functoid。</span><span class="sxs-lookup"><span data-stu-id="1c5da-158">In the previous example, the first input parameter is taken from the **StoreID** field of the incoming purchase order, and the remaining three input parameters are constants configured in the **Configure \<Functoid\> Functoid** dialog box for the **Database Lookup** functoid.</span></span> <span data-ttu-id="1c5da-159">4 つの入力パラメーターすべての値を提供するために、送信元スキーマからのリンクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1c5da-159">It is possible to create links from the source schema to supply values for all four input parameters.</span></span>  

> [!NOTE]
>  * <span data-ttu-id="1c5da-160">など一部の Microsoft SQL Server データ型を使用することはできません**テキスト**、 **ntext**、および**イメージ**、参照値として、**データベース検索**functoid。</span><span class="sxs-lookup"><span data-stu-id="1c5da-160">You cannot use some Microsoft SQL Server data types, such as **text**, **ntext**, and **image**, as lookup values for the **Database Lookup** functoid.</span></span> <span data-ttu-id="1c5da-161">この Functoid には、テキスト文字列として表すことができるデータ型が必要です。</span><span class="sxs-lookup"><span data-stu-id="1c5da-161">The functoid requires data types that can be represented as a text string.</span></span>  
>
>  * <span data-ttu-id="1c5da-162">入力パラメーターに一致する 1 つ以上のレコードがあるかどうか、**データベース検索**functoid、**値抽出**functoid は、最初のレコードからのみデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-162">If there is more than one record matching the input parameters of the **Database Lookup** functoid, the **Value Extractor** functoid extracts data only from the first record.</span></span>  
>
>  * <span data-ttu-id="1c5da-163">接続文字列で NT 認証を使用して、パスワードを暗号化で保護します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-163">Use NT authentication in connection strings to protect passwords with encryption.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="1c5da-164">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="1c5da-164">Available functoids</span></span>  
 <span data-ttu-id="1c5da-165">**データベース**functoid には。</span><span class="sxs-lookup"><span data-stu-id="1c5da-165">The **Database** functoids are:</span></span> 

* <span data-ttu-id="1c5da-166">データベース検索</span><span class="sxs-lookup"><span data-stu-id="1c5da-166">Database Lookup</span></span>
* <span data-ttu-id="1c5da-167">エラー通知</span><span class="sxs-lookup"><span data-stu-id="1c5da-167">Error Return</span></span>
* <span data-ttu-id="1c5da-168">メッセージの書式設定</span><span class="sxs-lookup"><span data-stu-id="1c5da-168">Format Message</span></span>
* <span data-ttu-id="1c5da-169">アプリケーション ID の取得</span><span class="sxs-lookup"><span data-stu-id="1c5da-169">Get Application ID</span></span>
* <span data-ttu-id="1c5da-170">アプリケーション値の取得</span><span class="sxs-lookup"><span data-stu-id="1c5da-170">Get Application Value</span></span>
* <span data-ttu-id="1c5da-171">共通 ID の取得</span><span class="sxs-lookup"><span data-stu-id="1c5da-171">Get Common ID</span></span>
* <span data-ttu-id="1c5da-172">共通値の取得</span><span class="sxs-lookup"><span data-stu-id="1c5da-172">Get Common Value</span></span>
* <span data-ttu-id="1c5da-173">アプリケーション ID の削除</span><span class="sxs-lookup"><span data-stu-id="1c5da-173">Remove Application ID</span></span>
* <span data-ttu-id="1c5da-174">共通 ID の設定</span><span class="sxs-lookup"><span data-stu-id="1c5da-174">Set Common ID</span></span>
* <span data-ttu-id="1c5da-175">値抽出</span><span class="sxs-lookup"><span data-stu-id="1c5da-175">Value Extractor</span></span>

<span data-ttu-id="1c5da-176">これらの functiods について詳しくは、次を参照してください。、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1c5da-176">For more details on these functiods, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="1c5da-177">参照</span><span class="sxs-lookup"><span data-stu-id="1c5da-177">See Also</span></span>  
- [<span data-ttu-id="1c5da-178">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="1c5da-178">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="1c5da-179">**データベース Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1c5da-179">**Database Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

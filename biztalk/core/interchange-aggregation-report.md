---
title: インターチェンジの集計レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4619e8d0-9e9e-4d19-a67a-ac1058a0579b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8163506f3b71379038e8beb82bc8f9f2297249
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381946"
---
# <a name="interchange-aggregation-report"></a><span data-ttu-id="c6dab-102">インターチェンジの集計レポート</span><span class="sxs-lookup"><span data-stu-id="c6dab-102">Interchange Aggregation Report</span></span>
<span data-ttu-id="c6dab-103">このレポートは、同じ EDI エンコードの種類、送信者パーティ、受信者パーティ、および方向を共有する EDI インターチェンジの数を示す 1 つのレコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6dab-103">This report provides one record that indicates the number of EDI interchanges that share the same EDI encoding type, sender party, receiver party, and direction.</span></span> <span data-ttu-id="c6dab-104">このレポートでは、個別のインターチェンジの詳細は提供されません。</span><span class="sxs-lookup"><span data-stu-id="c6dab-104">This report does not provide details about the individual interchanges.</span></span>  
  
 <span data-ttu-id="c6dab-105">[グループ ハブ] ページの下部にインターチェンジの集計レポート リンクをクリックしてこの状態レポートを表示、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c6dab-105">This status report is displayed by clicking the Interchange Aggregation Report link at the bottom of the Group Hub page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="c6dab-106">状態レポート内のフィールド</span><span class="sxs-lookup"><span data-stu-id="c6dab-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="c6dab-107">インターチェンジの集計レポートには、各レコードに対して次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6dab-107">The Interchange Aggregation Report displays the following information for each record:</span></span>  
  
- <span data-ttu-id="c6dab-108">同じ EDI エンコードの種類、送信者パーティ、受信者パーティ、および方向を共有するインターチェンジの数のカウント</span><span class="sxs-lookup"><span data-stu-id="c6dab-108">A count of how many interchanges share the same EDI encoding type, sender party, receiver party, and direction</span></span>  
  
- <span data-ttu-id="c6dab-109">レコード内の各インターチェンジの送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="c6dab-109">The Sender Party for each interchange in the record</span></span>  
  
- <span data-ttu-id="c6dab-110">レコード内の各インターチェンジの受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="c6dab-110">The Receiver Party for each interchange in the record</span></span>  
  
- <span data-ttu-id="c6dab-111">方向 (受信または送信)、レコード内の各インターチェンジの</span><span class="sxs-lookup"><span data-stu-id="c6dab-111">The Direction (receive or send) of each interchange in the record</span></span>  
  
- <span data-ttu-id="c6dab-112">日付と時刻を時間の範囲内の最初のインターチェンジが送信または受信 (最も早い開始日付/時刻)</span><span class="sxs-lookup"><span data-stu-id="c6dab-112">The date and time at which the earliest interchange in the time range was sent or received (Earliest Started Date/Time)</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="c6dab-113">受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。</span><span class="sxs-lookup"><span data-stu-id="c6dab-113">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="c6dab-114">日付が 75 未満である場合は、20YY として表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6dab-114">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="c6dab-115">たとえば、インターチェンジを受信した場合を含む最も早い開始 ISA09 の値の日付/時刻は、11/13/1999 としてレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6dab-115">For example, if you receive an interchange that contains the value 991113 in ISA09, the Earliest Started Date/time will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="c6dab-116">日付と時刻を時間の範囲の最後のインターチェンジが送信または受信 (最新が終了した日付/時刻)</span><span class="sxs-lookup"><span data-stu-id="c6dab-116">The date and time at which the latest interchange in the time range was sent or received (Latest Ended Date/Time)</span></span>  
  
- <span data-ttu-id="c6dab-117">EDI エンコードのレコード内の各インターチェンジの種類</span><span class="sxs-lookup"><span data-stu-id="c6dab-117">The EDI encoding type for each interchange in the record</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="c6dab-118">状態レポートのクエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="c6dab-118">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="c6dab-119">表示されるデータを決定するクエリ式のフィールドを変更することで、インターチェンジの集計レポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c6dab-119">You can customize the Interchange Aggregation Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="c6dab-120">使用できるフィールドは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c6dab-120">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="c6dab-121">クエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="c6dab-121">Query Expression Field</span></span>|<span data-ttu-id="c6dab-122">有効な演算子</span><span class="sxs-lookup"><span data-stu-id="c6dab-122">Potential Operators</span></span>|<span data-ttu-id="c6dab-123">潜在的な値</span><span class="sxs-lookup"><span data-stu-id="c6dab-123">Potential Values</span></span>|<span data-ttu-id="c6dab-124">既定で含まれますか。</span><span class="sxs-lookup"><span data-stu-id="c6dab-124">Included By Default?</span></span>|  
|<span data-ttu-id="c6dab-125">検索</span><span class="sxs-lookup"><span data-stu-id="c6dab-125">Search for</span></span>|<span data-ttu-id="c6dab-126">[等しい]</span><span class="sxs-lookup"><span data-stu-id="c6dab-126">Equals</span></span>|<span data-ttu-id="c6dab-127">インターチェンジの集計レポート</span><span class="sxs-lookup"><span data-stu-id="c6dab-127">Interchange Aggregation Report</span></span>|<span data-ttu-id="c6dab-128">指定あり (必須)</span><span class="sxs-lookup"><span data-stu-id="c6dab-128">Yes (required)</span></span>|  
|<span data-ttu-id="c6dab-129">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="c6dab-129">Interchange Date Time</span></span>|<span data-ttu-id="c6dab-130">[以下]</span><span class="sxs-lookup"><span data-stu-id="c6dab-130">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="c6dab-131">[以上]</span><span class="sxs-lookup"><span data-stu-id="c6dab-131">Greater Than or Equals</span></span>|<span data-ttu-id="c6dab-132">特定の日時</span><span class="sxs-lookup"><span data-stu-id="c6dab-132">Specific Date Time</span></span><br /><br /> <span data-ttu-id="c6dab-133">[今日]</span><span class="sxs-lookup"><span data-stu-id="c6dab-133">Today</span></span><br /><br /> <span data-ttu-id="c6dab-134">昨日</span><span class="sxs-lookup"><span data-stu-id="c6dab-134">Today - 1</span></span>|<span data-ttu-id="c6dab-135">はい</span><span class="sxs-lookup"><span data-stu-id="c6dab-135">Yes</span></span><br /><br /> <span data-ttu-id="c6dab-136">注:1 回と、クエリ式に 2 回含めることができます-演算子、値が高い 1 回の演算子は、範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6dab-136">Note: Can be included twice in the query expression, once with a less-than operator and once with a greater-than operator, to provide a range.</span></span>|  
|<span data-ttu-id="c6dab-137">[最大一致数]</span><span class="sxs-lookup"><span data-stu-id="c6dab-137">Maximum Matches</span></span>|<span data-ttu-id="c6dab-138">[等しい]</span><span class="sxs-lookup"><span data-stu-id="c6dab-138">Equals</span></span>|<span data-ttu-id="c6dab-139">整数 (既定値 50)</span><span class="sxs-lookup"><span data-stu-id="c6dab-139">Integer (default of 50)</span></span>|<span data-ttu-id="c6dab-140">はい</span><span class="sxs-lookup"><span data-stu-id="c6dab-140">Yes</span></span>|  
|<span data-ttu-id="c6dab-141">Direction</span><span class="sxs-lookup"><span data-stu-id="c6dab-141">Direction</span></span>|<span data-ttu-id="c6dab-142">[等しい]</span><span class="sxs-lookup"><span data-stu-id="c6dab-142">Equals</span></span>|<span data-ttu-id="c6dab-143">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="c6dab-143">All (default)</span></span><br /><br /> <span data-ttu-id="c6dab-144">Receive</span><span class="sxs-lookup"><span data-stu-id="c6dab-144">Receive</span></span><br /><br /> <span data-ttu-id="c6dab-145">Send</span><span class="sxs-lookup"><span data-stu-id="c6dab-145">Send</span></span>|<span data-ttu-id="c6dab-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="c6dab-146">No</span></span>|  
|<span data-ttu-id="c6dab-147">受信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="c6dab-147">Receiver Party Name</span></span>|<span data-ttu-id="c6dab-148">[等しい]</span><span class="sxs-lookup"><span data-stu-id="c6dab-148">Equals</span></span>|<span data-ttu-id="c6dab-149">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="c6dab-149">All (default)</span></span><br /><br /> <span data-ttu-id="c6dab-150">特定のパーティ名 (AN 文字列)</span><span class="sxs-lookup"><span data-stu-id="c6dab-150">Specific party name (AN string)</span></span>|<span data-ttu-id="c6dab-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="c6dab-151">No</span></span>|  
|<span data-ttu-id="c6dab-152">送信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="c6dab-152">Sender Party Name</span></span>|<span data-ttu-id="c6dab-153">[等しい]</span><span class="sxs-lookup"><span data-stu-id="c6dab-153">Equals</span></span>|<span data-ttu-id="c6dab-154">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="c6dab-154">All (default)</span></span><br /><br /> <span data-ttu-id="c6dab-155">特定のパーティ名 (AN 文字列)</span><span class="sxs-lookup"><span data-stu-id="c6dab-155">Specific party name (AN string)</span></span>|<span data-ttu-id="c6dab-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="c6dab-156">No</span></span>|  
|<span data-ttu-id="c6dab-157">状態</span><span class="sxs-lookup"><span data-stu-id="c6dab-157">Status</span></span>|<span data-ttu-id="c6dab-158">[等しい]</span><span class="sxs-lookup"><span data-stu-id="c6dab-158">Equals</span></span><br /><br /> <span data-ttu-id="c6dab-159">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="c6dab-159">Not Equals</span></span>|<span data-ttu-id="c6dab-160">受理</span><span class="sxs-lookup"><span data-stu-id="c6dab-160">Accepted</span></span><br /><br /> <span data-ttu-id="c6dab-161">受理 (ただしエラーが発生)</span><span class="sxs-lookup"><span data-stu-id="c6dab-161">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="c6dab-162">送信済み</span><span class="sxs-lookup"><span data-stu-id="c6dab-162">Sent</span></span><br /><br /> <span data-ttu-id="c6dab-163">All</span><span class="sxs-lookup"><span data-stu-id="c6dab-163">All</span></span><br /><br /> <span data-ttu-id="c6dab-164">確認が必要</span><span class="sxs-lookup"><span data-stu-id="c6dab-164">Ack Expected</span></span><br /><br /> <span data-ttu-id="c6dab-165">確認は不要</span><span class="sxs-lookup"><span data-stu-id="c6dab-165">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="c6dab-166">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="c6dab-166">Rejected</span></span>|<span data-ttu-id="c6dab-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="c6dab-167">No</span></span>|
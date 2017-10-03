---
title: "インターチェンジの状態と確認の詳細の状態レポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebba4af5-6dff-4bb8-9c63-739ef49bbbb8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cc596a99d1a49b01ccc417abccb73d12ed34ad5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interchange-status-and-ack-details-status-report"></a><span data-ttu-id="03d52-102">インターチェンジの状態と確認の詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="03d52-102">Interchange Status and ACK Details Status Report</span></span>
<span data-ttu-id="03d52-103">この状態レポートには、インターチェンジの詳細と、関連するインターチェンジの (技術) 確認および機能確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03d52-103">This status report displays details of an interchange and its correlated interchange (technical) acknowledgment and functional acknowledgments.</span></span> <span data-ttu-id="03d52-104">インターチェンジ/確認の状態レポート内のインターチェンジを右クリックし、このレポートを表示する**インターチェンジの状態と確認の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="03d52-104">You display this report for right-clicking an interchange within the Interchange/ACK status report, and then clicking **Interchange status and ack details**.</span></span>  
  
 <span data-ttu-id="03d52-105">このレポートでは、インターチェンジと、関連する確認について、それぞれ別のビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="03d52-105">This report provides the following separate views for the interchange and the correlated acknowledgments:</span></span>  
  
## <a name="interchange-status"></a><span data-ttu-id="03d52-106">インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="03d52-106">Interchange Status</span></span>  
 <span data-ttu-id="03d52-107">このビューには、次のフィールドの値を示すテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="03d52-107">This view provides a table showing the values for the following fields:</span></span>  
  
-   <span data-ttu-id="03d52-108">送信者パーティ ID</span><span class="sxs-lookup"><span data-stu-id="03d52-108">Sender party ID</span></span>  
  
-   <span data-ttu-id="03d52-109">受信者パーティ ID</span><span class="sxs-lookup"><span data-stu-id="03d52-109">Receiver party ID</span></span>  
  
-   <span data-ttu-id="03d52-110">制御 ID</span><span class="sxs-lookup"><span data-stu-id="03d52-110">Control ID</span></span>  
  
-   <span data-ttu-id="03d52-111">受信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="03d52-111">Receiver party name</span></span>  
  
-   <span data-ttu-id="03d52-112">送信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="03d52-112">Sender party name</span></span>  
  
-   <span data-ttu-id="03d52-113">Direction</span><span class="sxs-lookup"><span data-stu-id="03d52-113">Direction</span></span>  
  
-   <span data-ttu-id="03d52-114">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="03d52-114">Interchange Date Time</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03d52-115">受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。</span><span class="sxs-lookup"><span data-stu-id="03d52-115">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="03d52-116">日付が 75 未満である場合は、20YY として表示されます。</span><span class="sxs-lookup"><span data-stu-id="03d52-116">If the date is less than 75, it will be displayed as 20YY.</span></span>  
    >   
    >  <span data-ttu-id="03d52-117">たとえば、ISA09 の値が 991113 であるインターチェンジを受信した場合、インターチェンジの日付は 11/13/1999 としてレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="03d52-117">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date will be listed in the report as 11/13/1999.</span></span>  
  
-   <span data-ttu-id="03d52-118">グループ数</span><span class="sxs-lookup"><span data-stu-id="03d52-118">Group count</span></span>  
  
-   <span data-ttu-id="03d52-119">ポート ID</span><span class="sxs-lookup"><span data-stu-id="03d52-119">Port ID</span></span>  
  
-   <span data-ttu-id="03d52-120">インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="03d52-120">Interchange Status</span></span>  
  
-   <span data-ttu-id="03d52-121">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="03d52-121">EDI encoding type</span></span>  
  
-   <span data-ttu-id="03d52-122">トランザクション セット関連付け ID</span><span class="sxs-lookup"><span data-stu-id="03d52-122">Transaction Set Correlation Id</span></span>  
  
 <span data-ttu-id="03d52-123">インターチェンジの受信者であるパーティに対して技術確認が有効になっている場合 ([EDI のプロパティ] ダイアログ ボックスの [確認の処理と検証の設定] ページ)、BizTalk Server は、送信したインターチェンジへの応答として技術 (インターチェンジ) 確認が返されることを要求します。</span><span class="sxs-lookup"><span data-stu-id="03d52-123">If a technical acknowledgment is enabled for a party as an interchange receiver (in the ACK Processing and Validation Settings page of the EDI Properties dialog box), BizTalk Server expects a technical (interchange) acknowledgment to be returned in response to an interchange that it sends.</span></span> <span data-ttu-id="03d52-124">送信インターチェンジのインターチェンジ状態エントリを最初に作成するとき、[インターチェンジの状態] フィールドには [確認が必要] が設定されます。</span><span class="sxs-lookup"><span data-stu-id="03d52-124">When it initially creates an interchange status entry for an outbound interchange, it will enter ACK Expected in the Interchange Status field.</span></span> <span data-ttu-id="03d52-125">技術確認を受信し、それを元のインターチェンジに関連付けると、[インターチェンジの状態] フィールドは確認を受信したことを示す内容に更新されます。</span><span class="sxs-lookup"><span data-stu-id="03d52-125">When it receives a technical acknowledgment and correlates it to the original interchange, it will update the Interchange Status field to indicate that it has received the acknowledgment.</span></span>  
  
## <a name="interchange-ack-status"></a><span data-ttu-id="03d52-126">インターチェンジ確認の状態</span><span class="sxs-lookup"><span data-stu-id="03d52-126">Interchange Ack Status</span></span>  
 <span data-ttu-id="03d52-127">このビューには、インターチェンジの (技術) 確認の状態の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03d52-127">This view displays status values for an interchange (technical) acknowledgment:</span></span>  
  
-   <span data-ttu-id="03d52-128">確認のインターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="03d52-128">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="03d52-129">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="03d52-129">Receiver party</span></span>  
  
-   <span data-ttu-id="03d52-130">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="03d52-130">Sender party</span></span>  
  
-   <span data-ttu-id="03d52-131">Direction</span><span class="sxs-lookup"><span data-stu-id="03d52-131">Direction</span></span>  
  
-   <span data-ttu-id="03d52-132">確認のインターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="03d52-132">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="03d52-133">確認のインターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="03d52-133">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="03d52-134">確認の状態</span><span class="sxs-lookup"><span data-stu-id="03d52-134">Ack Status</span></span>  
  
-   <span data-ttu-id="03d52-135">状態コード</span><span class="sxs-lookup"><span data-stu-id="03d52-135">Status Code</span></span>  
  
-   <span data-ttu-id="03d52-136">確認通知コード 1</span><span class="sxs-lookup"><span data-stu-id="03d52-136">Ack Note Code1</span></span>  
  
-   <span data-ttu-id="03d52-137">確認通知コード 2</span><span class="sxs-lookup"><span data-stu-id="03d52-137">Ack Note Code2</span></span>  
  
## <a name="functional-acks"></a><span data-ttu-id="03d52-138">[機能確認]</span><span class="sxs-lookup"><span data-stu-id="03d52-138">Functional Ack(s)</span></span>  
 <span data-ttu-id="03d52-139">このビューには、機能確認の状態の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03d52-139">This view displays status values for an functional acknowledgment:</span></span>  
  
-   <span data-ttu-id="03d52-140">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="03d52-140">Group Control Number</span></span>  
  
-   <span data-ttu-id="03d52-141">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="03d52-141">Receiver party</span></span>  
  
-   <span data-ttu-id="03d52-142">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="03d52-142">Sender party</span></span>  
  
-   <span data-ttu-id="03d52-143">Direction</span><span class="sxs-lookup"><span data-stu-id="03d52-143">Direction</span></span>  
  
-   <span data-ttu-id="03d52-144">[状態]</span><span class="sxs-lookup"><span data-stu-id="03d52-144">Status</span></span>  
  
-   <span data-ttu-id="03d52-145">状態コード</span><span class="sxs-lookup"><span data-stu-id="03d52-145">Status Code</span></span>  
  
-   <span data-ttu-id="03d52-146">機能 ID コード</span><span class="sxs-lookup"><span data-stu-id="03d52-146">Functional ID Code</span></span>  
  
-   <span data-ttu-id="03d52-147">トランザクション セット数</span><span class="sxs-lookup"><span data-stu-id="03d52-147">TS Count</span></span>  
  
-   <span data-ttu-id="03d52-148">確認のインターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="03d52-148">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="03d52-149">確認のインターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="03d52-149">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="03d52-150">確認のインターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="03d52-150">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="03d52-151">配信されたトランザクション セットの数</span><span class="sxs-lookup"><span data-stu-id="03d52-151">Delivered TS Count</span></span>  
  
-   <span data-ttu-id="03d52-152">受理されたトランザクション セットの数</span><span class="sxs-lookup"><span data-stu-id="03d52-152">Accepted TS Count</span></span>  
  
-   <span data-ttu-id="03d52-153">ErrorCode 1</span><span class="sxs-lookup"><span data-stu-id="03d52-153">ErrorCode 1</span></span>  
  
-   <span data-ttu-id="03d52-154">ErrorCode 2</span><span class="sxs-lookup"><span data-stu-id="03d52-154">ErrorCode 2</span></span>  
  
-   <span data-ttu-id="03d52-155">ErrorCode 3</span><span class="sxs-lookup"><span data-stu-id="03d52-155">ErrorCode 3</span></span>  
  
-   <span data-ttu-id="03d52-156">ErrorCode 4</span><span class="sxs-lookup"><span data-stu-id="03d52-156">ErrorCode 4</span></span>  
  
-   <span data-ttu-id="03d52-157">エラー コード 5</span><span class="sxs-lookup"><span data-stu-id="03d52-157">ErrorCode 5</span></span>  
  
-   <span data-ttu-id="03d52-158">受信された時刻</span><span class="sxs-lookup"><span data-stu-id="03d52-158">Time Received</span></span>
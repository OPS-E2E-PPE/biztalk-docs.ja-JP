---
title: インターチェンジの状態と確認の詳細ステータス レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebba4af5-6dff-4bb8-9c63-739ef49bbbb8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3201bc969bc053e9a128cbb0e65a42a2714480c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999027"
---
# <a name="interchange-status-and-ack-details-status-report"></a><span data-ttu-id="3046d-102">インターチェンジの状態と確認の詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="3046d-102">Interchange Status and ACK Details Status Report</span></span>
<span data-ttu-id="3046d-103">この状態レポートには、インターチェンジの詳細と、関連するインターチェンジの (技術) 確認および機能確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3046d-103">This status report displays details of an interchange and its correlated interchange (technical) acknowledgment and functional acknowledgments.</span></span> <span data-ttu-id="3046d-104">このレポートには、インターチェンジ/確認の状態レポート内のインターチェンジを右クリックして表示する**インターチェンジの状態と確認の詳細**します。</span><span class="sxs-lookup"><span data-stu-id="3046d-104">You display this report for right-clicking an interchange within the Interchange/ACK status report, and then clicking **Interchange status and ack details**.</span></span>  
  
 <span data-ttu-id="3046d-105">このレポートでは、インターチェンジと、関連する確認について、それぞれ別のビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3046d-105">This report provides the following separate views for the interchange and the correlated acknowledgments:</span></span>  
  
## <a name="interchange-status"></a><span data-ttu-id="3046d-106">インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="3046d-106">Interchange Status</span></span>  
 <span data-ttu-id="3046d-107">このビューには、次のフィールドの値を示すテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3046d-107">This view provides a table showing the values for the following fields:</span></span>  
  
- <span data-ttu-id="3046d-108">送信者パーティ ID</span><span class="sxs-lookup"><span data-stu-id="3046d-108">Sender party ID</span></span>  
  
- <span data-ttu-id="3046d-109">受信者パーティ ID</span><span class="sxs-lookup"><span data-stu-id="3046d-109">Receiver party ID</span></span>  
  
- <span data-ttu-id="3046d-110">制御 ID</span><span class="sxs-lookup"><span data-stu-id="3046d-110">Control ID</span></span>  
  
- <span data-ttu-id="3046d-111">受信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="3046d-111">Receiver party name</span></span>  
  
- <span data-ttu-id="3046d-112">送信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="3046d-112">Sender party name</span></span>  
  
- <span data-ttu-id="3046d-113">Direction</span><span class="sxs-lookup"><span data-stu-id="3046d-113">Direction</span></span>  
  
- <span data-ttu-id="3046d-114">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="3046d-114">Interchange Date Time</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3046d-115">受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。</span><span class="sxs-lookup"><span data-stu-id="3046d-115">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="3046d-116">日付が 75 未満である場合は、20YY として表示されます。</span><span class="sxs-lookup"><span data-stu-id="3046d-116">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="3046d-117">たとえば、ISA09 の値が 991113 であるインターチェンジを受信した場合、インターチェンジの日付は 11/13/1999 としてレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3046d-117">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="3046d-118">グループ数</span><span class="sxs-lookup"><span data-stu-id="3046d-118">Group count</span></span>  
  
- <span data-ttu-id="3046d-119">ポート ID</span><span class="sxs-lookup"><span data-stu-id="3046d-119">Port ID</span></span>  
  
- <span data-ttu-id="3046d-120">インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="3046d-120">Interchange Status</span></span>  
  
- <span data-ttu-id="3046d-121">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="3046d-121">EDI encoding type</span></span>  
  
- <span data-ttu-id="3046d-122">トランザクション セット関連付け ID</span><span class="sxs-lookup"><span data-stu-id="3046d-122">Transaction Set Correlation Id</span></span>  
  
  <span data-ttu-id="3046d-123">インターチェンジの受信者であるパーティに対して技術確認が有効になっている場合 ([EDI のプロパティ] ダイアログ ボックスの [確認の処理と検証の設定] ページ)、BizTalk Server は、送信したインターチェンジへの応答として技術 (インターチェンジ) 確認が返されることを要求します。</span><span class="sxs-lookup"><span data-stu-id="3046d-123">If a technical acknowledgment is enabled for a party as an interchange receiver (in the ACK Processing and Validation Settings page of the EDI Properties dialog box), BizTalk Server expects a technical (interchange) acknowledgment to be returned in response to an interchange that it sends.</span></span> <span data-ttu-id="3046d-124">送信インターチェンジのインターチェンジ状態エントリを最初に作成するとき、[インターチェンジの状態] フィールドには [確認が必要] が設定されます。</span><span class="sxs-lookup"><span data-stu-id="3046d-124">When it initially creates an interchange status entry for an outbound interchange, it will enter ACK Expected in the Interchange Status field.</span></span> <span data-ttu-id="3046d-125">技術確認を受信し、それを元のインターチェンジに関連付けると、[インターチェンジの状態] フィールドは確認を受信したことを示す内容に更新されます。</span><span class="sxs-lookup"><span data-stu-id="3046d-125">When it receives a technical acknowledgment and correlates it to the original interchange, it will update the Interchange Status field to indicate that it has received the acknowledgment.</span></span>  
  
## <a name="interchange-ack-status"></a><span data-ttu-id="3046d-126">インターチェンジ確認の状態</span><span class="sxs-lookup"><span data-stu-id="3046d-126">Interchange Ack Status</span></span>  
 <span data-ttu-id="3046d-127">このビューには、インターチェンジの (技術) 確認の状態の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3046d-127">This view displays status values for an interchange (technical) acknowledgment:</span></span>  
  
-   <span data-ttu-id="3046d-128">確認のインターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="3046d-128">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="3046d-129">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="3046d-129">Receiver party</span></span>  
  
-   <span data-ttu-id="3046d-130">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="3046d-130">Sender party</span></span>  
  
-   <span data-ttu-id="3046d-131">Direction</span><span class="sxs-lookup"><span data-stu-id="3046d-131">Direction</span></span>  
  
-   <span data-ttu-id="3046d-132">確認のインターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="3046d-132">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="3046d-133">確認のインターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="3046d-133">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="3046d-134">確認の状態</span><span class="sxs-lookup"><span data-stu-id="3046d-134">Ack Status</span></span>  
  
-   <span data-ttu-id="3046d-135">状態コード</span><span class="sxs-lookup"><span data-stu-id="3046d-135">Status Code</span></span>  
  
-   <span data-ttu-id="3046d-136">確認通知コード 1</span><span class="sxs-lookup"><span data-stu-id="3046d-136">Ack Note Code1</span></span>  
  
-   <span data-ttu-id="3046d-137">確認通知コード 2</span><span class="sxs-lookup"><span data-stu-id="3046d-137">Ack Note Code2</span></span>  
  
## <a name="functional-acks"></a><span data-ttu-id="3046d-138">[機能確認]</span><span class="sxs-lookup"><span data-stu-id="3046d-138">Functional Ack(s)</span></span>  
 <span data-ttu-id="3046d-139">このビューには、機能確認の状態の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3046d-139">This view displays status values for an functional acknowledgment:</span></span>  
  
-   <span data-ttu-id="3046d-140">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="3046d-140">Group Control Number</span></span>  
  
-   <span data-ttu-id="3046d-141">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="3046d-141">Receiver party</span></span>  
  
-   <span data-ttu-id="3046d-142">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="3046d-142">Sender party</span></span>  
  
-   <span data-ttu-id="3046d-143">Direction</span><span class="sxs-lookup"><span data-stu-id="3046d-143">Direction</span></span>  
  
-   <span data-ttu-id="3046d-144">状態</span><span class="sxs-lookup"><span data-stu-id="3046d-144">Status</span></span>  
  
-   <span data-ttu-id="3046d-145">状態コード</span><span class="sxs-lookup"><span data-stu-id="3046d-145">Status Code</span></span>  
  
-   <span data-ttu-id="3046d-146">機能 ID コード</span><span class="sxs-lookup"><span data-stu-id="3046d-146">Functional ID Code</span></span>  
  
-   <span data-ttu-id="3046d-147">トランザクション セット数</span><span class="sxs-lookup"><span data-stu-id="3046d-147">TS Count</span></span>  
  
-   <span data-ttu-id="3046d-148">確認のインターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="3046d-148">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="3046d-149">確認のインターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="3046d-149">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="3046d-150">確認のインターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="3046d-150">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="3046d-151">配信されたトランザクション セットの数</span><span class="sxs-lookup"><span data-stu-id="3046d-151">Delivered TS Count</span></span>  
  
-   <span data-ttu-id="3046d-152">受理されたトランザクション セットの数</span><span class="sxs-lookup"><span data-stu-id="3046d-152">Accepted TS Count</span></span>  
  
-   <span data-ttu-id="3046d-153">ErrorCode 1</span><span class="sxs-lookup"><span data-stu-id="3046d-153">ErrorCode 1</span></span>  
  
-   <span data-ttu-id="3046d-154">エラー コード 2</span><span class="sxs-lookup"><span data-stu-id="3046d-154">ErrorCode 2</span></span>  
  
-   <span data-ttu-id="3046d-155">エラー コード 3</span><span class="sxs-lookup"><span data-stu-id="3046d-155">ErrorCode 3</span></span>  
  
-   <span data-ttu-id="3046d-156">エラー コード 4</span><span class="sxs-lookup"><span data-stu-id="3046d-156">ErrorCode 4</span></span>  
  
-   <span data-ttu-id="3046d-157">エラー コード 5</span><span class="sxs-lookup"><span data-stu-id="3046d-157">ErrorCode 5</span></span>  
  
-   <span data-ttu-id="3046d-158">受信時刻</span><span class="sxs-lookup"><span data-stu-id="3046d-158">Time Received</span></span>
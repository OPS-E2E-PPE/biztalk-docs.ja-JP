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
ms.openlocfilehash: 167162a47516279c22bd250589246b3dbd12f109
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381930"
---
# <a name="interchange-status-and-ack-details-status-report"></a><span data-ttu-id="efce6-102">インターチェンジの状態と確認の詳細ステータス レポート</span><span class="sxs-lookup"><span data-stu-id="efce6-102">Interchange Status and ACK Details Status Report</span></span>
<span data-ttu-id="efce6-103">この状態レポートには、インターチェンジとその関連するインターチェンジの (技術) 確認と機能確認の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efce6-103">This status report displays details of an interchange and its correlated interchange (technical) acknowledgment and functional acknowledgments.</span></span> <span data-ttu-id="efce6-104">このレポートには、インターチェンジ/確認の状態レポート内のインターチェンジを右クリックして表示する**インターチェンジの状態と確認の詳細**します。</span><span class="sxs-lookup"><span data-stu-id="efce6-104">You display this report for right-clicking an interchange within the Interchange/ACK status report, and then clicking **Interchange status and ack details**.</span></span>  
  
 <span data-ttu-id="efce6-105">このレポートは、インターチェンジと関連する確認をそれぞれ別のビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="efce6-105">This report provides the following separate views for the interchange and the correlated acknowledgments:</span></span>  
  
## <a name="interchange-status"></a><span data-ttu-id="efce6-106">インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="efce6-106">Interchange Status</span></span>  
 <span data-ttu-id="efce6-107">このビューは、次のフィールドの値を示すテーブルを提供します。</span><span class="sxs-lookup"><span data-stu-id="efce6-107">This view provides a table showing the values for the following fields:</span></span>  
  
- <span data-ttu-id="efce6-108">送信者パーティ ID</span><span class="sxs-lookup"><span data-stu-id="efce6-108">Sender party ID</span></span>  
  
- <span data-ttu-id="efce6-109">受信者パーティ ID</span><span class="sxs-lookup"><span data-stu-id="efce6-109">Receiver party ID</span></span>  
  
- <span data-ttu-id="efce6-110">制御 ID</span><span class="sxs-lookup"><span data-stu-id="efce6-110">Control ID</span></span>  
  
- <span data-ttu-id="efce6-111">受信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="efce6-111">Receiver party name</span></span>  
  
- <span data-ttu-id="efce6-112">送信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="efce6-112">Sender party name</span></span>  
  
- <span data-ttu-id="efce6-113">Direction</span><span class="sxs-lookup"><span data-stu-id="efce6-113">Direction</span></span>  
  
- <span data-ttu-id="efce6-114">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="efce6-114">Interchange Date Time</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="efce6-115">受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。</span><span class="sxs-lookup"><span data-stu-id="efce6-115">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="efce6-116">日付が 75 未満である場合は、20YY として表示されます。</span><span class="sxs-lookup"><span data-stu-id="efce6-116">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="efce6-117">たとえば、ISA09 の値が 991113 でインターチェンジを受信する場合そのインターチェンジ日付は 11/13/1999 としてで、レポートに表示します。</span><span class="sxs-lookup"><span data-stu-id="efce6-117">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="efce6-118">グループ数</span><span class="sxs-lookup"><span data-stu-id="efce6-118">Group count</span></span>  
  
- <span data-ttu-id="efce6-119">ポート ID</span><span class="sxs-lookup"><span data-stu-id="efce6-119">Port ID</span></span>  
  
- <span data-ttu-id="efce6-120">インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="efce6-120">Interchange Status</span></span>  
  
- <span data-ttu-id="efce6-121">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="efce6-121">EDI encoding type</span></span>  
  
- <span data-ttu-id="efce6-122">トランザクション セット関連付け ID</span><span class="sxs-lookup"><span data-stu-id="efce6-122">Transaction Set Correlation Id</span></span>  
  
  <span data-ttu-id="efce6-123">BizTalk Server への応答で返される技術 (インターチェンジ) 確認が必要ですが (EDI のプロパティ ダイアログ ボックスの 確認の処理と検証の設定 ページ) のインターチェンジ受信者としてのパーティで技術確認を有効にする場合、送信インターチェンジの場合。</span><span class="sxs-lookup"><span data-stu-id="efce6-123">If a technical acknowledgment is enabled for a party as an interchange receiver (in the ACK Processing and Validation Settings page of the EDI Properties dialog box), BizTalk Server expects a technical (interchange) acknowledgment to be returned in response to an interchange that it sends.</span></span> <span data-ttu-id="efce6-124">最初に、送信インターチェンジのインターチェンジ状態エントリを作成するときに確認が必要インターチェンジの状態 フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="efce6-124">When it initially creates an interchange status entry for an outbound interchange, it will enter ACK Expected in the Interchange Status field.</span></span> <span data-ttu-id="efce6-125">技術確認を受信し、元のインターチェンジに関連していることを示す受信確認を受信したインターチェンジの状態フィールド更新されます。</span><span class="sxs-lookup"><span data-stu-id="efce6-125">When it receives a technical acknowledgment and correlates it to the original interchange, it will update the Interchange Status field to indicate that it has received the acknowledgment.</span></span>  
  
## <a name="interchange-ack-status"></a><span data-ttu-id="efce6-126">インターチェンジ確認の状態</span><span class="sxs-lookup"><span data-stu-id="efce6-126">Interchange Ack Status</span></span>  
 <span data-ttu-id="efce6-127">このビューには、インターチェンジの (技術) 確認の状態の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efce6-127">This view displays status values for an interchange (technical) acknowledgment:</span></span>  
  
-   <span data-ttu-id="efce6-128">確認のインターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="efce6-128">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="efce6-129">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="efce6-129">Receiver party</span></span>  
  
-   <span data-ttu-id="efce6-130">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="efce6-130">Sender party</span></span>  
  
-   <span data-ttu-id="efce6-131">Direction</span><span class="sxs-lookup"><span data-stu-id="efce6-131">Direction</span></span>  
  
-   <span data-ttu-id="efce6-132">確認のインターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="efce6-132">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="efce6-133">確認のインターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="efce6-133">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="efce6-134">Ack の状態</span><span class="sxs-lookup"><span data-stu-id="efce6-134">Ack Status</span></span>  
  
-   <span data-ttu-id="efce6-135">状態コード</span><span class="sxs-lookup"><span data-stu-id="efce6-135">Status Code</span></span>  
  
-   <span data-ttu-id="efce6-136">確認通知コード 1</span><span class="sxs-lookup"><span data-stu-id="efce6-136">Ack Note Code1</span></span>  
  
-   <span data-ttu-id="efce6-137">確認通知コード 2</span><span class="sxs-lookup"><span data-stu-id="efce6-137">Ack Note Code2</span></span>  
  
## <a name="functional-acks"></a><span data-ttu-id="efce6-138">[機能確認]</span><span class="sxs-lookup"><span data-stu-id="efce6-138">Functional Ack(s)</span></span>  
 <span data-ttu-id="efce6-139">このビューには、機能確認の状態の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efce6-139">This view displays status values for an functional acknowledgment:</span></span>  
  
-   <span data-ttu-id="efce6-140">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="efce6-140">Group Control Number</span></span>  
  
-   <span data-ttu-id="efce6-141">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="efce6-141">Receiver party</span></span>  
  
-   <span data-ttu-id="efce6-142">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="efce6-142">Sender party</span></span>  
  
-   <span data-ttu-id="efce6-143">Direction</span><span class="sxs-lookup"><span data-stu-id="efce6-143">Direction</span></span>  
  
-   <span data-ttu-id="efce6-144">状態</span><span class="sxs-lookup"><span data-stu-id="efce6-144">Status</span></span>  
  
-   <span data-ttu-id="efce6-145">状態コード</span><span class="sxs-lookup"><span data-stu-id="efce6-145">Status Code</span></span>  
  
-   <span data-ttu-id="efce6-146">機能 ID コード</span><span class="sxs-lookup"><span data-stu-id="efce6-146">Functional ID Code</span></span>  
  
-   <span data-ttu-id="efce6-147">トランザクション セットの数</span><span class="sxs-lookup"><span data-stu-id="efce6-147">TS Count</span></span>  
  
-   <span data-ttu-id="efce6-148">確認のインターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="efce6-148">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="efce6-149">確認のインターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="efce6-149">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="efce6-150">確認のインターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="efce6-150">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="efce6-151">配信されたトランザクション セットの数</span><span class="sxs-lookup"><span data-stu-id="efce6-151">Delivered TS Count</span></span>  
  
-   <span data-ttu-id="efce6-152">受理されたトランザクション セット数</span><span class="sxs-lookup"><span data-stu-id="efce6-152">Accepted TS Count</span></span>  
  
-   <span data-ttu-id="efce6-153">エラー コード 1</span><span class="sxs-lookup"><span data-stu-id="efce6-153">ErrorCode 1</span></span>  
  
-   <span data-ttu-id="efce6-154">エラー コード 2</span><span class="sxs-lookup"><span data-stu-id="efce6-154">ErrorCode 2</span></span>  
  
-   <span data-ttu-id="efce6-155">エラー コード 3</span><span class="sxs-lookup"><span data-stu-id="efce6-155">ErrorCode 3</span></span>  
  
-   <span data-ttu-id="efce6-156">エラー コード 4</span><span class="sxs-lookup"><span data-stu-id="efce6-156">ErrorCode 4</span></span>  
  
-   <span data-ttu-id="efce6-157">エラー コード 5</span><span class="sxs-lookup"><span data-stu-id="efce6-157">ErrorCode 5</span></span>  
  
-   <span data-ttu-id="efce6-158">受信時刻</span><span class="sxs-lookup"><span data-stu-id="efce6-158">Time Received</span></span>
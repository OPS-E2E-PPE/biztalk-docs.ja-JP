---
title: AS2 状態レポート用に格納されているデータ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6aa4077-3768-436b-99b9-d203a86a7e69
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f14fc95dfba5e29089653ef02dddd1b0b366ff8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012517"
---
# <a name="data-stored-for-as2-status-reports"></a><span data-ttu-id="cad58-102">AS2 状態レポート用に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="cad58-102">Data Stored for AS2 Status Reports</span></span>
<span data-ttu-id="cad58-103">レポートの 2 つのレベルが AS2 状態レポートで使用可能: 最初の場合、**レポートを有効にする**、アグリーメントのプロパティが選択されている (から、**全般プロパティ**のページ、**全般**  タブで、**アグリーメントのプロパティ** ダイアログ ボックス)、アグリーメントに対して否認不可データベース ストレージのプロパティが選択されている場合、もう 1 つ。</span><span class="sxs-lookup"><span data-stu-id="cad58-103">Two levels of reporting are available in AS2 status reporting: the first if the **Turn ON Reporting** property is selected for an agreement (from the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box), and the second if a non-repudiation database storage property is selected for an agreement.</span></span>  
  
## <a name="data-stored-if-as2-reporting-is-activated"></a><span data-ttu-id="cad58-104">AS2 レポートがアクティブになっている場合に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="cad58-104">Data Stored If AS2 Reporting Is Activated</span></span>  
 <span data-ttu-id="cad58-105">場合、**レポートを有効にする**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信されるすべてのレコードを受信した AS2 メッセージおよび Mdn が保持されます。</span><span class="sxs-lookup"><span data-stu-id="cad58-105">If the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will keep a record of all sent or received AS2 messages and MDNs.</span></span>  
  
 <span data-ttu-id="cad58-106">受信した AS2 メッセージについては、BizTalk Server は次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="cad58-106">For a received AS2 message, BizTalk Server will store the following information:</span></span>  
  
- <span data-ttu-id="cad58-107">AS2 メッセージのレコード</span><span class="sxs-lookup"><span data-stu-id="cad58-107">A record of the AS2 message.</span></span>  
  
  <span data-ttu-id="cad58-108">受信または送信した MDN (同期または非同期) については、BizTalk Server は次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="cad58-108">For a received or sent MDN (synchronous or asynchronous), BizTalk Server will store the following information:</span></span>  
  
- <span data-ttu-id="cad58-109">MDN のレコード</span><span class="sxs-lookup"><span data-stu-id="cad58-109">A record of the MDN.</span></span>  
  
  <span data-ttu-id="cad58-110">状態レポート UI により、AS2 メッセージ レコードを適切な MDN レコードに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="cad58-110">The status reporting UI enables correlation of the AS2 message record to the appropriate MDN record.</span></span>  
  
## <a name="data-stored-if-resend-as2-message-if-mdn-not-received-is-enabled"></a><span data-ttu-id="cad58-111">"MDN を受信しない場合は AS2 メッセージを再送信する" が有効になっている場合に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="cad58-111">Data Stored If Resend AS2 Message If MDN Not Received Is Enabled</span></span>  
 <span data-ttu-id="cad58-112">場合、 **MDN を受信しない場合は再送信 AS2 メッセージ**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="cad58-112">If the **Resend AS2 message if MDN not received** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will record the following information:</span></span>  
  
-   <span data-ttu-id="cad58-113">各再送信の時刻</span><span class="sxs-lookup"><span data-stu-id="cad58-113">Time of each resend attempt</span></span>  
  
-   <span data-ttu-id="cad58-114">各再送信の状態</span><span class="sxs-lookup"><span data-stu-id="cad58-114">Status of each resend attempt</span></span>  
  
-   <span data-ttu-id="cad58-115">各再送信のインデックス</span><span class="sxs-lookup"><span data-stu-id="cad58-115">Index of each resend attempt</span></span>  
  
## <a name="data-stored-if-non-repudiation-database-storage-is-enabled"></a><span data-ttu-id="cad58-116">否認不可データベース ストレージが有効になっている場合に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="cad58-116">Data Stored If Non-Repudiation Database Storage Is Enabled</span></span>  
 <span data-ttu-id="cad58-117">否認不可データベース ストレージは、次のアグリーメントのプロパティが選択されている場合に有効になります。</span><span class="sxs-lookup"><span data-stu-id="cad58-117">Non-repudiation database storage is enabled by the following agreement properties is selected:</span></span>  
  
- <span data-ttu-id="cad58-118">エンコードされた送信 AS2 メッセージに対して有効な NRR</span><span class="sxs-lookup"><span data-stu-id="cad58-118">NRR enabled for outbound encoded AS2 messages</span></span>  
  
- <span data-ttu-id="cad58-119">デコードされた送信 AS2 メッセージに対して有効な NRR</span><span class="sxs-lookup"><span data-stu-id="cad58-119">NRR enabled for outbound decoded AS2 messages</span></span>  
  
- <span data-ttu-id="cad58-120">受信 MDN に対して有効な NRR</span><span class="sxs-lookup"><span data-stu-id="cad58-120">NRR enabled for inbound MDN</span></span>  
  
- <span data-ttu-id="cad58-121">エンコードされた受信 AS2 メッセージに対して有効な NRR</span><span class="sxs-lookup"><span data-stu-id="cad58-121">NRR enabled for inbound encoded AS2 messages</span></span>  
  
- <span data-ttu-id="cad58-122">デコードされた受信 AS2 メッセージに対して有効な NRR</span><span class="sxs-lookup"><span data-stu-id="cad58-122">NRR enabled for inbound decoded AS2 messages</span></span>  
  
- <span data-ttu-id="cad58-123">送信 MDN に対して有効な NRR</span><span class="sxs-lookup"><span data-stu-id="cad58-123">NRR enabled for outbound MDN</span></span>  
  
  <span data-ttu-id="cad58-124">上記のうち、1 つ以上のプロパティが選択されていると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="cad58-124">If one or more of the above properties is selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the following information:</span></span>  
  
- <span data-ttu-id="cad58-125">すべての AS2 メッセージのコンテンツ、およびすべての MDN のコンテンツ (AS2 ヘッダーの有無にかかわらず)</span><span class="sxs-lookup"><span data-stu-id="cad58-125">The content of any AS2 message and the content of any MDN (with or without AS2 headers).</span></span>  
  
## <a name="data-stored-for-edi-over-as2"></a><span data-ttu-id="cad58-126">EDI Over AS2 に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="cad58-126">Data Stored For EDI Over AS2</span></span>  
 <span data-ttu-id="cad58-127">場合、**レポートを有効にする**プロパティには、EDI アグリーメントと AS2 アグリーメントの両方が選択されているし、EDI メッセージ レコードの AS2 メッセージ レコード (EDI ペイロードを含む) を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="cad58-127">If the **Turn ON Reporting** property is selected both for an EDI agreement as well as an AS2 agreement, then you can correlate an AS2 message record (containing EDI payload) with an EDI message record.</span></span>  
  
 <span data-ttu-id="cad58-128">トランザクション セットの格納が有効になっている場合は、状態レポート UI にトランザクション セットの詳細と AS2 メッセージ コンテンツの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cad58-128">If transaction set storage is enabled, you can display transaction set details and AS2 message content details in the status reporting UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cad58-129">これらのレポートにアクセスするには、AS2EdiReceive または AS2EdiSend パイプラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cad58-129">You must use the AS2EdiReceive or AS2EdiSend pipeline to have access to these reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad58-130">参照</span><span class="sxs-lookup"><span data-stu-id="cad58-130">See Also</span></span>  
 <span data-ttu-id="cad58-131">[EDI および AS2 状態レポートの格納データ](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="cad58-131">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="cad58-132">[EDI 状態レポート用に格納されているデータ](../core/data-stored-for-edi-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="cad58-132">[Data Stored for EDI Status Reports](../core/data-stored-for-edi-status-reports.md) </span></span>  
 [<span data-ttu-id="cad58-133">バッチの状態レポート用に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="cad58-133">Data Stored for Batching Status Reports</span></span>](../core/data-stored-for-batching-status-reports.md)
---
title: BAM Api を使用した際の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd8ccf63-6989-4ad6-a193-cf3043e9a466
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4962849a8596316cced7d02a130266528506a22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354725"
---
# <a name="considerations-for-working-with-bam-apis"></a><span data-ttu-id="114b2-102">BAM API を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="114b2-102">Considerations for Working with BAM APIs</span></span>
<span data-ttu-id="114b2-103">DirectEventStream、BufferedEventStream、MessagingEventStream、OrchestrationEventStream などの "Microsoft.BizTalk.Bam.EventObservation.EventStream" オブジェクトを使用する場合、BAM では、協定世界時 (UTC) 形式 (グリニッジ標準時とも呼ばれます) で自動的に記録されたマイルストーンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="114b2-103">When using an  "Microsoft.BizTalk.Bam.EventObservation.EventStream" object, such as DirectEventStream, BufferedEventStream, MessagingEventStream, or OrchestrationEventStream, BAM captures milestones such that they are automatically recorded in Coordinated Universal Time (UTC) format (this is also referred to as Greenwich Mean Time).</span></span> <span data-ttu-id="114b2-104">API を使用して BAM に日時を送信する場合、日時は UTC 形式に変換されず、送信どおりの形式で受信されます。</span><span class="sxs-lookup"><span data-stu-id="114b2-104">When you send date/times to BAM using the APIs they are received in the format sent with no conversion to UTC format.</span></span> <span data-ttu-id="114b2-105">BAM ソリューションを開発する場合は、次の注意事項を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="114b2-105">You should take the following considerations into account when you are developing your BAM solutions:</span></span>  
  
- <span data-ttu-id="114b2-106">BizTalk Server で追跡されるデータは UTC 形式で受信されます。</span><span class="sxs-lookup"><span data-stu-id="114b2-106">Data traced from BizTalk Server is received in UTC format.</span></span> <span data-ttu-id="114b2-107">このデータは、イベント ストリームから取得した他のデータと一貫性がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="114b2-107">This could be inconsistent with other data that comes from the event stream.</span></span>  
  
- <span data-ttu-id="114b2-108">イベント ストリーム API を使用して、日時の追跡データをローカル時刻形式で指定すると、BAM データのすべての時刻は UTC 形式であることが求められるため、BAM ポータルのデータが正しくなくなります。</span><span class="sxs-lookup"><span data-stu-id="114b2-108">If you use the event stream APIs to provide date and time tracking data in local time format, the data in the BAM portal will be incorrect as the expectation is that all times in BAM data are in UTC format.</span></span>  
  
  <span data-ttu-id="114b2-109">現在アップグレード中の既存のアプリケーションがローカル時刻を使用しているときに、BAM ポータルを使用することを計画する場合、データを変更して UTC 形式に準拠させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="114b2-109">If you have existing applications that use local time, and you are now upgrading and planning to use the BAM portal, you must modify your data to make it conform to UTC format.</span></span> <span data-ttu-id="114b2-110">同様に、カスタム アプリケーションも変更して、UTC 形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="114b2-110">You also need to modify your custom application to convert to UTC format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114b2-111">参照</span><span class="sxs-lookup"><span data-stu-id="114b2-111">See Also</span></span>  
 [<span data-ttu-id="114b2-112">BAM ソリューションを実装します。</span><span class="sxs-lookup"><span data-stu-id="114b2-112">Implementing BAM Solutions</span></span>](../core/implementing-bam-solutions.md)
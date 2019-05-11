---
title: BizTalk Framework アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component]
ms.assetid: 116dff8d-b7f8-4564-a7fb-6440682683dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 139d4bedbe8f42e9e7c97b2647b27d712697e8f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358075"
---
# <a name="biztalk-framework-assembler-pipeline-component"></a><span data-ttu-id="7df99-102">BizTalk Framework アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7df99-102">BizTalk Framework Assembler Pipeline Component</span></span>
<span data-ttu-id="7df99-103">BizTalk Framework は正確に行うための 1 つの方法の 1 回 HTTP や SMTP などのネットワーク上のトランスポート プロトコルを使用して配信を保証します。</span><span class="sxs-lookup"><span data-stu-id="7df99-103">The BizTalk Framework is one approach for doing exactly-once guaranteed delivery using over-the-wire transport protocols such as HTTP or SMTP.</span></span> <span data-ttu-id="7df99-104">このフレームワークは 1998 年から存在して、保留中の標準的なイニシアチブ前段階としてという考えに基づいて Web サービス、特に WSReliable します。</span><span class="sxs-lookup"><span data-stu-id="7df99-104">This framework has existed since 1998, and can be thought of as a precursor to pending standards initiatives based on Web services, specifically WSReliable.</span></span> <span data-ttu-id="7df99-105">問題は通常、正確に保証-メッセージ キュー (MSMQ とも呼ばれます) などのテクノロジのドメインをデータの配信が行われたとします。</span><span class="sxs-lookup"><span data-stu-id="7df99-105">Typically, the problem of guaranteed exactly-once delivery of data has been the domain of technologies like Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="7df99-106">ただし、このようなテクノロジは、通常は、データ フローの 2 つのエンドポイントでの一般的なソフトウェアを必要し、もアドレス オープンなトランスポート プロトコルの使用に何も操作を行いますに基づいてパブリック ネットワークでは、たとえば、データを使用してエンタープライズの境界間のフローをインターネットです。</span><span class="sxs-lookup"><span data-stu-id="7df99-106">However, such technologies usually require common software at the two endpoints of a data flow, and also do nothing to address the use of open transport protocols based on public networks, for example, data that flows across enterprise boundaries by using the Internet.</span></span>  
  
 <span data-ttu-id="7df99-107">当然ながら、BizTalk Framework の一部を実装のこの問題を解決するために以前に試行に存在するのと同じメカニズム保証が正確に、データの 1 回だけ配信します。</span><span class="sxs-lookup"><span data-stu-id="7df99-107">Not surprisingly, the BizTalk Framework implements some of the same mechanisms present in earlier attempts to solve this problem of guaranteed exactly-once delivery of data.</span></span> <span data-ttu-id="7df99-108">問題を他のソリューションの良い例では、電子データ交換 (EDI)、ANSI X12 制御番号と標準的な 997 機能確認ドキュメント フォーム データを 1 回だけ受信されると、送信者であることを保証の基礎受信側で発生した問題の通知。</span><span class="sxs-lookup"><span data-stu-id="7df99-108">A good example of other solutions to the problem is electronic data interchange (EDI), where ANSI X12 control numbers and standard 997 functional acknowledgment documents form the basis of guaranteeing that data is received only one time, and that the sender is notified of any problems on the receiving end.</span></span>  
  
 <span data-ttu-id="7df99-109">BizTalk Framework での BizTalk Framework プロトコル要件を理解、両方のデータを取引先システム、ただし異なる。</span><span class="sxs-lookup"><span data-stu-id="7df99-109">The BizTalk Framework assumes that, however disparate the systems trading data, they both understand the BizTalk Framework protocol requirements of:</span></span>  
  
- <span data-ttu-id="7df99-110">予測可能なエンベロープ形式を使用して転送をラップします。</span><span class="sxs-lookup"><span data-stu-id="7df99-110">Using a predictable envelope format for wrapping transmissions.</span></span>  
  
- <span data-ttu-id="7df99-111">グローバルに一意の識別子を持つ各送信転送をタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="7df99-111">Tagging every outbound transmission with a globally unique identifier.</span></span>  
  
- <span data-ttu-id="7df99-112">済みのデータの場合でも、グローバルに一意の識別子を含む受信確認を送信者に常に返す受信、受信確認、および処理します。</span><span class="sxs-lookup"><span data-stu-id="7df99-112">Always returning to the sender an acknowledgment of receipt that includes the globally unique identifier, even for data already received, acknowledged, and processed.</span></span>  
  
- <span data-ttu-id="7df99-113">何らかの手段を送信者がこれを超える、転送が有効な送信、受信側から受信確認が到着するか、または一定の期間に渡すまでを繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="7df99-113">Some means by which the sender can repeat transmission until either a receipt arrives from the receiver, or some time period passes beyond which the transmission is no longer valid.</span></span>  
  
  <span data-ttu-id="7df99-114">BizTalk Framework アセンブラー パイプライン コンポーネントは、送信および受信確認が、指定した時間に到着しないことを再送信する前に、BizTalk Framework エンベロープとコンテンツをメッセージのシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="7df99-114">The BizTalk Framework Assembler pipeline component is responsible for serializing the BizTalk Framework envelope and contents onto the message before transmission and resending in the event that a receipt does not arrive in the allotted time period.</span></span> <span data-ttu-id="7df99-115">受信し、配信確認メッセージを処理およびメッセージ インスタンスを削除する責任を負いますもできます。</span><span class="sxs-lookup"><span data-stu-id="7df99-115">It is also responsible for receiving and processing the receipts and deleting the message instance.</span></span> <span data-ttu-id="7df99-116">(送信メッセージのメッセージ インスタンスのコピーは、BizTalk が宛先から受信確認を受け取るまでに、メッセージ ボックス データベースに保持されます。</span><span class="sxs-lookup"><span data-stu-id="7df99-116">(A copy of the message instance of the sent message is kept in the MessageBox database until BizTalk receives a confirmation receipt from the destination.</span></span> <span data-ttu-id="7df99-117">確認メッセージが受信した後、メッセージ インスタンスは削除、メッセージング エンジンによって。)</span><span class="sxs-lookup"><span data-stu-id="7df99-117">After the confirmation receipt is received, the message instance is deleted by the Messaging Engine.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df99-118">参照</span><span class="sxs-lookup"><span data-stu-id="7df99-118">See Also</span></span>  
 <span data-ttu-id="7df99-119">[BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="7df99-119">[How to Configure the BizTalk Framework Assembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="7df99-120">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7df99-120">Pipeline Components</span></span>](../core/pipeline-components.md)
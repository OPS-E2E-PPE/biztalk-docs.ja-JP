---
title: BizTalk Framework アセンブラー パイプライン コンポーネント |Microsoft ドキュメント
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
ms.openlocfilehash: 777e3d98ade5b4e0c54744cea6d37b1e43717e66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231106"
---
# <a name="biztalk-framework-assembler-pipeline-component"></a><span data-ttu-id="776b6-102">BizTalk Framework アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="776b6-102">BizTalk Framework Assembler Pipeline Component</span></span>
<span data-ttu-id="776b6-103">BizTalk Framework は、HTTP または SMTP などの、回線上で使用できるトランスポート プロトコルを使用して、1 回限りの確実な配信を行うための方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="776b6-103">The BizTalk Framework is one approach for doing exactly-once guaranteed delivery using over-the-wire transport protocols such as HTTP or SMTP.</span></span> <span data-ttu-id="776b6-104">このフレームワークは 1998 年から存在し、Web サービス (特に WSReliable) に基づいた、標準的なイニシアチブの先駆けと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="776b6-104">This framework has existed since 1998, and can be thought of as a precursor to pending standards initiatives based on Web services, specifically WSReliable.</span></span> <span data-ttu-id="776b6-105">一般的に、1 回限りの確実なデータ配信の問題点は、メッセージ キュー (MSMQ とも呼ばれる) のようなテクノロジに関するものでした。</span><span class="sxs-lookup"><span data-stu-id="776b6-105">Typically, the problem of guaranteed exactly-once delivery of data has been the domain of technologies like Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="776b6-106">通常、このようなテクノロジでは、データ フローの両端のエンドポイントに共通のソフトウェアが必要となります。また、インターネットによる企業間のデータ通信などで必要となる、パブリック ネットワークに基づいたオープンなトランスポート プロトコルも使用できません。</span><span class="sxs-lookup"><span data-stu-id="776b6-106">However, such technologies usually require common software at the two endpoints of a data flow, and also do nothing to address the use of open transport protocols based on public networks, for example, data that flows across enterprise boundaries by using the Internet.</span></span>  
  
 <span data-ttu-id="776b6-107">BizTalk Framework には、1 回限りの確実なデータ配信に関する問題を解決するためのメカニズムがいくつか実装されています。これらのメカニズムは、問題解決のために以前に試行されたことのあるメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="776b6-107">Not surprisingly, the BizTalk Framework implements some of the same mechanisms present in earlier attempts to solve this problem of guaranteed exactly-once delivery of data.</span></span> <span data-ttu-id="776b6-108">また、このような問題に対するソリューションの一例として、電子データ交換 (EDI) があります。これは、ANSI X12 制御番号と標準的な 997 の機能確認ドキュメントが基盤となっており、データの 1 回限りの受信、および受信側で発生した問題が送信側に通知されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="776b6-108">A good example of other solutions to the problem is electronic data interchange (EDI), where ANSI X12 control numbers and standard 997 functional acknowledgment documents form the basis of guaranteeing that data is received only one time, and that the sender is notified of any problems on the receiving end.</span></span>  
  
 <span data-ttu-id="776b6-109">ただし、BizTalk Framework では、データを交換するシステムが異なっていても、両方のシステムで BizTalk Framework プロトコルの次の要件を認識できることが前提となっています。</span><span class="sxs-lookup"><span data-stu-id="776b6-109">The BizTalk Framework assumes that, however disparate the systems trading data, they both understand the BizTalk Framework protocol requirements of:</span></span>  
  
-   <span data-ttu-id="776b6-110">転送をラップするための予測可能なエンベロープ形式の使用。</span><span class="sxs-lookup"><span data-stu-id="776b6-110">Using a predictable envelope format for wrapping transmissions.</span></span>  
  
-   <span data-ttu-id="776b6-111">グローバル一意識別子による各送信転送へのタグ付け。</span><span class="sxs-lookup"><span data-stu-id="776b6-111">Tagging every outbound transmission with a globally unique identifier.</span></span>  
  
-   <span data-ttu-id="776b6-112">既に受信したデータ、確認したデータ、および処理されたデータに対しても、グローバル一意識別子を含む受信確認が送信側に必ず返されること。</span><span class="sxs-lookup"><span data-stu-id="776b6-112">Always returning to the sender an acknowledgment of receipt that includes the globally unique identifier, even for data already received, acknowledged, and processed.</span></span>  
  
-   <span data-ttu-id="776b6-113">受信側からの確認メッセージを受け取るか、転送が無効とされる一定の期間が経過するまで、送信側が転送を繰り返す何らかの方法があること。</span><span class="sxs-lookup"><span data-stu-id="776b6-113">Some means by which the sender can repeat transmission until either a receipt arrives from the receiver, or some time period passes beyond which the transmission is no longer valid.</span></span>  
  
 <span data-ttu-id="776b6-114">BizTalk Framework アセンブラー パイプライン コンポーネントは、転送前に BizTalk Framework のエンベロープとコンテンツをメッセージにシリアル化し、指定した時間内に確認メッセージが配信されない場合はメッセージを再送信する役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="776b6-114">The BizTalk Framework Assembler pipeline component is responsible for serializing the BizTalk Framework envelope and contents onto the message before transmission and resending in the event that a receipt does not arrive in the allotted time period.</span></span> <span data-ttu-id="776b6-115">また、確認メッセージを受信および処理して、メッセージ インスタンスを削除します </span><span class="sxs-lookup"><span data-stu-id="776b6-115">It is also responsible for receiving and processing the receipts and deleting the message instance.</span></span> <span data-ttu-id="776b6-116">(送信メッセージのメッセージ インスタンスのコピーは、BizTalk が送信先から確認メッセージを受け取るまで、メッセージ ボックス データベース内に保存されます。</span><span class="sxs-lookup"><span data-stu-id="776b6-116">(A copy of the message instance of the sent message is kept in the MessageBox database until BizTalk receives a confirmation receipt from the destination.</span></span> <span data-ttu-id="776b6-117">確認メッセージを受け取ると、メッセージング エンジンによってメッセージ インスタンスが削除されます)。</span><span class="sxs-lookup"><span data-stu-id="776b6-117">After the confirmation receipt is received, the message instance is deleted by the Messaging Engine.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776b6-118">参照</span><span class="sxs-lookup"><span data-stu-id="776b6-118">See Also</span></span>  
 <span data-ttu-id="776b6-119">[BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="776b6-119">[How to Configure the BizTalk Framework Assembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="776b6-120">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="776b6-120">Pipeline Components</span></span>](../core/pipeline-components.md)
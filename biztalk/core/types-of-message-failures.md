---
title: メッセージ エラーの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transformation stage
- assembly stage
- errors, disassembly stage
- errors, assembly stage
- routing, errors
- errors, transformation stage
- errors, messages [HAT]
- errors, routing
- disassembly stage, errors
- messages, errors [HAT]
ms.assetid: 3a8e1c58-4b53-4439-837d-aaa233eb9158
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c72db5870f89525a6a0db5f88a54bbe2db3f24
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268807"
---
# <a name="types-of-message-failures"></a><span data-ttu-id="275e2-102">メッセージ エラーの種類</span><span class="sxs-lookup"><span data-stu-id="275e2-102">Types of Message Failures</span></span>
<span data-ttu-id="275e2-103">このトピックでは、メッセージ エラーが発生する可能性のあるさまざまな状況を示します。</span><span class="sxs-lookup"><span data-stu-id="275e2-103">This topic lists different points where a message failure may occur.</span></span>  
  
 <span data-ttu-id="275e2-104">**逆アセンブリ フェーズでのエラー**</span><span class="sxs-lookup"><span data-stu-id="275e2-104">**Failures in the disassembly phase**</span></span>  
  
 <span data-ttu-id="275e2-105">処理は逆アセンブリ フェーズでも失敗することがあります。つまり、いずれかのパイプライン コンポーネントでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="275e2-105">Processing might also fail during the disassembly phase; that is, failure in one of the pipeline components.</span></span> <span data-ttu-id="275e2-106">たとえば、処理サーバーに解読証明書がないことが原因で解読に失敗したり、スキーマやメッセージに問題があることが原因で解析が失敗したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="275e2-106">For example, decryption failed due to absence of decryption cert on the processing server, or parsing failure due to problem either in the schema or in the message.</span></span>  
  
 <span data-ttu-id="275e2-107">**ルーティングでのエラー**</span><span class="sxs-lookup"><span data-stu-id="275e2-107">**Failures in routing**</span></span>  
  
 <span data-ttu-id="275e2-108">メッセージが正常に逆アセンブルされた後、次にエラーが発生する可能性のある処理はルーティングです。たとえば、ユーザーがオーケストレーションの対応する受信場所を有効にしたにもかかわらず、オーケストレーションに参加させるのを忘れた場合などが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="275e2-108">After a message disassembles successfully, the next potential failure point is routing; for example, users enable a corresponding receive location of an orchestration and forget to enlist the orchestration.</span></span> <span data-ttu-id="275e2-109">この場合、受信場所から取得したメッセージはルーティングに失敗し、メッセージ ボックス データベースによってルーティング エラー報告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="275e2-109">In this case, the message picked up from the receive location fails routing and the MessageBox database generates a Routing Failure report.</span></span>  
  
 <span data-ttu-id="275e2-110">ルーティング エラー報告は、再開不可の保留メッセージとして BizTalk Server 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="275e2-110">Routing Failure reports are listed in the BizTalk Server Administration Console as non-resumable suspended messages.</span></span> <span data-ttu-id="275e2-111">各ルーティング エラー報告には、ルーティング エラーの発生時に作成された、メッセージ プロパティのスナップショットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="275e2-111">Each Routing Failure report contains a message property snap shot taken when the routing failure occurred.</span></span> <span data-ttu-id="275e2-112">各エラー報告に示されている情報を使用して、関連メッセージのルーティングが失敗した原因を判断できます。</span><span class="sxs-lookup"><span data-stu-id="275e2-112">You can use the information in each report to determine why routing failed for its associated message.</span></span> <span data-ttu-id="275e2-113">関連メッセージが再開可能である場合は、ルーティングの問題を修正し、メッセージを再開して、処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="275e2-113">If the associated message is resumable, you can correct the routing problem and resume the message so that processing continues.</span></span> <span data-ttu-id="275e2-114">サービス名とサービスの種類が空白の状態でルーティング エラー報告が結果一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="275e2-114">Routing Failure reports are listed in the results list with a blank service name and service type.</span></span> <span data-ttu-id="275e2-115">中断されているインスタンスを終了すると、既定では毎分実行される Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb ジョブによって、そのインスタンスに関連付けられているルーティング エラー報告が自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="275e2-115">When you terminate a suspended instance, the Routing Failure report associated with the suspended instance is automatically deleted by the Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job that runs every minute by default.</span></span> <span data-ttu-id="275e2-116">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb ジョブの詳細については、次を参照してください。[データベース構造とジョブ](../core/database-structure-and-jobs.md)します。</span><span class="sxs-lookup"><span data-stu-id="275e2-116">For more information about the Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job, see [Database Structure and Jobs](../core/database-structure-and-jobs.md).</span></span>  
  
 <span data-ttu-id="275e2-117">**変換フェーズ中にエラー**</span><span class="sxs-lookup"><span data-stu-id="275e2-117">**Failures during the transformation phase**</span></span>  
  
- <span data-ttu-id="275e2-118">**メッセージを受信した**します。</span><span class="sxs-lookup"><span data-stu-id="275e2-118">**Received Messages**.</span></span> <span data-ttu-id="275e2-119">メッセージは受信場所からの受信時に、逆アセンブル (解読や解析など) されます。受信ポートに指定された受信マップによって、必要に応じて異なる形式に変換された後、オーケストレーションや送信ポートにルーティングするためにメッセージ ボックスにパブリッシュされます。</span><span class="sxs-lookup"><span data-stu-id="275e2-119">When a message is received from Receive Location, the message is disassembled (for example, decrypted and parsed), the message might optionally be transformed to a different format via an Inbound Map specified on a receive Port, and published to the MessageBox for routing to an orchestration or a Send Port.</span></span> <span data-ttu-id="275e2-120">この場合、受信マップが正しくないか、スキーマまたは受信したメッセージに問題があることが原因で、変換フェーズ中に処理が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="275e2-120">In this case, processing may fail during transformation phase due to incorrect Inbound Map, or problems in the schema or in the message received.</span></span>  
  
- <span data-ttu-id="275e2-121">**メッセージを送信する**します。</span><span class="sxs-lookup"><span data-stu-id="275e2-121">**Sent Messages**.</span></span> <span data-ttu-id="275e2-122">メッセージは送信場所への送信時に、送信ポートに構成されている送信マップによって、必要に応じて変換されます。</span><span class="sxs-lookup"><span data-stu-id="275e2-122">When a message is to be sent to a Send Location, an Outbound Map configured on Send Port might optionally transform the message.</span></span> <span data-ttu-id="275e2-123">変換後のメッセージはアセンブルされ、最後に送信場所への送信を行うアダプターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="275e2-123">Then the transformed message is assembled and handed to the adapter for final transmission to the Send Location.</span></span> <span data-ttu-id="275e2-124">この場合、送信マップが正しくないか、スキーマまたは送信元メッセージに問題があることが原因で、変換フェーズ中に処理が失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="275e2-124">In this case, processing may fail during transformation phase due to incorrect Outbound Map or problem in schema or source message.</span></span>  
  
  <span data-ttu-id="275e2-125">**メッセージのアセンブリ フェーズでのエラー**</span><span class="sxs-lookup"><span data-stu-id="275e2-125">**Failures in the message assembly phase**</span></span>  
  
  <span data-ttu-id="275e2-126">メッセージのアセンブリ フェーズでもエラーが発生する場合があります。つまり、パイプライン コンポーネントでエラーが発生するということです。</span><span class="sxs-lookup"><span data-stu-id="275e2-126">Processing can also fail during message assembly phase – in other words, failing in pipeline component.</span></span> <span data-ttu-id="275e2-127">メッセージが正常にアセンブルされたら、次にエラーが発生する可能性のある処理は、送信場所への送信です。たとえば、(パートナーに属している) 送信場所がダウンしていたり存在しない場合にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="275e2-127">After a message successfully assembles, the next potential failure point becomes transmission to Send Location; for example, the Send Location (which belongs to the partner) might be down or not exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275e2-128">参照</span><span class="sxs-lookup"><span data-stu-id="275e2-128">See Also</span></span>  
 [<span data-ttu-id="275e2-129">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="275e2-129">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)
---
title: 例外を収集し、修復と再送信のメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a61658a-0bac-4802-b506-02e61a3d2a9b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e76164a26e1dfd227d7fea79cfa8106825f25d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302139"
---
# <a name="collecting-exceptions-and-routing-messages-for-repair-and-resubmit"></a><span data-ttu-id="12629-102">例外を収集し、修復と再送信のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="12629-102">Collecting Exceptions and Routing Messages for Repair and Resubmit</span></span>
<span data-ttu-id="12629-103">このユース ケースで、カスタム例外ハンドラーが Web サービス経由で受信したエラー メッセージを取得しに含まれている InfoPath テンプレートを使用した互換性のある形式でディスク ファイルにルーティング、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="12629-103">In this use case, a custom exception handler picks up a fault message received through a Web service and routes it to a disk file in a format compatible with an InfoPath template included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="12629-104">ユーザーは Microsoft InfoPath を使用してファイルを開き、メッセージの内容を編集および図 1 に示すように、処理には、メッセージを再実行してください。</span><span class="sxs-lookup"><span data-stu-id="12629-104">The user can open the file using Microsoft InfoPath, edit the message contents, and resubmit the message for processing, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="12629-105">![例外の修復を収集](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3 CollectingExceptionsRepair")</span><span class="sxs-lookup"><span data-stu-id="12629-105">![Collecting Exceptions Repair](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3-CollectingExceptionsRepair")</span></span>  
  
 <span data-ttu-id="12629-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="12629-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="12629-107">**修復と再送信メッセージのルーティング**</span><span class="sxs-lookup"><span data-stu-id="12629-107">**Routing a message for repair and resubmission**</span></span>  
  
 <span data-ttu-id="12629-108">含まれている修復と再送信のカスタム例外ハンドラーのサンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="12629-108">The Repair and Resubmit Custom Exception Handler sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="12629-109">オーケストレーションでのプロセスが検出した場合、エラー、例外ハンドラーで、オーケストレーションを生成、ESB エラー メッセージがパブリッシュされます。</span><span class="sxs-lookup"><span data-stu-id="12629-109">When a process in an orchestration encounters an error, the exception handler in that orchestration generates and publishes an ESB fault message.</span></span> <span data-ttu-id="12629-110">このエラー メッセージが含まれている、ペイロードでメッセージ (BizTalk Server に関連すると、コンテキスト プロパティを含む)"インフライト"であった場合、例外が発生したし、BizTalk オーケストレーション エンジンによって現在の例外がキャッチされました。</span><span class="sxs-lookup"><span data-stu-id="12629-110">This fault message includes, in its payload, the messages (including their context properties that are related to BizTalk Server) that were "in flight" when the exception occurred, and the current exception caught by the BizTalk Orchestration engine.</span></span> <span data-ttu-id="12629-111">サブスクライブするオーケストレーション (カスタム例外ハンドラー) を抽出し、インフライトのメッセージと、システム例外オブジェクトを検査し、元のファイルのフォルダーにインフライトのメッセージをルーティングするキューから取り出された ESB のエラー メッセージがパブリッシュされた後、ユーザーは、InfoPath を使用してメッセージを編集し、処理の BizTalk Server に再送信します。</span><span class="sxs-lookup"><span data-stu-id="12629-111">After an ESB fault message is published, it is de-queued to a subscribing orchestration (a custom exception handler) that extracts and inspects the in-flight messages and the system exception object, and routes the in-flight messages to a file folder, from which a user can edit the message using InfoPath and resubmit it to BizTalk Server for processing.</span></span>  
  
 <span data-ttu-id="12629-112">詳細については、次を参照してください。[修復と再送信のカスタム例外ハンドラーのサンプルを実行する](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="12629-112">For more information, see [Running the Repair and Resubmit Custom Exception Handler Sample](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md).</span></span>
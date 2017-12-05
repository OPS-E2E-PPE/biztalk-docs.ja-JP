---
title: "経由でメッセージの受信場所と InfoPath フォームを送信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4589649be79ce369f0e6756ae7f96615d4a36c0f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a><span data-ttu-id="61a2a-102">経由して送信メッセージの受信場所と InfoPath フォーム</span><span class="sxs-lookup"><span data-stu-id="61a2a-102">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>
<span data-ttu-id="61a2a-103">受信場所への発信メッセージを受信する[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="61a2a-103">Receive locations receive messages for submission into [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] applications.</span></span> <span data-ttu-id="61a2a-104">定義することが指定されたトランスポート プロトコルを使用してメッセージを受信するように構成する物理エンドポイントとしての受信場所。</span><span class="sxs-lookup"><span data-stu-id="61a2a-104">You can define receive locations as physical endpoints configured to receive messages using a specified transport protocol.</span></span> <span data-ttu-id="61a2a-105">たとえば、ファイル トランスポートを使用して、特定のファイル システム フォルダーにドロップされた受信ファイルを受信場所を構成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61a2a-105">For example, a receive location may be configured to receive files dropped to a particular file system folder using the FILE transport.</span></span>  
  
 <span data-ttu-id="61a2a-106">作成する受信場所を論理的にグループ化し、管理する受信ポートの受信場所。</span><span class="sxs-lookup"><span data-stu-id="61a2a-106">You create receive locations for receive ports that logically group and manage receive locations.</span></span> <span data-ttu-id="61a2a-107">各受信場所に対しては、その特定の受信場所で受信したメッセージの実際の処理 (デコード、逆アセンブル、検証、およびなど) を受信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="61a2a-107">For each receive location you specify a receive pipeline, which does the actual processing (decoding, disassembly, validation, and so on) of messages received at that particular receive location.</span></span> <span data-ttu-id="61a2a-108">A4SWIFT のバインドの受信場所を受信する受信場所を論理的にグループ化し、管理するポート。</span><span class="sxs-lookup"><span data-stu-id="61a2a-108">A4SWIFT binds receive locations to receive ports that logically group and manage receive locations.</span></span>  
  
 <span data-ttu-id="61a2a-109">受信場所を介して A4SWIFT アプリケーションに SWIFT メッセージを送信するに、メッセージ、構成されている受信場所にドロップした、SWIFT の逆アセンブラーを使用して、受信パイプラインによって処理されるを解析し、SWIFT 逆アセンブラーによって検証し、メッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="61a2a-109">To submit a SWIFT message into an A4SWIFT application through a receive location, the message must be dropped to a configured receive location, processed by a receive pipeline using the SWIFT disassembler, parsed and validated by the SWIFT disassembler, and published to the MessageBox database.</span></span> <span data-ttu-id="61a2a-110">メッセージがメッセージ ボックス データベースへ発行されると、A4SWIFT アプリケーションの他のコンポーネントは、追加の処理 (サブスクリプションを使用して) メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="61a2a-110">After messages are published to the MessageBox database, other components in your A4SWIFT application retrieve the messages (using subscriptions) for additional processing.</span></span> <span data-ttu-id="61a2a-111">たとえば、最終的なルーティングの送信ポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="61a2a-111">For example, you can use send ports for final routing.</span></span>  
  
 <span data-ttu-id="61a2a-112">作成と構成の詳細については受信ポートと受信場所、BizTalk Server ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61a2a-112">For more information about creating and configuring receive ports and receive locations, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="61a2a-113">経由で新しいメッセージを送信することも、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、Message Repair and New Submission の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="61a2a-113">You can also submit a new message through an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, using the Message Repair and New Submission feature.</span></span> <span data-ttu-id="61a2a-114">これを行うには、開く、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR サイト内のフォルダーからそのメッセージの形式です。</span><span class="sxs-lookup"><span data-stu-id="61a2a-114">To do so, you open the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form for that message from a folder in the MRSR site.</span></span> <span data-ttu-id="61a2a-115">内のデータを入力する、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、証明書を使用して署名し、して送信します。</span><span class="sxs-lookup"><span data-stu-id="61a2a-115">You fill in the data in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, sign it using your certificate, and then submit it.</span></span> <span data-ttu-id="61a2a-116">Message Repair and New Submission のオーケストレーションは、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="61a2a-116">The Message Repair and New Submission orchestration processes the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a2a-117">参照</span><span class="sxs-lookup"><span data-stu-id="61a2a-117">See Also</span></span>  
 [<span data-ttu-id="61a2a-118">BizTalk Accelerator for SWIFT ランタイム</span><span class="sxs-lookup"><span data-stu-id="61a2a-118">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)
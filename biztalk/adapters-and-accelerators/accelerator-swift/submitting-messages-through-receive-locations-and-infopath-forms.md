---
title: 経由でメッセージの受信場所と InfoPath フォームの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebf95acf08084f7382e166efdace182a4464178c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377011"
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a><span data-ttu-id="91918-102">経由して送信メッセージの受信場所と InfoPath フォーム</span><span class="sxs-lookup"><span data-stu-id="91918-102">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>
<span data-ttu-id="91918-103">受信場所に送信するメッセージを受信する[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="91918-103">Receive locations receive messages for submission into [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] applications.</span></span> <span data-ttu-id="91918-104">定義することが指定されたトランスポート プロトコルを使用してメッセージを受信するように構成する物理エンドポイントとしての受信場所。</span><span class="sxs-lookup"><span data-stu-id="91918-104">You can define receive locations as physical endpoints configured to receive messages using a specified transport protocol.</span></span> <span data-ttu-id="91918-105">たとえば、受信場所は、ファイル トランスポートを使用して、特定のファイル システム フォルダーにドロップされた受信ファイルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="91918-105">For example, a receive location may be configured to receive files dropped to a particular file system folder using the FILE transport.</span></span>  
  
 <span data-ttu-id="91918-106">作成する受信場所を論理的にグループ化し、管理する受信ポートの受信場所。</span><span class="sxs-lookup"><span data-stu-id="91918-106">You create receive locations for receive ports that logically group and manage receive locations.</span></span> <span data-ttu-id="91918-107">各受信場所の受信パイプラインで、その特定の受信場所で受信したメッセージの実際の処理 (デコード、逆アセンブル、検証、およびなど) を指定します。</span><span class="sxs-lookup"><span data-stu-id="91918-107">For each receive location you specify a receive pipeline, which does the actual processing (decoding, disassembly, validation, and so on) of messages received at that particular receive location.</span></span> <span data-ttu-id="91918-108">A4SWIFT のバインドを受信する場所を受信する受信場所を論理的にグループ化して管理されるポート。</span><span class="sxs-lookup"><span data-stu-id="91918-108">A4SWIFT binds receive locations to receive ports that logically group and manage receive locations.</span></span>  
  
 <span data-ttu-id="91918-109">A4SWIFT 受信場所を使用してアプリケーションに SWIFT メッセージを送信するメッセージ構成されている受信場所にドロップ、SWIFT 逆アセンブラーを使用して受信パイプラインによって処理されるを解析し、SWIFT 逆アセンブラーによって検証し、メッセージ ボックス データベースに発行されます。</span><span class="sxs-lookup"><span data-stu-id="91918-109">To submit a SWIFT message into an A4SWIFT application through a receive location, the message must be dropped to a configured receive location, processed by a receive pipeline using the SWIFT disassembler, parsed and validated by the SWIFT disassembler, and published to the MessageBox database.</span></span> <span data-ttu-id="91918-110">メッセージがメッセージ ボックス データベースにパブリッシュされた後、A4SWIFT アプリケーションでは、その他のコンポーネントは、追加の処理 (サブスクリプションを使用して) メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="91918-110">After messages are published to the MessageBox database, other components in your A4SWIFT application retrieve the messages (using subscriptions) for additional processing.</span></span> <span data-ttu-id="91918-111">たとえば、最終的なルーティングの送信ポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="91918-111">For example, you can use send ports for final routing.</span></span>  
  
 <span data-ttu-id="91918-112">作成と構成の詳細については受信ポートと受信場所、BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91918-112">For more information about creating and configuring receive ports and receive locations, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="91918-113">新しいメッセージを送信することもできます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームの Message Repair and New Submission の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="91918-113">You can also submit a new message through an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, using the Message Repair and New Submission feature.</span></span> <span data-ttu-id="91918-114">これを行うには、開く、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR サイト内のフォルダーからそのメッセージの形式。</span><span class="sxs-lookup"><span data-stu-id="91918-114">To do so, you open the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form for that message from a folder in the MRSR site.</span></span> <span data-ttu-id="91918-115">データを格納する、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム、証明書を使用してサインインし、それを送信します。</span><span class="sxs-lookup"><span data-stu-id="91918-115">You fill in the data in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, sign it using your certificate, and then submit it.</span></span> <span data-ttu-id="91918-116">Message Repair and New Submission のオーケストレーションは、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="91918-116">The Message Repair and New Submission orchestration processes the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91918-117">参照</span><span class="sxs-lookup"><span data-stu-id="91918-117">See Also</span></span>  
 [<span data-ttu-id="91918-118">BizTalk Accelerator for SWIFT ランタイム</span><span class="sxs-lookup"><span data-stu-id="91918-118">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)
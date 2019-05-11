---
title: 受信 AS2 メッセージのアグリーメントの解決 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 746d01af-de6a-4d5d-9433-b0e1a2b41861
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf569721a2a97aeb93b8b753599c64ae0ef890ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359874"
---
# <a name="agreement-resolution-for-incoming-as2-messages"></a><span data-ttu-id="d0882-102">受信 AS2 メッセージのアグリーメントの解決</span><span class="sxs-lookup"><span data-stu-id="d0882-102">Agreement Resolution for Incoming AS2 Messages</span></span>
<span data-ttu-id="d0882-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、EDIINT/AS2 でエンコードされたメッセージを HTTP/HTTPS トランスポート経由で受信すると、メッセージを送信した取引先のビジネス プロファイルの特定を試みます。</span><span class="sxs-lookup"><span data-stu-id="d0882-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDIINT/AS2-encoded message over HTTP/HTTPS transport, it attempts to determine the trading partner’s business profile that sent the message.</span></span> <span data-ttu-id="d0882-104">これは、次の処理を順番に試みることによって行われます。</span><span class="sxs-lookup"><span data-stu-id="d0882-104">It does so by attempting to do the following (in the order shown):</span></span>  
  
1. <span data-ttu-id="d0882-105">AS2 間との照合-の値を持つ受信メッセージのメッセージ ヘッダーから**AS2-から**で、**識別子**一方向の AS2 アグリーメントのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d0882-105">Make a match between the AS2-From header in the incoming message with the value for **AS2-From** in the **Identifiers** page of the one-way AS2 agreement in the **Agreement Properties** dialog box.</span></span>  
  
2. <span data-ttu-id="d0882-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でアグリーメントを特定できない場合は、受信メッセージに設定されている AS2-From コンテキスト プロパティと取引先名を照合します。</span><span class="sxs-lookup"><span data-stu-id="d0882-106">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement, it will attempt to match the AS2-From context property that is set for the incoming message with the name of a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0882-107">AS2-From ヘッダーには ASCII 文字しか含めることができないため、取引先名および AS2-From エイリアスにも ASCII 文字のみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0882-107">Since the AS2-From header can only contain ASCII characters, you must ensure that your trading partner name and the AS2-From alias also contain only ASCII characters.</span></span> <span data-ttu-id="d0882-108">完全に一致しない場合、BizTalk では着信メッセージのヘッダーに基づいてアグリーメントを特定できません。</span><span class="sxs-lookup"><span data-stu-id="d0882-108">If an exact match does not occur, BizTalk will be unable to determine the agreement based on the incoming message headers.</span></span>  
  
 <span data-ttu-id="d0882-109">AS2 受信パイプラインは、アグリーメントが特定された場合にのみメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d0882-109">The AS2 receive pipeline will process the message only if an agreement is determined.</span></span> <span data-ttu-id="d0882-110">EDI 処理とは異なり、アグリーメントを特定できない場合に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が使用できるフォールバック AS2 プロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="d0882-110">Unlike in EDI processing, there are no fallback AS2 properties that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can use if it cannot determine the agreement.</span></span>  
  
 <span data-ttu-id="d0882-111">設定を確認は、パイプラインでは、アグリーメントを特定した後、**アグリーメントの代わりにメッセージ ヘッダーの検証および MDN の設定を使用して、** プロパティ、**検証**一方向の AS2 のページアグリーメント、**アグリーメント設定** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d0882-111">Once the pipeline has determined the agreement, it will check the setting of the **Use agreement settings for validation and MDN instead message header** property in the **Validation** page of the one-way AS2 agreement in the **Agreement Settings** dialog box.</span></span> <span data-ttu-id="d0882-112">このプロパティがオンになっている場合、受信パイプラインはアグリーメント プロパティを使用してメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d0882-112">If that property is checked, the receive pipeline will use the agreement properties to process the message.</span></span> <span data-ttu-id="d0882-113">このプロパティがオフになっている場合、受信パイプラインはメッセージの AS2 ヘッダーの値を使用してメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d0882-113">If the property is cleared, the receive pipeline will use the values in the AS2 header of the message to process it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0882-114">アグリーメントの解決時に決定される AS2 アグリーメントは、EDI ペイロードと同じアグリーメントにならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0882-114">The AS2 agreement that is determined during agreement resolution may not be the same agreement as the EDI payload.</span></span> <span data-ttu-id="d0882-115">AS2 アグリーメントは、複数のパーティから EDI ドキュメントをルーティングするクリアリングハウスを表す場合があるので、AS2 と EDI が同じアグリーメントを共有する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d0882-115">There is no requirement that AS2 and EDI must share the same agreement, as the AS2 agreement may represent a clearinghouse that routes EDI documents from multiple parties.</span></span>  
  
 <span data-ttu-id="d0882-116">受信処理の詳細については、次を参照してください。[受信 AS2 メッセージの処理](../core/processing-an-incoming-as2-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0882-116">For more details on the receive process, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0882-117">参照</span><span class="sxs-lookup"><span data-stu-id="d0882-117">See Also</span></span>  
 [<span data-ttu-id="d0882-118">BizTalk Server が AS2 メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="d0882-118">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)
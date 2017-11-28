---
title: "MLLP の受信し、送信コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab82aa317b205d62b8bd05aff513e80d406b658b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mllp-receive-and-send-components"></a><span data-ttu-id="f4fa5-102">MLLP の受信し、送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f4fa5-102">MLLP Receive and Send Components</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="f4fa5-103">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) すべてサポート[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ネイティブ アダプターの種類、ファイル、HTTP、SQL では、FTP などです。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports all [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] native adapter types, including File, HTTP, SQL, and FTP.</span></span> <span data-ttu-id="f4fa5-104">HL7 でエンコードされたメッセージの受信と送信、ただし、通常使用する MLLP アダプター。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-104">For HL7-encoded message receiving and sending, however, you typically use the MLLP adapter.</span></span> <span data-ttu-id="f4fa5-105">このアダプターは、最小下位層プロトコル (MLLP) を使用する TCP/IP ソケット アダプターです。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-105">This adapter is a TCP/IP socket adapter that uses the Minimal Lower Layer Protocol (MLLP).</span></span> <span data-ttu-id="f4fa5-106">このプロトコルは、双方向メッセージのサポートおよびエンド ツー エンドの医療アプリケーション統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-106">This protocol provides bi-directional message support and end-to-end health care application integration.</span></span>  
  
 <span data-ttu-id="f4fa5-107">MLLP を構成することができます、アダプターを双方向または一方向のアダプターのいずれかとしてアダプターを受信します。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-107">You can configure the MLLP receive adapter as either a two-way adapter or a one-way adapter.</span></span> <span data-ttu-id="f4fa5-108">双方向の送信請求-応答送信アダプター、一方向の送信アダプターが同じソケット接続で受信確認 (Ack) を受信するように構成または一方向の送信アダプターでメッセージが返されないよう、MLLP 送信アダプターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-108">You can configure the MLLP send adapter as a two-way solicit-response send adapter, a one-way send adapter configured to receive acknowledgments (ACKs) on the same socket connection, or a one-way send adapter that does not return any messages.</span></span> <span data-ttu-id="f4fa5-109">送信請求-応答が MLLP アダプターを送信、双方向を使用する場合は、Ack または応答メッセージのいずれかを返す受信ポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-109">When you use the two-way solicit-response send MLLP adapter, you can configure the receive port to return either ACKs or response messages.</span></span> <span data-ttu-id="f4fa5-110">MLLP の例では、送信し、受信アダプターを参照してください[Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)です。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-110">For examples of MLLP send and receive adapters, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
 <span data-ttu-id="f4fa5-111">メッセージの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信または MLLP アダプターの送信には、次のラッパーが必要とします。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-111">Messages that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives or sends on an MLLP adapter require the following wrappers:</span></span>  
  
-   <span data-ttu-id="f4fa5-112">\<SB > ブロックの開始文字</span><span class="sxs-lookup"><span data-stu-id="f4fa5-112">\<SB> Start Block character</span></span>  
  
-   <span data-ttu-id="f4fa5-113">\<EB > ブロックの終了文字</span><span class="sxs-lookup"><span data-stu-id="f4fa5-113">\<EB> End Block character</span></span>  
  
-   <span data-ttu-id="f4fa5-114">\<CR > 復帰返すバイト (省略可能)</span><span class="sxs-lookup"><span data-stu-id="f4fa5-114">\<CR> Carriage Return Byte (optional)</span></span>  
  
 <span data-ttu-id="f4fa5-115">MLLP アダプターは、エラーのない処理を行う\<SB > または\<EB > ラッパー、接続の切断、またはタイムアウトです。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-115">MLLP adapters provide error handling for missing \<SB> or \<EB> wrappers, dropped connections, or timeouts.</span></span> <span data-ttu-id="f4fa5-116">MLLP アダプターでは、接続の数に制限を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-116">With an MLLP adapter, you can configure a limitation on the number of connections.</span></span> <span data-ttu-id="f4fa5-117">MLLP アダプターでは、多種多様な受信確認を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4fa5-117">You can use an assortment of acknowledgments with an MLLP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4fa5-118">参照</span><span class="sxs-lookup"><span data-stu-id="f4fa5-118">See Also</span></span>  
 <span data-ttu-id="f4fa5-119">[MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f4fa5-119">[Processing MLLP-encoded Messages](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span></span>  
 [<span data-ttu-id="f4fa5-120">BizTalk Accelerator for HL7 コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f4fa5-120">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
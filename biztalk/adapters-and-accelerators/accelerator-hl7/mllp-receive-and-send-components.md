---
title: MLLP 受信および送信コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eebc51d23c66fb9dd7047f29982fbcc05a8215f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971803"
---
# <a name="mllp-receive-and-send-components"></a><span data-ttu-id="4d880-102">MLLP 受信および送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4d880-102">MLLP Receive and Send Components</span></span>
<span data-ttu-id="4d880-103">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) すべての Microsoft のサポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ファイル、HTTP、SQL では、FTP などのネイティブ アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="4d880-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports all Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] native adapter types, including File, HTTP, SQL, and FTP.</span></span> <span data-ttu-id="4d880-104">HL7 でエンコードされたメッセージの受信と送信、ただし、通常使用する MLLP アダプター。</span><span class="sxs-lookup"><span data-stu-id="4d880-104">For HL7-encoded message receiving and sending, however, you typically use the MLLP adapter.</span></span> <span data-ttu-id="4d880-105">このアダプターは、最小限下位レイヤー プロトコル (MLLP) を使用する TCP/IP ソケット アダプターです。</span><span class="sxs-lookup"><span data-stu-id="4d880-105">This adapter is a TCP/IP socket adapter that uses the Minimal Lower Layer Protocol (MLLP).</span></span> <span data-ttu-id="4d880-106">このプロトコルは、双方向のメッセージのサポートとエンド ツー エンドの医療のアプリケーション統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d880-106">This protocol provides bi-directional message support and end-to-end health care application integration.</span></span>  
  
 <span data-ttu-id="4d880-107">MLLP を構成する受信アダプターのアダプターを双方向または一方向のアダプターのいずれかとして。</span><span class="sxs-lookup"><span data-stu-id="4d880-107">You can configure the MLLP receive adapter as either a two-way adapter or a one-way adapter.</span></span> <span data-ttu-id="4d880-108">MLLP 送信アダプターは、双方向の送信請求-応答送信アダプター、一方向の送信アダプターが、同じソケット接続で受信確認 (Ack) を受信するように構成または一方向の送信メッセージを返さないアダプターとして構成できます。</span><span class="sxs-lookup"><span data-stu-id="4d880-108">You can configure the MLLP send adapter as a two-way solicit-response send adapter, a one-way send adapter configured to receive acknowledgments (ACKs) on the same socket connection, or a one-way send adapter that does not return any messages.</span></span> <span data-ttu-id="4d880-109">双方向を使用する場合は、送信請求-応答送信の MLLP アダプター、Ack または応答メッセージのいずれかを返す受信ポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4d880-109">When you use the two-way solicit-response send MLLP adapter, you can configure the receive port to return either ACKs or response messages.</span></span> <span data-ttu-id="4d880-110">MLLP の例では、送信および受信アダプターを参照してください。 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d880-110">For examples of MLLP send and receive adapters, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
 <span data-ttu-id="4d880-111">メッセージの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信または MLLP アダプターの送信には、次のラッパーが必要とします。</span><span class="sxs-lookup"><span data-stu-id="4d880-111">Messages that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives or sends on an MLLP adapter require the following wrappers:</span></span>  
  
- <span data-ttu-id="4d880-112">\<SB\>ブロックの開始文字</span><span class="sxs-lookup"><span data-stu-id="4d880-112">\<SB\> Start Block character</span></span>  
  
- <span data-ttu-id="4d880-113">\<EB\>ブロックの終了文字</span><span class="sxs-lookup"><span data-stu-id="4d880-113">\<EB\> End Block character</span></span>  
  
- <span data-ttu-id="4d880-114">\<CR\>復帰返すバイト (省略可能)</span><span class="sxs-lookup"><span data-stu-id="4d880-114">\<CR\> Carriage Return Byte (optional)</span></span>  
  
  <span data-ttu-id="4d880-115">MLLP アダプターがエラーで不足している処理を行う\<SB\>または\<EB\>ラッパー、接続が切断、またはタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="4d880-115">MLLP adapters provide error handling for missing \<SB\> or \<EB\> wrappers, dropped connections, or timeouts.</span></span> <span data-ttu-id="4d880-116">MLLP アダプターでは、接続の数に制限を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4d880-116">With an MLLP adapter, you can configure a limitation on the number of connections.</span></span> <span data-ttu-id="4d880-117">MLLP アダプターでは、多種多様な受信確認を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d880-117">You can use an assortment of acknowledgments with an MLLP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d880-118">参照</span><span class="sxs-lookup"><span data-stu-id="4d880-118">See Also</span></span>  
 <span data-ttu-id="4d880-119">[MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4d880-119">[Processing MLLP-encoded Messages](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span></span>  
 [<span data-ttu-id="4d880-120">BizTalk Accelerator for HL7 コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4d880-120">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
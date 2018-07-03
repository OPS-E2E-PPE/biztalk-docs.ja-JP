---
title: メッセージ セキュリティの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 971977a0-b74e-4408-8a07-ad327658f2bc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae25a8e09b6e9aa8f4b5cef7b6dc5365a601e7de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001187"
---
# <a name="implementing-message-security"></a><span data-ttu-id="8a2f7-102">メッセージ セキュリティの実装</span><span class="sxs-lookup"><span data-stu-id="8a2f7-102">Implementing Message Security</span></span>
<span data-ttu-id="8a2f7-103">署名および暗号化されたメッセージの送受信に証明書を使用するように Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を構成できます。</span><span class="sxs-lookup"><span data-stu-id="8a2f7-103">You can configure your Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment to use certificates for sending and receiving signed and encrypted messages.</span></span> <span data-ttu-id="8a2f7-104">BizTalk Server では、暗号化およびデジタル署名用の証明書を使用することで次の処理が可能になります。</span><span class="sxs-lookup"><span data-stu-id="8a2f7-104">By using certificates for encryption and digital signatures, BizTalk Server can:</span></span>  
  
- <span data-ttu-id="8a2f7-105">信頼できるデータを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="8a2f7-105">Send and receive data that can be trusted.</span></span>  
  
- <span data-ttu-id="8a2f7-106">処理するデータの安全性を確保できます。</span><span class="sxs-lookup"><span data-stu-id="8a2f7-106">Make sure that the data it processes is secure.</span></span>  
  
- <span data-ttu-id="8a2f7-107">承認されたパーティにメッセージを確実に送信できます。</span><span class="sxs-lookup"><span data-stu-id="8a2f7-107">Make sure that authorized parties receive its messages.</span></span>  
  
- <span data-ttu-id="8a2f7-108">承認されたパーティからメッセージを確実に受信できます。</span><span class="sxs-lookup"><span data-stu-id="8a2f7-108">Make sure that it receives messages from authorized parties.</span></span>  
  
  <span data-ttu-id="8a2f7-109">ここでは、BizTalk Server パイプライン、受信場所、ポート、および BizTalk Server 環境を構成してメッセージ セキュリティを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a2f7-109">This section provides information about how to configure BizTalk Server pipelines, receive locations, ports, and the BizTalk Server environment to implement message security.</span></span>  
  
  <span data-ttu-id="8a2f7-110">メッセージ セキュリティの詳細については、次を参照してください。[メッセージ セキュリティの計画](../core/planning-message-security.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a2f7-110">For more information about message security, see [Planning Message Security](../core/planning-message-security.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a2f7-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8a2f7-111">In This Section</span></span>  
  
-   [<span data-ttu-id="8a2f7-112">暗号化されたメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="8a2f7-112">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)  
  
-   [<span data-ttu-id="8a2f7-113">署名付きメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="8a2f7-113">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)  
  
-   [<span data-ttu-id="8a2f7-114">パーティの解決での証明書の使用</span><span class="sxs-lookup"><span data-stu-id="8a2f7-114">Using Certificates for Party Resolution</span></span>](../core/using-certificates-for-party-resolution.md)
---
title: HTTP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, receive adapters
- HTTP adapters, send adapters
- HTTP adapters
- receive adapters, HTTP adapters
- send adapters, HTTP adapters
- HTTP adapters, about HTTP adapters
ms.assetid: a9423052-8392-4006-ab46-79834169c796
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d9bfc533222dad9411c6c56e67c37b5c9a37212
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382878"
---
# <a name="http-adapter"></a><span data-ttu-id="e14be-102">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="e14be-102">HTTP Adapter</span></span>
<span data-ttu-id="e14be-103">HTTP プロトコルを使用して、Microsoft BizTalk Server とアプリケーション間で情報を交換するのにには、HTTP アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e14be-103">You use the HTTP adapter to exchange information between Microsoft BizTalk Server and an application by means of the HTTP protocol.</span></span> <span data-ttu-id="e14be-104">HTTP は、企業間のメッセージ交換の主要なプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="e14be-104">HTTP is the primary protocol for interbusiness message exchange.</span></span> <span data-ttu-id="e14be-105">アプリケーションは、指定された HTTP URL に HTTP POST 要求または HTTP GET 要求を送信することで、サーバーにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="e14be-105">Applications can send messages to a server by sending HTTP POST or HTTP GET requests to a specified HTTP URL.</span></span> <span data-ttu-id="e14be-106">HTTP アダプターは、HTTP 要求を受け取り、処理のための BizTalk Server に送信します。</span><span class="sxs-lookup"><span data-stu-id="e14be-106">The HTTP adapter receives the HTTP requests and submits them to BizTalk Server for processing.</span></span> <span data-ttu-id="e14be-107">同様に、BizTalk Server では、指定された HTTP URL に HTTP POST 要求を送信してリモート アプリケーションにメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="e14be-107">Similarly, BizTalk Server can transmit messages to remote applications by sending HTTP POST requests to a specified HTTP URL.</span></span>  
  
 <span data-ttu-id="e14be-108">HTTP アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="e14be-108">The HTTP adapter consists of two adapters—a receive adapter and a send adapter.</span></span> <span data-ttu-id="e14be-109">HTTP 受信アダプターは、Microsoft インターネット インフォメーション サービス (IIS) インターネット サーバー アプリケーション プログラミング インターフェイス (ISAPI) 拡張機能、IIS のプロセスをホスト、および HTTP アダプターを使用する受信場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="e14be-109">The HTTP receive adapter is a Microsoft Internet Information Services (IIS) Internet Server Application Programming Interface (ISAPI) extension that the IIS process hosts, and controls the receive locations that use the HTTP adapter.</span></span> <span data-ttu-id="e14be-110">HTTP では、HTTP アダプターを使用する送信ポート アダプタのコントロールを送信します。</span><span class="sxs-lookup"><span data-stu-id="e14be-110">The HTTP send adapter controls the send ports that use the HTTP adapter.</span></span>  
  
 <span data-ttu-id="e14be-111">このセクションでは、ワークフローを説明し、バッチ処理の両方のサポート、HTTP 受信アダプタと HTTP 送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="e14be-111">This section discusses the workflow and batching support for both the HTTP receive adapter and the HTTP send adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e14be-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e14be-112">In This Section</span></span>  
  
-   [<span data-ttu-id="e14be-113">HTTP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="e14be-113">HTTP Receive Adapter</span></span>](../core/http-receive-adapter.md)  
  
-   [<span data-ttu-id="e14be-114">HTTP 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="e14be-114">HTTP Send Adapter</span></span>](../core/http-send-adapter.md)  
  
-   [<span data-ttu-id="e14be-115">HTTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="e14be-115">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)  
  
-   [<span data-ttu-id="e14be-116">HTTP アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="e14be-116">HTTP Adapter Security Recommendations</span></span>](../core/http-adapter-security-recommendations.md)
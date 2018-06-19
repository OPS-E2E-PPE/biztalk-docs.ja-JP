---
title: HTTP アダプター |Microsoft ドキュメント
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
ms.openlocfilehash: 6d9be9fac6fdb65c4516c671b6c0e30096e83a27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256050"
---
# <a name="http-adapter"></a><span data-ttu-id="05b1f-102">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="05b1f-102">HTTP Adapter</span></span>
<span data-ttu-id="05b1f-103">HTTP アダプタは、Microsoft BizTalk Server とアプリケーション間で HTTP プロトコルを介して情報を交換するために使用します。</span><span class="sxs-lookup"><span data-stu-id="05b1f-103">You use the HTTP adapter to exchange information between Microsoft BizTalk Server and an application by means of the HTTP protocol.</span></span> <span data-ttu-id="05b1f-104">HTTP は、企業間のメッセージ交換にとって主要なプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="05b1f-104">HTTP is the primary protocol for interbusiness message exchange.</span></span> <span data-ttu-id="05b1f-105">アプリケーションは、指定された HTTP URL に HTTP POST 要求または HTTP GET 要求を送信することで、サーバーにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="05b1f-105">Applications can send messages to a server by sending HTTP POST or HTTP GET requests to a specified HTTP URL.</span></span> <span data-ttu-id="05b1f-106">HTTP アダプタは、HTTP 要求を受信し、その要求を処理するために BizTalk Server に送信します。</span><span class="sxs-lookup"><span data-stu-id="05b1f-106">The HTTP adapter receives the HTTP requests and submits them to BizTalk Server for processing.</span></span> <span data-ttu-id="05b1f-107">同様に、BizTalk Server は、指定された HTTP URL に HTTP POST 要求を送信することで、リモート アプリケーションにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="05b1f-107">Similarly, BizTalk Server can transmit messages to remote applications by sending HTTP POST requests to a specified HTTP URL.</span></span>  
  
 <span data-ttu-id="05b1f-108">HTTP アダプタは、2 つのアダプタ (受信アダプタと送信アダプタ) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="05b1f-108">The HTTP adapter consists of two adapters—a receive adapter and a send adapter.</span></span> <span data-ttu-id="05b1f-109">HTTP 受信アダプタは、IIS プロセスでホストされる Microsoft インターネット インフォメーション サービス (IIS) の ISAPI (Internet Server API) 拡張で、HTTP アダプタを使用する受信場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="05b1f-109">The HTTP receive adapter is a Microsoft Internet Information Services (IIS) Internet Server Application Programming Interface (ISAPI) extension that the IIS process hosts, and controls the receive locations that use the HTTP adapter.</span></span> <span data-ttu-id="05b1f-110">HTTP 送信アダプタでは、HTTP アダプタを使用する送信ポートを制御します。</span><span class="sxs-lookup"><span data-stu-id="05b1f-110">The HTTP send adapter controls the send ports that use the HTTP adapter.</span></span>  
  
 <span data-ttu-id="05b1f-111">このセクションでは、HTTP 受信アダプタと HTTP 送信アダプタ両方のワークフローおよびバッチ処理のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="05b1f-111">This section discusses the workflow and batching support for both the HTTP receive adapter and the HTTP send adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05b1f-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="05b1f-112">In This Section</span></span>  
  
-   [<span data-ttu-id="05b1f-113">HTTP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="05b1f-113">HTTP Receive Adapter</span></span>](../core/http-receive-adapter.md)  
  
-   [<span data-ttu-id="05b1f-114">HTTP 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="05b1f-114">HTTP Send Adapter</span></span>](../core/http-send-adapter.md)  
  
-   [<span data-ttu-id="05b1f-115">HTTP アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="05b1f-115">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)  
  
-   [<span data-ttu-id="05b1f-116">HTTP アダプタのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="05b1f-116">HTTP Adapter Security Recommendations</span></span>](../core/http-adapter-security-recommendations.md)
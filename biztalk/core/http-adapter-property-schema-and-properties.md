---
title: HTTP アダプター プロパティ スキーマおよびプロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- AffiliateApplicationName property [HTTP adapters]
- Certificate property [HTTP adapters]
- Password property [HTTP adapters]
- HTTP adapters, properties
- InboundHttpHeaders property [HTTP adapters]
- UseHandlerProxySettings property [HTTP adapters]
- configuring [HTTP adapters], properties
- schemas, HTTP adapters
- RequestTimeout property [HTTP adapters]
- ProxyPassword property [HTTP adapters]
- UseSSO property [HTTP adapters]
- HTTP adapters, schemas
- AuthenticationScheme property [HTTP adapters]
- ProxyName property [HTTP adapters]
- ProxyPort property [HTTP adapters]
- UseProxy property [HTTP adapters]
- configuring [HTTP adapters], schemas
- ContentType property [HTTP adapters]
- MaxRedirects property [HTTP adapters]
- ProxyUsername property [HTTP adapters]
- UserName property, HTTP adapters
ms.assetid: c9b50a82-8cb1-4521-9cf3-5fd77a3531e1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416ad39e804a4907dc39c7cef941e9a1bb57d3dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257426"
---
# <a name="http-adapter-property-schema-and-properties"></a><span data-ttu-id="6db41-102">HTTP アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="6db41-102">HTTP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="6db41-103">HTTP アダプタ プロパティ スキーマのプロパティを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="6db41-103">The following table lists the properties in the HTTP adapter property schema.</span></span>  
  
 <span data-ttu-id="6db41-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/http-properties</span><span class="sxs-lookup"><span data-stu-id="6db41-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/http-properties</span></span>  
  
|<span data-ttu-id="6db41-105">名前</span><span class="sxs-lookup"><span data-stu-id="6db41-105">Name</span></span>|<span data-ttu-id="6db41-106">型</span><span class="sxs-lookup"><span data-stu-id="6db41-106">Type</span></span>|<span data-ttu-id="6db41-107">Description</span><span class="sxs-lookup"><span data-stu-id="6db41-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="6db41-108">**ProxyName**</span><span class="sxs-lookup"><span data-stu-id="6db41-108">**ProxyName**</span></span>|<span data-ttu-id="6db41-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-109">xs:string</span></span>|<span data-ttu-id="6db41-110">プロキシ サーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6db41-110">Specifies the proxy server name.</span></span>|  
|<span data-ttu-id="6db41-111">**ProxyPort**</span><span class="sxs-lookup"><span data-stu-id="6db41-111">**ProxyPort**</span></span>|<span data-ttu-id="6db41-112">xs:int</span><span class="sxs-lookup"><span data-stu-id="6db41-112">xs:int</span></span>|<span data-ttu-id="6db41-113">プロキシ サーバーのポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="6db41-113">Specifies the proxy server port.</span></span>|  
|<span data-ttu-id="6db41-114">**UseHandlerProxySettings**</span><span class="sxs-lookup"><span data-stu-id="6db41-114">**UseHandlerProxySettings**</span></span>|<span data-ttu-id="6db41-115">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="6db41-115">xs:boolean</span></span>|<span data-ttu-id="6db41-116">HTTP 送信ポートでハンドラのプロキシ構成を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6db41-116">Specifies whether the HTTP send port uses the proxy configuration for the handler.</span></span>|  
|<span data-ttu-id="6db41-117">**UseProxy**</span><span class="sxs-lookup"><span data-stu-id="6db41-117">**UseProxy**</span></span>|<span data-ttu-id="6db41-118">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="6db41-118">xs:boolean</span></span>|<span data-ttu-id="6db41-119">HTTP アダプタでプロキシ サーバーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6db41-119">Specifies whether HTTP adapter uses the proxy server.</span></span>|  
|<span data-ttu-id="6db41-120">**RequestTimeout**</span><span class="sxs-lookup"><span data-stu-id="6db41-120">**RequestTimeout**</span></span>|<span data-ttu-id="6db41-121">xs:int</span><span class="sxs-lookup"><span data-stu-id="6db41-121">xs:int</span></span>|<span data-ttu-id="6db41-122">サーバーからの応答を待機する際のタイムアウト値です。</span><span class="sxs-lookup"><span data-stu-id="6db41-122">Time-out period of waiting for a response from the server.</span></span> <span data-ttu-id="6db41-123">ゼロ (0) に設定されている場合、タイムアウト値は要求メッセージのサイズを基準に計算されます。</span><span class="sxs-lookup"><span data-stu-id="6db41-123">If this property is set to zero (0), the system calculates the time-out on the request message size.</span></span>|  
|<span data-ttu-id="6db41-124">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="6db41-124">**Username**</span></span>|<span data-ttu-id="6db41-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-125">xs:string</span></span>|<span data-ttu-id="6db41-126">サーバーでの認証に使用するユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="6db41-126">The user name to use for authentication with the server.</span></span>|  
|<span data-ttu-id="6db41-127">**Password**</span><span class="sxs-lookup"><span data-stu-id="6db41-127">**Password**</span></span>|<span data-ttu-id="6db41-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-128">xs:string</span></span>|<span data-ttu-id="6db41-129">サーバーでの認証に使用するユーザーのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="6db41-129">The user password to use for authentication with the server.</span></span>|  
|<span data-ttu-id="6db41-130">**ProxyUsername**</span><span class="sxs-lookup"><span data-stu-id="6db41-130">**ProxyUsername**</span></span>|<span data-ttu-id="6db41-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-131">xs:string</span></span>|<span data-ttu-id="6db41-132">プロキシ サーバーで認証のユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6db41-132">Specifies the user name for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="6db41-133">**ProxyPassword**</span><span class="sxs-lookup"><span data-stu-id="6db41-133">**ProxyPassword**</span></span>|<span data-ttu-id="6db41-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-134">xs:string</span></span>|<span data-ttu-id="6db41-135">プロキシ サーバーで認証用のユーザー パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6db41-135">Specifies the user password for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="6db41-136">**MaxRedirects**</span><span class="sxs-lookup"><span data-stu-id="6db41-136">**MaxRedirects**</span></span>|<span data-ttu-id="6db41-137">xs:int</span><span class="sxs-lookup"><span data-stu-id="6db41-137">xs:int</span></span>|<span data-ttu-id="6db41-138">HTTP アダプタで要求をリダイレクトする最大回数です。</span><span class="sxs-lookup"><span data-stu-id="6db41-138">The maximum number of times that the HTTP adapter will redirect the request.</span></span>|  
|<span data-ttu-id="6db41-139">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="6db41-139">**ContentType**</span></span>|<span data-ttu-id="6db41-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-140">xs:string</span></span>|<span data-ttu-id="6db41-141">要求メッセージのコンテンツの種類です。</span><span class="sxs-lookup"><span data-stu-id="6db41-141">Content type of the request messages.</span></span>|  
|<span data-ttu-id="6db41-142">**AuthenticationScheme**</span><span class="sxs-lookup"><span data-stu-id="6db41-142">**AuthenticationScheme**</span></span>|<span data-ttu-id="6db41-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-143">xs:string</span></span>|<span data-ttu-id="6db41-144">接続先のサーバーで使用する認証の種類です。</span><span class="sxs-lookup"><span data-stu-id="6db41-144">Type of authentication to use with the destination server.</span></span>|  
|<span data-ttu-id="6db41-145">**[MSSQLSERVER のプロトコルのプロパティ]**</span><span class="sxs-lookup"><span data-stu-id="6db41-145">**Certificate**</span></span>|<span data-ttu-id="6db41-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-146">xs:string</span></span>|<span data-ttu-id="6db41-147">SSL クライアント証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="6db41-147">Thumbprint of client SSL certificate.</span></span>|  
|<span data-ttu-id="6db41-148">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="6db41-148">**UseSSO**</span></span>|<span data-ttu-id="6db41-149">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="6db41-149">xs:boolean</span></span>|<span data-ttu-id="6db41-150">HTTP 送信ポートで SSO を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6db41-150">Specifies whether the HTTP send port will use SSO.</span></span>|  
|<span data-ttu-id="6db41-151">**AffiliateApplicationName**</span><span class="sxs-lookup"><span data-stu-id="6db41-151">**AffiliateApplicationName**</span></span>|<span data-ttu-id="6db41-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-152">xs:string</span></span>|<span data-ttu-id="6db41-153">SSO に使用する関連アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="6db41-153">Name of affiliate application to use for SSO.</span></span>|  
|<span data-ttu-id="6db41-154">**InboundHttpHeaders**</span><span class="sxs-lookup"><span data-stu-id="6db41-154">**InboundHttpHeaders**</span></span>|<span data-ttu-id="6db41-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-155">xs:string</span></span>|<span data-ttu-id="6db41-156">受信した HTTP 要求の HTTP ヘッダーを表します。</span><span class="sxs-lookup"><span data-stu-id="6db41-156">Contains the HTTP headers from the inbound HTTP request.</span></span>|  
|<span data-ttu-id="6db41-157">**SubmissionHandle**</span><span class="sxs-lookup"><span data-stu-id="6db41-157">**SubmissionHandle**</span></span>|<span data-ttu-id="6db41-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-158">xs:string</span></span>|<span data-ttu-id="6db41-159">要求メッセージの BizTalk Server 関連付けトークン (GUID) を表します。</span><span class="sxs-lookup"><span data-stu-id="6db41-159">Contains the BizTalk Server correlation token (GUID) for the request message.</span></span>|  
|<span data-ttu-id="6db41-160">**EnableChunkedEncoding**</span><span class="sxs-lookup"><span data-stu-id="6db41-160">**EnableChunkedEncoding**</span></span>|<span data-ttu-id="6db41-161">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="6db41-161">xs:boolean</span></span>|<span data-ttu-id="6db41-162">HTTP アダプターで使用されてエンコード チャンクかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6db41-162">Specifies whether or not chunked encoding is used by the HTTP adapter.</span></span>|  
|<span data-ttu-id="6db41-163">**UserHttpHeaders**</span><span class="sxs-lookup"><span data-stu-id="6db41-163">**UserHttpHeaders**</span></span>|<span data-ttu-id="6db41-164">xs:string</span><span class="sxs-lookup"><span data-stu-id="6db41-164">xs:string</span></span>|<span data-ttu-id="6db41-165">HTTP の要求メッセージまたは応答メッセージに含まれているカスタマイズされたヘッダーを表します。</span><span class="sxs-lookup"><span data-stu-id="6db41-165">Contains the customized headers contained in the HTTP request or response message</span></span><br /><br /> <span data-ttu-id="6db41-166">値、 **UserHttpHeaders**プロパティは、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db41-166">The value of the **UserHttpHeaders** property must have the following format:</span></span><br /><br /> `Header1: value\r\nHeader2: value\r\n`<br /><br /> <span data-ttu-id="6db41-167">**注**コロン (:) と、ヘッダーと値の間のスペース文字 () に配置します。</span><span class="sxs-lookup"><span data-stu-id="6db41-167">**Note** Put a colon (:) and a SPACE character ( ) between the header and the value.</span></span> <span data-ttu-id="6db41-168">ヘッダーが空の場合、エントリは表示されません。空の値は問題ありません。</span><span class="sxs-lookup"><span data-stu-id="6db41-168">An empty header will cause the entry to be filtered out. An empty value is okay.</span></span><br /><br /> <span data-ttu-id="6db41-169">使用して次の 5 つの標準 HTTP ヘッダーを変更することができます、 **UserHttpHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6db41-169">You can modify the following five standard HTTP headers by using the **UserHttpHeaders** property:</span></span><br /><br /> <span data-ttu-id="6db41-170">Accept します。</span><span class="sxs-lookup"><span data-stu-id="6db41-170">- Accept</span></span><br /><br /> <span data-ttu-id="6db41-171">-参照元</span><span class="sxs-lookup"><span data-stu-id="6db41-171">- Referrer</span></span><br /><br /> <span data-ttu-id="6db41-172">-期待します。</span><span class="sxs-lookup"><span data-stu-id="6db41-172">- Expect</span></span><br /><br /> <span data-ttu-id="6db41-173">場合の変更-以降</span><span class="sxs-lookup"><span data-stu-id="6db41-173">- If-Modified-Since</span></span><br /><br /> <span data-ttu-id="6db41-174">-ユーザー エージェント</span><span class="sxs-lookup"><span data-stu-id="6db41-174">- User-Agent</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6db41-175">参照</span><span class="sxs-lookup"><span data-stu-id="6db41-175">See Also</span></span>  
 [<span data-ttu-id="6db41-176">HTTP アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="6db41-176">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)
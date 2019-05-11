---
title: HTTP アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
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
ms.openlocfilehash: a2f4fdfbd082bb9bbb8e3a37355068b3c8d29c63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332890"
---
# <a name="http-adapter-property-schema-and-properties"></a><span data-ttu-id="0aef7-102">HTTP アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="0aef7-102">HTTP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="0aef7-103">次の表は、HTTP アダプタ プロパティ スキーマのプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-103">The following table lists the properties in the HTTP adapter property schema.</span></span>  
  
 <span data-ttu-id="0aef7-104">**名前空間:** http://schemas.microsoft.com/BizTalk/2003/http-properties</span><span class="sxs-lookup"><span data-stu-id="0aef7-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/http-properties</span></span>  
  
|<span data-ttu-id="0aef7-105">名前</span><span class="sxs-lookup"><span data-stu-id="0aef7-105">Name</span></span>|<span data-ttu-id="0aef7-106">型</span><span class="sxs-lookup"><span data-stu-id="0aef7-106">Type</span></span>|<span data-ttu-id="0aef7-107">説明</span><span class="sxs-lookup"><span data-stu-id="0aef7-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="0aef7-108">**ProxyName**</span><span class="sxs-lookup"><span data-stu-id="0aef7-108">**ProxyName**</span></span>|<span data-ttu-id="0aef7-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-109">xs:string</span></span>|<span data-ttu-id="0aef7-110">プロキシ サーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-110">Specifies the proxy server name.</span></span>|  
|<span data-ttu-id="0aef7-111">**ProxyPort**</span><span class="sxs-lookup"><span data-stu-id="0aef7-111">**ProxyPort**</span></span>|<span data-ttu-id="0aef7-112">xs:int</span><span class="sxs-lookup"><span data-stu-id="0aef7-112">xs:int</span></span>|<span data-ttu-id="0aef7-113">プロキシ サーバーのポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-113">Specifies the proxy server port.</span></span>|  
|<span data-ttu-id="0aef7-114">**UseHandlerProxySettings**</span><span class="sxs-lookup"><span data-stu-id="0aef7-114">**UseHandlerProxySettings**</span></span>|<span data-ttu-id="0aef7-115">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="0aef7-115">xs:boolean</span></span>|<span data-ttu-id="0aef7-116">HTTP 送信ポートが、ハンドラーのプロキシ構成を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-116">Specifies whether the HTTP send port uses the proxy configuration for the handler.</span></span>|  
|<span data-ttu-id="0aef7-117">**UseProxy**</span><span class="sxs-lookup"><span data-stu-id="0aef7-117">**UseProxy**</span></span>|<span data-ttu-id="0aef7-118">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="0aef7-118">xs:boolean</span></span>|<span data-ttu-id="0aef7-119">HTTP アダプタでプロキシ サーバーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-119">Specifies whether HTTP adapter uses the proxy server.</span></span>|  
|<span data-ttu-id="0aef7-120">**RequestTimeout**</span><span class="sxs-lookup"><span data-stu-id="0aef7-120">**RequestTimeout**</span></span>|<span data-ttu-id="0aef7-121">xs:int</span><span class="sxs-lookup"><span data-stu-id="0aef7-121">xs:int</span></span>|<span data-ttu-id="0aef7-122">サーバーからの応答を待機する際のタイムアウト値です。</span><span class="sxs-lookup"><span data-stu-id="0aef7-122">Time-out period of waiting for a response from the server.</span></span> <span data-ttu-id="0aef7-123">このプロパティが 0 (ゼロ) に設定されている場合のタイムアウト値を要求メッセージのサイズが計算されます。</span><span class="sxs-lookup"><span data-stu-id="0aef7-123">If this property is set to zero (0), the system calculates the time-out on the request message size.</span></span>|  
|<span data-ttu-id="0aef7-124">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="0aef7-124">**Username**</span></span>|<span data-ttu-id="0aef7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-125">xs:string</span></span>|<span data-ttu-id="0aef7-126">サーバーでの認証に使用するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="0aef7-126">The user name to use for authentication with the server.</span></span>|  
|<span data-ttu-id="0aef7-127">**Password**</span><span class="sxs-lookup"><span data-stu-id="0aef7-127">**Password**</span></span>|<span data-ttu-id="0aef7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-128">xs:string</span></span>|<span data-ttu-id="0aef7-129">サーバーでの認証に使用するユーザー パスワード。</span><span class="sxs-lookup"><span data-stu-id="0aef7-129">The user password to use for authentication with the server.</span></span>|  
|<span data-ttu-id="0aef7-130">**ProxyUsername**</span><span class="sxs-lookup"><span data-stu-id="0aef7-130">**ProxyUsername**</span></span>|<span data-ttu-id="0aef7-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-131">xs:string</span></span>|<span data-ttu-id="0aef7-132">プロキシ サーバーで認証のユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-132">Specifies the user name for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="0aef7-133">**ProxyPassword**</span><span class="sxs-lookup"><span data-stu-id="0aef7-133">**ProxyPassword**</span></span>|<span data-ttu-id="0aef7-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-134">xs:string</span></span>|<span data-ttu-id="0aef7-135">プロキシ サーバーで認証のユーザーのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-135">Specifies the user password for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="0aef7-136">**MaxRedirects**</span><span class="sxs-lookup"><span data-stu-id="0aef7-136">**MaxRedirects**</span></span>|<span data-ttu-id="0aef7-137">xs:int</span><span class="sxs-lookup"><span data-stu-id="0aef7-137">xs:int</span></span>|<span data-ttu-id="0aef7-138">HTTP アダプターが要求をリダイレクトする最大回数。</span><span class="sxs-lookup"><span data-stu-id="0aef7-138">The maximum number of times that the HTTP adapter will redirect the request.</span></span>|  
|<span data-ttu-id="0aef7-139">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="0aef7-139">**ContentType**</span></span>|<span data-ttu-id="0aef7-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-140">xs:string</span></span>|<span data-ttu-id="0aef7-141">要求メッセージのコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="0aef7-141">Content type of the request messages.</span></span>|  
|<span data-ttu-id="0aef7-142">**AuthenticationScheme**</span><span class="sxs-lookup"><span data-stu-id="0aef7-142">**AuthenticationScheme**</span></span>|<span data-ttu-id="0aef7-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-143">xs:string</span></span>|<span data-ttu-id="0aef7-144">接続先のサーバーで使用する認証の種類です。</span><span class="sxs-lookup"><span data-stu-id="0aef7-144">Type of authentication to use with the destination server.</span></span>|  
|<span data-ttu-id="0aef7-145">**[MSSQLSERVER のプロトコルのプロパティ]**</span><span class="sxs-lookup"><span data-stu-id="0aef7-145">**Certificate**</span></span>|<span data-ttu-id="0aef7-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-146">xs:string</span></span>|<span data-ttu-id="0aef7-147">SSL クライアント証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="0aef7-147">Thumbprint of client SSL certificate.</span></span>|  
|<span data-ttu-id="0aef7-148">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="0aef7-148">**UseSSO**</span></span>|<span data-ttu-id="0aef7-149">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="0aef7-149">xs:boolean</span></span>|<span data-ttu-id="0aef7-150">HTTP 送信ポートで SSO を使用しているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-150">Specifies whether the HTTP send port will use SSO.</span></span>|  
|<span data-ttu-id="0aef7-151">**AffiliateApplicationName**</span><span class="sxs-lookup"><span data-stu-id="0aef7-151">**AffiliateApplicationName**</span></span>|<span data-ttu-id="0aef7-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-152">xs:string</span></span>|<span data-ttu-id="0aef7-153">SSO に使用する関連アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="0aef7-153">Name of affiliate application to use for SSO.</span></span>|  
|<span data-ttu-id="0aef7-154">**InboundHttpHeaders**</span><span class="sxs-lookup"><span data-stu-id="0aef7-154">**InboundHttpHeaders**</span></span>|<span data-ttu-id="0aef7-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-155">xs:string</span></span>|<span data-ttu-id="0aef7-156">受信した HTTP 要求から HTTP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0aef7-156">Contains the HTTP headers from the inbound HTTP request.</span></span>|  
|<span data-ttu-id="0aef7-157">**SubmissionHandle**</span><span class="sxs-lookup"><span data-stu-id="0aef7-157">**SubmissionHandle**</span></span>|<span data-ttu-id="0aef7-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-158">xs:string</span></span>|<span data-ttu-id="0aef7-159">要求メッセージの BizTalk Server 関連付けトークン (GUID) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0aef7-159">Contains the BizTalk Server correlation token (GUID) for the request message.</span></span>|  
|<span data-ttu-id="0aef7-160">**EnableChunkedEncoding**</span><span class="sxs-lookup"><span data-stu-id="0aef7-160">**EnableChunkedEncoding**</span></span>|<span data-ttu-id="0aef7-161">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="0aef7-161">xs:boolean</span></span>|<span data-ttu-id="0aef7-162">HTTP アダプターによってエンコードされるチャンク対象かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-162">Specifies whether or not chunked encoding is used by the HTTP adapter.</span></span>|  
|<span data-ttu-id="0aef7-163">**UserHttpHeaders**</span><span class="sxs-lookup"><span data-stu-id="0aef7-163">**UserHttpHeaders**</span></span>|<span data-ttu-id="0aef7-164">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aef7-164">xs:string</span></span>|<span data-ttu-id="0aef7-165">HTTP 要求または応答メッセージに含まれるカスタマイズされたヘッダーが含まれています</span><span class="sxs-lookup"><span data-stu-id="0aef7-165">Contains the customized headers contained in the HTTP request or response message</span></span><br /><br /> <span data-ttu-id="0aef7-166">値、 **UserHttpHeaders**プロパティは、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0aef7-166">The value of the **UserHttpHeaders** property must have the following format:</span></span><br /><br /> `Header1: value\r\nHeader2: value\r\n`<br /><br /> <span data-ttu-id="0aef7-167">**注**コロン (:) の配置ヘッダーと値の間の空白文字 () を選択します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-167">**Note** Put a colon (:) and a SPACE character ( ) between the header and the value.</span></span> <span data-ttu-id="0aef7-168">空のヘッダーには、フィルターで除外するエントリが発生します。空の値は問題ありません。</span><span class="sxs-lookup"><span data-stu-id="0aef7-168">An empty header will cause the entry to be filtered out. An empty value is okay.</span></span><br /><br /> <span data-ttu-id="0aef7-169">使用して、次の 5 つの標準 HTTP ヘッダーを変更することができます、 **UserHttpHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0aef7-169">You can modify the following five standard HTTP headers by using the **UserHttpHeaders** property:</span></span><br /><br /> <span data-ttu-id="0aef7-170">-そのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-170">- Accept</span></span><br /><br /> <span data-ttu-id="0aef7-171">-参照元</span><span class="sxs-lookup"><span data-stu-id="0aef7-171">- Referrer</span></span><br /><br /> <span data-ttu-id="0aef7-172">-期待します。</span><span class="sxs-lookup"><span data-stu-id="0aef7-172">- Expect</span></span><br /><br /> <span data-ttu-id="0aef7-173">場合-変更-以降</span><span class="sxs-lookup"><span data-stu-id="0aef7-173">- If-Modified-Since</span></span><br /><br /> <span data-ttu-id="0aef7-174">-ユーザー エージェント</span><span class="sxs-lookup"><span data-stu-id="0aef7-174">- User-Agent</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0aef7-175">参照</span><span class="sxs-lookup"><span data-stu-id="0aef7-175">See Also</span></span>  
 [<span data-ttu-id="0aef7-176">HTTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="0aef7-176">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)
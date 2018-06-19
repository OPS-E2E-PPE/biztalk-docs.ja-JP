---
title: SOAP アダプター プロパティ スキーマおよびプロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ProxyUsername property [SOAP adapters]
- ClientConnectionTimeout property [SOAP adapters]
- SOAP adapters, properties
- ProxyAddress property [SOAP adapters]
- UserDefined property [SOAP adapters]
- AssemblyName property [SOAP adapters]
- ClientCertificate property [SOAP adapters]
- AffiliateApplicationName property [SOAP adapters]
- schemas, SOAP adapters
- AuthenticationScheme property [SOAP adapters]
- UserName property, SOAP adapters
- UseProxy property [SOAP adapters]
- Password property [SOAP adapters]
- configuring [SOAP adapters], schemas
- UnknownHeaders property [SOAP adapters]
- configuring [SOAP adapters], properties
- UseSoap12 property [SOAP adapters]
- UseHandlerSetting property [SOAP adapters]
- SOAP adapters, schemas
- ProxyPassword property [SOAP adapters]
- UseSSO property [SOAP adapters]
- MethodName property [SOAP adapters]
- ProxyPort property [SOAP adapters]
ms.assetid: b471cf4b-2d87-4aa2-ae4a-f48517fd4c94
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a24a9ccfc3a07abe925761fe2d6886646981be9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277514"
---
# <a name="soap-adapter-property-schema-and-properties"></a><span data-ttu-id="f2172-102">SOAP アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="f2172-102">SOAP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="f2172-103">SOAP アダプタ プロパティ スキーマのプロパティを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f2172-103">The following table lists the properties in the SOAP adapter property schema.</span></span>  
  
 <span data-ttu-id="f2172-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span><span class="sxs-lookup"><span data-stu-id="f2172-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span></span>  
  
|<span data-ttu-id="f2172-105">名前</span><span class="sxs-lookup"><span data-stu-id="f2172-105">Name</span></span>|<span data-ttu-id="f2172-106">型</span><span class="sxs-lookup"><span data-stu-id="f2172-106">Type</span></span>|<span data-ttu-id="f2172-107">Description</span><span class="sxs-lookup"><span data-stu-id="f2172-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="f2172-108">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="f2172-108">**AssemblyName**</span></span>|<span data-ttu-id="f2172-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-109">xs:string</span></span>|<span data-ttu-id="f2172-110">読み込んで実行する .NET 型およびアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="f2172-110">Identifies the .NET type and assembly to be loaded and executed.</span></span>|  
|<span data-ttu-id="f2172-111">**MethodName**</span><span class="sxs-lookup"><span data-stu-id="f2172-111">**MethodName**</span></span>|<span data-ttu-id="f2172-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-112">xs:string</span></span>|<span data-ttu-id="f2172-113">.NET アセンブリの呼び出す対象メソッドを識別します。</span><span class="sxs-lookup"><span data-stu-id="f2172-113">Identifies the target method on the .NET assembly that is to be invoked.</span></span>|  
|<span data-ttu-id="f2172-114">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="f2172-114">**Username**</span></span>|<span data-ttu-id="f2172-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-115">xs:string</span></span>|<span data-ttu-id="f2172-116">サーバーで認証に使用するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="f2172-116">User name to use for authentication with the server.</span></span>|  
|<span data-ttu-id="f2172-117">**Password**</span><span class="sxs-lookup"><span data-stu-id="f2172-117">**Password**</span></span>|<span data-ttu-id="f2172-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-118">xs:string</span></span>|<span data-ttu-id="f2172-119">サーバーでの認証に使用するユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="f2172-119">User password to use for authentication with the server.</span></span>|  
|<span data-ttu-id="f2172-120">**ClientCertificate**</span><span class="sxs-lookup"><span data-stu-id="f2172-120">**ClientCertificate**</span></span>|<span data-ttu-id="f2172-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-121">xs:string</span></span>|<span data-ttu-id="f2172-122">SSL クライアント証明書の拇印。</span><span class="sxs-lookup"><span data-stu-id="f2172-122">Thumbprint of the client SSL certificate.</span></span>|  
|<span data-ttu-id="f2172-123">**UseProxy**</span><span class="sxs-lookup"><span data-stu-id="f2172-123">**UseProxy**</span></span>|<span data-ttu-id="f2172-124">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="f2172-124">xs:Boolean</span></span>|<span data-ttu-id="f2172-125">SOAP アダプタでプロキシ サーバーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-125">Specifies whether the SOAP adapter uses a proxy server.</span></span>|  
|<span data-ttu-id="f2172-126">**ProxyAddress**</span><span class="sxs-lookup"><span data-stu-id="f2172-126">**ProxyAddress**</span></span>|<span data-ttu-id="f2172-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-127">xs:string</span></span>|<span data-ttu-id="f2172-128">プロキシ サーバーのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-128">Specifies the proxy server address.</span></span>|  
|<span data-ttu-id="f2172-129">**ProxyPort**</span><span class="sxs-lookup"><span data-stu-id="f2172-129">**ProxyPort**</span></span>|<span data-ttu-id="f2172-130">xs:int</span><span class="sxs-lookup"><span data-stu-id="f2172-130">xs:int</span></span>|<span data-ttu-id="f2172-131">プロキシ サーバーのポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-131">Specifies the proxy server port.</span></span>|  
|<span data-ttu-id="f2172-132">**ProxyUsername**</span><span class="sxs-lookup"><span data-stu-id="f2172-132">**ProxyUsername**</span></span>|<span data-ttu-id="f2172-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-133">xs:string</span></span>|<span data-ttu-id="f2172-134">プロキシ サーバーで認証のユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-134">Specifies the user name for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="f2172-135">**ProxyPassword**</span><span class="sxs-lookup"><span data-stu-id="f2172-135">**ProxyPassword**</span></span>|<span data-ttu-id="f2172-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-136">xs:string</span></span>|<span data-ttu-id="f2172-137">プロキシ サーバーで認証用のユーザー パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-137">Specifies the user password for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="f2172-138">**UnknownHeaders**</span><span class="sxs-lookup"><span data-stu-id="f2172-138">**UnknownHeaders**</span></span>|<span data-ttu-id="f2172-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-139">xs:string</span></span>|<span data-ttu-id="f2172-140">不明な SOAP ヘッダーのシリアル化された一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-140">Specifies the serialized list of unknown SOAP headers.</span></span>|  
|<span data-ttu-id="f2172-141">**AffiliateApplicationName**</span><span class="sxs-lookup"><span data-stu-id="f2172-141">**AffiliateApplicationName**</span></span>|<span data-ttu-id="f2172-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-142">xs:string</span></span>|<span data-ttu-id="f2172-143">SSO に使用する関連アプリケーションの名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="f2172-143">Defines the name of the affiliate application to use for SSO.</span></span>|  
|<span data-ttu-id="f2172-144">**AuthenticationScheme**</span><span class="sxs-lookup"><span data-stu-id="f2172-144">**AuthenticationScheme**</span></span>|<span data-ttu-id="f2172-145">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-145">xs:string</span></span>|<span data-ttu-id="f2172-146">移行先サーバーで使用する認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-146">Specifies the type of authentication to use with the destination server.</span></span>|  
|<span data-ttu-id="f2172-147">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="f2172-147">**UseSSO**</span></span>|<span data-ttu-id="f2172-148">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="f2172-148">xs:boolean</span></span>|<span data-ttu-id="f2172-149">SOAP アダプタで送信ポートに SSO を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-149">Specifies whether the SOAP adapter uses SSO for the send port.</span></span>|  
|<span data-ttu-id="f2172-150">**UseHandlerSetting**</span><span class="sxs-lookup"><span data-stu-id="f2172-150">**UseHandlerSetting**</span></span>|<span data-ttu-id="f2172-151">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="f2172-151">xs:boolean</span></span>|<span data-ttu-id="f2172-152">SOAP 送信ポートでハンドラのプロキシ構成を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-152">Specifies whether the SOAP send port uses the proxy configuration for the handler.</span></span>|  
|<span data-ttu-id="f2172-153">**ClientConnectionTimeout**</span><span class="sxs-lookup"><span data-stu-id="f2172-153">**ClientConnectionTimeout**</span></span>|<span data-ttu-id="f2172-154">xs:int</span><span class="sxs-lookup"><span data-stu-id="f2172-154">xs:int</span></span>|<span data-ttu-id="f2172-155">サーバーからの応答を待機する際のタイムアウト期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-155">Specifies the time-out period of waiting for a response from the server.</span></span> <span data-ttu-id="f2172-156">ゼロ (0) に設定すると、システムは要求メッセージのサイズに基づくタイムアウト値を計算します。</span><span class="sxs-lookup"><span data-stu-id="f2172-156">If set to zero (0), the system will calculate the time-out based on the request message size.</span></span>|  
|<span data-ttu-id="f2172-157">**UserDefined**</span><span class="sxs-lookup"><span data-stu-id="f2172-157">**UserDefined**</span></span>|<span data-ttu-id="f2172-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2172-158">xs:string</span></span>|<span data-ttu-id="f2172-159">ユーザー定義のクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2172-159">Defines user-defined classes.</span></span>|  
|<span data-ttu-id="f2172-160">**UseSoap12**</span><span class="sxs-lookup"><span data-stu-id="f2172-160">**UseSoap12**</span></span>|<span data-ttu-id="f2172-161">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="f2172-161">xs:boolean</span></span>|<span data-ttu-id="f2172-162">SOAP 1.2 プロトコルをサポートするプロキシ コードを生成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2172-162">Specifies whether to generate proxy code that supports the SOAP 1.2 protocol.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2172-163">参照</span><span class="sxs-lookup"><span data-stu-id="f2172-163">See Also</span></span>  
 [<span data-ttu-id="f2172-164">SOAP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="f2172-164">Configuring the SOAP Adapter</span></span>](../core/configuring-the-soap-adapter.md)
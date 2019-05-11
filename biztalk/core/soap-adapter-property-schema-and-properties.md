---
title: SOAP アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
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
ms.openlocfilehash: 681a7f529d1326b3301a5cc09dc31e94c8bfbb96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314052"
---
# <a name="soap-adapter-property-schema-and-properties"></a><span data-ttu-id="f3b73-102">SOAP アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="f3b73-102">SOAP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="f3b73-103">次の表は、SOAP アダプタ プロパティ スキーマのプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-103">The following table lists the properties in the SOAP adapter property schema.</span></span>  
  
 <span data-ttu-id="f3b73-104">**名前空間:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span><span class="sxs-lookup"><span data-stu-id="f3b73-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span></span>  
  
|<span data-ttu-id="f3b73-105">名前</span><span class="sxs-lookup"><span data-stu-id="f3b73-105">Name</span></span>|<span data-ttu-id="f3b73-106">型</span><span class="sxs-lookup"><span data-stu-id="f3b73-106">Type</span></span>|<span data-ttu-id="f3b73-107">説明</span><span class="sxs-lookup"><span data-stu-id="f3b73-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="f3b73-108">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="f3b73-108">**AssemblyName**</span></span>|<span data-ttu-id="f3b73-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-109">xs:string</span></span>|<span data-ttu-id="f3b73-110">読み込んで実行する .NET 型およびアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-110">Identifies the .NET type and assembly to be loaded and executed.</span></span>|  
|<span data-ttu-id="f3b73-111">**MethodName**</span><span class="sxs-lookup"><span data-stu-id="f3b73-111">**MethodName**</span></span>|<span data-ttu-id="f3b73-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-112">xs:string</span></span>|<span data-ttu-id="f3b73-113">対象のメソッドを呼び出す .NET アセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-113">Identifies the target method on the .NET assembly that is to be invoked.</span></span>|  
|<span data-ttu-id="f3b73-114">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="f3b73-114">**Username**</span></span>|<span data-ttu-id="f3b73-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-115">xs:string</span></span>|<span data-ttu-id="f3b73-116">サーバーで認証に使用するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="f3b73-116">User name to use for authentication with the server.</span></span>|  
|<span data-ttu-id="f3b73-117">**Password**</span><span class="sxs-lookup"><span data-stu-id="f3b73-117">**Password**</span></span>|<span data-ttu-id="f3b73-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-118">xs:string</span></span>|<span data-ttu-id="f3b73-119">サーバーでの認証に使用するユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="f3b73-119">User password to use for authentication with the server.</span></span>|  
|<span data-ttu-id="f3b73-120">**ClientCertificate**</span><span class="sxs-lookup"><span data-stu-id="f3b73-120">**ClientCertificate**</span></span>|<span data-ttu-id="f3b73-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-121">xs:string</span></span>|<span data-ttu-id="f3b73-122">SSL クライアント証明書の拇印。</span><span class="sxs-lookup"><span data-stu-id="f3b73-122">Thumbprint of the client SSL certificate.</span></span>|  
|<span data-ttu-id="f3b73-123">**UseProxy**</span><span class="sxs-lookup"><span data-stu-id="f3b73-123">**UseProxy**</span></span>|<span data-ttu-id="f3b73-124">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="f3b73-124">xs:Boolean</span></span>|<span data-ttu-id="f3b73-125">SOAP アダプターでプロキシ サーバーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-125">Specifies whether the SOAP adapter uses a proxy server.</span></span>|  
|<span data-ttu-id="f3b73-126">**ProxyAddress**</span><span class="sxs-lookup"><span data-stu-id="f3b73-126">**ProxyAddress**</span></span>|<span data-ttu-id="f3b73-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-127">xs:string</span></span>|<span data-ttu-id="f3b73-128">プロキシ サーバーのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-128">Specifies the proxy server address.</span></span>|  
|<span data-ttu-id="f3b73-129">**ProxyPort**</span><span class="sxs-lookup"><span data-stu-id="f3b73-129">**ProxyPort**</span></span>|<span data-ttu-id="f3b73-130">xs:int</span><span class="sxs-lookup"><span data-stu-id="f3b73-130">xs:int</span></span>|<span data-ttu-id="f3b73-131">プロキシ サーバーのポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-131">Specifies the proxy server port.</span></span>|  
|<span data-ttu-id="f3b73-132">**ProxyUsername**</span><span class="sxs-lookup"><span data-stu-id="f3b73-132">**ProxyUsername**</span></span>|<span data-ttu-id="f3b73-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-133">xs:string</span></span>|<span data-ttu-id="f3b73-134">プロキシ サーバーで認証のユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-134">Specifies the user name for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="f3b73-135">**ProxyPassword**</span><span class="sxs-lookup"><span data-stu-id="f3b73-135">**ProxyPassword**</span></span>|<span data-ttu-id="f3b73-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-136">xs:string</span></span>|<span data-ttu-id="f3b73-137">プロキシ サーバーで認証のユーザーのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-137">Specifies the user password for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="f3b73-138">**UnknownHeaders**</span><span class="sxs-lookup"><span data-stu-id="f3b73-138">**UnknownHeaders**</span></span>|<span data-ttu-id="f3b73-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-139">xs:string</span></span>|<span data-ttu-id="f3b73-140">不明な SOAP ヘッダーのシリアル化された一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-140">Specifies the serialized list of unknown SOAP headers.</span></span>|  
|<span data-ttu-id="f3b73-141">**AffiliateApplicationName**</span><span class="sxs-lookup"><span data-stu-id="f3b73-141">**AffiliateApplicationName**</span></span>|<span data-ttu-id="f3b73-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-142">xs:string</span></span>|<span data-ttu-id="f3b73-143">SSO に使用する関連アプリケーションの名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-143">Defines the name of the affiliate application to use for SSO.</span></span>|  
|<span data-ttu-id="f3b73-144">**AuthenticationScheme**</span><span class="sxs-lookup"><span data-stu-id="f3b73-144">**AuthenticationScheme**</span></span>|<span data-ttu-id="f3b73-145">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-145">xs:string</span></span>|<span data-ttu-id="f3b73-146">移行先サーバーで使用する認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-146">Specifies the type of authentication to use with the destination server.</span></span>|  
|<span data-ttu-id="f3b73-147">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="f3b73-147">**UseSSO**</span></span>|<span data-ttu-id="f3b73-148">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="f3b73-148">xs:boolean</span></span>|<span data-ttu-id="f3b73-149">SOAP アダプターが送信ポートの SSO を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-149">Specifies whether the SOAP adapter uses SSO for the send port.</span></span>|  
|<span data-ttu-id="f3b73-150">**UseHandlerSetting**</span><span class="sxs-lookup"><span data-stu-id="f3b73-150">**UseHandlerSetting**</span></span>|<span data-ttu-id="f3b73-151">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="f3b73-151">xs:boolean</span></span>|<span data-ttu-id="f3b73-152">SOAP 送信ポートが、ハンドラーのプロキシ構成を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-152">Specifies whether the SOAP send port uses the proxy configuration for the handler.</span></span>|  
|<span data-ttu-id="f3b73-153">**ClientConnectionTimeout**</span><span class="sxs-lookup"><span data-stu-id="f3b73-153">**ClientConnectionTimeout**</span></span>|<span data-ttu-id="f3b73-154">xs:int</span><span class="sxs-lookup"><span data-stu-id="f3b73-154">xs:int</span></span>|<span data-ttu-id="f3b73-155">サーバーからの応答の待機のタイムアウト期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-155">Specifies the time-out period of waiting for a response from the server.</span></span> <span data-ttu-id="f3b73-156">ゼロ (0) に設定すると、システムは要求メッセージのサイズに基づいて、タイムアウトを計算します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-156">If set to zero (0), the system will calculate the time-out based on the request message size.</span></span>|  
|<span data-ttu-id="f3b73-157">**UserDefined**</span><span class="sxs-lookup"><span data-stu-id="f3b73-157">**UserDefined**</span></span>|<span data-ttu-id="f3b73-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3b73-158">xs:string</span></span>|<span data-ttu-id="f3b73-159">ユーザー定義のクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-159">Defines user-defined classes.</span></span>|  
|<span data-ttu-id="f3b73-160">**UseSoap12**</span><span class="sxs-lookup"><span data-stu-id="f3b73-160">**UseSoap12**</span></span>|<span data-ttu-id="f3b73-161">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="f3b73-161">xs:boolean</span></span>|<span data-ttu-id="f3b73-162">SOAP 1.2 プロトコルをサポートするプロキシ コードを生成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b73-162">Specifies whether to generate proxy code that supports the SOAP 1.2 protocol.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3b73-163">参照</span><span class="sxs-lookup"><span data-stu-id="f3b73-163">See Also</span></span>  
 [<span data-ttu-id="f3b73-164">SOAP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="f3b73-164">Configuring the SOAP Adapter</span></span>](../core/configuring-the-soap-adapter.md)
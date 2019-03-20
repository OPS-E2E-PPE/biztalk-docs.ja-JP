---
title: WCF アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2093745e-86c0-4276-a7cc-a0187391ca4a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10781e8743eeea68ff0be8993b3588d5ecd204d7
ms.sourcegitcommit: 0e14c3e018b091d81d0e4a68fafc10f6e31697e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "29139298"
---
# <a name="wcf-adapters-property-schema-and-properties"></a><span data-ttu-id="d76d6-102">WCF アダプタ プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="d76d6-102">WCF Adapters Property Schema and Properties</span></span>
<span data-ttu-id="d76d6-103">WCF アダプタ プロパティ スキーマの昇格させたプロパティをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-103">Read about the promoted properties in the WCF adapter property schema.</span></span> <span data-ttu-id="d76d6-104">WCF アダプタは、アプリケーションで使用できるプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-104">The WCF adapters assign values to the properties that you can use in your application.</span></span> <span data-ttu-id="d76d6-105">また、WCF アダプタは、カスタム プロパティを BizTalk メッセージ コンテキストに書き込むが昇格させないメカニズムと、カスタム プロパティを BizTalk メッセージ コンテキストに昇格させるメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-105">WCF adapter also provides a mechanism to write but not promote the custom properties to the BizTalk message context, and a mechanism to promote the custom properties to the BizTalk message context.</span></span> <span data-ttu-id="d76d6-106">詳細については、次を参照してください。[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-106">For more details, see [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md).</span></span>  

## <a name="promoted-properties"></a><span data-ttu-id="d76d6-107">昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="d76d6-107">Promoted properties</span></span>  
<span data-ttu-id="d76d6-108">**名前空間:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties</span><span class="sxs-lookup"><span data-stu-id="d76d6-108">**Namespace:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties</span></span>  

#### <a name="action"></a><span data-ttu-id="d76d6-109">操作</span><span class="sxs-lookup"><span data-stu-id="d76d6-109">Action</span></span>
<span data-ttu-id="d76d6-110">指定、 **SOAPAction**送信メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="d76d6-110">Specify the **SOAPAction** header field for outgoing messages.</span></span> <span data-ttu-id="d76d6-111">2 つの方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式。</span><span class="sxs-lookup"><span data-stu-id="d76d6-111">You can specify this value in two different ways: the single action format and the action mapping format.</span></span> <span data-ttu-id="d76d6-112">シングル アクション形式では、このプロパティを設定するかどうか: たとえば、 http://contoso.com/Svc/Op1 —、 **SOAPAction**このプロパティで指定された値を設定は常に送信メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d76d6-112">If you set this property in the single action format—for example, http://contoso.com/Svc/Op1 — the **SOAPAction** header for outgoing messages is always set to the value specified in this property.</span></span>

<span data-ttu-id="d76d6-113">送信アクション マッピング形式でこのプロパティを設定する場合**SOAPAction**ヘッダーはによって決定されます、 **BTS します。操作**コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d76d6-113">If you set this property in the action mapping format, the outgoing **SOAPAction** header is determined by the **BTS.Operation** context property.</span></span> <span data-ttu-id="d76d6-114">たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**を Op1 に設定されているプロパティ、WCF 送信アダプタを使用して `http://contoso.com/Svc/Op1` アウトゴーイング**SOAPAction**ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d76d6-114">For example, if this property is set to the following XML format and the **BTS.Operation** property is set to Op1, the WCF send adapter uses `http://contoso.com/Svc/Op1` for the outgoing **SOAPAction** header.</span></span>

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

<span data-ttu-id="d76d6-115">送信メッセージがオーケストレーション ポートに由来する場合、オーケストレーション インスタンスは動的に設定、 **BTS します。操作**ポートの操作の名前を持つプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d76d6-115">If outgoing messages come from an orchestration port, orchestration instances dynamically set the **BTS.Operation** property with the operation name of the port.</span></span> <span data-ttu-id="d76d6-116">設定することができますコンテンツ ベースのルーティングでは、送信メッセージがルーティングされている場合、 **BTS します。操作**パイプライン コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d76d6-116">If outgoing messages are routed with content-based routing, you can set the **BTS.Operation** property in pipeline components.</span></span>
<span data-ttu-id="d76d6-117">このプロパティは、シングル アクション形式で受信したメッセージから自動的に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-117">This property is automatically promoted from incoming messages with the single action format.</span></span>

<span data-ttu-id="d76d6-118">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-118">Type: String</span></span>  
<span data-ttu-id="d76d6-119">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-119">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-120">適用対象すべての WCF 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-120">Applies to: All WCF send adapters</span></span>

#### <a name="affiliateapplicationname"></a><span data-ttu-id="d76d6-121">AffiliateApplicationName</span><span class="sxs-lookup"><span data-stu-id="d76d6-121">AffiliateApplicationName</span></span>
<span data-ttu-id="d76d6-122">エンタープライズ シングル サインオン (SSO) に使用する関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-122">Specify the affiliate application to use for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="d76d6-123">このプロパティは必要な場合、 **UseSSO**プロパティに設定されて**True**。</span><span class="sxs-lookup"><span data-stu-id="d76d6-123">This property is required if the **UseSSO** property is set to **True**.</span></span> 

<span data-ttu-id="d76d6-124">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-124">Type: String</span></span>  
<span data-ttu-id="d76d6-125">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-125">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-126">適用対象すべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-126">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="algorithmsuite"></a><span data-ttu-id="d76d6-127">AlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="d76d6-127">AlgorithmSuite</span></span>
<span data-ttu-id="d76d6-128">メッセージの暗号化とキー ラップのアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-128">Specify the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="d76d6-129">これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-129">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>

<span data-ttu-id="d76d6-130">適用可能な値の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティ、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-130">For more information about the applicable values for the **AlgorithmSuite** property, see the **Algorithm suite** property in the **WCF-NetTcp Transport Properties Dialog Box, Send, Security** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="d76d6-131">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-131">Type: String</span></span>  
<span data-ttu-id="d76d6-132">既定値:**Basic256**</span><span class="sxs-lookup"><span data-stu-id="d76d6-132">Default value: **Basic256**</span></span>  
<span data-ttu-id="d76d6-133">適用対象</span><span class="sxs-lookup"><span data-stu-id="d76d6-133">Applies to:</span></span> 

- <span data-ttu-id="d76d6-134">Wcf-basichttp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-134">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="d76d6-135">Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-135">WCF-NetMsmq adapter</span></span>
- <span data-ttu-id="d76d6-136">WCF-NetTcp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-136">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="d76d6-137">WCF-WSHttp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-137">WCF-WSHttp adapter</span></span>

#### <a name="bindingconfiguration"></a><span data-ttu-id="d76d6-138">BindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d76d6-138">BindingConfiguration</span></span>
<span data-ttu-id="d76d6-139">XML 文字列を指定、 **\<バインド\>** さまざまな種類の構成要素の定義済みの Windows Communication Foundation (WCF) によって提供されるバインディング。</span><span class="sxs-lookup"><span data-stu-id="d76d6-139">Specify an XML string with the **\<binding\>** element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="d76d6-140">システム指定のバインディングとカスタム バインドの詳細については、「参照」の該当するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d76d6-140">For more information about the system-provided binding and custom binding, see the appropriate topics in See Also.</span></span>

<span data-ttu-id="d76d6-141">例:</span><span class="sxs-lookup"><span data-stu-id="d76d6-141">Example:</span></span>

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

<span data-ttu-id="d76d6-142">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-142">Type: String</span></span>  
<span data-ttu-id="d76d6-143">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-143">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-144">適用対象WCF カスタム アダプター、Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-144">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="bindingtype"></a><span data-ttu-id="d76d6-145">BindingType</span><span class="sxs-lookup"><span data-stu-id="d76d6-145">BindingType</span></span>
<span data-ttu-id="d76d6-146">エンドポイントに使用するバインドの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-146">Specify the type of the binding to use for the endpoint.</span></span> <span data-ttu-id="d76d6-147">適用可能な値の詳細については、 **BindingType**プロパティを参照してください、**バインドの種類**プロパティ、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックスの送信、バインド**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-147">For more information about the applicable values for the **BindingType** property, see the **Binding Type** property in the **WCF-Custom Transport Properties Dialog Box, Send, Binding** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="d76d6-148">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-148">Type: String</span></span>  
<span data-ttu-id="d76d6-149">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-149">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-150">適用対象WCF カスタム アダプター、Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-150">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="clientcertificate"></a><span data-ttu-id="d76d6-151">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="d76d6-151">ClientCertificate</span></span>
<span data-ttu-id="d76d6-152">この送信ポートをサービスに対して認証する際に使用する X.509 証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-152">Specify the thumbprint of the X.509 certificate for authenticating this send port to services.</span></span> <span data-ttu-id="d76d6-153">このプロパティは必要な場合、 **ClientCredentialsType**プロパティに設定されて**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-153">This property is required if the **ClientCredentialsType** property is set to **Certificate**.</span></span> <span data-ttu-id="d76d6-154">このプロパティに使用する証明書をインストールする必要があります、**マイ**で格納、**現在のユーザー**場所。</span><span class="sxs-lookup"><span data-stu-id="d76d6-154">The certificate to be used for this property must be installed into the **My** store in the **Current User** location.</span></span>

<span data-ttu-id="d76d6-155">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-155">Type: String</span></span>  
<span data-ttu-id="d76d6-156">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-156">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-157">適用対象</span><span class="sxs-lookup"><span data-stu-id="d76d6-157">Applies to:</span></span> 

- <span data-ttu-id="d76d6-158">WCF-BasicHttp 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-158">WCF-BasicHttp send adapter</span></span>
- <span data-ttu-id="d76d6-159">WCF-WSHttp 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-159">WCF-WSHttp send adapter</span></span>
- <span data-ttu-id="d76d6-160">Wcf-nettcp 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-160">WCF-NetTcp send adapter</span></span>
- <span data-ttu-id="d76d6-161">Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-161">WCF-NetMsmq send adapter</span></span>

#### <a name="closetimeout"></a><span data-ttu-id="d76d6-162">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="d76d6-162">CloseTimeout</span></span>
<span data-ttu-id="d76d6-163">チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-163">Specify a time span value that indicates the interval of time provided for a channel close operation to complete.</span></span>

<span data-ttu-id="d76d6-164">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-164">Type: String</span></span>  
<span data-ttu-id="d76d6-165">既定値:00:01:00</span><span class="sxs-lookup"><span data-stu-id="d76d6-165">Default value: 00:01:00</span></span>  
<span data-ttu-id="d76d6-166">適用対象すべての WCF アダプター*を除く*Wcf-custom および Wcf-customisolated</span><span class="sxs-lookup"><span data-stu-id="d76d6-166">Applies to: All WCF adapters *except* WCF-Custom and WCF-CustomIsolated</span></span>

#### <a name="customdeadletterqueue"></a><span data-ttu-id="d76d6-167">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="d76d6-167">CustomDeadLetterQueue</span></span>
<span data-ttu-id="d76d6-168">完全修飾 URI を指定、 **net.msmq**期限切れになったか、転送または配信に失敗したメッセージが置かれて、アプリケーションごとの配信不能キューの場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-168">Specify the fully qualified URI with the **net.msmq** scheme for the location of the per-application dead-letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span> <span data-ttu-id="d76d6-169">たとえば、net.msmq://localhost/deadLetterQueueName と指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-169">For example, net.msmq://localhost/deadLetterQueueName.</span></span> <span data-ttu-id="d76d6-170">配信不能キューは、配信に失敗した期限切れのメッセージの送信アプリケーションのキュー マネージャのキューです。</span><span class="sxs-lookup"><span data-stu-id="d76d6-170">The dead-letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span> <span data-ttu-id="d76d6-171">このプロパティは必要な場合、 **DeadLetterQueue**プロパティに設定されて**カスタム**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-171">This property is required if the **DeadLetterQueue** property is set to **Custom**.</span></span>

<span data-ttu-id="d76d6-172">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-172">Type: String</span></span>  
<span data-ttu-id="d76d6-173">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-173">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-174">適用対象Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-174">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="deadletterqueue"></a><span data-ttu-id="d76d6-175">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="d76d6-175">DeadLetterQueue</span></span>
<span data-ttu-id="d76d6-176">アプリケーションへの配信に失敗したメッセージの転送先となる配信不能キューを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-176">Specify the dead-letter queue where messages that have failed to be delivered to the application will be transferred.</span></span> <span data-ttu-id="d76d6-177">配信不能キューに配信されたメッセージの詳細については、次を参照してください。、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックスの送信、バインド**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-177">For more information about the messages delivered to the dead-letter queue, see the **WCF-NetMsmq Transport Properties Dialog Box, Send, Binding** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="d76d6-178">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-178">Type: String</span></span>  
<span data-ttu-id="d76d6-179">既定値:**システム**</span><span class="sxs-lookup"><span data-stu-id="d76d6-179">Default value: **System**</span></span>  
<span data-ttu-id="d76d6-180">適用対象Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-180">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="disablelocationonfailure"></a><span data-ttu-id="d76d6-181">DisableLocationOnFailure</span><span class="sxs-lookup"><span data-stu-id="d76d6-181">DisableLocationOnFailure</span></span>
<span data-ttu-id="d76d6-182">受信パイプラインまたはルーティングの障害によって受信処理に失敗した受信場所を無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-182">Specify whether to disable the receive location that fails inbound processing due to a receive pipeline failure or a routing failure.</span></span> <span data-ttu-id="d76d6-183">このプロパティを設定する**True**を受信するタイミングの場所を無効にすることができ、サービス拒否 (DoS) は問題になりません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-183">You may want to set this property to **True** when receive locations can be disabled and Denial-of-Service (DoS) is not a concern.</span></span>

<span data-ttu-id="d76d6-184">例 :</span><span class="sxs-lookup"><span data-stu-id="d76d6-184">For example:</span></span>  
- <span data-ttu-id="d76d6-185">WCF-Custom アダプター: ときに、 **BindingType**プロパティに設定されて**netMsmqBinding**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-185">WCF-Custom adapter: When the **BindingType** property is set to **netMsmqBinding**.</span></span>
- <span data-ttu-id="d76d6-186">WCF-Custom アダプター: ときに、 **BindingType**プロパティに設定されて**customBinding**、および**BindingConfiguration**プロパティを構成してキューに置かれたトランスポートに依存するカスタム チャネルを使用するにはMSMQ など。</span><span class="sxs-lookup"><span data-stu-id="d76d6-186">WCF-Custom adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on queued transports such as MSMQ.</span></span>
- <span data-ttu-id="d76d6-187">WCF-CustomIsolated アダプター: ときに、 **BindingType**プロパティに設定されて**customBinding**、および**BindingConfiguration**プロパティを構成してキューに置かれたトランスポートに依存するカスタム チャネルを使用するにはMSMQ など</span><span class="sxs-lookup"><span data-stu-id="d76d6-187">WCF-CustomIsolated adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on queued transports such as MSMQ</span></span>
- <span data-ttu-id="d76d6-188">Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-188">WCF-NetMsmq adapter</span></span>

<span data-ttu-id="d76d6-189">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-189">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-190">既定値:**False**</span><span class="sxs-lookup"><span data-stu-id="d76d6-190">Default: **False**</span></span>  
<span data-ttu-id="d76d6-191">適用対象</span><span class="sxs-lookup"><span data-stu-id="d76d6-191">Applies to:</span></span>  
- <span data-ttu-id="d76d6-192">Wcf-netmsmq 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-192">WCF-NetMsmq receive adapter</span></span>
- <span data-ttu-id="d76d6-193">Wcf-custom 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-193">WCF-Custom receive adapter</span></span>
- <span data-ttu-id="d76d6-194">WCF-CustomIsolated 受信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-194">WCF-CustomIsolated receive adapter</span></span>

#### <a name="enabletransaction"></a><span data-ttu-id="d76d6-195">EnableTransaction</span><span class="sxs-lookup"><span data-stu-id="d76d6-195">EnableTransaction</span></span>
<span data-ttu-id="d76d6-196">このプロパティの効果は、WCF アダプタによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d76d6-196">The effect of this property varies depending on the WCF adapter.</span></span> <span data-ttu-id="d76d6-197">このプロパティの詳細については、の各 WCF アダプタの操作方法に関するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-197">For more information about this property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="d76d6-198">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-198">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-199">適用対象</span><span class="sxs-lookup"><span data-stu-id="d76d6-199">Applies to:</span></span> 

- <span data-ttu-id="d76d6-200">WCF-WSHttp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-200">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="d76d6-201">WCF-NetTcp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-201">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="d76d6-202">Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-202">WCF-NetNamedPipe adapter</span></span>
- <span data-ttu-id="d76d6-203">Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-203">WCF-NetMsmq adapter</span></span>

#### <a name="endpointbehaviorconfiguration"></a><span data-ttu-id="d76d6-204">EndpointBehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d76d6-204">EndpointBehaviorConfiguration</span></span>
<span data-ttu-id="d76d6-205">XML 文字列を指定、 **\<動作\>** の要素、 **\<endpointBehaviors\>** の動作の設定を構成するのには、WCF エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="d76d6-205">Specify an XML string with the **\<behavior\>** element of the **\<endpointBehaviors\>** element to configure the behavior settings of a WCF endpoint.</span></span> <span data-ttu-id="d76d6-206">詳細については、 **\<endpointBehaviors\>** 要素では、「も該当するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d76d6-206">For more information about the **\<endpointBehaviors\>** element, see the appropriate topic in See Also.</span></span>

<span data-ttu-id="d76d6-207">例:</span><span class="sxs-lookup"><span data-stu-id="d76d6-207">Example:</span></span> 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

<span data-ttu-id="d76d6-208">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-208">Type: String</span></span>  
<span data-ttu-id="d76d6-209">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-209">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-210">適用対象Wcf-custom 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-210">Applies to: WCF-Custom send adapter</span></span>

#### <a name="establishsecuritycontext"></a><span data-ttu-id="d76d6-211">EstablishSecurityContext</span><span class="sxs-lookup"><span data-stu-id="d76d6-211">EstablishSecurityContext</span></span>
<span data-ttu-id="d76d6-212">セキュリティ チャネルで、セキュリティで保護されたセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-212">Specify whether the security channel establishes a secure session.</span></span> <span data-ttu-id="d76d6-213">セキュリティで保護されたセッションでは、アプリケーションのメッセージを交換する前に、セキュリティ コンテキスト トークン (SCT) が確立されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-213">A secure session establishes a Security Context Token (SCT) before exchanging the application messages.</span></span>

<span data-ttu-id="d76d6-214">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-214">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-215">既定値:True</span><span class="sxs-lookup"><span data-stu-id="d76d6-215">Default value: True</span></span>  
<span data-ttu-id="d76d6-216">適用されます。WCF-WSHttp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-216">Applied to: WCF-WSHttp adapter</span></span>

#### <a name="fromaddress"></a><span data-ttu-id="d76d6-217">FromAddress</span><span class="sxs-lookup"><span data-stu-id="d76d6-217">FromAddress</span></span>
<span data-ttu-id="d76d6-218">受信 WCF メッセージの送信元のエンドポイント アドレスを示します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-218">Indicate the source endpoint address through which the incoming WCF messages are sent.</span></span> <span data-ttu-id="d76d6-219">このプロパティは、受信メッセージから自動的に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-219">The property is automatically promoted from incoming messages.</span></span>

<span data-ttu-id="d76d6-220">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-220">Type: String</span></span>  
<span data-ttu-id="d76d6-221">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-221">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>
  
#### <a name="headers"></a><span data-ttu-id="d76d6-222">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="d76d6-222">Headers</span></span>
<span data-ttu-id="d76d6-223">URI 以外の追加アドレス指定情報を提供するエンドポイント参照を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-223">Specify the endpoint references used to provide additional addressing information beyond the URI.</span></span> <span data-ttu-id="d76d6-224">このプロパティを使用すると、このプロパティが必要、 \<**ヘッダー** \>ルート要素としての要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-224">When this property is used, this property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="d76d6-225">内ですべてのアドレス ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-225">All of the address headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="d76d6-226">このプロパティは、受信メッセージに自動的に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-226">This property is automatically promoted for incoming messages.</span></span>

<span data-ttu-id="d76d6-227">例:</span><span class="sxs-lookup"><span data-stu-id="d76d6-227">Example:</span></span>
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

<span data-ttu-id="d76d6-228">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-228">Type: String</span></span>  
<span data-ttu-id="d76d6-229">適用対象すべての WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-229">Applies to: All WCF adapters</span></span>
  
#### <a name="identity"></a><span data-ttu-id="d76d6-230">同一。</span><span class="sxs-lookup"><span data-stu-id="d76d6-230">Identity</span></span>
<span data-ttu-id="d76d6-231">受信場所が提供するか、送信ポートが必要とするサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-231">Specify the identity of the service that a receive location provides or a send port expects.</span></span> <span data-ttu-id="d76d6-232">指定できる値、 **Identity**プロパティは、セキュリティの構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d76d6-232">The values that can be specified for the **Identity** property differ according to the security configuration.</span></span> <span data-ttu-id="d76d6-233">これらの設定により、クライアントがサービスを認証できます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-233">These settings enable clients to authenticate services.</span></span> <span data-ttu-id="d76d6-234">クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、クライアントの値とサービスの ID が照合されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-234">In the handshake process between clients and services, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the services matches the values of the clients.</span></span>

<span data-ttu-id="d76d6-235">例:</span><span class="sxs-lookup"><span data-stu-id="d76d6-235">Example:</span></span>
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

<span data-ttu-id="d76d6-236">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-236">Type: String</span></span>  
<span data-ttu-id="d76d6-237">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-237">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-238">適用対象すべての WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-238">Applies to: All WCF adapters</span></span>

#### <a name="inboundbodylocation"></a><span data-ttu-id="d76d6-239">InboundBodyLocation</span><span class="sxs-lookup"><span data-stu-id="d76d6-239">InboundBodyLocation</span></span>
<span data-ttu-id="d76d6-240">SOAP データ選択を指定**本文**受信 WCF メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-240">Specify the data selection for the SOAP **Body** element of incoming WCF messages.</span></span> <span data-ttu-id="d76d6-241">使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-241">For more information about how to use the **InboundBodyLocation** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="d76d6-242">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-242">Type: String</span></span>  
<span data-ttu-id="d76d6-243">既定値:UseBodyElement</span><span class="sxs-lookup"><span data-stu-id="d76d6-243">Default value: UseBodyElement</span></span>  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

<span data-ttu-id="d76d6-244">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信</span><span class="sxs-lookup"><span data-stu-id="d76d6-244">Applies to: All WCF adapters *except* WCF-NetMsmq send</span></span>  

#### <a name="inboundbodypathexpression"></a><span data-ttu-id="d76d6-245">InboundBodyPathExpression</span><span class="sxs-lookup"><span data-stu-id="d76d6-245">InboundBodyPathExpression</span></span>
<span data-ttu-id="d76d6-246">BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-246">Specify the body path expression to identify a specific part of an incoming message used to create the BizTalk message body part.</span></span> <span data-ttu-id="d76d6-247">このボディ パス式は、SOAP の直接の子要素に対して評価される**本文**受信メッセージのノード。</span><span class="sxs-lookup"><span data-stu-id="d76d6-247">This body path expression is evaluated against the immediate child element of the SOAP **Body** node of an incoming message.</span></span> <span data-ttu-id="d76d6-248">このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-248">If this body path expression returns more than one node, only the first node is chosen for the BizTalk message body part.</span></span> <span data-ttu-id="d76d6-249">このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されて**UseBodyPath**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-249">This property is required if the **InboundBodyLocation** property is set to **UseBodyPath**.</span></span> <span data-ttu-id="d76d6-250">使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-250">For more information about how to use the **InboundBodyPathExpression** property, see [WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md).</span></span>

<span data-ttu-id="d76d6-251">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-251">Type: String</span></span>  
<span data-ttu-id="d76d6-252">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-252">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-253">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-253">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="inboundheaders"></a><span data-ttu-id="d76d6-254">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="d76d6-254">InboundHeaders</span></span>
<span data-ttu-id="d76d6-255">使用して、 **InboundHeaders**受信 WCF メッセージの SOAP ヘッダーにアクセスするプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d76d6-255">Use the **InboundHeaders** property to access the SOAP headers of incoming WCF messages.</span></span> <span data-ttu-id="d76d6-256">WCF アダプタは、このプロパティに受信メッセージのすべての SOAP ヘッダー値をコピーします。このヘッダー値には、WCF インフラストラクチャが WS-Addressing、WS-Security、WS-AtomicTransaction などに使用するカスタム SOAP ヘッダーおよび標準 SOAP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d76d6-256">The WCF adapters copy all the SOAP header values in inbound messages to this property, which include custom SOAP headers and standard SOAP headers that the WCF infrastructure uses for such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="d76d6-257">コンテキスト プロパティに含まれる値は、XML データを格納している文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-257">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="d76d6-258">WCF アダプタで SOAP ヘッダーをアクセスする方法の詳細についてから、WCF アダプタでのカスタム SOAP ヘッダーの使用の SDK サンプルを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-258">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>

<span data-ttu-id="d76d6-259">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-259">Type: String</span></span>  
<span data-ttu-id="d76d6-260">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-260">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="inboundnodeencoding"></a><span data-ttu-id="d76d6-261">InboundNodeEncoding</span><span class="sxs-lookup"><span data-stu-id="d76d6-261">InboundNodeEncoding</span></span>
<span data-ttu-id="d76d6-262">WCF 受信アダプターで指定されたボディ パス式で識別されるノードのデコードに使用するエンコードの種類を指定**InboundBodyPathExpression**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-262">Specify the type of encoding that the WCF receive adapter uses to decode the node identified by the body path expression specified in **InboundBodyPathExpression**.</span></span> <span data-ttu-id="d76d6-263">このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されて**UseBodyPath**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-263">This property is required if the **InboundBodyLocation** property is set to **UseBodyPath**.</span></span>

<span data-ttu-id="d76d6-264">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-264">Type: String</span></span>  
<span data-ttu-id="d76d6-265">既定値:XML</span><span class="sxs-lookup"><span data-stu-id="d76d6-265">Default value: XML</span></span>  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

<span data-ttu-id="d76d6-266">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-266">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="isfault"></a><span data-ttu-id="d76d6-267">IsFault</span><span class="sxs-lookup"><span data-stu-id="d76d6-267">IsFault</span></span>
<span data-ttu-id="d76d6-268">SOAP エラー メッセージが受信されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-268">Indicate whether SOAP fault messages are received.</span></span> <span data-ttu-id="d76d6-269">このプロパティは、受信メッセージから自動的に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-269">The property is automatically promoted from incoming messages.</span></span> 

<span data-ttu-id="d76d6-270">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-270">**Note**</span></span>  
<span data-ttu-id="d76d6-271">**IsFault** HTTP 404 (ファイルまたはディレクトリが見つかりません) エラーなどのトランスポート エラーを受信したメッセージを確認するプロパティを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-271">The **IsFault** property cannot be used to check the received messages for transport errors such as the HTTP 404 (File or Directory Not Found) error.</span></span>

<span data-ttu-id="d76d6-272">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-272">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-273">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-273">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="leasetimeout"></a><span data-ttu-id="d76d6-274">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="d76d6-274">LeaseTimeout</span></span>
<span data-ttu-id="d76d6-275">アクティブなプールされた接続の最大有効期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-275">Specify the maximum lifetime of an active pooled connection.</span></span> <span data-ttu-id="d76d6-276">指定した時間が経過すると、現在の要求が処理された後、接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-276">After the specified time elapses, the connection closes after the current request is serviced.</span></span>

<span data-ttu-id="d76d6-277">Wcf-nettcp アダプターの活用、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)エンドポイントと通信するクラス。</span><span class="sxs-lookup"><span data-stu-id="d76d6-277">The WCF-NetTcp adapter leverages the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) class to communicate with an endpoint.</span></span> <span data-ttu-id="d76d6-278">使用する場合、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)負荷分散のシナリオで、既定のリース タイムアウトを減らすことを検討します。負荷分散を使用する場合の詳細については、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)、関連の適切なトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d76d6-278">When using the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) in load-balanced scenarios, consider reducing the default lease time-out. For more information about load balancing when using the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087), see the appropriate topic in See Also.</span></span>

<span data-ttu-id="d76d6-279">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-279">Type: String</span></span>  
<span data-ttu-id="d76d6-280">既定値:00:05:00</span><span class="sxs-lookup"><span data-stu-id="d76d6-280">Default value: 00:05:00</span></span>  
<span data-ttu-id="d76d6-281">適用対象WCF-NetTcp 受信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-281">Applies to: WCF-NetTcp receive adapter</span></span>  

#### <a name="maxconcurrentcalls"></a><span data-ttu-id="d76d6-282">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="d76d6-282">MaxConcurrentCalls</span></span>
<span data-ttu-id="d76d6-283">単一のサービス インスタンスに対する同時呼び出しの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-283">Specify the number of concurrent calls to a single service instance.</span></span> <span data-ttu-id="d76d6-284">制限を超える呼び出しはキューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-284">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="d76d6-285">この値を 0 に設定することは、 **Int32.MaxValue**に設定するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="d76d6-285">Setting this value to 0 is equivalent to setting it to **Int32.MaxValue**.</span></span> 

<span data-ttu-id="d76d6-286">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-286">**Note**</span></span>  
<span data-ttu-id="d76d6-287">このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-287">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="d76d6-288">型:Integer</span><span class="sxs-lookup"><span data-stu-id="d76d6-288">Type: Integer</span></span>  
<span data-ttu-id="d76d6-289">既定値:200</span><span class="sxs-lookup"><span data-stu-id="d76d6-289">Default value: 200</span></span>  
<span data-ttu-id="d76d6-290">適用対象すべての WCF 受信アダプタ*を除く*Wcf-custom および Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-290">Applies to: All WCF receive adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="maxconnections"></a><span data-ttu-id="d76d6-291">MaxConnections</span><span class="sxs-lookup"><span data-stu-id="d76d6-291">MaxConnections</span></span>
<span data-ttu-id="d76d6-292">リスナーが保持することができる、アプリケーションによる受け入れを待機する接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-292">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="d76d6-293">この数を超えた場合、新しい受信接続は受け入れを待機する代わりに削除されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-293">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> 

<span data-ttu-id="d76d6-294">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-294">**Note**</span></span>  
<span data-ttu-id="d76d6-295">これはアダプタ ハンドラ プロパティであるため、このプロパティはパイプライン コンポーネントおよびオーケストレーションでは構成できません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-295">Because this is an adapter handler property, this property cannot be configured in pipeline components and orchestrations.</span></span> 

<span data-ttu-id="d76d6-296">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-296">**Note**</span></span>  
<span data-ttu-id="d76d6-297">このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-297">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="d76d6-298">型:Integer</span><span class="sxs-lookup"><span data-stu-id="d76d6-298">Type: Integer</span></span>  
<span data-ttu-id="d76d6-299">既定値:10</span><span class="sxs-lookup"><span data-stu-id="d76d6-299">Default value: 10</span></span>  
<span data-ttu-id="d76d6-300">適用対象Wcf-netnamedpipe アダプター、Wcf-nettcp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-300">Applies to: WCF-NetNamedPipe adapter, WCF-NetTcp adapter</span></span>  

#### <a name="maxreceivedmessagesize"></a><span data-ttu-id="d76d6-301">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="d76d6-301">MaxReceivedMessageSize</span></span>
<span data-ttu-id="d76d6-302">有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-302">Specify the maximum size, in bytes, for a message (including headers) that can be received on the wire.</span></span> <span data-ttu-id="d76d6-303">メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-303">The size of the messages is bounded by the amount of memory allocated for each message.</span></span> <span data-ttu-id="d76d6-304">このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-304">You can use this property to limit exposure to denial of service (DoS) attacks.</span></span>

<span data-ttu-id="d76d6-305">型:Integer</span><span class="sxs-lookup"><span data-stu-id="d76d6-305">Type: Integer</span></span>  
<span data-ttu-id="d76d6-306">既定値:65536</span><span class="sxs-lookup"><span data-stu-id="d76d6-306">Default value: 65536</span></span>  
<span data-ttu-id="d76d6-307">適用対象</span><span class="sxs-lookup"><span data-stu-id="d76d6-307">Applies to:</span></span> 
- <span data-ttu-id="d76d6-308">Wcf-basichttp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-308">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="d76d6-309">WCF-WSHttp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-309">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="d76d6-310">WCF-NetTcp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-310">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="d76d6-311">Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-311">WCF-NetNamedPipe adapter</span></span>
- <span data-ttu-id="d76d6-312">Wcf-netmsmq 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-312">WCF-NetMsmq receive adapter</span></span>

#### <a name="messageclientcredentialtype"></a><span data-ttu-id="d76d6-313">MessageClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d76d6-313">MessageClientCredentialType</span></span>
<span data-ttu-id="d76d6-314">メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-314">Specify the type of credential to be used when performing client authentication using message-based security.</span></span>

<span data-ttu-id="d76d6-315">適用可能な値は、WCF アダプタごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="d76d6-315">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="d76d6-316">詳細については、 **MessageClientCredentialType**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-316">For more information about the **MessageClientCredentialType** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="d76d6-317">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-317">Type: String</span></span>  
<span data-ttu-id="d76d6-318">適用対象</span><span class="sxs-lookup"><span data-stu-id="d76d6-318">Applies to:</span></span> 
- <span data-ttu-id="d76d6-319">Wcf-basichttp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-319">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="d76d6-320">WCF-WSHttp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-320">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="d76d6-321">WCF-NetTcp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-321">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="d76d6-322">Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-322">WCF-NetNamedPipe adapter</span></span>

#### <a name="messageencoding"></a><span data-ttu-id="d76d6-323">MessageEncoding</span><span class="sxs-lookup"><span data-stu-id="d76d6-323">MessageEncoding</span></span>
<span data-ttu-id="d76d6-324">SOAP メッセージをエンコードするために使用されるエンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-324">Specify the encoder used to encode the SOAP message.</span></span>

<span data-ttu-id="d76d6-325">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-325">Type: String</span></span>  
<span data-ttu-id="d76d6-326">既定値:テキスト</span><span class="sxs-lookup"><span data-stu-id="d76d6-326">Default value: Text</span></span>  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

<span data-ttu-id="d76d6-327">適用対象Wcf-basichttp アダプター、Wcf-wshttp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-327">Applies to: WCF-BasicHttp adapter, WCF-WSHttp adapter</span></span>


#### <a name="msmqauthenticationmode"></a><span data-ttu-id="d76d6-328">MsmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="d76d6-328">MsmqAuthenticationMode</span></span>
<span data-ttu-id="d76d6-329">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-329">Specify how the message must be authenticated by the MSMQ transport.</span></span>

<span data-ttu-id="d76d6-330">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-330">Type: String</span></span>  
<span data-ttu-id="d76d6-331">既定値:**WindowsDomain**</span><span class="sxs-lookup"><span data-stu-id="d76d6-331">Default value: **WindowsDomain**</span></span>  
    <span data-ttu-id="d76d6-332">適用可能な値の詳細については、 **MsmqAuthenticationMode**プロパティを参照してください、 **MSMQ 認証モード**プロパティ、 **Wcf-netmsmq トランスポートのプロパティダイアログ ボックスで、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-332">For more information about the applicable values for the **MsmqAuthenticationMode** property, see the **MSMQ authentication mode** property in the **WCF-NetMsmq Transport Properties Dialog Box, Send, Security** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
<span data-ttu-id="d76d6-333">適用対象Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-333">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqencryptionalgorithm"></a><span data-ttu-id="d76d6-334">MsmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="d76d6-334">MsmqEncryptionAlgorithm</span></span>
<span data-ttu-id="d76d6-335">メッセージ キュー マネージャー間でメッセージを転送するときに、有線ネットワーク上でメッセージを暗号化するために使用するアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-335">Specify the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="d76d6-336">このプロパティは、使用可能な場合にのみ、 **MsmqProtectionLevel**プロパティに設定されて**EncryptAndSign**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-336">This property is available only if the **MsmqProtectionLevel** property is set to **EncryptAndSign**.</span></span>

<span data-ttu-id="d76d6-337">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-337">Type: String</span></span>  
<span data-ttu-id="d76d6-338">既定値:**[Rc4stream]**</span><span class="sxs-lookup"><span data-stu-id="d76d6-338">Default value: **RC4Stream**</span></span>  

    Applicable values are: RC4Stream, AES

<span data-ttu-id="d76d6-339">適用対象Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-339">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqprotectionlevel"></a><span data-ttu-id="d76d6-340">MsmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="d76d6-340">MsmqProtectionLevel</span></span>
<span data-ttu-id="d76d6-341">MSMQ トランスポートのレベルでメッセージをセキュリティ保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-341">Specify the way messages are secured at the level of the MSMQ transport.</span></span>

<span data-ttu-id="d76d6-342">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-342">Type: String</span></span>  
<span data-ttu-id="d76d6-343">既定値:**[署名]**</span><span class="sxs-lookup"><span data-stu-id="d76d6-343">Default value: **Sign**</span></span>  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

<span data-ttu-id="d76d6-344">適用対象Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-344">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqsecurehashalgorithm"></a><span data-ttu-id="d76d6-345">MsmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="d76d6-345">MsmqSecureHashAlgorithm</span></span>
<span data-ttu-id="d76d6-346">メッセージ ダイジェストの計算に使用するハッシュ アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-346">Specify the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="d76d6-347">このプロパティは使用可能な場合、 **MsmqProtectionLevel**プロパティに設定されて**None**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-347">This property is not available if the **MsmqProtectionLevel** property is set to **None**.</span></span>

<span data-ttu-id="d76d6-348">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-348">Type: String</span></span>  
<span data-ttu-id="d76d6-349">既定値:**SHA1**</span><span class="sxs-lookup"><span data-stu-id="d76d6-349">Default value: **SHA1**</span></span>  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

<span data-ttu-id="d76d6-350">適用対象Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-350">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="negotiateservicecredential"></a><span data-ttu-id="d76d6-351">NegotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="d76d6-351">NegotiateServiceCredential</span></span>
<span data-ttu-id="d76d6-352">サービスの資格情報が帯域外のクライアントで提供されるか、またはネゴシエーションのプロセスによってクライアントへのサービスから取得されるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-352">Specify whether the service credential is provisioned at the client out of band, or is obtained from the service to the client through a process of negotiation.</span></span> <span data-ttu-id="d76d6-353">そのようなネゴシエーションは、通常のメッセージ交換の準備です。</span><span class="sxs-lookup"><span data-stu-id="d76d6-353">Such a negotiation is a precursor to the usual message exchange.</span></span>

<span data-ttu-id="d76d6-354">場合、 **MessageClientCredentialType**プロパティと等しい**None**、 **Username**、または**証明書**にこのプロパティの設定**False**サービス証明書がクライアントの帯域外で使用可能であり、クライアントがサービス証明書を指定する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-354">If the **MessageClientCredentialType** property equals **None**, **Username**, or **Certificate**, setting this property to **False** implies that the service certificate is available at the client out of band and that the client needs to specify the service certificate.</span></span> <span data-ttu-id="d76d6-355">このモードは、WS-Trust および WS-SecureConversation が実装された SOAP スタックと同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-355">This mode is interoperable with SOAP stacks that implement WS-Trust and WS-SecureConversation.</span></span>

<span data-ttu-id="d76d6-356">場合、 **MessageClientCredentialType**プロパティに設定されて**Windows**、このプロパティを設定**False** Kerberos ベースの認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-356">If the **MessageClientCredentialType** property is set to **Windows**, setting this property to **False** specifies Kerberos-based authentication.</span></span> <span data-ttu-id="d76d6-357">つまり、クライアントとサービスは同じ Kerberos ドメイン内に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d76d6-357">This means that the client and service must be part of the same Kerberos domain.</span></span> <span data-ttu-id="d76d6-358">このモードは、WS-Trust や WS-SecureConversation に加えて (OASIS WSS TC で定義されている) Kerberos トークン プロファイルを実装する SOAP スタックと相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-358">This mode is interoperable with SOAP stacks that implement the Kerberos token profile (as defined at OASIS WSS TC) as well as WS-Trust and WS-SecureConversation.</span></span>

<span data-ttu-id="d76d6-359">このプロパティが**True**、SOAP メッセージで SPNego 交換をトンネリングする .NET SOAP ネゴシエーションが発生します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-359">When this property is **True**, it causes a .NET SOAP negotiation that tunnels SPNego exchange over SOAP messages.</span></span>

<span data-ttu-id="d76d6-360">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-360">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-361">既定値:True</span><span class="sxs-lookup"><span data-stu-id="d76d6-361">Default value: True</span></span>  
<span data-ttu-id="d76d6-362">適用対象WCF-WSHttp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-362">Applies to: WCF-WSHttp adapter</span></span>  

#### <a name="opentimeout"></a><span data-ttu-id="d76d6-363">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="d76d6-363">OpenTimeout</span></span>
<span data-ttu-id="d76d6-364">チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-364">Specify a time span value that indicates the interval of time provided for a channel open operation to complete.</span></span> 

<span data-ttu-id="d76d6-365">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-365">**Note**</span></span>  
<span data-ttu-id="d76d6-366">このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-366">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="d76d6-367">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-367">Type: String</span></span>  
<span data-ttu-id="d76d6-368">既定値:00:01:00</span><span class="sxs-lookup"><span data-stu-id="d76d6-368">Default value: 00:01:00</span></span>  
<span data-ttu-id="d76d6-369">適用対象すべての WCF アダプター*を除く*Wcf-custom および Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-369">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="orderedprocessing"></a><span data-ttu-id="d76d6-370">OrderedProcessing</span><span class="sxs-lookup"><span data-stu-id="d76d6-370">OrderedProcessing</span></span>
<span data-ttu-id="d76d6-371">メッセージを順番に処理するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-371">Specify whether to process messages serially.</span></span> <span data-ttu-id="d76d6-372">この受信場所でこのプロパティがオンの場合、BizTalk メッセージングまたはオーケストレーション送信ポートを持つと組み合わせて使用すると、メッセージの順次配送の対応、**順次配送**オプションに設定されて`True`します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-372">When this property is selected, this receive location accommodates ordered message delivery when used in conjunction with a BizTalk messaging or orchestration send port that has the **Ordered Delivery** option set to `True`.</span></span> <span data-ttu-id="d76d6-373">詳細については、**順次配送**オプションで、「参照」の該当するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d76d6-373">For more information about the **Ordered Delivery** option, see the appropriate topics in See Also.</span></span>

<span data-ttu-id="d76d6-374">このプロパティの値は次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-374">This property is applicable in the following cases:</span></span>
- <span data-ttu-id="d76d6-375">WCF-Custom アダプター: ときに、 **BindingType**プロパティに設定されて**netMsmqBinding**</span><span class="sxs-lookup"><span data-stu-id="d76d6-375">WCF-Custom adapter: When the **BindingType** property is set to **netMsmqBinding**</span></span>
- <span data-ttu-id="d76d6-376">WCF-Custom アダプター: ときに、 **BindingType**プロパティに設定されて**customBinding**、および**BindingConfiguration**プロパティがトランスポートに依存するカスタム チャネルを使用するよう構成MSMQ などの順次配送をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d76d6-376">WCF-Custom adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on transports supporting ordered delivery such as MSMQ.</span></span>
- <span data-ttu-id="d76d6-377">WCF-CustomIsolated アダプター: ときに、 **BindingType**プロパティに設定されて**customBinding**、および**BindingConfiguration**プロパティがトランスポートに依存するカスタム チャネルを使用するよう構成順次配送をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d76d6-377">WCF-CustomIsolated adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on transports supporting ordered delivery.</span></span>
- <span data-ttu-id="d76d6-378">Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-378">WCF-NetMsmq adapter</span></span>

<span data-ttu-id="d76d6-379">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-379">Type: String</span></span>  
<span data-ttu-id="d76d6-380">既定値:**False**</span><span class="sxs-lookup"><span data-stu-id="d76d6-380">Default value: **False**</span></span>  
<span data-ttu-id="d76d6-381">適用対象</span><span class="sxs-lookup"><span data-stu-id="d76d6-381">Applies to:</span></span> 
- <span data-ttu-id="d76d6-382">Wcf-netmsmq 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-382">WCF-NetMsmq receive adapter</span></span>
- <span data-ttu-id="d76d6-383">Wcf-custom 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-383">WCF-Custom receive adapter</span></span>
- <span data-ttu-id="d76d6-384">WCF-CustomIsolated 受信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-384">WCF-CustomIsolated receive adapter</span></span>

#### <a name="outboundbodylocation"></a><span data-ttu-id="d76d6-385">OutboundBodyLocation</span><span class="sxs-lookup"><span data-stu-id="d76d6-385">OutboundBodyLocation</span></span>
<span data-ttu-id="d76d6-386">SOAP データ選択を指定**本文**送信 WCF メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-386">Specify the data selection for the SOAP **Body** element of outgoing WCF messages.</span></span> <span data-ttu-id="d76d6-387">使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-387">For more information about how to use the **OutboundBodyLocation** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="d76d6-388">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-388">Type: String</span></span>  
<span data-ttu-id="d76d6-389">既定値:UseBodyElement</span><span class="sxs-lookup"><span data-stu-id="d76d6-389">Default value: UseBodyElement</span></span>  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

<span data-ttu-id="d76d6-390">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-390">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="outboundcustomheaders"></a><span data-ttu-id="d76d6-391">OutboundCustomHeaders</span><span class="sxs-lookup"><span data-stu-id="d76d6-391">OutboundCustomHeaders</span></span>
<span data-ttu-id="d76d6-392">送信メッセージのカスタム SOAP ヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-392">Specify the custom SOAP headers for outgoing messages.</span></span> <span data-ttu-id="d76d6-393">このプロパティを使用すると、プロパティが必要、 \<**ヘッダー** \>ルート要素としての要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-393">When this property is used, the property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="d76d6-394">内ですべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-394">All of the custom SOAP headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="d76d6-395">カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**\>\</**ヘッダー** \>または\<**ヘッダー** \>このプロパティにします。</span><span class="sxs-lookup"><span data-stu-id="d76d6-395">If the custom SOAP header value is an empty string, you must assign \<**headers**\>\</**headers**\> or \<**headers**\> to this property.</span></span> <span data-ttu-id="d76d6-396">WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、WCF アダプタでのカスタム SOAP ヘッダーの使用の SDK サンプルから[ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-396">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>

<span data-ttu-id="d76d6-397">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-397">Type: String</span></span>  
<span data-ttu-id="d76d6-398">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-398">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="outboundxmltemplate"></a><span data-ttu-id="d76d6-399">OutboundXmlTemplate</span><span class="sxs-lookup"><span data-stu-id="d76d6-399">OutboundXmlTemplate</span></span>
<span data-ttu-id="d76d6-400">SOAP のコンテンツを XML 形式のテンプレートを指定**本文**送信メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-400">Specify the XML-formatted template for the content of the SOAP **Body** element of an outgoing message.</span></span> <span data-ttu-id="d76d6-401">このプロパティは必要な場合、 **OutboundBodyLocation**プロパティに設定されて**UseTemplate**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-401">This property is required if the **OutboundBodyLocation** property is set to **UseTemplate**.</span></span> <span data-ttu-id="d76d6-402">使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-402">For more information about how to use the **OutboundXMLTemplate** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="d76d6-403">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-403">Type: String</span></span>  
<span data-ttu-id="d76d6-404">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-404">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-405">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-405">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="password"></a><span data-ttu-id="d76d6-406">パスワード</span><span class="sxs-lookup"><span data-stu-id="d76d6-406">Password</span></span>
<span data-ttu-id="d76d6-407">移行先サーバーでの認証に使用するパスワードを指定するときに、 **UseSSO**プロパティに設定されて**False**。</span><span class="sxs-lookup"><span data-stu-id="d76d6-407">Specify the password to use for authentication with the destination server when the **UseSSO** property is set to **False**.</span></span>

<span data-ttu-id="d76d6-408">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-408">Type: String</span></span>  
<span data-ttu-id="d76d6-409">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-409">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-410">適用対象すべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-410">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>  

#### <a name="propagatefaultmessage"></a><span data-ttu-id="d76d6-411">PropagateFaultMessage</span><span class="sxs-lookup"><span data-stu-id="d76d6-411">PropagateFaultMessage</span></span>
<span data-ttu-id="d76d6-412">送信処理に失敗したメッセージを回送または保留するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-412">Specify whether to route or suspend messages that fail in outbound processing.</span></span> <span data-ttu-id="d76d6-413">このプロパティは、送信請求 - 応答のポートに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d76d6-413">This property is valid only for solicit-response ports.</span></span> 

<span data-ttu-id="d76d6-414">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-414">**Note**</span></span>  
<span data-ttu-id="d76d6-415">このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-415">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span>

<span data-ttu-id="d76d6-416">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-416">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-417">既定値:**True**</span><span class="sxs-lookup"><span data-stu-id="d76d6-417">Default value: **True**</span></span>  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

<span data-ttu-id="d76d6-418">適用対象すべての WCF 送信アダプタ*を除く*Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-418">Applies to: All WCF send adapters *except* the WCF-NetMsmq adapter</span></span>
  
#### <a name="proxyaddress"></a><span data-ttu-id="d76d6-419">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="d76d6-419">ProxyAddress</span></span>
<span data-ttu-id="d76d6-420">プロキシ サーバーのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-420">Specify the address of the proxy server.</span></span> <span data-ttu-id="d76d6-421">使用して、 **https**または**http**セキュリティ構成に応じてスキーム。</span><span class="sxs-lookup"><span data-stu-id="d76d6-421">Use the **https** or the **http** scheme depending on the security configuration.</span></span> <span data-ttu-id="d76d6-422">このアドレスの後に、コロンとポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-422">This address can be followed by a colon and the port number.</span></span> <span data-ttu-id="d76d6-423">場合、プロパティは必須、 **ProxyToUse**プロパティに設定されて**UserSpecified** (例。 http://127.0.0.1:8080)</span><span class="sxs-lookup"><span data-stu-id="d76d6-423">The property is required if the **ProxyToUse** property is set to **UserSpecified** (For example, http://127.0.0.1:8080)</span></span>

<span data-ttu-id="d76d6-424">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-424">Type: String</span></span>  
<span data-ttu-id="d76d6-425">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-425">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-426">適用対象Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-426">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>  

#### <a name="proxypassword"></a><span data-ttu-id="d76d6-427">ProxyPassword</span><span class="sxs-lookup"><span data-stu-id="d76d6-427">ProxyPassword</span></span>
<span data-ttu-id="d76d6-428">指定されたプロキシ サーバーを使用するパスワードを指定、 **ProxyAddress**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d76d6-428">Specify the password to use for the proxy server specified in the **ProxyAddress** property.</span></span>

<span data-ttu-id="d76d6-429">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-429">Type: String</span></span>  
<span data-ttu-id="d76d6-430">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-430">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-431">適用対象Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-431">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>

#### <a name="proxytouse"></a><span data-ttu-id="d76d6-432">ProxyToUse</span><span class="sxs-lookup"><span data-stu-id="d76d6-432">ProxyToUse</span></span>
<span data-ttu-id="d76d6-433">送信 HTTP トラフィックに使用するプロキシ サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-433">Specify which proxy server to use for outgoing HTTP traffic.</span></span>

<span data-ttu-id="d76d6-434">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-434">Type: String</span></span>  
<span data-ttu-id="d76d6-435">既定値:**None**</span><span class="sxs-lookup"><span data-stu-id="d76d6-435">Default value: **None**</span></span>  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

<span data-ttu-id="d76d6-436">適用対象Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-436">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>  

#### <a name="proxyusername"></a><span data-ttu-id="d76d6-437">ProxyUserName</span><span class="sxs-lookup"><span data-stu-id="d76d6-437">ProxyUserName</span></span>
<span data-ttu-id="d76d6-438">指定されているプロキシ サーバーを使用するユーザー名を指定、 **ProxyAddress**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d76d6-438">Specify the user name to use for the proxy server specified in the **ProxyAddress** property.</span></span> <span data-ttu-id="d76d6-439">場合、プロパティは必須、 **ProxyToUse**プロパティに設定されて**UserSpecified**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-439">The property is required if the **ProxyToUse** property is set to **UserSpecified**.</span></span>

<span data-ttu-id="d76d6-440">このプロパティの詳細については、次を参照してください。 [、Wcf-wshttp 送信ポートを構成する方法](../core/how-to-configure-a-wcf-wshttp-send-port.md)と[Wcf-basichttp 送信ポートを構成する方法](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-440">For more information about this property, see [How to Configure a WCF-WSHttp Send Port](../core/how-to-configure-a-wcf-wshttp-send-port.md) and [How to Configure a WCF-BasicHttp Send Port](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f).</span></span>

<span data-ttu-id="d76d6-441">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-441">Type: String</span></span>  
<span data-ttu-id="d76d6-442">適用対象Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-442">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>

#### <a name="replytoaddress"></a><span data-ttu-id="d76d6-443">ReplyToAddress</span><span class="sxs-lookup"><span data-stu-id="d76d6-443">ReplyToAddress</span></span>
<span data-ttu-id="d76d6-444">要求 - 応答受信場所を介して受信された受信メッセージに対応する送信 WCF メッセージの応答エンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-444">Indicate the reply endpoint address for the outgoing WCF messages corresponding to incoming messages received through the request-response receive locations.</span></span> <span data-ttu-id="d76d6-445">このプロパティは、受信メッセージから自動的に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-445">The property is automatically promoted from incoming messages.</span></span>

<span data-ttu-id="d76d6-446">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-446">Type: String</span></span>  
<span data-ttu-id="d76d6-447">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-447">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-448">適用対象すべての WCF アダプター*を除く*Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-448">Applies to: All WCF adapters *except* the WCF-NetMsmq adapter</span></span>

#### <a name="securitymode"></a><span data-ttu-id="d76d6-449">SecurityMode</span><span class="sxs-lookup"><span data-stu-id="d76d6-449">SecurityMode</span></span>
<span data-ttu-id="d76d6-450">使用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-450">Specify the type of security that is used.</span></span> <span data-ttu-id="d76d6-451">適用可能な値は、WCF アダプタごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="d76d6-451">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="d76d6-452">詳細については、 **SecurityMode**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-452">For more information about the **SecurityMode** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span> 

<span data-ttu-id="d76d6-453">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-453">**Note**</span></span>  
<span data-ttu-id="d76d6-454">このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-454">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span>

<span data-ttu-id="d76d6-455">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-455">Type: String</span></span>  
<span data-ttu-id="d76d6-456">適用対象すべての WCF アダプター*を除く*Wcf-custom および Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-456">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="sendtimeout"></a><span data-ttu-id="d76d6-457">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="d76d6-457">SendTimeout</span></span>
<span data-ttu-id="d76d6-458">送信操作が完了するまでの間隔を示す期間値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-458">Specify a time span value that indicates the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d76d6-459">この値は、送信者が大きなメッセージを送信した場合、対話処理がすべて完了するまでの時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-459">This value specifies a time span for the whole interaction to complete, even if the correspondent sends a large message.</span></span>

<span data-ttu-id="d76d6-460">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-460">Type: String</span></span>  
<span data-ttu-id="d76d6-461">既定値:00:01:00</span><span class="sxs-lookup"><span data-stu-id="d76d6-461">Default value: 00:01:00</span></span>  
<span data-ttu-id="d76d6-462">適用対象すべての WCF アダプター*を除く*Wcf-custom および Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-462">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="servicebehaviorconfiguration"></a><span data-ttu-id="d76d6-463">ServiceBehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d76d6-463">ServiceBehaviorConfiguration</span></span>
<span data-ttu-id="d76d6-464">XML 文字列を指定、 **\<動作\>** の要素、 **\<serviceBehaviors\>** WCF の動作の設定を構成するのにはサービス。</span><span class="sxs-lookup"><span data-stu-id="d76d6-464">Specify an XML string with the **\<behavior\>** element of the **\<serviceBehaviors\>** element to configure the behavior settings of a WCF service.</span></span> <span data-ttu-id="d76d6-465">詳細については、 **\<serviceBehaviors\>** 要素では、「も該当するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d76d6-465">For more information about the **\<serviceBehaviors\>** element, see the appropriate topic in See Also.</span></span>

<span data-ttu-id="d76d6-466">例:</span><span class="sxs-lookup"><span data-stu-id="d76d6-466">Example:</span></span>

```
<behavior name="SampleServiceBehavior">
<serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
<serviceCredentials>
<serviceCertificate findValue="539d9ab3089bb6dc187fa7dbb382cf01f8d78f5f" storeLocation="CurrentUser" x509FindType="FindByThumbprint"/>
</serviceCredentials>
<serviceMetadata httpGetEnabled="true"/>
</behavior>
```

<span data-ttu-id="d76d6-467">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-467">Type: String</span></span>  
<span data-ttu-id="d76d6-468">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-468">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-469">適用対象Wcf-custom 受信アダプター、Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-469">Applies to: WCF-Custom receive adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="servicecertificate"></a><span data-ttu-id="d76d6-470">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="d76d6-470">ServiceCertificate</span></span>
<span data-ttu-id="d76d6-471">このプロパティを受信場所で使用する場合、クライアントがサービスの認証に使用する、この受信場所に対する X.509 証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-471">If this property is used for receive locations, specify the thumbprint of the X.509 certificate for the receive locations that clients use to authenticate the service.</span></span> <span data-ttu-id="d76d6-472">このプロパティに使用する証明書をインストールする必要があります、**マイ**で格納、**現在のユーザー**場所。</span><span class="sxs-lookup"><span data-stu-id="d76d6-472">The certificate to be used for this property must be installed into the **My** store in the **Current User** location.</span></span>

<span data-ttu-id="d76d6-473">このプロパティを送信ポートで使用する場合、この送信ポートのメッセージ送信先のサービスの認証に使用する X.509 証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-473">If this property is used for send ports, specify the thumbprint of the X.509 certificate for authenticating the service to which this send port sends messages.</span></span> <span data-ttu-id="d76d6-474">このプロパティに使用する証明書をインストールする必要があります、**その他のユーザー**で格納、**ローカル マシン**場所。</span><span class="sxs-lookup"><span data-stu-id="d76d6-474">The certificate to be used for this property must be installed into the **Other People** store in the **Local Machine** location.</span></span>

<span data-ttu-id="d76d6-475">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-475">Type: String</span></span>  
<span data-ttu-id="d76d6-476">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-476">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-477">適用対象</span><span class="sxs-lookup"><span data-stu-id="d76d6-477">Applies to:</span></span> 
- <span data-ttu-id="d76d6-478">Wcf-basichttp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-478">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="d76d6-479">Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-479">WCF-NetMsmq adapter</span></span>
- <span data-ttu-id="d76d6-480">WCF-WSHttp アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-480">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="d76d6-481">WCF-NetTcp 受信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-481">WCF-NetTcp receive adapter</span></span>

#### <a name="suspendmessageonfailure"></a><span data-ttu-id="d76d6-482">SuspendMessageOnFailure</span><span class="sxs-lookup"><span data-stu-id="d76d6-482">SuspendMessageOnFailure</span></span>
<span data-ttu-id="d76d6-483">受信パイプラインまたはルーティングの障害によって受信処理に失敗した要求メッセージを保留するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-483">Specify whether to suspend the request message that fails inbound processing due to a receive pipeline failure or a routing failure.</span></span>

<span data-ttu-id="d76d6-484">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-484">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-485">既定値:True</span><span class="sxs-lookup"><span data-stu-id="d76d6-485">Default value: True</span></span>  
<span data-ttu-id="d76d6-486">適用対象すべての WCF 受信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-486">Applies to: All WCF receive adapters</span></span>  

#### <a name="textencoding"></a><span data-ttu-id="d76d6-487">TextEncoding</span><span class="sxs-lookup"><span data-stu-id="d76d6-487">TextEncoding</span></span>
<span data-ttu-id="d76d6-488">文字セットのバインディングでメッセージを出力するために使用するエンコードを指定するときに、 **MessageEncoding**プロパティに設定されて**テキスト**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-488">Specify the character set encoding to be used for emitting messages on the binding when the **MessageEncoding** property is set to **Text**.</span></span> 

<span data-ttu-id="d76d6-489">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-489">**Note**</span></span>  
<span data-ttu-id="d76d6-490">このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-490">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="d76d6-491">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-491">Type: String</span></span>  
<span data-ttu-id="d76d6-492">既定値: utf-8</span><span class="sxs-lookup"><span data-stu-id="d76d6-492">Default value: utf-8</span></span>  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

<span data-ttu-id="d76d6-493">適用対象Wcf-basichttp アダプター、Wcf-wshttp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-493">Applies to: WCF-BasicHttp adapter, WCF-WSHttp adapter</span></span>
  
#### <a name="timetolive"></a><span data-ttu-id="d76d6-494">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="d76d6-494">TimeToLive</span></span>
<span data-ttu-id="d76d6-495">メッセージが期限切れになり、配信不能キューに格納されるまでのメッセージが有効な期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-495">Specify a time span for how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="d76d6-496">このプロパティは、時間が重要な要素になるメッセージが送信ポートによって処理されるまで古くならないようにするために設定されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-496">This property is set to ensure that time-sensitive messages do not become stale before they are processed by a send port.</span></span> <span data-ttu-id="d76d6-497">指定された時間間隔内にこの送信ポートによって処理されないキュー内のメッセージは、期限切れのメッセージといいます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-497">A message in a queue that is not consumed by this send port within the time interval specified is said to be expired.</span></span> <span data-ttu-id="d76d6-498">期限切れのメッセージは、配信不能キューと呼ばれる特別なキューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-498">Expired messages are sent to special queue called the dead-letter queue.</span></span> <span data-ttu-id="d76d6-499">配信不能キューの場所に設定されて、 **DeadLetterQueue**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d76d6-499">The location of the dead-letter queue is set with the **DeadLetterQueue** property.</span></span>

<span data-ttu-id="d76d6-500">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-500">Type: String</span></span>  
<span data-ttu-id="d76d6-501">既定値:1.00:00:00</span><span class="sxs-lookup"><span data-stu-id="d76d6-501">Default value: 1.00:00:00</span></span>  
<span data-ttu-id="d76d6-502">適用対象Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-502">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="to"></a><span data-ttu-id="d76d6-503">目的</span><span class="sxs-lookup"><span data-stu-id="d76d6-503">To</span></span>
<span data-ttu-id="d76d6-504">WCF 送信ポートが送信する送信 WCF メッセージの送信先エンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-504">Specify the destination endpoint address for outgoing WCF messages that the WCF send ports send.</span></span>

<span data-ttu-id="d76d6-505">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-505">Type: String</span></span>  
<span data-ttu-id="d76d6-506">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-506">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-507">適用対象すべての WCF 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="d76d6-507">Applies to: All WCF send adapters</span></span>  

#### <a name="transactionprotocol"></a><span data-ttu-id="d76d6-508">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="d76d6-508">TransactionProtocol</span></span>
<span data-ttu-id="d76d6-509">このバインドで使用するトランザクション プロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-509">Specify the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="d76d6-510">このプロパティは必要な場合、 **EnableTransaction**プロパティに設定されて**True**。</span><span class="sxs-lookup"><span data-stu-id="d76d6-510">This property is required if the **EnableTransaction** property is set to **True**.</span></span>

<span data-ttu-id="d76d6-511">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-511">Type: String</span></span>  
<span data-ttu-id="d76d6-512">既定値:OleTransaction</span><span class="sxs-lookup"><span data-stu-id="d76d6-512">Default value: OleTransaction</span></span>  

    Applicable values are: OleTransaction, WS-AtomicTransaction

<span data-ttu-id="d76d6-513">適用対象Wcf-netnamedpipe アダプター、Wcf-nettcp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-513">Applies to: WCF-NetNamedPipe adapter,  WCF-NetTcp adapter</span></span>  

#### <a name="transportclientcredentialtype"></a><span data-ttu-id="d76d6-514">TransportClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d76d6-514">TransportClientCredentialType</span></span>
<span data-ttu-id="d76d6-515">送信ポート認証の実行時に使用する資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-515">Specify the type of credential to be used when performing the send port authentication.</span></span> <span data-ttu-id="d76d6-516">適用可能な値は、WCF アダプタごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="d76d6-516">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="d76d6-517">詳細については、 **TransportClientCredentialType**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-517">For more information about the **TransportClientCredentialType** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="d76d6-518">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-518">Type: String</span></span>  
<span data-ttu-id="d76d6-519">適用対象Wcf-basic アダプター、Wcf-nettcp アダプター、Wcf-wshttp アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-519">Applies to: WCF-Basic adapter, WCF-NetTcp adapter, WCF-WSHttp adapter</span></span>  

#### <a name="transportprotectionlevel"></a><span data-ttu-id="d76d6-520">TransportProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="d76d6-520">TransportProtectionLevel</span></span>
<span data-ttu-id="d76d6-521">TCP トランスポートのレベルでのセキュリティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-521">Specify security at the level of the TCP transport.</span></span> <span data-ttu-id="d76d6-522">メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-522">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="d76d6-523">暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-523">Encryption provides data-level privacy during transport.</span></span>

<span data-ttu-id="d76d6-524">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-524">Type: String</span></span>  
<span data-ttu-id="d76d6-525">既定値:**EncryptAndSign**</span><span class="sxs-lookup"><span data-stu-id="d76d6-525">Default value: **EncryptAndSign**</span></span>  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

<span data-ttu-id="d76d6-526">適用対象Wcf-nettcp アダプター、Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-526">Applies to: WCF-NetTcp adapter, WCF-NetNamedPipe adapter</span></span>  

#### <a name="username"></a><span data-ttu-id="d76d6-527">UserName</span><span class="sxs-lookup"><span data-stu-id="d76d6-527">UserName</span></span>
<span data-ttu-id="d76d6-528">移行先サーバーでの認証に使用するユーザー名を指定するときに、 **UseSSO**プロパティに設定されて**False**します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-528">Specify the user name to use for authentication with the destination server when the **UseSSO** property is set to **False**.</span></span> <span data-ttu-id="d76d6-529">このプロパティでは domain\user 形式は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-529">You do not have to use the domain\user format for this property.</span></span>

<span data-ttu-id="d76d6-530">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-530">Type: String</span></span>  
<span data-ttu-id="d76d6-531">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-531">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-532">適用対象すべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-532">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="usesourcejournal"></a><span data-ttu-id="d76d6-533">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="d76d6-533">UseSourceJournal</span></span>
<span data-ttu-id="d76d6-534">この送信ポートによって処理されるメッセージのコピーをソース ジャーナル キューに保存する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-534">Specify whether copies of messages processed by this send port should be stored in the source journal queue.</span></span>

<span data-ttu-id="d76d6-535">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-535">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-536">既定値:False</span><span class="sxs-lookup"><span data-stu-id="d76d6-536">Default value: False</span></span>  
<span data-ttu-id="d76d6-537">適用対象Wcf-netmsmq 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-537">Applies to: WCF-NetMsmq send adapter</span></span>  

#### <a name="usesso"></a><span data-ttu-id="d76d6-538">UseSSO</span><span class="sxs-lookup"><span data-stu-id="d76d6-538">UseSSO</span></span>
<span data-ttu-id="d76d6-539">接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-539">Specify whether to use Single Sign-On to retrieve client credentials for authentication with the destination server.</span></span> 

<span data-ttu-id="d76d6-540">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-540">**Note**</span></span>  
<span data-ttu-id="d76d6-541">このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="d76d6-541">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="d76d6-542">型:ブール値</span><span class="sxs-lookup"><span data-stu-id="d76d6-542">Type: Boolean</span></span>  
<span data-ttu-id="d76d6-543">既定値:False</span><span class="sxs-lookup"><span data-stu-id="d76d6-543">Default value: False</span></span>  
<span data-ttu-id="d76d6-544">適用対象すべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-544">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="referencedbindings"></a><span data-ttu-id="d76d6-545">ReferencedBindings</span><span class="sxs-lookup"><span data-stu-id="d76d6-545">ReferencedBindings</span></span>
<span data-ttu-id="d76d6-546">によって参照されるバインド構成を指定、 **bindingConfiguration**の属性、 **\<発行者\>** の要素、 **wsFederationHttpBinding**と**customBinding**、セキュリティ トークン サービス (STS) セキュリティ トークンを発行することを示します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-546">Specify the binding configurations referenced by the **bindingConfiguration** attribute of the **\<issuer\>** element for the **wsFederationHttpBinding** and **customBinding**, which indicates the Security Token Service (STS) that issues security tokens.</span></span> <span data-ttu-id="d76d6-547">詳細については、 **\<発行者\>** 要素のトピック「」を参照してください"\<発行者\>"で[ http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)します。</span><span class="sxs-lookup"><span data-stu-id="d76d6-547">For more information about the **\<issuer\>** element, see the topic, "\<issuer\>" at [http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476).</span></span>

<span data-ttu-id="d76d6-548">バインド情報など、 **\<発行者\>** の要素、 **wsFederationHttpBinding**と**customBinding**できます使用して構成、 **BindingConfiguration** Wcf-custom および Wcf-customisolated アダプターのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d76d6-548">The binding information including the **\<issuer\>** element for the **wsFederationHttpBinding** and **customBinding** can be configured through the **BindingConfiguration** property of the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="d76d6-549">このプロパティの参照先のバインド構成のすべての形式で配置する必要があります、 [\<バインド\>](http://go.microsoft.com/fwlink/?LinkID=80878)要素。</span><span class="sxs-lookup"><span data-stu-id="d76d6-549">All of the referenced binding configurations for this property must be placed in the form of the [\<bindings\>](http://go.microsoft.com/fwlink/?LinkID=80878) element.</span></span> 

<span data-ttu-id="d76d6-550">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-550">**Note**</span></span>  
<span data-ttu-id="d76d6-551">**BindingConfiguration**の属性、 **\<発行者\>** 要素は、このプロパティで有効なバインド名を指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d76d6-551">The **bindingConfiguration** attribute of the **\<issuer\>** element must refer to a valid binding name in this property.</span></span> 

<span data-ttu-id="d76d6-552">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-552">**Note**</span></span>  
<span data-ttu-id="d76d6-553">**\<発行者\>** この参照チェーンが循環する依存関係を行わない場合は、参照されるバインド構成要素はこのプロパティで異なるバインド構成を参照もできます。</span><span class="sxs-lookup"><span data-stu-id="d76d6-553">The **\<issuer\>** element in the referenced binding configurations can also refer to a different binding configuration in this property if this reference chain does not make a circular dependency.</span></span> 

<span data-ttu-id="d76d6-554">例:</span><span class="sxs-lookup"><span data-stu-id="d76d6-554">Example:</span></span> 

```
WCF.BindingConfiguration = @"<wsFederationHttpBinding>
<binding name=""sampleBinding"">
<security mode=""Message"">
<message issuedKeyType=""AsymmetricKey"">
<issuer address=""http://www.contoso.com/samplests"" binding=""wsFederationHttpBinding"" bindingConfiguration=""**contosoSTSBinding**""/>
</message>
</security>
</binding>
</wsFederationHttpBinding>";
WCF.ReferencedBinding =@"<bindings>
<wsFederationHttpBinding>
<binding name=""**contosoSTSBinding**"">
<security mode=""Message"">
<message negotiateServiceCredential=""false"">
<issuer address=""http://northwind.com/samplests"" bindingConfiguration=""**northwindBinding**"" binding=""wsHttpBinding"">
</issuer>
</message>
</security>
</binding>
</wsFederationHttpBinding>
<wsHttpBinding>
<binding name=""**northwindBinding**"">
<security mode=""Message"">
<message clientCredentialType=""Certificate""/>
</security>
</binding>
</wsHttpBinding>
</bindings>" 
``` 

<span data-ttu-id="d76d6-555">**注:**</span><span class="sxs-lookup"><span data-stu-id="d76d6-555">**Note**</span></span>  
<span data-ttu-id="d76d6-556">**ReferencedBinding**プロパティにはで使用されるバインド構成が含まれていない必要があります、 **BindingConfiguration**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d76d6-556">**ReferencedBinding** property must not contain the binding configuration used in the **BindingConfiguration** property.</span></span>

<span data-ttu-id="d76d6-557">型:String</span><span class="sxs-lookup"><span data-stu-id="d76d6-557">Type: String</span></span>  
<span data-ttu-id="d76d6-558">既定値:空の文字列</span><span class="sxs-lookup"><span data-stu-id="d76d6-558">Default value: An empty string</span></span>  
<span data-ttu-id="d76d6-559">適用対象WCF カスタム アダプター、Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="d76d6-559">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d76d6-560">参照</span><span class="sxs-lookup"><span data-stu-id="d76d6-560">See Also</span></span>  
 <span data-ttu-id="d76d6-561">[WCF アダプタ](../core/wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="d76d6-561">[WCF Adapters](../core/wcf-adapters.md) </span></span>  
 <span data-ttu-id="d76d6-562">[\<動作\>の\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879) </span><span class="sxs-lookup"><span data-stu-id="d76d6-562">[\<behavior\> of \<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879) </span></span>  
 <span data-ttu-id="d76d6-563">[\<バインド\>](http://go.microsoft.com/fwlink/?LinkId=80878) </span><span class="sxs-lookup"><span data-stu-id="d76d6-563">[\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878) </span></span>  
 <span data-ttu-id="d76d6-564">[\<動作\>の\<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095) </span><span class="sxs-lookup"><span data-stu-id="d76d6-564">[\<behavior\> of \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095) </span></span>  
 <span data-ttu-id="d76d6-565">[メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="d76d6-565">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="d76d6-566">負荷分散</span><span class="sxs-lookup"><span data-stu-id="d76d6-566">Load Balancing</span></span>](http://go.microsoft.com/fwlink/?LinkId=81089)

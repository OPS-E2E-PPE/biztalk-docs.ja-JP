---
title: "WCF 送信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, headers
- serializing, SOAP messages
- WCF adapters, extracting information
- messages, extracting information
- SOAP messages, serializing
- WCF adapters, message bodies
- send adapters, WCF adapters
- Web services, headers
- WCF adapters, send adapters
ms.assetid: 226a020a-2e12-41fe-a4a2-6683d9e98219
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70604fbc15f5f15b0a7ff2325debdc28ac3a97c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-send-adapter"></a><span data-ttu-id="2fdb9-102">WCF 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="2fdb9-102">WCF Send Adapter</span></span>
<span data-ttu-id="2fdb9-103">WCF 送信アダプタでは、型宣言が不要なコントラクトを使用して WCF サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-103">The WCF send adapter enables you to call a WCF service through the typeless contract.</span></span>  
  
## <a name="specifying-the-wcf-message-body"></a><span data-ttu-id="2fdb9-104">WCF メッセージ本文の指定</span><span class="sxs-lookup"><span data-stu-id="2fdb9-104">Specifying the WCF Message Body</span></span>  
 <span data-ttu-id="2fdb9-105">BizTalk Server から送信する必要があるメッセージ本文は、次のオプションのいずれかを使用して、SOAP メッセージに挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-105">The message body that needs to be sent from BizTalk Server can be inserted into the SOAP message by using one of the following options:</span></span>  
  
-   <span data-ttu-id="2fdb9-106">Extract the content of the BizTalk message body (BizTalk メッセージ本文の内容を抽出)</span><span class="sxs-lookup"><span data-stu-id="2fdb9-106">Extract the content of the BizTalk message body</span></span>  
  
-   <span data-ttu-id="2fdb9-107">Specify the content by using the template (テンプレートを使用して内容を指定)</span><span class="sxs-lookup"><span data-stu-id="2fdb9-107">Specify the content by using the template</span></span>  
  
 <span data-ttu-id="2fdb9-108">送信ポートのトランスポート プロパティ ダイアログ ボックスで、これらのオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-108">You can configure these options in the send port transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a><span data-ttu-id="2fdb9-109">Extract the Content of the BizTalk Message Body (BizTalk メッセージ本文の内容を抽出)</span><span class="sxs-lookup"><span data-stu-id="2fdb9-109">Extract the Content of the BizTalk Message Body</span></span>  
 <span data-ttu-id="2fdb9-110">このオプションを選択すると、BizTalk メッセージ本文の内容が、送信 WCF メッセージ本文の SOAP Body 要素に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-110">When this option is selected, the content of the BizTalk message body is inserted into the SOAP Body element for the outbound WCF message body.</span></span>  
  
#### <a name="specify-the-content-by-using-the-template"></a><span data-ttu-id="2fdb9-111">Specify the Content by Using the Template (テンプレートを使用して内容を指定)</span><span class="sxs-lookup"><span data-stu-id="2fdb9-111">Specify the Content by Using the Template</span></span>  
 <span data-ttu-id="2fdb9-112">このオプションを選択すると、BizTalk メッセージ本文が、送信 WCF メッセージ本文の指定された XML テンプレートの下にある SOAP Body 要素に配置されます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-112">When this option is selected, the BizTalk message body is placed in the SOAP body element under the given XML template for the outbound WCF message body.</span></span>  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a><span data-ttu-id="2fdb9-113">BizTalk メッセージの SOAP メッセージへのシリアル化</span><span class="sxs-lookup"><span data-stu-id="2fdb9-113">Serializing the BizTalk Message into a SOAP Message</span></span>  
 <span data-ttu-id="2fdb9-114">送信アダプタは、BizTalk メッセージを送信する前に SOAP メッセージにシリアル化します。メッセージのシリアル化中に、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-114">The send adapter serializes the BizTalk message into a SOAP message before sending it out. The following rules apply during serialization of the message:</span></span>  
  
-   <span data-ttu-id="2fdb9-115">BizTalk メッセージがマルチパート メッセージの場合、ボディ部のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-115">If the BizTalk message is a multipart message, then only the body part is used.</span></span>  
  
-   <span data-ttu-id="2fdb9-116">BizTalk メッセージに SOAP エンベロープ全体が含まれる場合は、別の SOAP エンベロープにラップされます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-116">If the BizTalk message contains the entire SOAP envelope, then it is wrapped into another SOAP envelope.</span></span>  
  
-   <span data-ttu-id="2fdb9-117">BizTalk メッセージに任意の XML データが含まれている場合、BizTalk メッセージは SOAP 本文要素に配置されます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-117">If the BizTalk message contains arbitrary XML data, then the BizTalk message is placed into the SOAP Body element.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="2fdb9-118">Web サービス ヘッダーの処理</span><span class="sxs-lookup"><span data-stu-id="2fdb9-118">Handling Web Services Headers</span></span>  
 <span data-ttu-id="2fdb9-119">送信操作中、BizTalk Server は Web サービスの標準ヘッダーを制御できません。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-119">During send operations BizTalk Server does not have control over Web services standard headers.</span></span> <span data-ttu-id="2fdb9-120">これらのヘッダーは、WCF によって設定され、処理されます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-120">Those headers are set and processed by the WCF.</span></span> <span data-ttu-id="2fdb9-121">BizTalk Server アプリケーションによって変更できる唯一の標準ヘッダーは、 **、: アクション**ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-121">The only standard header that can be modified by the BizTalk Server application is the **a:Action** header.</span></span> <span data-ttu-id="2fdb9-122">場合、コンテキスト プロパティ**アクション**、WCF 送信アダプタを設定するプロパティの値を使用して、アダプターの名前空間が指定されて、**アクション**SOAP メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-122">If the context property **Action** is specified on the adapter namespace, then the WCF send adapter will use the value of the property to set the **Action** on the SOAP message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fdb9-123">動的送信ポート場合、**アクション**で指定された、 **OutboundHeaders**、コンテキスト プロパティを設定する、 **WCF です。アクション**は無視されます。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-123">For dynamic send ports, if **Action** is specified in the **OutboundHeaders**, the context property you set for the **WCF.Action** will be ignored.</span></span>  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a><span data-ttu-id="2fdb9-124">BTS.IsDynamicSend コンテキスト プロパティの指定</span><span class="sxs-lookup"><span data-stu-id="2fdb9-124">Specifying the BTS.IsDynamicSend Context Property</span></span>  
 <span data-ttu-id="2fdb9-125">WCF 送信アダプタは、送信ポートの構成をキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-125">The WCF send adapter caches the configuration for send ports.</span></span> <span data-ttu-id="2fdb9-126">場合、 **BTS です。IsDynamicSend**プロパティが true に、WCF 送信アダプタはキャッシュされた構成を使用しませんが、代わりにすべての構成情報メッセージから読み取り、送信メッセージのコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-126">If the **BTS.IsDynamicSend** property is set to true, the WCF send adapter does not use the cached configuration, but instead reads all configuration information from the message context properties of the outbound messages.</span></span> <span data-ttu-id="2fdb9-127">静的送信ポートで、WCF 送信アダプタで使用**BTS です。SPLastUpdatedTime**、最終変更時刻を静的送信ポートの設定は、任意の構成があるかどうかを検出するために、静的な 変更の送信ポート。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-127">On a static send port, the WCF send adapter uses **BTS.SPLastUpdatedTime**, which is the time that the static send port settings were last modified, to detect if there are any configuration changes on the static send port.</span></span> <span data-ttu-id="2fdb9-128">この方法では、WCF 送信アダプタは、すべてのメッセージ コンテキストからのすべての設定を読み取る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-128">In this way the WCF send adapter does not need to read all of the settings from every message context.</span></span>  
  
 <span data-ttu-id="2fdb9-129">以外の場合、静的送信ポートのプロパティをオーバーライドするかどうか、 **WCF です。アクション**送信パイプラインのプロパティを設定する必要があります、 **BTS です。IsDynamicSend**真の場合でも、最終更新タイムスタンプは、WCF 送信アダプターにキャッシュされた構成は使用しないようにするプロパティが変更されていません。</span><span class="sxs-lookup"><span data-stu-id="2fdb9-129">If you want to override the static send port properties other than the **WCF.Action** property in a send pipeline, you need to set the **BTS.IsDynamicSend** property to true so that the WCF send adapter will not use the cached configuration even though the last updated timestamp has not changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fdb9-130">参照</span><span class="sxs-lookup"><span data-stu-id="2fdb9-130">See Also</span></span>  
 <span data-ttu-id="2fdb9-131">[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="2fdb9-131">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="2fdb9-132">[WCF 受信アダプター](../core/wcf-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2fdb9-132">[WCF Receive Adapter](../core/wcf-receive-adapter.md) </span></span>  
 <span data-ttu-id="2fdb9-133">[WCF アダプタは?](../core/what-are-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="2fdb9-133">[What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md) </span></span>  
 [<span data-ttu-id="2fdb9-134">メッセージ コンテキスト プロパティを使用する方法</span><span class="sxs-lookup"><span data-stu-id="2fdb9-134">How to Use Message Context Properties</span></span>](../core/how-to-use-message-context-properties.md)
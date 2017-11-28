---
title: "構成エラー。 メッセージの署名ではありません &#39; t が期待値と一致します。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0bacd605908abae984247b3d7ed775ea8f5de4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a><span data-ttu-id="684b5-104">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="684b5-104">Configuration error.</span></span> <span data-ttu-id="684b5-105">メッセージの署名ではありません &#39; t が期待値と一致します。</span><span class="sxs-lookup"><span data-stu-id="684b5-105">The message signing doesn&#39;t match the expected value.</span></span>
## <a name="details"></a><span data-ttu-id="684b5-106">詳細</span><span class="sxs-lookup"><span data-stu-id="684b5-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="684b5-107">製品名</span><span class="sxs-lookup"><span data-stu-id="684b5-107">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="684b5-108">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="684b5-108">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="684b5-109">イベント ID</span><span class="sxs-lookup"><span data-stu-id="684b5-109">Event ID</span></span>|-|  
|<span data-ttu-id="684b5-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="684b5-110">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="684b5-111"> EDI</span><span class="sxs-lookup"><span data-stu-id="684b5-111"> EDI</span></span>|  
|<span data-ttu-id="684b5-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="684b5-112">Component</span></span>|<span data-ttu-id="684b5-113">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="684b5-113">AS2 Engine</span></span>|  
|<span data-ttu-id="684b5-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="684b5-114">Symbolic Name</span></span>|<span data-ttu-id="684b5-115">AS2DecoderPartySigningConfigurationError</span><span class="sxs-lookup"><span data-stu-id="684b5-115">AS2DecoderPartySigningConfigurationError</span></span>|  
|<span data-ttu-id="684b5-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="684b5-116">Message Text</span></span>|<span data-ttu-id="684b5-117">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="684b5-117">Configuration error.</span></span> <span data-ttu-id="684b5-118">メッセージの署名が予期された値と一致しません。</span><span class="sxs-lookup"><span data-stu-id="684b5-118">The message signing doesn't match the expected value.</span></span> <span data-ttu-id="684b5-119">送信元パートナーに問い合わせて、使用された署名を確認してください。</span><span class="sxs-lookup"><span data-stu-id="684b5-119">Contact the sending partner and verify signature use.</span></span> <span data-ttu-id="684b5-120">AS2-から:"{0}"AS2-を:"\ "MessageID:"\ {2 \}"</span><span class="sxs-lookup"><span data-stu-id="684b5-120">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="684b5-121">説明</span><span class="sxs-lookup"><span data-stu-id="684b5-121">Explanation</span></span>  
 <span data-ttu-id="684b5-122">このエラー/警告/情報イベントは、パーティの設定で署名が指定されているにもかかわらず、AS2 メッセージが署名されていないか、署名が有効にならないように指定されているのにメッセージが署名されているため、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="684b5-122">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not process the AS2 message because signing is specified in the party settings, but the AS2 message is not signed, or signing is specified not to be enabled, but the message is signed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="684b5-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="684b5-123">User Action</span></span>  
 <span data-ttu-id="684b5-124">このエラーを解決するには、パーティの設定で署名が指定されている場合は受信 AS2 メッセージが署名されていることを確認します。または、パーティの設定で署名が有効にならないように指定されている場合は、受信 AS2 メッセージが署名されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="684b5-124">To resolve this error, verify that the incoming AS2 message is signed if signing is specified in the party settings or that the incoming AS2 message is not signed if signing is specified as not enabled in the party settings.</span></span> <span data-ttu-id="684b5-125">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="684b5-125">Do one of the following:</span></span>  
  
1.  <span data-ttu-id="684b5-126">場合、**受信メッセージのプロパティをオーバーライド**の [パーティ-AS2 メッセージの送信者] ページで AS2 のプロパティ ダイアログ ボックスのプロパティが選択されて、[!INCLUDE[prague](../includes/prague-md.md)]管理コンソールで、**メッセージは署名付きをする必要があります**プロパティが選択されているが、メッセージが署名されていない、メッセージを送信したパーティに連絡し、メッセージに署名するように依頼して、再送信します。</span><span class="sxs-lookup"><span data-stu-id="684b5-126">If the **Override inbound message properties** property is selected in the Party as AS2 Message Sender page of the AS2 Properties dialog box in the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, the **Message should be signed** property is selected, but the message is not signed, contact the party that sent the message and ask them to sign the message, and resend it.</span></span> <span data-ttu-id="684b5-127">クリアするか、**メッセージに署名する必要があります**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="684b5-127">Or you can clear the **Message should be signed** property, or the **Override inbound message properties** property.</span></span>  
  
2.  <span data-ttu-id="684b5-128">場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージに署名する必要があります**プロパティをオフにしたが、メッセージが署名されているメッセージを送信したパーティに連絡、しないように依頼してくださいメッセージに署名し、再送信します。</span><span class="sxs-lookup"><span data-stu-id="684b5-128">If the **Override inbound message properties** property is selected, the **Message should be signed** property is cleared, but the message is signed, contact the party that sent the message and ask them not to sign the message, and resend it.</span></span> <span data-ttu-id="684b5-129">選択することができます、**メッセージに署名する必要があります**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="684b5-129">Or you can select the **Message should be signed** property.</span></span>
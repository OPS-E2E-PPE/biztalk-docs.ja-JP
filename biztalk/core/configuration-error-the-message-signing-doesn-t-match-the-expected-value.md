---
title: 構成エラー。 メッセージの署名は&#39;t が予期される値と一致します。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfe2b610724a346ed31fb0951aa90c660f41d82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975939"
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a><span data-ttu-id="f0a5c-104">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-104">Configuration error.</span></span> <span data-ttu-id="f0a5c-105">メッセージの署名は&#39;t が予期される値と一致します。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-105">The message signing doesn&#39;t match the expected value.</span></span>
## <a name="details"></a><span data-ttu-id="f0a5c-106">詳細</span><span class="sxs-lookup"><span data-stu-id="f0a5c-106">Details</span></span>  
  
|                 |                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f0a5c-107">製品名</span><span class="sxs-lookup"><span data-stu-id="f0a5c-107">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                              |
| <span data-ttu-id="f0a5c-108">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f0a5c-108">Product Version</span></span> |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                          |
|    <span data-ttu-id="f0a5c-109">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f0a5c-109">Event ID</span></span>     |                                                                                      -                                                                                       |
|  <span data-ttu-id="f0a5c-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f0a5c-110">Event Source</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f0a5c-111"> EDI</span><span class="sxs-lookup"><span data-stu-id="f0a5c-111"> EDI</span></span>                                            |
|    <span data-ttu-id="f0a5c-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f0a5c-112">Component</span></span>    |                                                                                  <span data-ttu-id="f0a5c-113">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="f0a5c-113">AS2 Engine</span></span>                                                                                  |
|  <span data-ttu-id="f0a5c-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f0a5c-114">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="f0a5c-115">AS2DecoderPartySigningConfigurationError</span><span class="sxs-lookup"><span data-stu-id="f0a5c-115">AS2DecoderPartySigningConfigurationError</span></span>                                                                   |
|  <span data-ttu-id="f0a5c-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f0a5c-116">Message Text</span></span>   | <span data-ttu-id="f0a5c-117">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-117">Configuration error.</span></span> <span data-ttu-id="f0a5c-118">メッセージの署名が予期された値と一致しません。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-118">The message signing doesn't match the expected value.</span></span> <span data-ttu-id="f0a5c-119">送信元パートナーに問い合わせて、使用された署名を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-119">Contact the sending partner and verify signature use.</span></span> <span data-ttu-id="f0a5c-120">AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"</span><span class="sxs-lookup"><span data-stu-id="f0a5c-120">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f0a5c-121">説明</span><span class="sxs-lookup"><span data-stu-id="f0a5c-121">Explanation</span></span>  
 <span data-ttu-id="f0a5c-122">このエラー/警告/情報イベントは、パーティの設定で署名が指定されているにもかかわらず、AS2 メッセージが署名されていないか、署名が有効にならないように指定されているのにメッセージが署名されているため、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-122">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not process the AS2 message because signing is specified in the party settings, but the AS2 message is not signed, or signing is specified not to be enabled, but the message is signed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0a5c-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f0a5c-123">User Action</span></span>  
 <span data-ttu-id="f0a5c-124">このエラーを解決するには、パーティの設定で署名が指定されている場合は受信 AS2 メッセージが署名されていることを確認します。または、パーティの設定で署名が有効にならないように指定されている場合は、受信 AS2 メッセージが署名されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-124">To resolve this error, verify that the incoming AS2 message is signed if signing is specified in the party settings or that the incoming AS2 message is not signed if signing is specified as not enabled in the party settings.</span></span> <span data-ttu-id="f0a5c-125">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-125">Do one of the following:</span></span>  
  
1.  <span data-ttu-id="f0a5c-126">場合、**受信メッセージのプロパティをオーバーライド**として、BizTalk Server 管理コンソールでの AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの送信者 ページで、パーティ プロパティが選択されている、**メッセージは署名付きをする必要があります**プロパティが選択されているが、メッセージが署名されていない、メッセージを送信したパーティにお問い合わせくださいとメッセージに署名するように依頼して、再送信します。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-126">If the **Override inbound message properties** property is selected in the Party as AS2 Message Sender page of the AS2 Properties dialog box in the BizTalk Server Administration Console, the **Message should be signed** property is selected, but the message is not signed, contact the party that sent the message and ask them to sign the message, and resend it.</span></span> <span data-ttu-id="f0a5c-127">または、オフにすることができます、**メッセージに署名する必要があります**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-127">Or you can clear the **Message should be signed** property, or the **Override inbound message properties** property.</span></span>  
  
2.  <span data-ttu-id="f0a5c-128">場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージに署名する必要があります**、しないように依頼して、メッセージを送信したパーティにお問い合わせくださいプロパティをオフになっても、メッセージの署名メッセージに署名し、再送信します。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-128">If the **Override inbound message properties** property is selected, the **Message should be signed** property is cleared, but the message is signed, contact the party that sent the message and ask them not to sign the message, and resend it.</span></span> <span data-ttu-id="f0a5c-129">選択することができます、**メッセージに署名する必要があります**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f0a5c-129">Or you can select the **Message should be signed** property.</span></span>
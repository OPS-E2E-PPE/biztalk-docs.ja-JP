---
title: "構成エラー。 メッセージの暗号化ではありません &#39; 期待値と一致する t |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b17460c4dcd6f9d2a8c18e5e7284cd36940d6820
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a><span data-ttu-id="cdf75-103">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="cdf75-103">Configuration error.</span></span> <span data-ttu-id="cdf75-104">メッセージの暗号化ではありません &#39; 一致予期される値</span><span class="sxs-lookup"><span data-stu-id="cdf75-104">The message encryption doesn&#39;t match the expected value</span></span>
## <a name="details"></a><span data-ttu-id="cdf75-105">詳細</span><span class="sxs-lookup"><span data-stu-id="cdf75-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cdf75-106">製品名</span><span class="sxs-lookup"><span data-stu-id="cdf75-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="cdf75-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cdf75-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="cdf75-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cdf75-108">Event ID</span></span>|-|  
|<span data-ttu-id="cdf75-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cdf75-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cdf75-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="cdf75-110"> EDI</span></span>|  
|<span data-ttu-id="cdf75-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cdf75-111">Component</span></span>|<span data-ttu-id="cdf75-112">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="cdf75-112">AS2 Engine</span></span>|  
|<span data-ttu-id="cdf75-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cdf75-113">Symbolic Name</span></span>|<span data-ttu-id="cdf75-114">AS2DecoderPartyEncryptionConfigurationError</span><span class="sxs-lookup"><span data-stu-id="cdf75-114">AS2DecoderPartyEncryptionConfigurationError</span></span>|  
|<span data-ttu-id="cdf75-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cdf75-115">Message Text</span></span>|<span data-ttu-id="cdf75-116">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="cdf75-116">Configuration error.</span></span> <span data-ttu-id="cdf75-117">メッセージの暗号化が予期された値と一致しません。</span><span class="sxs-lookup"><span data-stu-id="cdf75-117">The message encryption doesn't match the expected value.</span></span> <span data-ttu-id="cdf75-118">送信元パートナーに問い合わせて、使用された暗号化を確認してください。</span><span class="sxs-lookup"><span data-stu-id="cdf75-118">Contact the sending partner and verify encryption use.</span></span> <span data-ttu-id="cdf75-119">AS2-から:"{0}"AS2-を:"\ "MessageID:"\ {2 \}"</span><span class="sxs-lookup"><span data-stu-id="cdf75-119">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cdf75-120">説明</span><span class="sxs-lookup"><span data-stu-id="cdf75-120">Explanation</span></span>  
 <span data-ttu-id="cdf75-121">このエラー/警告/情報イベントは、パーティの設定で暗号化が指定されているにもかかわらず、AS2 メッセージが暗号化されていないか、暗号化が有効にならないように指定されているのにメッセージが暗号化されているため、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="cdf75-121">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not process the AS2 message because encryption is specified in the party settings, but the AS2 message is not encrypted, or encryption is specified not to be enabled, but the message is encrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cdf75-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cdf75-122">User Action</span></span>  
 <span data-ttu-id="cdf75-123">このエラーを解決するには、パーティ設定で暗号化が指定されている場合は受信 AS2 メッセージが暗号化されていることを確認し、パーティ設定で暗号化を有効にしないように指定されている場合は、受信 AS2 メッセージが暗号化されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cdf75-123">To resolve this error, verify that the incoming AS2 message is encrypted if encryption is specified in the party settings or that the incoming AS2 message is not encrypted if encryption is specified as not enabled in the party settings.</span></span> <span data-ttu-id="cdf75-124">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cdf75-124">Do one of the following:</span></span>  
  
1.  <span data-ttu-id="cdf75-125">場合、**受信メッセージのプロパティのプロパティが選択されている上書き**パーティの AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの送信者 ページで、[!INCLUDE[prague](../includes/prague-md.md)]管理コンソールで、**メッセージを暗号化する必要があります**プロパティが選択されているが、メッセージが暗号化されていない、メッセージを送信したパーティに連絡し、メッセージを暗号化するように依頼して、再送信します。</span><span class="sxs-lookup"><span data-stu-id="cdf75-125">If the **Override inbound message properties property is selected** in the Party as AS2 Message Sender page of the AS2 Properties dialog box in the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, the **Message should be encrypted** property is selected, but the message is not encrypted, contact the party that sent the message and ask them to encrypt the message, and resend it.</span></span> <span data-ttu-id="cdf75-126">クリアするか、**メッセージを暗号化する**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="cdf75-126">Or you can clear the **Message should be encrypted** property, or the **Override inbound message properties** property.</span></span>  
  
2.  <span data-ttu-id="cdf75-127">場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージを暗号化する**プロパティをオフにしたが、メッセージが暗号化されて、メッセージを送信したパーティに連絡しように依頼してメッセージを暗号化して、再送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cdf75-127">If the **Override inbound message properties** property is selected, the **Message should be encrypted** property is cleared, but the message is encrypted, contact the party that sent the message and ask them not to encrypt the message, and resend it.</span></span> <span data-ttu-id="cdf75-128">選択することができます、**メッセージを暗号化する**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="cdf75-128">Or you can select the **Message should be encrypted** property.</span></span>
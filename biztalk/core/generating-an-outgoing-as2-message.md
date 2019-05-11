---
title: 送信 AS2 メッセージの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 288c8101-9a96-4f98-ae18-df43c7cdb3a0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd96debd3099eee795ebb661a9f5828d7de6f10f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387773"
---
# <a name="generating-an-outgoing-as2-message"></a><span data-ttu-id="92d04-102">送信 AS2 メッセージの生成</span><span class="sxs-lookup"><span data-stu-id="92d04-102">Generating an Outgoing AS2 Message</span></span>
<span data-ttu-id="92d04-103">AS2EDISend および AS2Send 送信パイプラインは次のように、送信メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="92d04-103">The AS2EDISend and AS2Send send pipelines generate an outbound message as follows.</span></span> <span data-ttu-id="92d04-104">各パイプラインの一方向アグリーメント タブでプロパティを使用して、**アグリーメントのプロパティ** ダイアログ ボックスで、送信 AS2 メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="92d04-104">Each pipeline uses the properties in the one-way agreement tab of the **Agreement Properties** dialog box to generate the outgoing AS2 message.</span></span>  
  
## <a name="agreement-destination-and-messageid-determination"></a><span data-ttu-id="92d04-105">アグリーメント、送信先、および MessageID の決定</span><span class="sxs-lookup"><span data-stu-id="92d04-105">Agreement, Destination, and MessageID Determination</span></span>  
 <span data-ttu-id="92d04-106">AS2 送信パイプラインは、次のように AS2 メッセージの送信に使用されるアグリーメントおよび送信先を決定します。</span><span class="sxs-lookup"><span data-stu-id="92d04-106">The AS2 send pipelines determine the agreement and destination to be used in sending an AS2 message as follows:</span></span>  
  
-   <span data-ttu-id="92d04-107">送信メッセージの処理に使用するアグリーメントを特定するには、AS2 エンコーダー照合しようと、AS2 のメッセージとパーティのビジネス プロファイル、または送信ポートの AS2Identity のプロパティをサブスクライブする送信ポートでメッセージに関連付けられています。アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="92d04-107">To determine the agreement to use in processing an outgoing message, the AS2 encoder attempts to match the AS2-To properties in the message and the AS2Identity for a party’s business profile, or the send port subscribing to the message with a send port associated with the agreement.</span></span> <span data-ttu-id="92d04-108">このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="92d04-108">For more information on this process, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="92d04-109">メッセージの送信先を確認するのには、動的送信ポートで送信パイプラインは、OutboundTransportLocation プロパティは、書き込まれるか、動的送信ポートを機能させるためのバックエンド アプリケーションで、コンテキストに昇格させる必要がありますを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d04-109">To determine the destination of the message, the send pipeline in a dynamic send port uses the OutboundTransportLocation property, which must be written or promoted to the context by a backend application for the dynamic send port to work.</span></span> <span data-ttu-id="92d04-110">静的送信パイプラインで送信パイプラインは、AS2 から変換先を決定の AS2 アグリーメントのプロパティとビジネス プロファイルのプロパティの id プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92d04-110">The send pipeline in a static send pipeline will determine the destination from the AS2-From property in the AS2 agreement properties and the identities of the business profile properties.</span></span>  
  
-   <span data-ttu-id="92d04-111">AS2 エンコーダーは、送信 AS2 メッセージの MessageId ヘッダーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d04-111">The AS2 Encoder needs to set the MessageId header of an outgoing AS2 message.</span></span> <span data-ttu-id="92d04-112">送信パイプラインが MessageId をからいずれかを決定します、`EdiIntAS.MessageId`コンテキスト プロパティまたは`HTTP.UserHttpHeaders`コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92d04-112">The send pipeline determines the MessageId from either the `EdiIntAS.MessageId` context property or the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="92d04-113">エンコーダーから値を使用してどちらのコンテキスト プロパティが設定されている場合、`HTTP.UserHttpHeaders`コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92d04-113">If both of those context properties are set, the encoder uses the value from the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="92d04-114">設定されている場合、送信パイプラインによって値 MessageID のです。</span><span class="sxs-lookup"><span data-stu-id="92d04-114">If neither of them is set, the send pipeline autogenerates a value for MessageID.</span></span>  
  
## <a name="outgoing-message-processing"></a><span data-ttu-id="92d04-115">送信メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="92d04-115">Outgoing Message Processing</span></span>  
 <span data-ttu-id="92d04-116">送信 AS2 メッセージの処理で、AS2 送信パイプラインを使用する手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="92d04-116">The steps that the AS2 send pipelines use in processing an outgoing AS2 message are as follows:</span></span>  
  
-   <span data-ttu-id="92d04-117">ネイティブ形式は、メッセージのコピーを作成し、AS2 メッセージの否認がアグリーメント プロパティで有効になっている場合は、コピーを否認不可データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="92d04-117">Makes a copy of the message in native format, and stores the copy in the non-repudiation database, if non-repudiation of AS2 messages is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="92d04-118">AS2 エンコーダーに HTTP (および AS2) ヘッダーをビルド、`HTTP.UserHttpHeaders`コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92d04-118">The AS2 Encoder builds the HTTP (and AS2) headers into the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="92d04-119">このプロセスの詳細については、次を参照してください。 [AS2 経由で送信 EDI メッセージの送信側の処理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="92d04-119">For more information on this process, see [Send-Side Processing of an Outgoing EDI Message over AS2](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md).</span></span>  
  
-   <span data-ttu-id="92d04-120">書き込みます`HTTP.UserHttpHeaders`コンテキストにします。</span><span class="sxs-lookup"><span data-stu-id="92d04-120">Writes `HTTP.UserHttpHeaders` to the context.</span></span>  
  
-   <span data-ttu-id="92d04-121">有効になっている場合は、送信のメッセージを圧縮します。</span><span class="sxs-lookup"><span data-stu-id="92d04-121">Compresses the outgoing message, if enabled.</span></span>  
  
-   <span data-ttu-id="92d04-122">メッセージの暗号化を含む MIME 処理を実行します (有効な場合に、**メッセージを暗号化する必要があります**アグリーメント プロパティ) とデジタル署名の適用 (で有効になっている場合、**メッセージは署名付きをする必要があります**アグリーメントのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="92d04-122">Performs MIME processing, including encrypting the message (if enabled in the **Message should be encrypted** agreement property) and applying a digital signature (if enabled in the **Message should be signed** agreement properties).</span></span> <span data-ttu-id="92d04-123">AS2Send パイプラインは、アグリーメントの設定に基づき、署名を適用するのに、SHA1 または MD5 を使用します。</span><span class="sxs-lookup"><span data-stu-id="92d04-123">The AS2Send pipeline uses either SHA1 or MD5 to apply the signature, based upon agreement settings.</span></span>  
  
-   <span data-ttu-id="92d04-124">Content-disposition MIME を作成します。 場合、指定した値を含むヘッダー ファイルを送信するアグリーメントのプロパティの名前が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="92d04-124">Creates a Content-Disposition MIME header containing the specified value, if transmit file name is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="92d04-125">暗号化されたメッセージのコピー (ワイヤ形式) を作成し、有効な場合に、コピーを否認不可データベースに格納、**エンコードされた送信の AS2 メッセージに対して有効な NRR**アグリーメント プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92d04-125">Makes a copy of the encrypted message (in wire format), and stores the copy in the non-repudiation database, if enabled in the **NRR enabled for outbound encoded AS2 messages** in the agreement property.</span></span>  
  
-   <span data-ttu-id="92d04-126">MDN が必要な場合は、MIC 値を計算し、データ ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="92d04-126">If an MDN is required, computes the MIC value and stores it in the data store.</span></span>  
  
-   <span data-ttu-id="92d04-127">UserHTTPHeaders コンテキスト プロパティから、送信 AS2 メッセージにヘッダーの書き込みを行う HTTP アダプターにメッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="92d04-127">Delivers the message to the HTTP adapter, which writes the headers from the UserHTTPHeaders context property into the outgoing AS2 message.</span></span>  
  
-   <span data-ttu-id="92d04-128">信頼性の高いメッセージングが必要な場合は、MDN が受信されるまで、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="92d04-128">If reliable messaging is required, resends the message until an MDN is received.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d04-129">参照</span><span class="sxs-lookup"><span data-stu-id="92d04-129">See Also</span></span>  
 <span data-ttu-id="92d04-130">[BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="92d04-130">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 [<span data-ttu-id="92d04-131">AS2 送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="92d04-131">AS2 Send Components</span></span>](../core/as2-send-components.md)
---
title: 送信 AS2 メッセージを生成する |Microsoft ドキュメント
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
ms.openlocfilehash: 90a0b1e37e96086de7d8901b61afa8dea859a388
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246546"
---
# <a name="generating-an-outgoing-as2-message"></a><span data-ttu-id="f48d1-102">送信 AS2 メッセージの生成</span><span class="sxs-lookup"><span data-stu-id="f48d1-102">Generating an Outgoing AS2 Message</span></span>
<span data-ttu-id="f48d1-103">AS2EDISend および AS2Send の各送信パイプラインは、次に示すように送信メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-103">The AS2EDISend and AS2Send send pipelines generate an outbound message as follows.</span></span> <span data-ttu-id="f48d1-104">各パイプラインの一方向アグリーメント タブでプロパティを使用して、**アグリーメントのプロパティ** ダイアログ ボックスを送信 AS2 メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-104">Each pipeline uses the properties in the one-way agreement tab of the **Agreement Properties** dialog box to generate the outgoing AS2 message.</span></span>  
  
## <a name="agreement-destination-and-messageid-determination"></a><span data-ttu-id="f48d1-105">アグリーメント、送信先、および MessageID の決定</span><span class="sxs-lookup"><span data-stu-id="f48d1-105">Agreement, Destination, and MessageID Determination</span></span>  
 <span data-ttu-id="f48d1-106">AS2 メッセージの送信に使用されるアグリーメントおよび送信先は、AS2 送信パイプラインによって次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="f48d1-106">The AS2 send pipelines determine the agreement and destination to be used in sending an AS2 message as follows:</span></span>  
  
-   <span data-ttu-id="f48d1-107">送信メッセージの処理に使用するアグリーメントを決定する場合、AS2 エンコーダーは、メッセージ内の AS2-To プロパティとパーティのビジネス プロファイルの AS2Identity の照合、またはメッセージをサブスクライブしている送信ポートアグリーメントに関連付けられた送信ポートの照合を行います。</span><span class="sxs-lookup"><span data-stu-id="f48d1-107">To determine the agreement to use in processing an outgoing message, the AS2 encoder attempts to match the AS2-To properties in the message and the AS2Identity for a party’s business profile, or the send port subscribing to the message with a send port associated with the agreement.</span></span> <span data-ttu-id="f48d1-108">このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="f48d1-108">For more information on this process, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="f48d1-109">メッセージの送信先を決定する場合、動的送信ポート内の送信パイプラインは、OutboundTransportLocation プロパティを使用します。このプロパティを使用するには、動的送信ポートのバックエンド アプリケーションを使用してコンテキストに書き込むか、コンテキストに昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f48d1-109">To determine the destination of the message, the send pipeline in a dynamic send port uses the OutboundTransportLocation property, which must be written or promoted to the context by a backend application for the dynamic send port to work.</span></span> <span data-ttu-id="f48d1-110">静的送信パイプライン内の送信パイプラインは、AS2 アグリーメント プロパティ内の AS2-From プロパティ、およびビジネス プロファイル プロパティの ID から送信先を決定します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-110">The send pipeline in a static send pipeline will determine the destination from the AS2-From property in the AS2 agreement properties and the identities of the business profile properties.</span></span>  
  
-   <span data-ttu-id="f48d1-111">AS2 エンコーダーは、送信 AS2 メッセージの MessageId ヘッダーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f48d1-111">The AS2 Encoder needs to set the MessageId header of an outgoing AS2 message.</span></span> <span data-ttu-id="f48d1-112">送信パイプラインは、`EdiIntAS.MessageId` コンテキスト プロパティまたは `HTTP.UserHttpHeaders` コンテキスト プロパティから MessageId を決定します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-112">The send pipeline determines the MessageId from either the `EdiIntAS.MessageId` context property or the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="f48d1-113">どちらのコンテキスト プロパティも設定されている場合、AS2 エンコーダーは `HTTP.UserHttpHeaders` コンテキスト プロパティの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-113">If both of those context properties are set, the encoder uses the value from the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="f48d1-114">どちらのコンテキスト プロパティも設定されていない場合は、送信パイプラインが MessageID の値を自動生成します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-114">If neither of them is set, the send pipeline autogenerates a value for MessageID.</span></span>  
  
## <a name="outgoing-message-processing"></a><span data-ttu-id="f48d1-115">送信メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="f48d1-115">Outgoing Message Processing</span></span>  
 <span data-ttu-id="f48d1-116">AS2 送信パイプラインは、次の手順により送信 AS2 メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-116">The steps that the AS2 send pipelines use in processing an outgoing AS2 message are as follows:</span></span>  
  
-   <span data-ttu-id="f48d1-117">ネイティブ形式のメッセージのコピーを作成し、否認不可データベースに保存します (AS2 メッセージの否認不可がアグリーメント プロパティで有効になっている場合)。</span><span class="sxs-lookup"><span data-stu-id="f48d1-117">Makes a copy of the message in native format, and stores the copy in the non-repudiation database, if non-repudiation of AS2 messages is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="f48d1-118">AS2 エンコーダーは、HTTP (および AS2) ヘッダーを `HTTP.UserHttpHeaders` コンテキスト プロパティに構築します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-118">The AS2 Encoder builds the HTTP (and AS2) headers into the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="f48d1-119">このプロセスの詳細については、次を参照してください。 [AS2 経由で送信 EDI メッセージの送信側の処理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="f48d1-119">For more information on this process, see [Send-Side Processing of an Outgoing EDI Message over AS2](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md).</span></span>  
  
-   <span data-ttu-id="f48d1-120">`HTTP.UserHttpHeaders` をコンテキストに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f48d1-120">Writes `HTTP.UserHttpHeaders` to the context.</span></span>  
  
-   <span data-ttu-id="f48d1-121">送信メッセージを圧縮します (有効になっている場合)。</span><span class="sxs-lookup"><span data-stu-id="f48d1-121">Compresses the outgoing message, if enabled.</span></span>  
  
-   <span data-ttu-id="f48d1-122">メッセージの暗号化を含む MIME 処理を実行します (有効な場合に、**メッセージを暗号化する**アグリーメント プロパティ) デジタル署名を適用して (で有効になっている場合、**メッセージは署名付きをする必要があります**アグリーメントのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="f48d1-122">Performs MIME processing, including encrypting the message (if enabled in the **Message should be encrypted** agreement property) and applying a digital signature (if enabled in the **Message should be signed** agreement properties).</span></span> <span data-ttu-id="f48d1-123">AS2Send パイプラインは、SHA1 または MD5 を使用してアグリーメント設定に基づき署名を適用します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-123">The AS2Send pipeline uses either SHA1 or MD5 to apply the signature, based upon agreement settings.</span></span>  
  
-   <span data-ttu-id="f48d1-124">指定された値を含む Content-Disposition MIME ヘッダーを作成します (送信ファイル名がアグリーメント プロパティで有効になっている場合)。</span><span class="sxs-lookup"><span data-stu-id="f48d1-124">Creates a Content-Disposition MIME header containing the specified value, if transmit file name is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="f48d1-125">(ワイヤ形式)、暗号化されたメッセージのコピーを作成し、保存、否認不可データベース内で有効になっている場合、**エンコードされた送信の AS2 メッセージに対して有効な NRR**アグリーメント プロパティです。</span><span class="sxs-lookup"><span data-stu-id="f48d1-125">Makes a copy of the encrypted message (in wire format), and stores the copy in the non-repudiation database, if enabled in the **NRR enabled for outbound encoded AS2 messages** in the agreement property.</span></span>  
  
-   <span data-ttu-id="f48d1-126">MDN が必要な場合は、MIC 値を計算してデータ ストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-126">If an MDN is required, computes the MIC value and stores it in the data store.</span></span>  
  
-   <span data-ttu-id="f48d1-127">メッセージを HTTP アダプターに配信します。HTTP アダプターは、UserHTTPHeaders コンテキスト プロパティから送信 AS2 メッセージにヘッダーを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f48d1-127">Delivers the message to the HTTP adapter, which writes the headers from the UserHTTPHeaders context property into the outgoing AS2 message.</span></span>  
  
-   <span data-ttu-id="f48d1-128">信頼できるメッセージ処理が必要な場合は、MDN が受信するまでメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="f48d1-128">If reliable messaging is required, resends the message until an MDN is received.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f48d1-129">参照</span><span class="sxs-lookup"><span data-stu-id="f48d1-129">See Also</span></span>  
 <span data-ttu-id="f48d1-130">[BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f48d1-130">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 [<span data-ttu-id="f48d1-131">AS2 送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f48d1-131">AS2 Send Components</span></span>](../core/as2-send-components.md)
---
title: MIME/SMIME デコーダー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component]
ms.assetid: ff6c963c-1b5c-4be4-9eef-3ec9a018e7fd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593873b1d3252eed752de21fe4bb9c99dc664974
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394479"
---
# <a name="mime-smime-decoder-pipeline-component"></a><span data-ttu-id="b07b8-102">MIME/SMIME デコーダー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b07b8-102">MIME-SMIME Decoder Pipeline Component</span></span>
<span data-ttu-id="b07b8-103">MIME/SMIME デコーダー コンポーネントは、MIME デコードのメッセージの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b07b8-103">The MIME/SMIME Decoder component provides MIME decoding functionality for messages.</span></span> <span data-ttu-id="b07b8-104">このパイプライン コンポーネントは、受信パイプラインのデコード ステージに配置できる 7 bit、8 bit、binary、引用符で囲まれた印刷可能な UUEncode、および base64 デコードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b07b8-104">This pipeline component can be placed into the Decode stage of a receive pipeline, and it supports 7bit, 8bit, binary, quoted-printable, UUEncode, and base64 decoding.</span></span> <span data-ttu-id="b07b8-105">ローカライズされたデータの文字セットの変更では、デコードすることは変わりません。</span><span class="sxs-lookup"><span data-stu-id="b07b8-105">Localized data character set changes will not affect the decoding.</span></span>  
  
 <span data-ttu-id="b07b8-106">MIME/SMIME デコーダー コンポーネントは、復号化し、受信メッセージの署名検証できます。</span><span class="sxs-lookup"><span data-stu-id="b07b8-106">The MIME/SMIME Decoder component can decrypt and sign-validate an incoming message.</span></span> <span data-ttu-id="b07b8-107">サービスが実行されている現在のユーザーの個人証明書ストアから暗号化解除証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b07b8-107">Decryption certificates are used from the personal certificate store of the current user under which the service is running.</span></span> <span data-ttu-id="b07b8-108">ローカル コンピューターのアドレス帳ストアまたはメッセージ自体から、署名検証証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b07b8-108">Sign-validation certificates are used from the Address Book store of the local computer or from the message itself.</span></span>  
  
 <span data-ttu-id="b07b8-109">成功したメッセージの暗号化の解除、MIME/SMIME デコーダー パイプライン コンポーネントは、メッセージの述語としてメッセージを復号化するために使用する暗号化解除証明書の拇印を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b07b8-109">On successful decryption of a message, the MIME/SMIME Decoder pipeline component associates the thumbprint of the decryption certificate used to decrypt the message as a predicate of the message.</span></span> <span data-ttu-id="b07b8-110">これは、そのメッセージをサブスクライブしている任意のサービス (オーケストレーションまたは送信ポート) がそのキーを所有しているホストを関連付ける必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b07b8-110">This means that any service (orchestration or send port) that is subscribing to that message must be associated with a host that owns that key.</span></span> <span data-ttu-id="b07b8-111">ホストとキー間の関連付けは、ホストのプロパティとして、BizTalk 管理コンソールで完了できます。</span><span class="sxs-lookup"><span data-stu-id="b07b8-111">Associations between hosts and keys can be completed in the BizTalk Administration console as a property of the host.</span></span> <span data-ttu-id="b07b8-112">BizTalk 管理コンソールで、ホストを構成する方法の詳細については、次を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="b07b8-112">For more information about configuring the host in the BizTalk Administration console, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
 <span data-ttu-id="b07b8-113">MIME/SMIME デコーダー パイプライン コンポーネントは、のみ-、-インボックス マルチパート MIME/SMIME メッセージなどのマルチパート メッセージを処理するパイプライン コンポーネントを受信します。</span><span class="sxs-lookup"><span data-stu-id="b07b8-113">The MIME/SMIME Decoder pipeline component is the only out-of-the-box receive pipeline component that handles multi-part messages, including multi-part MIME/SMIME messages.</span></span> <span data-ttu-id="b07b8-114">パイプライン コンポーネントは、メッセージを解析し、同等のマルチパート BizTalk メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="b07b8-114">The pipeline component parses the message and creates an equivalent multi-part BizTalk message.</span></span> <span data-ttu-id="b07b8-115">マルチパート BizTalk メッセージが、ボディ部という 1 つの一意の部分です。</span><span class="sxs-lookup"><span data-stu-id="b07b8-115">A multi-part BizTalk message has one unique part named the body part.</span></span> <span data-ttu-id="b07b8-116">すべての他のパイプライン コンポーネントなど、XML 逆アセンブラー パイプライン コンポーネントは、BizTalk メッセージのボディ部を処理するだけです。</span><span class="sxs-lookup"><span data-stu-id="b07b8-116">All other pipeline components, such as the XML Disassembler pipeline component, only process the body part of the BizTalk Message.</span></span> <span data-ttu-id="b07b8-117">また、BizTalk ボディ部に対応する MessageType をサブスクライバーにメッセージをルーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b07b8-117">Also the MessageType corresponding to the BizTalk body part is used for routing the message to subscribers.</span></span>  
  
 <span data-ttu-id="b07b8-118">マルチパート MIME メッセージに対応する BizTalk BodyPart を識別するために、MIME/SMIME デコーダー パイプライン コンポーネントでは、次の条件が評価されます。</span><span class="sxs-lookup"><span data-stu-id="b07b8-118">The following conditions are evaluated by the MIME/SMIME Decoder pipeline component to identify the BizTalk BodyPart corresponding to a multi-part MIME message.</span></span> <span data-ttu-id="b07b8-119">条件の評価の順序は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b07b8-119">The order of the condition evaluation is as follows:</span></span>  
  
1.  <span data-ttu-id="b07b8-120">Content-description ヘッダーが"body"(大文字) に設定する最初の MIME/SMIME 部分。</span><span class="sxs-lookup"><span data-stu-id="b07b8-120">The first MIME/SMIME part that has the Content-Description header set to "body" (case-insensitive).</span></span>  
  
2.  <span data-ttu-id="b07b8-121">最初の MIME/SMIME 部分を"text/xml"(case-insensitive) に設定されたコンテンツ タイプ ヘッダーを持ちます。</span><span class="sxs-lookup"><span data-stu-id="b07b8-121">The first MIME/SMIME part that has the Content-Type header set to "text/xml"(case-insensitive).</span></span>  
  
3.  <span data-ttu-id="b07b8-122">設定コンテンツ タイプ ヘッダーを持つ最初の MIME/SMIME 部分"text/"(大文字)。</span><span class="sxs-lookup"><span data-stu-id="b07b8-122">The first MIME/SMIME part that has the Content-Type header set to "text/" (case-insensitive).</span></span>  
  
4.  <span data-ttu-id="b07b8-123">最初の MIME/SMIME 部分。</span><span class="sxs-lookup"><span data-stu-id="b07b8-123">The first MIME/SMIME part.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b07b8-124">順序の出力の部分の BizTalk メッセージが MIME/SMIME メッセージの MIME/SMIME 部分の順序と同じです。</span><span class="sxs-lookup"><span data-stu-id="b07b8-124">The order of the parts in the output BizTalk message is same as the order of MIME/SMIME parts in the MIME/SMIME message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b07b8-125">マルチパート BizTalk メッセージの中の場合はサブスクライブまたはオーケストレーションによって使用される、メッセージ内の部分の数が、オーケストレーションをアクティブにするメッセージの部分の数と一致します。</span><span class="sxs-lookup"><span data-stu-id="b07b8-125">If the multi-part BizTalk message is being subscribed or consumed by an orchestration, the number of parts in the message has to match the number of parts in the message that activates the orchestration.</span></span>  
  
 <span data-ttu-id="b07b8-126">MIME/SMIME デコーダー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="b07b8-126">For information about configuring the MIME/SMIME Decoder pipeline component, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span> <span data-ttu-id="b07b8-127">BizTalk Server のサポートの復号化、署名認証、証明書の利用状況の詳細については、次を参照してください。[送信と受信メッセージのセキュリティ](../core/security-for-sending-and-receiving-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="b07b8-127">For more information about BizTalk Server support for decryption, sign-validation, and usage of certificates, see [Security for Sending and Receiving Messages](../core/security-for-sending-and-receiving-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07b8-128">参照</span><span class="sxs-lookup"><span data-stu-id="b07b8-128">See Also</span></span>  
 <span data-ttu-id="b07b8-129">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b07b8-129">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 <span data-ttu-id="b07b8-130">[MIME-SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b07b8-130">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="b07b8-131">MIME (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="b07b8-131">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)
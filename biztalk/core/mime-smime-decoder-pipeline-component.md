---
title: MIME/SMIME デコーダー パイプライン コンポーネント |Microsoft ドキュメント
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
ms.openlocfilehash: d85fe099cb876156410ba86c5f204a154dfbac36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263226"
---
# <a name="mime-smime-decoder-pipeline-component"></a><span data-ttu-id="28bbf-102">MIME/SMIME デコーダー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="28bbf-102">MIME-SMIME Decoder Pipeline Component</span></span>
<span data-ttu-id="28bbf-103">MIME/SMIME デコーダー コンポーネントは、メッセージに MIME デコード機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="28bbf-103">The MIME/SMIME Decoder component provides MIME decoding functionality for messages.</span></span> <span data-ttu-id="28bbf-104">このパイプライン コンポーネントは、受信パイプラインのデコード ステージに配置できます。サポートされているエンコードは、7bit、8bit、binary、quoted-printable、UUencode、および base64 です。</span><span class="sxs-lookup"><span data-stu-id="28bbf-104">This pipeline component can be placed into the Decode stage of a receive pipeline, and it supports 7bit, 8bit, binary, quoted-printable, UUEncode, and base64 decoding.</span></span> <span data-ttu-id="28bbf-105">データのローカライズによって文字セットが変わっても、デコードは変更されません。</span><span class="sxs-lookup"><span data-stu-id="28bbf-105">Localized data character set changes will not affect the decoding.</span></span>  
  
 <span data-ttu-id="28bbf-106">MIME/SMIME デコーダー コンポーネントを使用すると、受信メッセージを復号化および署名認証できます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-106">The MIME/SMIME Decoder component can decrypt and sign-validate an incoming message.</span></span> <span data-ttu-id="28bbf-107">暗号化証明書は、サービスを実行する現在のユーザーの個人証明書ストアから使用されます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-107">Decryption certificates are used from the personal certificate store of the current user under which the service is running.</span></span> <span data-ttu-id="28bbf-108">署名認証の証明書は、ローカル コンピューターのアドレス帳ストアまたはメッセージ自体から使用されます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-108">Sign-validation certificates are used from the Address Book store of the local computer or from the message itself.</span></span>  
  
 <span data-ttu-id="28bbf-109">メッセージの復号化に成功すると、MIME/SMIME デコーダー パイプライン コンポーネントは、メッセージの述語としてメッセージを復号化するために使用される暗号化証明書の拇印を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-109">On successful decryption of a message, the MIME/SMIME Decoder pipeline component associates the thumbprint of the decryption certificate used to decrypt the message as a predicate of the message.</span></span> <span data-ttu-id="28bbf-110">これは、メッセージにサブスクライブしているサービス (オーケストレーションまたは送信ポート) をこのキーを所有するホストに関連付ける必要があることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="28bbf-110">This means that any service (orchestration or send port) that is subscribing to that message must be associated with a host that owns that key.</span></span> <span data-ttu-id="28bbf-111">ホストとキー間の関連付けは、BizTalk 管理コンソールで行い、ホストのプロパティで表します。</span><span class="sxs-lookup"><span data-stu-id="28bbf-111">Associations between hosts and keys can be completed in the BizTalk Administration console as a property of the host.</span></span> <span data-ttu-id="28bbf-112">BizTalk 管理コンソールで、ホストの構成の詳細については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="28bbf-112">For more information about configuring the host in the BizTalk Administration console, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
 <span data-ttu-id="28bbf-113">MIME/SMIME デコーダー パイプライン コンポーネントとは、すぐに使用できる受信パイプライン コンポーネントです。このパイプライン コンポーネントでは、マルチパート MIME/SMIME メッセージなどのマルチパート メッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-113">The MIME/SMIME Decoder pipeline component is the only out-of-the-box receive pipeline component that handles multi-part messages, including multi-part MIME/SMIME messages.</span></span> <span data-ttu-id="28bbf-114">パイプライン コンポーネントは、メッセージを解析し、同等のマルチパート BizTalk メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="28bbf-114">The pipeline component parses the message and creates an equivalent multi-part BizTalk message.</span></span> <span data-ttu-id="28bbf-115">マルチパート BizTalk メッセージには、ボディ部というメッセージ固有の部分が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="28bbf-115">A multi-part BizTalk message has one unique part named the body part.</span></span> <span data-ttu-id="28bbf-116">XML 逆アセンブラー パイプライン コンポーネントなどの他のすべてのパイプライン コンポーネントは、BizTalk メッセージのボディ部だけを処理します。</span><span class="sxs-lookup"><span data-stu-id="28bbf-116">All other pipeline components, such as the XML Disassembler pipeline component, only process the body part of the BizTalk Message.</span></span> <span data-ttu-id="28bbf-117">また、BizTalk ボディ部に対応する MessageType は、サブスクライバーへのメッセージのルーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-117">Also the MessageType corresponding to the BizTalk body part is used for routing the message to subscribers.</span></span>  
  
 <span data-ttu-id="28bbf-118">マルチパート MIME メッセージに対応する BizTalk BodyPart を識別するため、MIME/SMIME デコーダー パイプライン コンポーネントによって次の条件が評価されます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-118">The following conditions are evaluated by the MIME/SMIME Decoder pipeline component to identify the BizTalk BodyPart corresponding to a multi-part MIME message.</span></span> <span data-ttu-id="28bbf-119">条件の評価の順番を次に示します。</span><span class="sxs-lookup"><span data-stu-id="28bbf-119">The order of the condition evaluation is as follows:</span></span>  
  
1.  <span data-ttu-id="28bbf-120">Content-Description ヘッダーが "body" (大文字と小文字を区別しない) に設定されている、最初の MIME/SMIME 部分。</span><span class="sxs-lookup"><span data-stu-id="28bbf-120">The first MIME/SMIME part that has the Content-Description header set to "body" (case-insensitive).</span></span>  
  
2.  <span data-ttu-id="28bbf-121">Content-Type ヘッダーが "text/xml" (大文字と小文字を区別しない) に設定されている、最初の MIME/SMIME 部分。</span><span class="sxs-lookup"><span data-stu-id="28bbf-121">The first MIME/SMIME part that has the Content-Type header set to "text/xml"(case-insensitive).</span></span>  
  
3.  <span data-ttu-id="28bbf-122">Content-Type ヘッダーが "text/" (大文字と小文字を区別しない) に設定されている、最初の MIME/SMIME 部分。</span><span class="sxs-lookup"><span data-stu-id="28bbf-122">The first MIME/SMIME part that has the Content-Type header set to "text/" (case-insensitive).</span></span>  
  
4.  <span data-ttu-id="28bbf-123">最初の MIME/SMIME 部分。</span><span class="sxs-lookup"><span data-stu-id="28bbf-123">The first MIME/SMIME part.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28bbf-124">BizTalk 出力メッセージにおける上記の各部分の順序は、MIME/SMIME メッセージの MIME/SMIME 部分の順序と同じです。</span><span class="sxs-lookup"><span data-stu-id="28bbf-124">The order of the parts in the output BizTalk message is same as the order of MIME/SMIME parts in the MIME/SMIME message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28bbf-125">マルチパート BizTalk メッセージがオーケストレーションによってサブスクライブまたは使用されている場合、メッセージの構成部分の数と、オーケストレーションをアクティブにするメッセージの構成部分の数は一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28bbf-125">If the multi-part BizTalk message is being subscribed or consumed by an orchestration, the number of parts in the message has to match the number of parts in the message that activates the orchestration.</span></span>  
  
 <span data-ttu-id="28bbf-126">MIME/SMIME デコーダー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [- MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="28bbf-126">For information about configuring the MIME/SMIME Decoder pipeline component, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span> <span data-ttu-id="28bbf-127">復号化、署名の検証、および証明書の使用状況の BizTalk Server サポートに関する詳細については、次を参照してください。[送信および受信メッセージのセキュリティを](../core/security-for-sending-and-receiving-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="28bbf-127">For more information about BizTalk Server support for decryption, sign-validation, and usage of certificates, see [Security for Sending and Receiving Messages](../core/security-for-sending-and-receiving-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28bbf-128">参照</span><span class="sxs-lookup"><span data-stu-id="28bbf-128">See Also</span></span>  
 <span data-ttu-id="28bbf-129">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="28bbf-129">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 <span data-ttu-id="28bbf-130">[MIME/SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="28bbf-130">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="28bbf-131">MIME (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="28bbf-131">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)
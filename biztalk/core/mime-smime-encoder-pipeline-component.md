---
title: MIME/SMIME エンコーダー パイプライン コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Encoder
- MIME/SMIME Encoder [pipeline component]
- BTS.EncryptionCert property
ms.assetid: 397505e6-47d0-4b63-9197-814ee4388369
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c6a79052d3294420c46bff2a1ce3c0ed869e48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263066"
---
# <a name="mime-smime-encoder-pipeline-component"></a><span data-ttu-id="d0415-102">MIME/SMIME エンコーダー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d0415-102">MIME-SMIME Encoder Pipeline Component</span></span>
<span data-ttu-id="d0415-103">MIME/SMIME エンコーダー コンポーネントは、送信パイプラインのエンコード ステージに配置できます。</span><span class="sxs-lookup"><span data-stu-id="d0415-103">The MIME/SMIME Encoder component can be placed into the Encode stage of a send pipeline.</span></span> <span data-ttu-id="d0415-104">サポートされているエンコードは、7bit、8bit、binary、quoted-printable、base64、および UUencode です。</span><span class="sxs-lookup"><span data-stu-id="d0415-104">It supports 7bit, 8bit, binary, quoted-printable, base64, and UUencode encoding.</span></span> <span data-ttu-id="d0415-105">データのローカライズによって文字セットが変わっても、エンコードは変更されません。</span><span class="sxs-lookup"><span data-stu-id="d0415-105">Localized data character set changes do not affect the encoding.</span></span>  
  
 <span data-ttu-id="d0415-106">このコンポーネントは、MIME エンコードのほか、暗号化証明書や署名証明書による送信メッセージの署名および暗号化に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0415-106">This component can be used to either MIME encode, sign or encrypt an outgoing message with encryption and signing certificates.</span></span>  
  
 <span data-ttu-id="d0415-107">メッセージに署名を施すように構成されたエンコード コンポーネントが送信パイプラインに存在していても、そのパイプラインの実行ホストの BizTalk グループが署名証明書を使って構成されていなかった場合、送信メッセージは中断され (該当するエラーが発生する)、パイプラインを実行しているホストの保留キューに移動されます。</span><span class="sxs-lookup"><span data-stu-id="d0415-107">If there is an encoding component in the send pipeline that is configured to sign messages, and the BizTalk group that includes the host running the pipeline is not configured with a signing certificate, the outgoing message will be suspended (with the appropriate error) to the suspended queue of the host that is running the pipeline.</span></span> <span data-ttu-id="d0415-108">サービスの実行に使用されているアカウント (現在のユーザー) の個人証明書ストアに署名証明書が見つからなかった場合、メッセージは中断され、パイプラインを実行しているホストの保留キューに移動されます。</span><span class="sxs-lookup"><span data-stu-id="d0415-108">If the signing certificate cannot be found in the personal certificate store of the current user under which the service is running, the message will be suspended to the suspended queue of the host that is running the pipeline.</span></span>  
  
 <span data-ttu-id="d0415-109">送信メッセージを暗号化するように構成されたエンコード コンポーネントが送信パイプラインに存在していても、その証明書が証明書ストアに見つからない場合、メッセージは中断され、パイプラインを実行しているホストの保留キューに移動されます。</span><span class="sxs-lookup"><span data-stu-id="d0415-109">If there is an encoding component in the outbound pipeline configured to encrypt outbound messages, and the certificate cannot be found in the certificate store, the message will be suspended to the suspended queue of the host that is running the pipeline.</span></span>  
  
 <span data-ttu-id="d0415-110">署名または暗号化されたメッセージを受け取る要求 - 応答ポートで応答を暗号化する場合は、MIME/SMIME Encoder パイプライン コンポーネントの前のパイプラインにカスタム パイプライン コンポーネントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0415-110">To perform response encryption on a request-response port that is receiving signed and encrypted messages, a custom pipeline component must be added to the pipeline before the MIME/SMIME Encoder pipeline component.</span></span> <span data-ttu-id="d0415-111">このカスタム パイプライン コンポーネントは、暗号化証明書に対応する拇印を識別する必要がありますに設定し、 **BTS です。EncryptionCert**メッセージ コンテキストのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d0415-111">This custom pipeline component must identify the thumbprint corresponding to the encryption certificate and set it to the **BTS.EncryptionCert** property on the message context.</span></span> <span data-ttu-id="d0415-112">メッセージ コンテキスト プロパティの詳細については、次を参照してください。[グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0415-112">For more information about message context properties, see [How to Modify Group Properties](../core/how-to-modify-group-properties.md).</span></span>  
  
 <span data-ttu-id="d0415-113">MIME/SMIME エンコーダー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [- MIME/SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0415-113">For information about configuring the MIME/SMIME Encoder pipeline component, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span> <span data-ttu-id="d0415-114">暗号化、署名、および証明書の使用状況の BizTalk Server サポートに関する詳細については、次を参照してください。[送信および受信メッセージのセキュリティを](../core/security-for-sending-and-receiving-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0415-114">For more information about BizTalk Server support for encryption, signing, and usage of certificates, see [Security for Sending and Receiving Messages](../core/security-for-sending-and-receiving-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0415-115">参照</span><span class="sxs-lookup"><span data-stu-id="d0415-115">See Also</span></span>  
 <span data-ttu-id="d0415-116">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="d0415-116">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 <span data-ttu-id="d0415-117">[MIME/SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d0415-117">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="d0415-118">MIME (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d0415-118">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)
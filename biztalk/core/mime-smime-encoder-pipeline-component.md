---
title: MIME-SMIME エンコーダー パイプライン コンポーネント |Microsoft Docs
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
ms.openlocfilehash: c20197519f6bde52470712175cb632a7309c3609
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527536"
---
# <a name="mime-smime-encoder-pipeline-component"></a><span data-ttu-id="876bf-102">MIME-SMIME エンコーダー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="876bf-102">MIME-SMIME Encoder Pipeline Component</span></span>
<span data-ttu-id="876bf-103">MIME/SMIME エンコーダー コンポーネントは、送信パイプラインのエンコード ステージに配置できます。</span><span class="sxs-lookup"><span data-stu-id="876bf-103">The MIME/SMIME Encoder component can be placed into the Encode stage of a send pipeline.</span></span> <span data-ttu-id="876bf-104">7 bit、8 bit、binary、quoted-printable、base64、および UUencode エンコーディングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="876bf-104">It supports 7bit, 8bit, binary, quoted-printable, base64, and UUencode encoding.</span></span> <span data-ttu-id="876bf-105">ローカライズされたデータの文字セットの変更は、エンコーディングには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="876bf-105">Localized data character set changes do not affect the encoding.</span></span>  
  
 <span data-ttu-id="876bf-106">このコンポーネントは、いずれかの MIME に使用することができます、エンコードの署名または暗号化と署名証明書による送信メッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="876bf-106">This component can be used to either MIME encode, sign or encrypt an outgoing message with encryption and signing certificates.</span></span>  
  
 <span data-ttu-id="876bf-107">エンコード コンポーネントが構成されている送信パイプラインである場合は、メッセージ、およびパイプラインを実行しているホストを含む BizTalk グループの署名に使用されていない署名証明書を (と適切な送信メッセージは中断されます。エラー)、パイプラインを実行しているホストの保留キューにします。</span><span class="sxs-lookup"><span data-stu-id="876bf-107">If there is an encoding component in the send pipeline that is configured to sign messages, and the BizTalk group that includes the host running the pipeline is not configured with a signing certificate, the outgoing message will be suspended (with the appropriate error) to the suspended queue of the host that is running the pipeline.</span></span> <span data-ttu-id="876bf-108">サービスが実行されている現在のユーザーの個人証明書ストアに署名証明書が見つからない場合は、パイプラインを実行しているホストの保留キューにメッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="876bf-108">If the signing certificate cannot be found in the personal certificate store of the current user under which the service is running, the message will be suspended to the suspended queue of the host that is running the pipeline.</span></span>  
  
 <span data-ttu-id="876bf-109">送信メッセージを暗号化するように構成する送信パイプラインのエンコード コンポーネントがあるし、証明書ストアに証明書が見つかりません場合、は、パイプラインを実行しているホストの保留キューにメッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="876bf-109">If there is an encoding component in the outbound pipeline configured to encrypt outbound messages, and the certificate cannot be found in the certificate store, the message will be suspended to the suspended queue of the host that is running the pipeline.</span></span>  
  
 <span data-ttu-id="876bf-110">署名および暗号化されたメッセージを受信する要求-応答ポートで応答を暗号化を実行するには、MIME/SMIME エンコーダー パイプライン コンポーネントの前にパイプラインにカスタム パイプライン コンポーネントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="876bf-110">To perform response encryption on a request-response port that is receiving signed and encrypted messages, a custom pipeline component must be added to the pipeline before the MIME/SMIME Encoder pipeline component.</span></span> <span data-ttu-id="876bf-111">このカスタム パイプライン コンポーネントの暗号化証明書に対応する拇印を識別しに設定する必要があります、 **BTS します。EncryptionCert**メッセージ コンテキストのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="876bf-111">This custom pipeline component must identify the thumbprint corresponding to the encryption certificate and set it to the **BTS.EncryptionCert** property on the message context.</span></span> <span data-ttu-id="876bf-112">メッセージ コンテキスト プロパティの詳細については、次を参照してください。[グループ プロパティを変更する方法](../core/how-to-modify-group-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="876bf-112">For more information about message context properties, see [How to Modify Group Properties](../core/how-to-modify-group-properties.md).</span></span>  
  
 <span data-ttu-id="876bf-113">MIME/SMIME エンコーダー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="876bf-113">For information about configuring the MIME/SMIME Encoder pipeline component, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span> <span data-ttu-id="876bf-114">暗号化、署名、および証明書の使用状況の BizTalk Server のサポートの詳細については、次を参照してください。[送信と受信メッセージのセキュリティ](../core/security-for-sending-and-receiving-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="876bf-114">For more information about BizTalk Server support for encryption, signing, and usage of certificates, see [Security for Sending and Receiving Messages](../core/security-for-sending-and-receiving-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876bf-115">参照</span><span class="sxs-lookup"><span data-stu-id="876bf-115">See Also</span></span>  
 <span data-ttu-id="876bf-116">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="876bf-116">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 <span data-ttu-id="876bf-117">[MIME-SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="876bf-117">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="876bf-118">MIME (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="876bf-118">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)
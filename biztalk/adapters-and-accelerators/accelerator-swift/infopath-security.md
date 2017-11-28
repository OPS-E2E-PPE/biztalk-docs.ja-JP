---
title: "InfoPath セキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, InfoPath forms
- InfoPath forms, security
ms.assetid: 6ed7b5cc-9801-45a5-8fdb-e5d56dd36435
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ec5478af7c404840bf1c5c80be5520e405bd26a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="infopath-security"></a><span data-ttu-id="3b92b-102">InfoPath のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3b92b-102">InfoPath Security</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="3b92b-103">[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 では、XML 署名を使用して、デジタル証明書を使用してフォームにデジタル署名できます。</span><span class="sxs-lookup"><span data-stu-id="3b92b-103"> [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 uses XML Signatures to let you digitally sign a form using a digital certificate.</span></span> <span data-ttu-id="3b92b-104">XML 署名では、XML ドキュメントに含まれるデータを保護するために使用する XML ベースのデジタル署名用の標準を定義します。</span><span class="sxs-lookup"><span data-stu-id="3b92b-104">XML Signatures defines a standard for XML-based digital signatures that you use to help secure the data contained in XML documents.</span></span> <span data-ttu-id="3b92b-105">XML 署名は、World Wide Web Consortium (W3C) によって管理される標準です。</span><span class="sxs-lookup"><span data-stu-id="3b92b-105">XML Signatures is a standard governed by the World Wide Web Consortium (W3C).</span></span>  
  
 <span data-ttu-id="3b92b-106">デジタル署名は、マクロまたはドキュメントの認証の電子、暗号化ベース、セキュリティで保護されたタイムスタンプです。</span><span class="sxs-lookup"><span data-stu-id="3b92b-106">A digital signature is an electronic, encryption-based, secure stamp of authentication on a macro or document.</span></span> <span data-ttu-id="3b92b-107">デジタル署名するときに、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、フォームを使用して入力 XML インスタンスが「スタンプ」デジタル署名 (署名公開キーおよび署名されたデータ ダイジェストは、XML に専用のノードに書き込まれます)。</span><span class="sxs-lookup"><span data-stu-id="3b92b-107">When digitally signing an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, the XML instance entered through the form is "stamped" with a digital signature (the signature public key and signed data digest is written to a dedicated node in the XML).</span></span> <span data-ttu-id="3b92b-108">この署名は、XML ドキュメントが署名者から発信されが改変されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b92b-108">This signature confirms that the XML document originated from the signer and has not been altered.</span></span> [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]<span data-ttu-id="3b92b-109">署名の検証可能な否認、部分署名、cosigning と副強化されたデジタル署名のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="3b92b-109"> provides verifiable, non-repudiable signing, partial signing, cosigning and countersigning through enhanced digital signature support.</span></span>  
  
 <span data-ttu-id="3b92b-110">SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] A4SWIFT によって提供される FormGenerator ユーティリティを使用して生成されたフォームでは、デジタル署名の countersigning メソッドを使用して、互いの上に重ねられます countersigners の署名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b92b-110">The SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms generated with the FormGenerator utility provided by A4SWIFT use the countersigning method of digital signing to let signatures of countersigners to be stacked on top of each other.</span></span> <span data-ttu-id="3b92b-111">この countersigning 署名スタックの作成、SWIFT メッセージを編集または確認し、1 つ以上のレビュー担当者と、承認者によって承認されたメッセージが含まれる、および最後に、ワークフロー内のすべての段階の後にそのメッセージを送信する、人間指向プロセスをモデル化します。サインオフします。</span><span class="sxs-lookup"><span data-stu-id="3b92b-111">This countersigning signature stack models the human-oriented process of creating or editing a SWIFT message, having the message reviewed and approved by one or more reviewers and approvers, and finally submitting that message only after all stages in a workflow have signed off.</span></span>  
  
 <span data-ttu-id="3b92b-112">Repairers、レビュー担当者、または承認者は、承認または拒否するかどうかに関係なくメッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="3b92b-112">Repairers, reviewers, or approvers sign the message regardless of whether they approve or reject it.</span></span> <span data-ttu-id="3b92b-113">署名は、応答の信頼性を示すし、「承認済み」の意思決定を必ずしも意味しません。</span><span class="sxs-lookup"><span data-stu-id="3b92b-113">The signature signifies authenticity of the response and does not necessarily signify an "accepted" decision.</span></span>  
  
 <span data-ttu-id="3b92b-114">ときに、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームが送信されるメッセージの有効性がチェックされ、フォームへの署名、ユーザーが適切なロールにあります。</span><span class="sxs-lookup"><span data-stu-id="3b92b-114">When the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form is submitted, it checks messages for validity and that the user signing the form is in the correct role.</span></span>  
  
 <span data-ttu-id="3b92b-115">(修復) だけでなく、ワークフローで何らかの段階でメッセージが拒否された場合、メッセージは、修復ステージに送信されます。</span><span class="sxs-lookup"><span data-stu-id="3b92b-115">If the message is rejected at any stage in a workflow (besides repair), the message is sent back to the repair stage.</span></span> <span data-ttu-id="3b92b-116">場合は、修理会社または作成者段階で、Message Repair、メッセージは拒否され、New Submission Message Repair and New Submission のオーケストレーション インスタンスにスイッチ_バック拒否メッセージをマークする特定のプロパティを持つメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3b92b-116">If the message is rejected at the repairer or creator stage, Message Repair and New Submission sends the message back to the Message Repair and New Submission orchestration instance with specific properties marking the message as rejected.</span></span>  
  
 <span data-ttu-id="3b92b-117">このセクションでは、Message Repair and New Submission のロールに対して定義されている機能に基づくデジタル署名を処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b92b-117">This section describes how Message Repair and New Submission handles the digital signatures based on the capabilities defined for a role.</span></span> <span data-ttu-id="3b92b-118">役割と機能の組み合わせには、ワークフロー内の「ステージ」は呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3b92b-118">The role and capability combination is called a "stage" in the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b92b-119">ロールの「作成」は、すべての部門間で 1 つの作成者に制限されます。</span><span class="sxs-lookup"><span data-stu-id="3b92b-119">The "create" role is limited to a single creator across all departments.</span></span>  
  
 <span data-ttu-id="3b92b-120">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b92b-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="3b92b-121">作成し、修復ステージ</span><span class="sxs-lookup"><span data-stu-id="3b92b-121">Create and Repair Stages</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [<span data-ttu-id="3b92b-122">検証ステージを鍵更新します。</span><span class="sxs-lookup"><span data-stu-id="3b92b-122">Rekey Verification Stage</span></span>](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [<span data-ttu-id="3b92b-123">承認ステージ</span><span class="sxs-lookup"><span data-stu-id="3b92b-123">Approval Stage</span></span>](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [<span data-ttu-id="3b92b-124">デジタル証明書を配布します。</span><span class="sxs-lookup"><span data-stu-id="3b92b-124">Distributing Digital Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)
---
title: パイプラインをセキュリティで保護する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3a717f-acf8-4f08-a6fb-6d1d48b5b80a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e27ba4d24dd8109366af95b0a477fc8fb049ce5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334824"
---
# <a name="how-to-secure-pipelines"></a><span data-ttu-id="38024-102">パイプラインをセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="38024-102">How to Secure Pipelines</span></span>

## <a name="authentication-trusted"></a><span data-ttu-id="38024-103">信頼された認証</span><span class="sxs-lookup"><span data-stu-id="38024-103">Authentication trusted</span></span>
<span data-ttu-id="38024-104">ホストとして、管理コンソールでマークできる**信頼されている認証**します。</span><span class="sxs-lookup"><span data-stu-id="38024-104">Hosts can be marked in the administration console as **Authentication Trusted**.</span></span> <span data-ttu-id="38024-105">信頼されている認証としてホストを示す Microsoft BizTalk Server がメッセージのメッセージ コンテキストでそのホストから送信されたセキュリティ関連のプロパティを信頼することを意味します。</span><span class="sxs-lookup"><span data-stu-id="38024-105">Denoting a host as Authentication Trusted means that the Microsoft BizTalk Server will trust the security-related properties sent on the message context of a message from that host.</span></span> <span data-ttu-id="38024-106">セキュリティ関連のプロパティをメッセージ コンテキストでは、 **OriginatorPID**、BTS メッセージ コンテキスト プロパティに対応します。SourcePartyID、および**OriginatorSID**、メッセージ コンテキスト プロパティに対応する**BTS します。WindowsUser**します。</span><span class="sxs-lookup"><span data-stu-id="38024-106">The security-related properties on the message context are the **OriginatorPID**, which corresponds to the message context property BTS.SourcePartyID, and the **OriginatorSID**, which corresponds to the message context property **BTS.WindowsUser**.</span></span> <span data-ttu-id="38024-107">詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="38024-107">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="38024-108">としてマークされているホスト**認証が信頼された**を信頼されたホストが追加されるメッセージ キュー自体以外のユーザーから、メッセージの送信者として示すためには許可されています。</span><span class="sxs-lookup"><span data-stu-id="38024-108">A host that is marked as **Authentication Trusted** is allowed to indicate that the trusted host is adding a message to the queue from someone other than itself as the sender of the message.</span></span> <span data-ttu-id="38024-109">つまり、としてマークされていないホスト**信頼されている認証**自体以外のメッセージの送信者からキューにメッセージを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="38024-109">In other words, hosts that are not marked as **Authentication Trusted** are not allowed to add a message to the queue from a message sender other than themselves.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="38024-110">MIME/SMIME デコーダー パイプライン コンポーネントでは、暗号化解除証明書の有効期限はチェックしません。</span><span class="sxs-lookup"><span data-stu-id="38024-110">The MIME/SMIME Decoder pipeline component does not check the expiration date of decryption certificates.</span></span> <span data-ttu-id="38024-111">ただし、署名証明書の有効期限はチェックします。</span><span class="sxs-lookup"><span data-stu-id="38024-111">However, it does check the expiration date of signing certificates.</span></span>  
  
 <span data-ttu-id="38024-112">エンコードおよびデコードの SMTP または HTTP 経由で送信されるメッセージについては、次を参照してください。 [MIME-SMIME エンコーダー パイプライン コンポーネント](../core/mime-smime-encoder-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="38024-112">For information about encoding and decoding messages sent over SMTP or HTTP, see [MIME-SMIME Encoder Pipeline Component](../core/mime-smime-encoder-pipeline-component.md).</span></span> <span data-ttu-id="38024-113">参照してください[MIME/SMIME デコーダー パイプライン コンポーネント](../core/mime-smime-decoder-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="38024-113">Also see [MIME-SMIME Decoder Pipeline Component](../core/mime-smime-decoder-pipeline-component.md).</span></span>  
  
 <span data-ttu-id="38024-114">ときに、サード パーティの署名の確認については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="38024-114">For information about signature verification when dealing with third parties, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span> <span data-ttu-id="38024-115">参照してください[アグリーメントを作成する方法](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)します。</span><span class="sxs-lookup"><span data-stu-id="38024-115">Also see [How to Create an Agreement](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38024-116">参照</span><span class="sxs-lookup"><span data-stu-id="38024-116">See Also</span></span>  
 <span data-ttu-id="38024-117">[パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="38024-117">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="38024-118">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="38024-118">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)
---
title: "生成して、証明書の有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, enabling
- private process tutorial, creating certificates
- private process tutorial, enabling certificates
ms.assetid: a36d9725-d57c-499d-948d-558096709d67
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93293939ae509dcb2af04e17fcdd35e9cf6d03cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generating-and-enabling-certificates"></a><span data-ttu-id="8c7f4-102">生成して、証明書の有効化</span><span class="sxs-lookup"><span data-stu-id="8c7f4-102">Generating and Enabling Certificates</span></span>
<span data-ttu-id="8c7f4-103">このチュートリアルでは、Contoso 組織と Fabrikam 組織によって送信されたメッセージに署名し、暗号化するために、証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c7f4-103">This tutorial uses certificates to sign and encrypt messages sent by the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="8c7f4-104">ダブル アクション チュートリアルを既に実行している場合は、この手順をスキップしてに移動することが[Contoso ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="8c7f4-104">If you have already completed the Double Action Tutorial, you may skip this step and move on to [Creating the Contoso Solution](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md).</span></span> <span data-ttu-id="8c7f4-105">このチュートリアルで使う証明書を生成して使用するには、以下のトピックの順番で手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8c7f4-105">To generate and use certificates for this tutorial, follow the procedures in the following topics:</span></span>  
  
-   [<span data-ttu-id="8c7f4-106">手順 1: 証明機関の作成</span><span class="sxs-lookup"><span data-stu-id="8c7f4-106">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="8c7f4-107">手順 2: パブリックおよびプライベート証明書の作成</span><span class="sxs-lookup"><span data-stu-id="8c7f4-107">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="8c7f4-108">手順 3: パブリックおよびプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="8c7f4-108">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="8c7f4-109">手順 4: IIS でレイヤーをソケット セキュリティで保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8c7f4-109">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c7f4-110">これらの手順は、ダブル アクション チュートリアルにあります。</span><span class="sxs-lookup"><span data-stu-id="8c7f4-110">These steps are in the Double Action Tutorial.</span></span> <span data-ttu-id="8c7f4-111">各手順を完了したら、このトピックに戻り、プライベート プロセス チュートリアルを続行します。</span><span class="sxs-lookup"><span data-stu-id="8c7f4-111">After completing each step, return to this topic to continue the Private Process Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7f4-112">参照</span><span class="sxs-lookup"><span data-stu-id="8c7f4-112">See Also</span></span>  
 [<span data-ttu-id="8c7f4-113">Contoso ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="8c7f4-113">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)
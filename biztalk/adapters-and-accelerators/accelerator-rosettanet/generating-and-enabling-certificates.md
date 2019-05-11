---
title: 生成と証明書の有効化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, enabling
- private process tutorial, creating certificates
- private process tutorial, enabling certificates
ms.assetid: a36d9725-d57c-499d-948d-558096709d67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faf4218919ec2c47729ce1002f17d73ac79584ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283687"
---
# <a name="generating-and-enabling-certificates"></a><span data-ttu-id="5a5c4-102">生成と証明書の有効化</span><span class="sxs-lookup"><span data-stu-id="5a5c4-102">Generating and Enabling Certificates</span></span>
<span data-ttu-id="5a5c4-103">このチュートリアルでは、署名し、Contoso と Fabrikam 組織によって送信されたメッセージの暗号化に証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a5c4-103">This tutorial uses certificates to sign and encrypt messages sent by the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="5a5c4-104">ダブル アクション チュートリアルを既に完了この手順をスキップしに移動する可能性があります[Contoso ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a5c4-104">If you have already completed the Double Action Tutorial, you may skip this step and move on to [Creating the Contoso Solution](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md).</span></span> <span data-ttu-id="5a5c4-105">生成して、証明書を使用して、このチュートリアルでは、次のトピックの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5a5c4-105">To generate and use certificates for this tutorial, follow the procedures in the following topics:</span></span>  
  
-   [<span data-ttu-id="5a5c4-106">ステップ 1: 証明機関の作成</span><span class="sxs-lookup"><span data-stu-id="5a5c4-106">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="5a5c4-107">手順 2:パブリックおよびプライベート証明書の作成</span><span class="sxs-lookup"><span data-stu-id="5a5c4-107">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="5a5c4-108">ステップ 3:パブリック証明書とプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="5a5c4-108">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="5a5c4-109">手順 4:IIS での SSL (Secure Sockets Layer) の有効化</span><span class="sxs-lookup"><span data-stu-id="5a5c4-109">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)  
  
> [!IMPORTANT]
>  <span data-ttu-id="5a5c4-110">これらの手順では、ダブル アクション チュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="5a5c4-110">These steps are in the Double Action Tutorial.</span></span> <span data-ttu-id="5a5c4-111">各手順を完了するには、プライベート プロセス チュートリアルを続行するには、このトピックに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5a5c4-111">After completing each step, return to this topic to continue the Private Process Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a5c4-112">参照</span><span class="sxs-lookup"><span data-stu-id="5a5c4-112">See Also</span></span>  
 [<span data-ttu-id="5a5c4-113">Contoso ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="5a5c4-113">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)
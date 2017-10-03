---
title: "BizTalk Server で RosettaNet のダブル アクション チュートリアルの前提条件 |Microsoft ドキュメント"
description: "BizTalk Server では、RosettaNet accelerator (BTARN)、ダブル アクション チュートリアルの手順の前提条件"
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87e2750a16d2c65b5838b6d61f27cbd2b2ff9885
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-for-the-double-action-tutorial"></a><span data-ttu-id="56f8b-103">ダブル アクション チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="56f8b-103">Prepare for the Double Action tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56f8b-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="56f8b-104">Prerequisites</span></span>
<span data-ttu-id="56f8b-105">このチュートリアルを開始: する前に</span><span class="sxs-lookup"><span data-stu-id="56f8b-105">Before starting the tutorial:</span></span>
  
-   <span data-ttu-id="56f8b-106">BizTalk Server の完全インストールを行うと[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]2 台のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="56f8b-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="56f8b-107">詳細については、次を参照してください。[をインストールして構成する](install-configure-biztalk-accelerator-for-rosettanet.md)です。</span><span class="sxs-lookup"><span data-stu-id="56f8b-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="56f8b-108">BTARN オーケストレーションを開始するなど、RosettaNet accelerator を完全に構成することを確認します。</span><span class="sxs-lookup"><span data-stu-id="56f8b-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="56f8b-109">参照してください[をインストールして構成する](install-configure-biztalk-accelerator-for-rosettanet.md)です。</span><span class="sxs-lookup"><span data-stu-id="56f8b-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
-   <span data-ttu-id="56f8b-110">このチュートリアルでは、ループバック アグリーメントを持つ 1 台のコンピューターではなく 2 台のコンピューターを使用して、実際のシナリオをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="56f8b-110">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loopback agreement.</span></span> <span data-ttu-id="56f8b-111">このチュートリアルで使用するコンピューター名は、プレースホルダーとして示されます。</span><span class="sxs-lookup"><span data-stu-id="56f8b-111">Whenever this tutorial uses computer names, it uses a placeholder.</span></span> <span data-ttu-id="56f8b-112">選択した実際のコンピューター名でそのプレース ホルダーを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="56f8b-112">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="56f8b-113">たとえば、コンピューター、Contoso ソリューションを実行している場合は、という名前の**Contoso**のチュートリアルでは置換\\ \\< contoso**_** *コンピューター*> そのコンピューターの名前を持つ。</span><span class="sxs-lookup"><span data-stu-id="56f8b-113">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso**_***computer*> with that computer name.</span></span>  
  
-   <span data-ttu-id="56f8b-114">このチュートリアルでは、Contoso と Fabrikam の間で証明書を使用する、セキュリティで保護された通信の使用を推奨します。</span><span class="sxs-lookup"><span data-stu-id="56f8b-114">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="56f8b-115">を必要として、それぞれのコンピューターでインストールするには、すべての証明書を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56f8b-115">You must generate any certificates you require, and install them on their respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="56f8b-116">次の手順</span><span class="sxs-lookup"><span data-stu-id="56f8b-116">Next steps</span></span> 
  
-   [<span data-ttu-id="56f8b-117">手順 1: 証明機関の作成</span><span class="sxs-lookup"><span data-stu-id="56f8b-117">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="56f8b-118">手順 2: パブリックおよびプライベート証明書の作成</span><span class="sxs-lookup"><span data-stu-id="56f8b-118">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="56f8b-119">手順 3: パブリックおよびプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="56f8b-119">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="56f8b-120">手順 4: IIS でレイヤーをソケット セキュリティで保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="56f8b-120">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)
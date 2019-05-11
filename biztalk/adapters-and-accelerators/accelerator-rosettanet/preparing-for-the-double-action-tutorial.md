---
title: BizTalk Server で RosettaNet のダブル アクション チュートリアルの前提条件 |Microsoft Docs
description: BizTalk Server では、RosettaNet アクセラレータ (BTARN) のダブル アクション チュートリアルの手順の前提条件
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 402740d8ed1af9cd3677652d7c2e1a9bbc2724c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282667"
---
# <a name="prepare-for-the-double-action-tutorial"></a><span data-ttu-id="80466-103">ダブル アクション チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="80466-103">Prepare for the Double Action tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80466-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="80466-104">Prerequisites</span></span>
<span data-ttu-id="80466-105">前に、チュートリアルを開始するには。</span><span class="sxs-lookup"><span data-stu-id="80466-105">Before starting the tutorial:</span></span>
  
- <span data-ttu-id="80466-106">BizTalk Server のフル インストールを行うと[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]2 台のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="80466-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="80466-107">詳細については、次を参照してください。[インストールおよび構成](install-configure-biztalk-accelerator-for-rosettanet.md)します。</span><span class="sxs-lookup"><span data-stu-id="80466-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="80466-108">BTARN オーケストレーションを開始するなど、RosettaNet アクセラレータを完全に構成してください。</span><span class="sxs-lookup"><span data-stu-id="80466-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="80466-109">参照してください[インストールおよび構成](install-configure-biztalk-accelerator-for-rosettanet.md)します。</span><span class="sxs-lookup"><span data-stu-id="80466-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
- <span data-ttu-id="80466-110">このチュートリアルでは、2 台のコンピューターを使用して、ループバック アグリーメントを持つ 1 台のコンピューターではなく、実際のシナリオをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="80466-110">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loopback agreement.</span></span> <span data-ttu-id="80466-111">このチュートリアルで使用するコンピューター名は、プレースホルダーとして示されます。</span><span class="sxs-lookup"><span data-stu-id="80466-111">Whenever this tutorial uses computer names, it uses a placeholder.</span></span> <span data-ttu-id="80466-112">選択した実際のコンピューター名では、そのプレース ホルダーを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="80466-112">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="80466-113">たとえば、コンピューター、Contoso ソリューションを実行している場合がという名前**Contoso**のチュートリアルでは置換\\ \\< contoso<strong>_</strong> *コンピューター* \>そのコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="80466-113">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso<strong>_</strong>*computer*\> with that computer name.</span></span>  
  
- <span data-ttu-id="80466-114">このチュートリアルでは、Contoso と Fabrikam の間で証明書を使用する、セキュリティで保護された通信の使用を推奨します。</span><span class="sxs-lookup"><span data-stu-id="80466-114">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="80466-115">それぞれのコンピューターにインストールして、必要なすべての証明書を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80466-115">You must generate any certificates you require, and install them on their respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="80466-116">次のステップ</span><span class="sxs-lookup"><span data-stu-id="80466-116">Next steps</span></span> 
  
-   [<span data-ttu-id="80466-117">ステップ 1: 証明機関の作成</span><span class="sxs-lookup"><span data-stu-id="80466-117">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="80466-118">手順 2:パブリックおよびプライベート証明書の作成</span><span class="sxs-lookup"><span data-stu-id="80466-118">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="80466-119">ステップ 3:パブリック証明書とプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="80466-119">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="80466-120">手順 4:IIS での SSL (Secure Sockets Layer) の有効化</span><span class="sxs-lookup"><span data-stu-id="80466-120">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)
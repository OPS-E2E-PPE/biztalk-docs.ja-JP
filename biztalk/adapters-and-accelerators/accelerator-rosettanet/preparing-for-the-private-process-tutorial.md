---
title: BizTalk Server で RosettaNet プライベート プロセス チュートリアルの前提条件 |Microsoft Docs
description: BizTalk Server では、RosettaNet アクセラレータ (BTARN) のプライベート プロセス チュートリアルの手順の前提条件
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 4f2a218063bc7f8d90205480887c90c6f6be78d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282723"
---
# <a name="prepare-for-the-private-process-tutorial"></a><span data-ttu-id="8c312-103">プライベート プロセス チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="8c312-103">Prepare for the Private Process tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c312-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="8c312-104">Prerequisites</span></span>
<span data-ttu-id="8c312-105">前に、チュートリアルを開始するには。</span><span class="sxs-lookup"><span data-stu-id="8c312-105">Before starting the tutorial:</span></span>
  
- <span data-ttu-id="8c312-106">BizTalk Server のフル インストールを行うと[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]2 台のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="8c312-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="8c312-107">詳細については、次を参照してください。[インストールおよび構成](install-configure-biztalk-accelerator-for-rosettanet.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c312-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="8c312-108">BTARN オーケストレーションを開始するなど、RosettaNet アクセラレータを完全に構成してください。</span><span class="sxs-lookup"><span data-stu-id="8c312-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="8c312-109">参照してください[インストールおよび構成](install-configure-biztalk-accelerator-for-rosettanet.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c312-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span> <span data-ttu-id="8c312-110">追加する必要がありますも、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Microsoft Windows® SharePoint™ Services 管理パスの除外一覧に仮想ディレクトリ (btarnhttpreceive を含む)。</span><span class="sxs-lookup"><span data-stu-id="8c312-110">You may also have to add the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] virtual directories (including btarnhttpreceive) to the Microsoft Windows® SharePoint™ Services managed path exclusion list.</span></span> 
  
- <span data-ttu-id="8c312-111">このチュートリアルでは、ループバック アグリーメントを使用して 1 台のコンピューターでシミュレートするのではなく、コンピューターを 2 台使用して、現実的なシナリオをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="8c312-111">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loop-back agreement.</span></span> <span data-ttu-id="8c312-112">このチュートリアルでは、コンピューター名を使用するたびに、コンピューター名としてプレース ホルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c312-112">Whenever this tutorial uses computer names, it uses a placeholder as the computer name.</span></span> <span data-ttu-id="8c312-113">選択した実際のコンピューター名では、そのプレース ホルダーを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8c312-113">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="8c312-114">たとえば、コンピューター、Contoso ソリューションを実行している場合がという名前**Contoso**のチュートリアルでは置換\\ \\< contoso<strong>_</strong> *コンピューター* \>そのコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="8c312-114">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso<strong>_</strong>*computer*\> with that computer name.</span></span>  
  
  <span data-ttu-id="8c312-115">このチュートリアルでは、Contoso と Fabrikam の間で証明書を使用する、セキュリティで保護された通信の使用を推奨します。</span><span class="sxs-lookup"><span data-stu-id="8c312-115">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="8c312-116">それぞれのコンピューターにインストールして、必要なすべての証明書を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c312-116">You must generate any certificates you require, and install them on the respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8c312-117">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8c312-117">Next steps</span></span>
  
-   [<span data-ttu-id="8c312-118">Contoso データベースの復元</span><span class="sxs-lookup"><span data-stu-id="8c312-118">Restoring the Contoso Database</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [<span data-ttu-id="8c312-119">証明書の生成と有効化</span><span class="sxs-lookup"><span data-stu-id="8c312-119">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)
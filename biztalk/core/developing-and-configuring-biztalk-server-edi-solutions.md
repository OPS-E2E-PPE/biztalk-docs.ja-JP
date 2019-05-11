---
title: 開発と BizTalk Server EDI ソリューションの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65629eb1-8e08-4233-9331-c53ae0abaed4
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e846048a8aa90cd671bae085459632c807dd5d65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389425"
---
# <a name="developing-and-configuring-biztalk-server-edi-solutions"></a><span data-ttu-id="7b49a-102">BizTalk Server EDI ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="7b49a-102">Developing and Configuring BizTalk Server EDI Solutions</span></span>
<span data-ttu-id="7b49a-103">作成する開発者向け情報[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI ソリューション。</span><span class="sxs-lookup"><span data-stu-id="7b49a-103">Information for developers to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI solutions.</span></span> <span data-ttu-id="7b49a-104">BizTalk プロジェクト システム設計環境を使用してこれらのソリューションを作成し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7b49a-104">These solutions are created using the BizTalk project system design environment and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="7b49a-105">開発する前に、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI ソリューションを完全にインストールされていることを確認し、構成されていることを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b49a-105">Before developing a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI solution, make sure that you have fully installed and configured [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the EDI feature.</span></span> <span data-ttu-id="7b49a-106">参照してください[BizTalk Server の新機能については、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b49a-106">See [BizTalk Server - What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="7b49a-107">EDI ソリューションを開発するために必要な追加の EDI 固有の構成では、次を参照してください。[構成後の手順、環境を最適化する](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b49a-107">For additional EDI-specific configuration required for developing an EDI solution, see [Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b49a-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7b49a-108">In This Section</span></span>  
  
-   [<span data-ttu-id="7b49a-109">EDI のプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7b49a-109">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)  
  
-   [<span data-ttu-id="7b49a-110">グローバルまたはフォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7b49a-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)  
  
-   [<span data-ttu-id="7b49a-111">EDI パイプラインのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7b49a-111">Configuring EDI Pipeline Properties</span></span>](../core/configuring-edi-pipeline-properties.md)  
  
-   [<span data-ttu-id="7b49a-112">EDI ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="7b49a-112">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)  
  
-   [<span data-ttu-id="7b49a-113">EDI 受信確認の構成</span><span class="sxs-lookup"><span data-stu-id="7b49a-113">Configuring EDI Acknowledgments</span></span>](../core/configuring-edi-acknowledgments.md)  
  
-   [<span data-ttu-id="7b49a-114">EDI バッチの構成</span><span class="sxs-lookup"><span data-stu-id="7b49a-114">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)  
  
-   [<span data-ttu-id="7b49a-115">EDI スキーマの開発</span><span class="sxs-lookup"><span data-stu-id="7b49a-115">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)  
  
-   [<span data-ttu-id="7b49a-116">デザイン時 XML ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b49a-116">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)  
  
-   [<span data-ttu-id="7b49a-117">EDI のコンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="7b49a-117">EDI Context Properties</span></span>](../core/edi-context-properties.md)  
  
-   [<span data-ttu-id="7b49a-118">EDI オーバーライドコンテキストのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7b49a-118">EDI Override Context Properties</span></span>](../core/edi-override-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b49a-119">参照</span><span class="sxs-lookup"><span data-stu-id="7b49a-119">See Also</span></span>  

[<span data-ttu-id="7b49a-120">EDI、AS2、および EDIFACT のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="7b49a-120">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)  
[<span data-ttu-id="7b49a-121">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="7b49a-121">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)
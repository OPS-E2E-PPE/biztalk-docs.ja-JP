---
title: 開発と BizTalk Server AS2 ソリューションの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62aa76f2-b692-41d9-862a-3e0089635800
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22356c4f7bf8c6e3523bd2ae3fbbb9f506c2c9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351451"
---
# <a name="developing-and-configuring-biztalk-server-as2-solutions"></a><span data-ttu-id="b0ef8-102">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="b0ef8-102">Developing and Configuring BizTalk Server AS2 Solutions</span></span>
## <a name="overview"></a><span data-ttu-id="b0ef8-103">概要</span><span class="sxs-lookup"><span data-stu-id="b0ef8-103">Overview</span></span>
<span data-ttu-id="b0ef8-104">BizTalk AS2 ソリューションを作成する開発者向けの情報。</span><span class="sxs-lookup"><span data-stu-id="b0ef8-104">Information for developers to create BizTalk AS2 solutions.</span></span> <span data-ttu-id="b0ef8-105">BizTalk プロジェクト システム設計環境を使用してこれらのソリューションを作成し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b0ef8-105">These solutions are created using the BizTalk project system design environment and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>
  
 <span data-ttu-id="b0ef8-106">BizTalk Server AS2 ソリューションを開発する前に行うことを完全にインストールして構成したことを確認して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]AS2 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0ef8-106">Before developing a BizTalk Server AS2 solution, make sure that you have fully installed and configured [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the AS2 feature.</span></span> <span data-ttu-id="b0ef8-107">参照してください[BizTalk Server の新機能については、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0ef8-107">See [BizTalk Server - What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="b0ef8-108">EDI ソリューションを開発するために必要な追加 AS2 固有構成では、次を参照してください。[構成後の手順、環境を最適化する](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0ef8-108">For additional AS2-specific configuration that is required for developing an EDI solution, see [Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b0ef8-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0ef8-109">In This Section</span></span>  
  
-   [<span data-ttu-id="b0ef8-110">FILE 送信ポートを使用した AS2 メッセージの送信</span><span class="sxs-lookup"><span data-stu-id="b0ef8-110">Sending an AS2 Message over a FILE Send Port</span></span>](../core/sending-an-as2-message-over-a-file-send-port.md)  
  
-   [<span data-ttu-id="b0ef8-111">AS2 プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="b0ef8-111">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)  
  
-   [<span data-ttu-id="b0ef8-112">AS2 パイプラインのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="b0ef8-112">Configuring AS2 Pipeline Properties</span></span>](../core/configuring-as2-pipeline-properties.md)  
  
-   [<span data-ttu-id="b0ef8-113">AS2 ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="b0ef8-113">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)  
  
-   [<span data-ttu-id="b0ef8-114">AS2 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="b0ef8-114">AS2 Security</span></span>](../core/as2-security.md)  
  
-   [<span data-ttu-id="b0ef8-115">送信パーティ解決のための AS2 コンテキスト プロパティの記述</span><span class="sxs-lookup"><span data-stu-id="b0ef8-115">Writing AS2 Context Properties for Outbound Party Resolution</span></span>](../core/writing-as2-context-properties-for-outbound-party-resolution.md)  
  
-   [<span data-ttu-id="b0ef8-116">AS2 のコンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="b0ef8-116">AS2 Context Properties</span></span>](../core/as2-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="b0ef8-117">参照</span><span class="sxs-lookup"><span data-stu-id="b0ef8-117">See Also</span></span>  
[<span data-ttu-id="b0ef8-118">EDI、AS2、および EDIFACT のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="b0ef8-118">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)  
[<span data-ttu-id="b0ef8-119">BizTalk Server EDI ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="b0ef8-119">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)
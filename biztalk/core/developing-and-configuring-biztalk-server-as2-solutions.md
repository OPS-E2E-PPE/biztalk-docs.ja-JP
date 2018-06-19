---
title: 開発と BizTalk Server AS2 ソリューションの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: b3cd1bfb6bba469f6096242f3e57fd199a4439e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239346"
---
# <a name="developing-and-configuring-biztalk-server-as2-solutions"></a><span data-ttu-id="bfcb6-102">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="bfcb6-102">Developing and Configuring BizTalk Server AS2 Solutions</span></span>
## <a name="overview"></a><span data-ttu-id="bfcb6-103">概要</span><span class="sxs-lookup"><span data-stu-id="bfcb6-103">Overview</span></span>
<span data-ttu-id="bfcb6-104">BizTalk AS2 ソリューションを作成する開発者向けの情報です。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-104">Information for developers to create BizTalk AS2 solutions.</span></span> <span data-ttu-id="bfcb6-105">BizTalk プロジェクト システム設計環境を使用してこれらのソリューションを作成し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-105">These solutions are created using the BizTalk project system design environment and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>
  
 <span data-ttu-id="bfcb6-106">BizTalk Server AS2 ソリューションを開発する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と AS2 機能が完全にインストールおよび構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-106">Before developing a BizTalk Server AS2 solution, make sure that you have fully installed and configured [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the AS2 feature.</span></span> <span data-ttu-id="bfcb6-107">参照してください[BizTalk Server の新機能、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-107">See [BizTalk Server - What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="bfcb6-108">追加の AS2 固有の構成を EDI ソリューションを開発するために必要な次を参照してください。 [、環境を最適化するために後の構成手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)です。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-108">For additional AS2-specific configuration that is required for developing an EDI solution, see [Post-configuration steps to optimize your environment](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="bfcb6-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bfcb6-109">In This Section</span></span>  
  
-   [<span data-ttu-id="bfcb6-110">FILE 送信ポート経由で AS2 メッセージの送信</span><span class="sxs-lookup"><span data-stu-id="bfcb6-110">Sending an AS2 Message over a FILE Send Port</span></span>](../core/sending-an-as2-message-over-a-file-send-port.md)  
  
-   [<span data-ttu-id="bfcb6-111">AS2 のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-111">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)  
  
-   [<span data-ttu-id="bfcb6-112">AS2 パイプラインのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-112">Configuring AS2 Pipeline Properties</span></span>](../core/configuring-as2-pipeline-properties.md)  
  
-   [<span data-ttu-id="bfcb6-113">AS2 ソリューションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-113">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)  
  
-   [<span data-ttu-id="bfcb6-114">AS2 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="bfcb6-114">AS2 Security</span></span>](../core/as2-security.md)  
  
-   [<span data-ttu-id="bfcb6-115">送信パーティ解決の AS2 コンテキスト プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="bfcb6-115">Writing AS2 Context Properties for Outbound Party Resolution</span></span>](../core/writing-as2-context-properties-for-outbound-party-resolution.md)  
  
-   [<span data-ttu-id="bfcb6-116">AS2 コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="bfcb6-116">AS2 Context Properties</span></span>](../core/as2-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="bfcb6-117">参照</span><span class="sxs-lookup"><span data-stu-id="bfcb6-117">See Also</span></span>  
[<span data-ttu-id="bfcb6-118">EDI、AS2、および EDIFACT のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="bfcb6-118">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)  
[<span data-ttu-id="bfcb6-119">開発および BizTalk Server EDI ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="bfcb6-119">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)
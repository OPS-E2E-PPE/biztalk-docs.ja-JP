---
title: "BizTalk Server での Visual Studio Team Services での自動展開の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 23d79eae3bd89a572a919cfeff800178f9163796
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a><span data-ttu-id="1067c-102">BizTalk Server での Visual Studio Team Services の自動展開を構成します。</span><span class="sxs-lookup"><span data-stu-id="1067c-102">Configure automatic deployment with Visual Studio Team Services in BizTalk Server</span></span>
<span data-ttu-id="1067c-103">自動的に展開[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]Visual Studio Team Services を使用するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1067c-103">Automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] applications using Visual Studio Team Services.</span></span> 

<span data-ttu-id="1067c-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]強化された自動展開とアプリケーション ライフ サイクル管理 (ALM) のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1067c-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] provides an improved automatic deployment and application lifecycle management (ALM) experience.</span></span> 

<span data-ttu-id="1067c-105">ここでは、VSTS でをセットアップする方法を説明[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を展開する、最初のアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="1067c-105">This section shows you how to setup VSTS with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and add your first application to deploy.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1067c-106">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="1067c-106">Before you begin</span></span>

* <span data-ttu-id="1067c-107">準備ができて、Visual Studio Team Services (VSTS) アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="1067c-107">Have your Visual Studio Team Services (VSTS) account ready.</span></span> <span data-ttu-id="1067c-108">1 つを持っていない場合</span><span class="sxs-lookup"><span data-stu-id="1067c-108">Don't have one?</span></span> <span data-ttu-id="1067c-109">[Visual Studio Team Services にサインアップする](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)です。</span><span class="sxs-lookup"><span data-stu-id="1067c-109">[Sign up for Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span></span>
* <span data-ttu-id="1067c-110">BizTalk コンピューターにインストールされている VSTS エージェントがある場合、既存のエージェントは、最新のエージェントが VSTS で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="1067c-110">If you already have a VSTS Agent installed on your BizTalk computer, then the existing agent is overwritten with the latest VSTS Agent.</span></span> <span data-ttu-id="1067c-111">更新する必要があります、[新しいエージェントに合うように VSTS サービス](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)です。</span><span class="sxs-lookup"><span data-stu-id="1067c-111">You may have to update your [VSTS service to align with the new agent](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span></span>
* <span data-ttu-id="1067c-112">VSTS と自動展開はいずれかで行われる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループにします。</span><span class="sxs-lookup"><span data-stu-id="1067c-112">Automatic deployment with VSTS is done on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="1067c-113">コンピューターに Visual Studio があることを確認して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]開発ツールおよび SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1067c-113">Be sure the computer has Visual Studio and the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Developer Tools and SDK installed.</span></span> <span data-ttu-id="1067c-114">参照してください、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [ハードウェアおよびソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。</span><span class="sxs-lookup"><span data-stu-id="1067c-114">See the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [hardware and software requirements](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1067c-115">次の手順</span><span class="sxs-lookup"><span data-stu-id="1067c-115">Next steps</span></span>
[<span data-ttu-id="1067c-116">自動展開用 VSTS を構成します。</span><span class="sxs-lookup"><span data-stu-id="1067c-116">Configure VSTS for automatic deployment</span></span>](../core/configure-visual-studio-team-services-to-deploy-biztalk-solutions-or-projects.md)

[<span data-ttu-id="1067c-117">JSON テンプレートを構成します。</span><span class="sxs-lookup"><span data-stu-id="1067c-117">Configure the JSON template</span></span>](../core/configure-the-json-template-for-automatic-deployment.md)

[<span data-ttu-id="1067c-118">環境のトークンと変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="1067c-118">Configure environmental tokens and variables</span></span>](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)

[<span data-ttu-id="1067c-119">VSTS を BizTalk アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="1067c-119">Add a BizTalk application to VSTS</span></span>](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)
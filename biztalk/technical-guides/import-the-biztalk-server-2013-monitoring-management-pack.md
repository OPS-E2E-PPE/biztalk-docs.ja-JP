---
title: BizTalk Server 2013 Monitoring 管理パックのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bee2bfe9-4eb0-46d4-8eee-75182202080c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7561007ddf03b4a17357b2c5204f2bdd91acc73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395853"
---
# <a name="import-the-biztalk-server-2013-monitoring-management-pack"></a><span data-ttu-id="6d58c-102">BizTalk Server 2013 Monitoring 管理パックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6d58c-102">Import the BizTalk Server 2013 Monitoring Management Pack</span></span>
<span data-ttu-id="6d58c-103">管理パックをインポートする方法についてで管理パックをインポートする方法を参照してください。 [Operations Manager 2007 R2 または 2012](http://go.microsoft.com/fwlink/?LinkId=142351) (<http://go.microsoft.com/fwlink/?LinkId=142351>)。</span><span class="sxs-lookup"><span data-stu-id="6d58c-103">For instructions about how to import a management pack, see How to Import a Management Pack in [Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=142351) (<http://go.microsoft.com/fwlink/?LinkId=142351>).</span></span> <span data-ttu-id="6d58c-104">後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックのインポートは、次の手順を実行して初期構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="6d58c-104">After the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack is imported, follow these procedures to finish your initial configuration:</span></span>  
  
### <a name="to-configure-the-management-pack"></a><span data-ttu-id="6d58c-105">管理パックを構成するには</span><span class="sxs-lookup"><span data-stu-id="6d58c-105">To configure the management pack</span></span>  
  
1.  <span data-ttu-id="6d58c-106">新しい管理パック作成上書きやその他のカスタマイズを格納します。</span><span class="sxs-lookup"><span data-stu-id="6d58c-106">Create a new management pack in which you store overrides and other customizations.</span></span>  
  
2.  <span data-ttu-id="6d58c-107">エージェント プロキシ設定を有効にするには、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6d58c-107">To enable the Agent Proxy setting, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="6d58c-108">オペレーション コンソールを開くし、[管理] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d58c-108">Open the Operations console and then click the Administration button.</span></span>  
  
    2.  <span data-ttu-id="6d58c-109">管理者 ウィンドウで次のようにクリックします。**エージェントで管理**します。</span><span class="sxs-lookup"><span data-stu-id="6d58c-109">In the Administrator pane, click **Agent Managed**.</span></span>  
  
    3.  <span data-ttu-id="6d58c-110">一覧内のエージェントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d58c-110">Double-click an agent in the list.</span></span>  
  
    4.  <span data-ttu-id="6d58c-111">[セキュリティ] タブで、次のように選択します。**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出できるようにする**します。</span><span class="sxs-lookup"><span data-stu-id="6d58c-111">On the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**.</span></span>  
  
    5.  <span data-ttu-id="6d58c-112">BizTalk Server にインストールされている各エージェントには、手順 3 ~ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6d58c-112">Repeat steps 3 through 4 for each agent that is installed on a BizTalk Server.</span></span>
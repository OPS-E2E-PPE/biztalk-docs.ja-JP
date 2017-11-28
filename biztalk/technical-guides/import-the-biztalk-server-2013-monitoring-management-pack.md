---
title: "BizTalk Server 2013 の監視管理パックのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bee2bfe9-4eb0-46d4-8eee-75182202080c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6dff55cce17d9b9159a8eca754f91373621929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="import-the-biztalk-server-2013-monitoring-management-pack"></a><span data-ttu-id="29f07-102">BizTalk Server 2013 の監視管理パックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="29f07-102">Import the BizTalk Server 2013 Monitoring Management Pack</span></span>
<span data-ttu-id="29f07-103">管理パックをインポートする方法については、管理パックをインポートする方法を参照してください[Operations Manager 2007 R2 または 2012](http://go.microsoft.com/fwlink/?LinkId=142351) (http://go.microsoft.com/fwlink/?LinkId=142351)。</span><span class="sxs-lookup"><span data-stu-id="29f07-103">For instructions about how to import a management pack, see How to Import a Management Pack in [Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=142351) (http://go.microsoft.com/fwlink/?LinkId=142351).</span></span> <span data-ttu-id="29f07-104">後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックのインポートは、次の手順を実行して初期構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="29f07-104">After the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack is imported, follow these procedures to finish your initial configuration:</span></span>  
  
### <a name="to-configure-the-management-pack"></a><span data-ttu-id="29f07-105">管理パックを構成するには</span><span class="sxs-lookup"><span data-stu-id="29f07-105">To configure the management pack</span></span>  
  
1.  <span data-ttu-id="29f07-106">新しい管理パックを作成する上書きやその他のカスタマイズを格納します。</span><span class="sxs-lookup"><span data-stu-id="29f07-106">Create a new management pack in which you store overrides and other customizations.</span></span>  
  
2.  <span data-ttu-id="29f07-107">エージェント プロキシ設定を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="29f07-107">To enable the Agent Proxy setting, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="29f07-108">オペレーション コンソールを開き、管理 をクリック をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29f07-108">Open the Operations console and then click the Administration button.</span></span>  
  
    2.  <span data-ttu-id="29f07-109">ペインで、管理者、クリックして**エージェントで管理**です。</span><span class="sxs-lookup"><span data-stu-id="29f07-109">In the Administrator pane, click **Agent Managed**.</span></span>  
  
    3.  <span data-ttu-id="29f07-110">一覧内のエージェントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="29f07-110">Double-click an agent in the list.</span></span>  
  
    4.  <span data-ttu-id="29f07-111">[セキュリティ] タブで、**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出**です。</span><span class="sxs-lookup"><span data-stu-id="29f07-111">On the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**.</span></span>  
  
    5.  <span data-ttu-id="29f07-112">BizTalk Server にインストールされているエージェントごとに手順 3 ~ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="29f07-112">Repeat steps 3 through 4 for each agent that is installed on a BizTalk Server.</span></span>
---
title: 新しいマスター シークレット サーバーを手動で指定する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e198d5aa82b22170fe4ed52115bf7c72b0c55f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305785"
---
# <a name="designating-a-new-master-secret-server-manually"></a><span data-ttu-id="60036-102">新しいマスター シークレット サーバーを手動で指定します。</span><span class="sxs-lookup"><span data-stu-id="60036-102">Designating a New Master Secret Server Manually</span></span>
<span data-ttu-id="60036-103">クラスターのハードウェアは高価にすることはできます。</span><span class="sxs-lookup"><span data-stu-id="60036-103">Cluster hardware can be expensive.</span></span> <span data-ttu-id="60036-104">ハードウェアのコストが重要である場合は、障害のシナリオの中にマスター シークレット サーバーに別のエンタープライズ シングル サインオン (SSO) サーバーを手動で指定することを検討できます。</span><span class="sxs-lookup"><span data-stu-id="60036-104">If hardware cost is a concern, you can consider manually designating another Enterprise Single Sign-On (SSO) server to be the master secret server during failure scenarios.</span></span> <span data-ttu-id="60036-105">このオプションを使用して、SSO グループの他の SSO サーバーは、マスター シークレット サーバーに昇格できます。</span><span class="sxs-lookup"><span data-stu-id="60036-105">Using this option, any other SSO server in the SSO group can be promoted to the master secret server.</span></span> <span data-ttu-id="60036-106">マスターは、ときに、マスター シークレット サーバーを使用する SSO サーバーのいずれかを手動で昇格できます。</span><span class="sxs-lookup"><span data-stu-id="60036-106">When the master is down, you can manually promote one of the SSO servers to be the master secret server.</span></span> <span data-ttu-id="60036-107">この手法の最大の欠点は、既存の展開を編集、既存を再起動できません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス、または新しいマスター シークレット サーバーを昇格するまで、新しい BizTalk アプリケーションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="60036-107">The biggest disadvantage of this technique is that you cannot edit the existing deployments, restart the existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services, or deploy new BizTalk applications until you promote a new master secret server.</span></span>  
  
 <span data-ttu-id="60036-108">プロセスをシームレスにするは、エラーをできるだけ早く検出ができるように、いくつかの監視メカニズムを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60036-108">To make the process seamless, you will need to implement some monitoring mechanism so you will discover the failure as soon as possible.</span></span> <span data-ttu-id="60036-109">System Center Operations Manager などの監視アプリケーションを使用して、昇格プロセスを自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="60036-109">You can also automate the promotion process by using a monitoring application such as System Center Operations Manager.</span></span>  
  
 <span data-ttu-id="60036-110">マスター シークレット サーバーを手動で移動する方法についての詳細については、次を参照してください。[マスター シークレット サーバーを移動する方法](http://go.microsoft.com/fwlink/?LinkId=156841)(<http://go.microsoft.com/fwlink/?LinkId=156841>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="60036-110">For more information about manually moving the master secret server, see [How to Move the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156841) (<http://go.microsoft.com/fwlink/?LinkId=156841>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60036-111">参照</span><span class="sxs-lookup"><span data-stu-id="60036-111">See Also</span></span>  
 [<span data-ttu-id="60036-112">マスター シークレット サーバーのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="60036-112">Clustering the Master Secret Server</span></span>](../technical-guides/clustering-the-master-secret-server.md)
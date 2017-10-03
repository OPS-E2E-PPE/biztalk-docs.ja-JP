---
title: "新しいマスター シークレット サーバーを手動で指定する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b6d635312d3765c37f1ab9c2b64505698f93e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="designating-a-new-master-secret-server-manually"></a><span data-ttu-id="7a0b0-102">新しいマスター シークレット サーバーを手動で指定します。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-102">Designating a New Master Secret Server Manually</span></span>
<span data-ttu-id="7a0b0-103">クラスターのハードウェアは高価にすることはできます。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-103">Cluster hardware can be expensive.</span></span> <span data-ttu-id="7a0b0-104">ハードウェアのコストに問題がある場合は、障害のシナリオの中にマスター シークレット サーバーに別のエンタープライズ シングル サインオン (SSO) サーバーを手動で指定するを検討することができます。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-104">If hardware cost is a concern, you can consider manually designating another Enterprise Single Sign-On (SSO) server to be the master secret server during failure scenarios.</span></span> <span data-ttu-id="7a0b0-105">このオプションを使用して、SSO グループの他の SSO サーバーは、マスタ シークレット サーバーに昇格できます。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-105">Using this option, any other SSO server in the SSO group can be promoted to the master secret server.</span></span> <span data-ttu-id="7a0b0-106">マスターが下にある場合は、マスター シークレット サーバーを使用する SSO サーバーのいずれかを手動で昇格できます。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-106">When the master is down, you can manually promote one of the SSO servers to be the master secret server.</span></span> <span data-ttu-id="7a0b0-107">この手法の最大の欠点は、既存の展開を編集、既存を再起動できません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services、または新しいマスター シークレット サーバーを昇格するまでに、新しい BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-107">The biggest disadvantage of this technique is that you cannot edit the existing deployments, restart the existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services, or deploy new BizTalk applications until you promote a new master secret server.</span></span>  
  
 <span data-ttu-id="7a0b0-108">プロセスをシームレスにするには、いくつかの監視メカニズムを実装するため、できるだけ早く障害は検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-108">To make the process seamless, you will need to implement some monitoring mechanism so you will discover the failure as soon as possible.</span></span> <span data-ttu-id="7a0b0-109">System Center Operations Manager などの監視アプリケーションを使用して、昇格プロセスを自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-109">You can also automate the promotion process by using a monitoring application such as System Center Operations Manager.</span></span>  
  
 <span data-ttu-id="7a0b0-110">マスター シークレット サーバーを手動で移動の詳細については、次を参照してください。[マスター シークレット サーバーを移動する方法](http://go.microsoft.com/fwlink/?LinkId=156841)(http://go.microsoft.com/fwlink/?LinkId=156841) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="7a0b0-110">For more information about manually moving the master secret server, see [How to Move the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156841) (http://go.microsoft.com/fwlink/?LinkId=156841) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0b0-111">参照</span><span class="sxs-lookup"><span data-stu-id="7a0b0-111">See Also</span></span>  
 [<span data-ttu-id="7a0b0-112">マスター シークレット サーバーをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="7a0b0-112">Clustering the Master Secret Server</span></span>](../technical-guides/clustering-the-master-secret-server.md)
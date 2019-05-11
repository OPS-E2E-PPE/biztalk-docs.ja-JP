---
title: SSO の処理サーバー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, processing servers
- processing servers [SSO]
ms.assetid: 9e80a456-974a-49b3-bb64-2e4713036cfb
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2676de4e698f3ea9221b35c349819f163b74b3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255138"
---
# <a name="processing-servers-for-sso"></a><span data-ttu-id="bd9b6-102">SSO の処理サーバー</span><span class="sxs-lookup"><span data-stu-id="bd9b6-102">Processing Servers for SSO</span></span>
<span data-ttu-id="bd9b6-103">複数コンピューター環境で、マスター シークレット サーバーと SSO データベースが作成した後をエンタープライズ シングル サインオン コンピューターにインストールできます以降。</span><span class="sxs-lookup"><span data-stu-id="bd9b6-103">In a multi-computer environment, after the master secret server and SSO database have been created, you can install Enterprise Single Sign-On on subsequent computers.</span></span> <span data-ttu-id="bd9b6-104">これらは、通常、BizTalk Server または Host Integration Server のいずれかがインストールされているものコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="bd9b6-104">These are typically the computers on which either BizTalk Server or Host Integration Server is installed as well.</span></span>  
  
 <span data-ttu-id="bd9b6-105">最初のインストール プロセスは、最初のコンピューターと同じです。</span><span class="sxs-lookup"><span data-stu-id="bd9b6-105">The initial installation process is the same as on the first computer.</span></span> <span data-ttu-id="bd9b6-106">ただし、構成は若干異なるなります。</span><span class="sxs-lookup"><span data-stu-id="bd9b6-106">Configuration, however, becomes slightly different.</span></span> <span data-ttu-id="bd9b6-107">マスター シークレット サーバーと SSO データベースは既に場所であるために選択**参加**構成ウィザードが表示されたら、**新しい SSO システムを作成する**または**既存システムに参加**.</span><span class="sxs-lookup"><span data-stu-id="bd9b6-107">Since the master secret server and the SSO database are already in place, select **Join** when the Configuration Wizard asks, **Create a new SSO system** or **Join an existing system**.</span></span>  
  
 <span data-ttu-id="bd9b6-108">SSO データベースがそのグループ用に構成されたデータベースを別のコンピューターに参加するには、1 台のコンピューターのグループの構成中にできるに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bd9b6-108">Note that it is possible during configuration for a group on one computer to join an SSO database on a different computer that is not the database configured for that group.</span></span> <span data-ttu-id="bd9b6-109">これは可能ですが、これは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="bd9b6-109">While this is possible, it is not recommended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9b6-110">参照</span><span class="sxs-lookup"><span data-stu-id="bd9b6-110">See Also</span></span>  
 [<span data-ttu-id="bd9b6-111">以前のバージョンの SSO からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="bd9b6-111">Upgrading from a Previous Version of SSO</span></span>](../core/upgrading-from-a-previous-version-of-sso.md)
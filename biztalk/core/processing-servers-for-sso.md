---
title: SSO の処理サーバー |Microsoft ドキュメント
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
ms.openlocfilehash: 972e1a3b01394cbf63fb0c8094586d2beda73c3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263666"
---
# <a name="processing-servers-for-sso"></a><span data-ttu-id="ebfe7-102">SSO の処理サーバー</span><span class="sxs-lookup"><span data-stu-id="ebfe7-102">Processing Servers for SSO</span></span>
<span data-ttu-id="ebfe7-103">複数コンピューター環境で、マスター シークレット サーバーと SSO データベースを作成した後にすることができますエンタープライズ シングル サインオン コンピューターにインストール以降。</span><span class="sxs-lookup"><span data-stu-id="ebfe7-103">In a multi-computer environment, after the master secret server and SSO database have been created, you can install Enterprise Single Sign-On on subsequent computers.</span></span> <span data-ttu-id="ebfe7-104">このようなコンピューターは通常、BizTalk Server または Host Integration Server のどちらかがインストールされているコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="ebfe7-104">These are typically the computers on which either BizTalk Server or Host Integration Server is installed as well.</span></span>  
  
 <span data-ttu-id="ebfe7-105">最初のインストール プロセスは、1 台目のコンピューターと同じです。</span><span class="sxs-lookup"><span data-stu-id="ebfe7-105">The initial installation process is the same as on the first computer.</span></span> <span data-ttu-id="ebfe7-106">ただし、構成は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="ebfe7-106">Configuration, however, becomes slightly different.</span></span> <span data-ttu-id="ebfe7-107">マスター シークレット サーバーと SSO データベースが既に定められて、ので選択**参加**問い合わせるときに、構成ウィザード、**新しい SSO システムを作成**または**既存システムに参加**.</span><span class="sxs-lookup"><span data-stu-id="ebfe7-107">Since the master secret server and the SSO database are already in place, select **Join** when the Configuration Wizard asks, **Create a new SSO system** or **Join an existing system**.</span></span>  
  
 <span data-ttu-id="ebfe7-108">構成中に、あるコンピューター上のグループを、別のコンピューターの (そのグループ用に構成されていない) SSO データベースに参加させることも可能です。</span><span class="sxs-lookup"><span data-stu-id="ebfe7-108">Note that it is possible during configuration for a group on one computer to join an SSO database on a different computer that is not the database configured for that group.</span></span> <span data-ttu-id="ebfe7-109">ただし、これは可能であるというだけで、お勧めはできません。</span><span class="sxs-lookup"><span data-stu-id="ebfe7-109">While this is possible, it is not recommended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebfe7-110">参照</span><span class="sxs-lookup"><span data-stu-id="ebfe7-110">See Also</span></span>  
 [<span data-ttu-id="ebfe7-111">SSO の以前のバージョンからアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="ebfe7-111">Upgrading from a Previous Version of SSO</span></span>](../core/upgrading-from-a-previous-version-of-sso.md)
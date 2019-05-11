---
title: BizTalk グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, groups
- groups
- groups, Management database
- groups, about groups
ms.assetid: 197cbcf6-c722-4cbb-9642-3cb8a34757e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 960f7afa1138e1be3293ae3bc0c65898539630d8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528301"
---
# <a name="biztalk-groups"></a><span data-ttu-id="6975d-102">BizTalk グループ</span><span class="sxs-lookup"><span data-stu-id="6975d-102">BizTalk Groups</span></span>

## <a name="overview"></a><span data-ttu-id="6975d-103">概要</span><span class="sxs-lookup"><span data-stu-id="6975d-103">Overview</span></span>
<span data-ttu-id="6975d-104">*BizTalk グループ*は通常、企業、部署、ハブ、または含まれている BizTalk Server の実装を必要とするその他の部署を表す組織の単位です。</span><span class="sxs-lookup"><span data-stu-id="6975d-104">The *BizTalk group* is a unit of organization that usually represents an enterprise, department, hub, or other business unit that requires a contained BizTalk Server implementation.</span></span> <span data-ttu-id="6975d-105">BizTalk グループが BizTalk Server 管理データベースと一対一のリレーションシップ (で BizTalk Server 構成データベースと呼ばれる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="6975d-105">The BizTalk group has a one-to-one relationship with a BizTalk Server Management database (known as the BizTalk Server Configuration database in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6975d-106">中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループが複数あります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、特定のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが 1 つに関連付けることのみ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。</span><span class="sxs-lookup"><span data-stu-id="6975d-106">While [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] groups may contain multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers, any given [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer may only be associated with a single [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span>  
  
 <span data-ttu-id="6975d-107">BizTalk 管理データベースは、BizTalk グループの構成情報を格納し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="6975d-107">The BizTalk Management database stores configuration information for the BizTalk group and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in that group.</span></span> <span data-ttu-id="6975d-108">この構成情報には、サーバーと、このロジックを物理的に実行するためのメッセージ処理ロジックの一部を指定します。</span><span class="sxs-lookup"><span data-stu-id="6975d-108">This configuration information specifies part of the message-processing logic for the servers and where this logic will physically run.</span></span> <span data-ttu-id="6975d-109">BizTalk Server 管理データベースの詳細については、次を参照してください。 [BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="6975d-109">For more information about the BizTalk Server Management database, see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="6975d-110">管理コンソールから、各サーバーを管理できるように、グループのサーバーのインストールごとに同じ BizTalk Server 管理データベースを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6975d-110">You must specify the same BizTalk Server Management database for each server installation in the group so that you can administer each server from the administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6975d-111">参照</span><span class="sxs-lookup"><span data-stu-id="6975d-111">See Also</span></span>  
 <span data-ttu-id="6975d-112">[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="6975d-112">[Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md) </span></span>  
 <span data-ttu-id="6975d-113">[グループの管理](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="6975d-113">[Managing Groups](../core/managing-groups.md) </span></span>  
 [<span data-ttu-id="6975d-114">エンティティ</span><span class="sxs-lookup"><span data-stu-id="6975d-114">Entities</span></span>](../core/entities.md)
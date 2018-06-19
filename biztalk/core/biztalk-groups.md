---
title: BizTalk グループ |Microsoft ドキュメント
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
ms.openlocfilehash: 5b9cd38012f0e2a7ba5f4cfcb56ae63678aacbf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231282"
---
# <a name="biztalk-groups"></a><span data-ttu-id="b18cd-102">BizTalk グループ</span><span class="sxs-lookup"><span data-stu-id="b18cd-102">BizTalk Groups</span></span>

## <a name="overview"></a><span data-ttu-id="b18cd-103">概要</span><span class="sxs-lookup"><span data-stu-id="b18cd-103">Overview</span></span>
<span data-ttu-id="b18cd-104">*BizTalk グループ*を通常、企業、部署、ハブ、または、BizTalk Server の実装を必要とするその他のビジネス単位を表す組織の単位です。</span><span class="sxs-lookup"><span data-stu-id="b18cd-104">The *BizTalk group* is a unit of organization that usually represents an enterprise, department, hub, or other business unit that requires a contained BizTalk Server implementation.</span></span> <span data-ttu-id="b18cd-105">BizTalk グループは、BizTalk Server 管理データベース ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では BizTalk Server 構成データベースと呼ばれている) と一対一の関係にあります。</span><span class="sxs-lookup"><span data-stu-id="b18cd-105">The BizTalk group has a one-to-one relationship with a BizTalk Server Management database (known as the BizTalk Server Configuration database in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b18cd-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループは複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターを含むことができますが、ある特定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターは、1 つの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループのみと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b18cd-106">While [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] groups may contain multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers, any given [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer may only be associated with a single [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span>  
  
 <span data-ttu-id="b18cd-107">BizTalk 管理データベースには、BizTalk グループとそのグループ内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターの構成情報が格納されています。</span><span class="sxs-lookup"><span data-stu-id="b18cd-107">The BizTalk Management database stores configuration information for the BizTalk group and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in that group.</span></span> <span data-ttu-id="b18cd-108">この構成情報には、サーバーのメッセージ処理ロジックの一部とこのロジックを物理的に実行する場所が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b18cd-108">This configuration information specifies part of the message-processing logic for the servers and where this logic will physically run.</span></span> <span data-ttu-id="b18cd-109">BizTalk Server 管理データベースの詳細については、次を参照してください。 [BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="b18cd-109">For more information about the BizTalk Server Management database, see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="b18cd-110">グループ内の各サーバーのインストールに同じ BizTalk Server 管理データベースを指定する必要があります。これにより、管理コンソールから各サーバーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b18cd-110">You must specify the same BizTalk Server Management database for each server installation in the group so that you can administer each server from the administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18cd-111">参照</span><span class="sxs-lookup"><span data-stu-id="b18cd-111">See Also</span></span>  
 <span data-ttu-id="b18cd-112">[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="b18cd-112">[Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md) </span></span>  
 <span data-ttu-id="b18cd-113">[グループを管理します。](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="b18cd-113">[Managing Groups](../core/managing-groups.md) </span></span>  
 [<span data-ttu-id="b18cd-114">エンティティ</span><span class="sxs-lookup"><span data-stu-id="b18cd-114">Entities</span></span>](../core/entities.md)
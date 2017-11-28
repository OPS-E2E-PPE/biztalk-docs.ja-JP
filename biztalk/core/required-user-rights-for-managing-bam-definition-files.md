---
title: "BAM 定義ファイルを管理するためのユーザー権利を必要な |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb4fb73f-b783-4a04-9bd6-a135b3dd2655
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5e39c86eec0cf198a5b879cbc98d29321de71dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="required-user-rights-for-managing-bam-definition-files"></a><span data-ttu-id="c349d-102">BAM 定義ファイルの管理に必要なユーザー権利</span><span class="sxs-lookup"><span data-stu-id="c349d-102">Required User Rights for Managing BAM Definition Files</span></span>
<span data-ttu-id="c349d-103">BAM 定義ファイルは、どのロールのユーザーでも作成、管理、および表示を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c349d-103">BAM definition files can be created, managed, and viewed by users in any role.</span></span> <span data-ttu-id="c349d-104">BAM 定義ファイルの管理には、これらのファイルの展開と削除だけでなく、定義ファイルに関連付けられているアクティビティ、ビュー、警告、およびアイテムの管理も伴います。</span><span class="sxs-lookup"><span data-stu-id="c349d-104">Managing BAM definition files includes deploying and removing them as well as managing the activities, views, alerts, and artifacts that are associated with the definition file.</span></span>  
  
 <span data-ttu-id="c349d-105">管理者は、適切なアクセス許可を使用して共有フォルダーを作成するなど、適切な資産保護を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c349d-105">Administrators should maintain proper asset protection, such as creating shared folders with appropriate access permissions.</span></span> <span data-ttu-id="c349d-106">Excel の BAM アドインを使用する際は、マクロ セキュリティ レベルを高く設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c349d-106">When using the BAM Add-In for Excel, we recommend that users set the macro security level to high.</span></span>  
  
 <span data-ttu-id="c349d-107">BAM 定義ファイルの変更に必要なユーザー権利はありません (定義ファイルが保存されるアクセス許可セットによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="c349d-107">There are no required user rights needed to modify the BAM definition files (depending on permissions set on where the definition files are stored).</span></span> <span data-ttu-id="c349d-108">定義ファイルへの変更は、BAM インフラストラクチャに自動的に適用されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c349d-108">Changes to definition files are not automatically applied to the BAM infrastructure.</span></span> <span data-ttu-id="c349d-109">変更を適用するには、BAM 管理ユーティリティを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c349d-109">To apply the changes you must use the BAM Management utility.</span></span>  
  
 <span data-ttu-id="c349d-110">BAM 管理ユーティリティを使用するには、BAM 定義が適用されるコンピューターの管理者か、または BizTalk Server 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c349d-110">To use the BAM Management utility, you must be an administrator on the computer to which the BAM definition is being applied or a member of the BizTalk Server Administrators group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c349d-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c349d-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c349d-112">参照</span><span class="sxs-lookup"><span data-stu-id="c349d-112">See Also</span></span>  
 <span data-ttu-id="c349d-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="c349d-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="c349d-114">[BAM 定義とは何ですか。](../core/what-is-a-bam-definition.md) </span><span class="sxs-lookup"><span data-stu-id="c349d-114">[What Is a BAM Definition?](../core/what-is-a-bam-definition.md) </span></span>  
 [<span data-ttu-id="c349d-115">BAM 定義を展開する方法</span><span class="sxs-lookup"><span data-stu-id="c349d-115">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)
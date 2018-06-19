---
title: BAM インフラストラクチャに対する変更を一覧表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], listing infrastructure changes
- managing [BAM definitions], listing infrastructure changes
- Get-Changes command [BAM]
- infrastructure, listing changes [BAM]
ms.assetid: 3feacd7d-6f42-4626-835b-0dc3befc9fd6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d0ed240f156d853c18f28a52022eea585af513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253922"
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a><span data-ttu-id="98879-102">BAM インフラストラクチャへの変更を一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="98879-102">How to List Changes to the BAM Infrastructure</span></span>
<span data-ttu-id="98879-103">管理者を使用して、 **get 変更**コマンドを BAM 管理ユーティリティの配置済みの BAM 定義に関する現在の情報を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="98879-103">Administrators use the **get-changes** command of the BAM Management utility to list current information about a deployed BAM definition.</span></span> <span data-ttu-id="98879-104">このコマンドでは、BAM プライマリ インポート データベースの現在の展開アイテムを一覧表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="98879-104">You can also use the get-changes command to list current deployment artifacts in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="98879-105">表示される情報には、成功した展開と展開解除、BAM 定義ファイルの名前、BAM 構成ファイルの名前、定義ファイルに関連付けられたすべてのアクティビティとビューの名前、および変更を適用したユーザー アカウントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98879-105">The information includes successful deployments and undeployments, the name of the BAM definition file, the name of the BAM configuration file, the names of all activities and views associated with the definition file, and the user account that applied the change.</span></span> <span data-ttu-id="98879-106">get-changes の一覧には、展開した定義と削除した定義が、それに関連付けられた識別番号と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="98879-106">The get-changes list shows deployments and definition removals with their associated identification numbers.</span></span>  
  
### <a name="to-list-changes-to-the-bam-definition"></a><span data-ttu-id="98879-107">BAM 定義への変更を一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="98879-107">To list changes to the BAM definition</span></span>  
  
1.  <span data-ttu-id="98879-108">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="98879-108">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="98879-109">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="98879-109">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="98879-110">型**bm get 変更します。**</span><span class="sxs-lookup"><span data-stu-id="98879-110">Type **bm get-changes.**</span></span>  
  
4.  <span data-ttu-id="98879-111">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="98879-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98879-112">参照</span><span class="sxs-lookup"><span data-stu-id="98879-112">See Also</span></span>  
 <span data-ttu-id="98879-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="98879-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="98879-114">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="98879-114">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="98879-115">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="98879-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)
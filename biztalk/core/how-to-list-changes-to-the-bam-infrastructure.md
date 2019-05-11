---
title: BAM インフラストラクチャの変更を一覧表示する方法 |Microsoft Docs
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
ms.openlocfilehash: 5bb796c7572e00c0a66cf89eb61035a46ac361c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336881"
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a><span data-ttu-id="79e4c-102">BAM インフラストラクチャへの変更を一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="79e4c-102">How to List Changes to the BAM Infrastructure</span></span>
<span data-ttu-id="79e4c-103">管理者を使用して、 **get 変更**展開された BAM 定義に関する現在の情報を一覧に、BAM 管理ユーティリティのコマンド。</span><span class="sxs-lookup"><span data-stu-id="79e4c-103">Administrators use the **get-changes** command of the BAM Management utility to list current information about a deployed BAM definition.</span></span> <span data-ttu-id="79e4c-104">BAM プライマリ インポート データベースの現在の展開アイテムを一覧表示するのに get-changes コマンドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="79e4c-104">You can also use the get-changes command to list current deployment artifacts in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="79e4c-105">情報には、成功した展開と展開解除、BAM 定義ファイルの名前、BAM 構成ファイルの名前、すべてのアクティビティと、定義ファイルと変更を適用したユーザー アカウントに関連付けられたビューの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79e4c-105">The information includes successful deployments and undeployments, the name of the BAM definition file, the name of the BAM configuration file, the names of all activities and views associated with the definition file, and the user account that applied the change.</span></span> <span data-ttu-id="79e4c-106">Get 変更一覧には、展開と定義の削除とその関連付けられている識別番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="79e4c-106">The get-changes list shows deployments and definition removals with their associated identification numbers.</span></span>  
  
### <a name="to-list-changes-to-the-bam-definition"></a><span data-ttu-id="79e4c-107">BAM 定義に変更を一覧表示</span><span class="sxs-lookup"><span data-stu-id="79e4c-107">To list changes to the BAM definition</span></span>  
  
1. <span data-ttu-id="79e4c-108">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="79e4c-108">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="79e4c-109">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="79e4c-109">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="79e4c-110">型**bm get に変更します。**</span><span class="sxs-lookup"><span data-stu-id="79e4c-110">Type **bm get-changes.**</span></span>  
  
4. <span data-ttu-id="79e4c-111">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="79e4c-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e4c-112">参照</span><span class="sxs-lookup"><span data-stu-id="79e4c-112">See Also</span></span>  
 <span data-ttu-id="79e4c-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="79e4c-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="79e4c-114">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="79e4c-114">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="79e4c-115">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="79e4c-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)
---
title: BAM アイテムを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update-All command [BAM]
- managing [BAM definitions], updating artifacts
- updating, artifacts
- artifacts, updating
ms.assetid: bc28159e-df51-499b-bd51-7b682b849891
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8bd9abbf0e466097744f6a02f7ae3aa0ccdf372
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383646"
---
# <a name="how-to-update-bam-artifacts"></a><span data-ttu-id="ba801-102">BAM アイテムを更新する方法</span><span class="sxs-lookup"><span data-stu-id="ba801-102">How to Update BAM Artifacts</span></span>
<span data-ttu-id="ba801-103">管理者を使用して、**更新すべて**BAM プライマリ インポート データベースに展開されたアイテムを更新するコマンド。</span><span class="sxs-lookup"><span data-stu-id="ba801-103">Administrators use the **update-all** command to update artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="ba801-104">指定する BAM 定義は、XML ファイルまたは更新するアイテムについての Excel ブックのコンテナー情報のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ba801-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be updated.</span></span>  
  
### <a name="to-update-bam-artifacts"></a><span data-ttu-id="ba801-105">BAM アイテムを更新するには</span><span class="sxs-lookup"><span data-stu-id="ba801-105">To update BAM Artifacts</span></span>  
  
1. <span data-ttu-id="ba801-106">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="ba801-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="ba801-107">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="ba801-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="ba801-108">型**bm 更新すべて-definitionfile:\<def ファイル\>** します。</span><span class="sxs-lookup"><span data-stu-id="ba801-108">Type **bm update-all -DefinitionFile:\<def file\>**.</span></span>  
  
4. <span data-ttu-id="ba801-109">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ba801-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba801-110">参照</span><span class="sxs-lookup"><span data-stu-id="ba801-110">See Also</span></span>  
 <span data-ttu-id="ba801-111">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="ba801-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="ba801-112">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="ba801-112">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="ba801-113">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="ba801-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)
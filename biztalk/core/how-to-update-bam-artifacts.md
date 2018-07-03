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
ms.openlocfilehash: 083940baf4d6e51e15bc91f4ee7e867d50750c83
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011771"
---
# <a name="how-to-update-bam-artifacts"></a><span data-ttu-id="a9aa0-102">BAM アイテムを更新する方法</span><span class="sxs-lookup"><span data-stu-id="a9aa0-102">How to Update BAM Artifacts</span></span>
<span data-ttu-id="a9aa0-103">管理者を使用して、**更新すべて**BAM プライマリ インポート データベースに展開されたアイテムを更新するコマンド。</span><span class="sxs-lookup"><span data-stu-id="a9aa0-103">Administrators use the **update-all** command to update artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="a9aa0-104">指定する BAM 定義は、更新するアイテムについての情報を含んでいる XML ファイルまたは Excel ブックのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="a9aa0-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be updated.</span></span>  
  
### <a name="to-update-bam-artifacts"></a><span data-ttu-id="a9aa0-105">BAM アイテムを更新するには</span><span class="sxs-lookup"><span data-stu-id="a9aa0-105">To update BAM Artifacts</span></span>  
  
1. <span data-ttu-id="a9aa0-106">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="a9aa0-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="a9aa0-107">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="a9aa0-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="a9aa0-108">型**bm 更新すべて-definitionfile:\<def ファイル\>** します。</span><span class="sxs-lookup"><span data-stu-id="a9aa0-108">Type **bm update-all -DefinitionFile:\<def file\>**.</span></span>  
  
4. <span data-ttu-id="a9aa0-109">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a9aa0-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9aa0-110">参照</span><span class="sxs-lookup"><span data-stu-id="a9aa0-110">See Also</span></span>  
 <span data-ttu-id="a9aa0-111">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="a9aa0-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="a9aa0-112">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="a9aa0-112">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="a9aa0-113">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="a9aa0-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)
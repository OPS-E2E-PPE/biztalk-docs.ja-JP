---
title: 展開済みのアイテムを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cea6c9e72b9820420888551e8d36f3aaac3762b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384299"
---
# <a name="how-to-remove-deployed-artifacts"></a><span data-ttu-id="60397-102">展開済みのアイテムを削除する方法</span><span class="sxs-lookup"><span data-stu-id="60397-102">How to Remove Deployed Artifacts</span></span>
<span data-ttu-id="60397-103">管理者を使用して、**すべて削除**BAM プライマリ インポート データベースに展開されたアイテムを削除するコマンド。</span><span class="sxs-lookup"><span data-stu-id="60397-103">Administrators use the **remove-all** command to remove artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="60397-104">指定する BAM 定義は、XML ファイルまたは削除するアイテムについての Excel ブックのコンテナー情報のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="60397-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be removed.</span></span>  
  
### <a name="to-remove-deployed-artifacts"></a><span data-ttu-id="60397-105">展開済みのアイテムを削除するには</span><span class="sxs-lookup"><span data-stu-id="60397-105">To remove deployed artifacts</span></span>  
  
1. <span data-ttu-id="60397-106">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="60397-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="60397-107">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="60397-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="60397-108">型**bm のすべての削除に-definitionfile:\<def ファイル\>** します。</span><span class="sxs-lookup"><span data-stu-id="60397-108">Type **bm remove-all -DefinitionFile:\<def file\>**.</span></span>  
  
4. <span data-ttu-id="60397-109">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="60397-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60397-110">参照</span><span class="sxs-lookup"><span data-stu-id="60397-110">See Also</span></span>  
 <span data-ttu-id="60397-111">[アプリケーションに BAM アイテムを追加する方法](../core/how-to-add-a-bam-artifact-to-an-application.md) </span><span class="sxs-lookup"><span data-stu-id="60397-111">[How to Add a BAM Artifact to an Application](../core/how-to-add-a-bam-artifact-to-an-application.md) </span></span>  
 <span data-ttu-id="60397-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="60397-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="60397-113">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="60397-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="60397-114">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="60397-114">BAM Management Utility</span></span>](../core/bam-management-utility.md)
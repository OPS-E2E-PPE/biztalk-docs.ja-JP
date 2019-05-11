---
title: シナリオ:複数のコンピューター間でのアイテムの分散 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [artifacts], multiple computers
- examples, distributing
- examples, artifacts
- artifacts, distributing
- artifacts, examples
- deploying [artifacts], examples
- examples, deploying
ms.assetid: 7000cded-1fda-4276-b7f3-3f427f686f64
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e64cdf9ac474697961d4f8fd41bb75057d27aa54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308319"
---
# <a name="scenario-distributing-artifacts-among-multiple-computers"></a><span data-ttu-id="da602-102">シナリオ:複数のコンピューター間でのアイテムを配布します。</span><span class="sxs-lookup"><span data-stu-id="da602-102">Scenario: Distributing Artifacts Among Multiple Computers</span></span>
<span data-ttu-id="da602-103">このトピックではアプリケーションでアイテムが選択的に別のコンピューターにインストールされているアプリケーションの展開シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="da602-103">This topic describes the application deployment scenario when the artifacts in an application are selectively installed on different computers.</span></span> <span data-ttu-id="da602-104">特定のアセンブリまたはその他の種類の BizTalk グループ内の特定のコンピューターにのみインストールするアプリケーションでアイテムをする場合は、これを行う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da602-104">You might want to do this if you want certain assemblies or other types of artifacts in an application to be installed only on specific computers in a BizTalk group.</span></span> <span data-ttu-id="da602-105">これを行うには、これに基づいてアイテムをまとめてインストール、物理コンピューター上の複数の .msi ファイルにアプリケーションに含まれるアイテムをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="da602-105">To do this, you can export the artifacts included in an application into multiple .msi files, according to which artifacts you want to install together on a physical computer.</span></span>  
  
 <span data-ttu-id="da602-106">次の図は、BizTalk グループ 1 の BizTalk 管理データベースにインポートする .msi ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="da602-106">The following diagram shows an .msi file that is imported into the BizTalk Management database for BizTalk Group 1.</span></span> <span data-ttu-id="da602-107">これにより、そのグループの Order Processing アプリケーションとすべてのアーティファクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="da602-107">This creates the Order Processing application and all of its artifacts in that group.</span></span> <span data-ttu-id="da602-108">アプリケーションのアイテムは、2 つの複数の .msi ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="da602-108">The application artifacts are then exported into two different .msi files.</span></span> <span data-ttu-id="da602-109">1 つの .msi ファイルには、Assembly1、Certificate1、および Script1 が含まれています。</span><span class="sxs-lookup"><span data-stu-id="da602-109">One .msi file contains Assembly1, Certificate1, and Script1.</span></span> <span data-ttu-id="da602-110">その他の .msi ファイルには、Assembly2、Script2、および virtualdirectory1 を含みますが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da602-110">The other .msi file contains Assembly2, Script2, and VirtualDirectory1.</span></span>  
  
 <span data-ttu-id="da602-111">両方の .msi ファイルは、BizTalk グループ 2 にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="da602-111">Both .msi files are imported into BizTalk Group 2.</span></span> <span data-ttu-id="da602-112">どちらも Order Processing アプリケーションに属している、ために、注文処理をという新しいグループに同じアプリケーションに両方の .msi ファイル内の成果物のすべてインポートされます。</span><span class="sxs-lookup"><span data-stu-id="da602-112">Because they both belong to the Order Processing application, all of the artifacts in both .msi files are imported into the same application named Order Processing in the new group.</span></span>  
  
 <span data-ttu-id="da602-113">さらに、アプリケーションのアイテムは、それらを実行するグループ内のコンピューターに .msi ファイルからインストールされます。</span><span class="sxs-lookup"><span data-stu-id="da602-113">In addition, the application artifacts are installed from the .msi files onto the computers in the group that will run them.</span></span> <span data-ttu-id="da602-114">どちらも IIS を実行している BizTalk Server B および BizTalk Server C に仮想ディレクトリを含む .msi ファイルがインストールされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="da602-114">Note that the .msi file containing the virtual directory is installed on BizTalk Server B and BizTalk Server C, which are both running IIS.</span></span>  
  
 <span data-ttu-id="da602-115">![別のコンピューターにインストールされている成果物](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")</span><span class="sxs-lookup"><span data-stu-id="da602-115">![Artifacts installed on different computers](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da602-116">参照</span><span class="sxs-lookup"><span data-stu-id="da602-116">See Also</span></span>  
 <span data-ttu-id="da602-117">[アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="da602-117">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 <span data-ttu-id="da602-118">[BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="da602-118">[How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md) </span></span>  
 <span data-ttu-id="da602-119">[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="da602-119">[How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="da602-120">BizTalk アプリケーションをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="da602-120">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)
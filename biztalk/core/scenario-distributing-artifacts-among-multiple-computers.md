---
title: "シナリオ: 複数のコンピューター間でのアイテムの分散 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abedc60ad13c7e8b2be3ce4caa7b8d34262b4e5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-distributing-artifacts-among-multiple-computers"></a><span data-ttu-id="dcb75-102">シナリオ: 複数のコンピューター間での成果物を配布します。</span><span class="sxs-lookup"><span data-stu-id="dcb75-102">Scenario: Distributing Artifacts Among Multiple Computers</span></span>
<span data-ttu-id="dcb75-103">このトピックでは、アプリケーション内のアイテムを、別々のコンピューターに選択的にインストールする場合のアプリケーション展開シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dcb75-103">This topic describes the application deployment scenario when the artifacts in an application are selectively installed on different computers.</span></span> <span data-ttu-id="dcb75-104">これを行うのは、アプリケーション内の特定のアセンブリまたはその他の種類のアイテムを、BizTalk グループ内の特定のコンピューターにのみインストールする場合です。</span><span class="sxs-lookup"><span data-stu-id="dcb75-104">You might want to do this if you want certain assemblies or other types of artifacts in an application to be installed only on specific computers in a BizTalk group.</span></span> <span data-ttu-id="dcb75-105">そのためには、アプリケーションに含まれているアイテムを、物理コンピューターに同時にインストールするアイテムに応じて、複数の .msi ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dcb75-105">To do this, you can export the artifacts included in an application into multiple .msi files, according to which artifacts you want to install together on a physical computer.</span></span>  
  
 <span data-ttu-id="dcb75-106">次の図は、BizTalk グループ 1 の BizTalk 管理データベースにインポートする .msi ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="dcb75-106">The following diagram shows an .msi file that is imported into the BizTalk Management database for BizTalk Group 1.</span></span> <span data-ttu-id="dcb75-107">これにより、そのグループで、Order Processing アプリケーションとすべてのアイテムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dcb75-107">This creates the Order Processing application and all of its artifacts in that group.</span></span> <span data-ttu-id="dcb75-108">アプリケーションのアイテムは、2 つの .msi ファイルに分けてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dcb75-108">The application artifacts are then exported into two different .msi files.</span></span> <span data-ttu-id="dcb75-109">一方の .msi ファイルは、Assembly1、Certificate1、および Script1 を含みます。</span><span class="sxs-lookup"><span data-stu-id="dcb75-109">One .msi file contains Assembly1, Certificate1, and Script1.</span></span> <span data-ttu-id="dcb75-110">もう一方の .msi ファイルは、Assembly2、Script2、および VirtualDirectory1 を含みます。</span><span class="sxs-lookup"><span data-stu-id="dcb75-110">The other .msi file contains Assembly2, Script2, and VirtualDirectory1.</span></span>  
  
 <span data-ttu-id="dcb75-111">両方の .msi ファイルは、BizTalk グループ 2 にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="dcb75-111">Both .msi files are imported into BizTalk Group 2.</span></span> <span data-ttu-id="dcb75-112">両方に所属するため、Order Processing アプリケーションは、新しいグループの注文処理をという同じアプリケーションに両方の .msi ファイル内の成果物のすべてインポートされます。</span><span class="sxs-lookup"><span data-stu-id="dcb75-112">Because they both belong to the Order Processing application, all of the artifacts in both .msi files are imported into the same application named Order Processing in the new group.</span></span>  
  
 <span data-ttu-id="dcb75-113">また、アプリケーションのアイテムは、.msi ファイルから、グループ内でアイテムを実行するコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dcb75-113">In addition, the application artifacts are installed from the .msi files onto the computers in the group that will run them.</span></span> <span data-ttu-id="dcb75-114">仮想ディレクトリが格納されている .msi ファイルは BizTalk Server B および BizTalk Server C にインストールされます (両方が IIS を実行しています)。</span><span class="sxs-lookup"><span data-stu-id="dcb75-114">Note that the .msi file containing the virtual directory is installed on BizTalk Server B and BizTalk Server C, which are both running IIS.</span></span>  
  
 <span data-ttu-id="dcb75-115">![別のコンピューターにインストールされている成果物](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")</span><span class="sxs-lookup"><span data-stu-id="dcb75-115">![Artifacts installed on different computers](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb75-116">参照</span><span class="sxs-lookup"><span data-stu-id="dcb75-116">See Also</span></span>  
 <span data-ttu-id="dcb75-117">[アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="dcb75-117">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 <span data-ttu-id="dcb75-118">[BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="dcb75-118">[How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md) </span></span>  
 <span data-ttu-id="dcb75-119">[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="dcb75-119">[How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="dcb75-120">BizTalk アプリケーションをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="dcb75-120">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)
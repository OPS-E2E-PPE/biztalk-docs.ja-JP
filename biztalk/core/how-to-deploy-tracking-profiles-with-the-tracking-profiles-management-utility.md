---
title: プロファイル管理ユーティリティの追跡を使用して追跡プロファイルを展開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4402c8e2951e069c908e431fac203c582c80be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385267"
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a><span data-ttu-id="f141d-102">追跡プロファイル管理ユーティリティを使用して追跡プロファイルを展開する方法</span><span class="sxs-lookup"><span data-stu-id="f141d-102">How to Deploy Tracking Profiles with the Tracking Profiles Management Utility</span></span>
<span data-ttu-id="f141d-103">ビジネス マネージャーは、ソリューション開発者は、新しい追跡プロファイルを作成またはより良く管理および、組織の特定のビジネス プロセスを監視するには、既存の変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="f141d-103">A business manager asks a solutions developer to create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span>  
  
 <span data-ttu-id="f141d-104">ソリューション開発者は、ビジネス アナリストが必要とするデータを定義するのに追跡プロファイル エディター (TPE) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f141d-104">The solutions developer uses the Tracking Profile Editor (TPE) to define the data that the business analyst requires.</span></span>  
  
 <span data-ttu-id="f141d-105">ソリューション開発者作成または追跡プロファイルを変更し、後に、管理者が、bttdeploy.exe コマンド ライン ユーティリティを使用して、変更を有効にされ、データが収集されるように展開します。</span><span class="sxs-lookup"><span data-stu-id="f141d-105">After a solutions developer creates or modifies the tracking profile, an administrator uses the bttdeploy.exe command line utility to deploy it so that the changes take affect and the data is collected.</span></span> <span data-ttu-id="f141d-106">ソリューション開発者は TPE を使用して追跡プロファイルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="f141d-106">The solutions developer can deploy tracking profiles with the TPE.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f141d-107">追跡プロファイルを展開する前に、追跡プロファイルに関連付けられているアセンブリを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f141d-107">You must deploy the assemblies associated with the tracking profile before you deploy the tracking profile.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f141d-108">このツールを使用するには、BizTalk® 管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="f141d-108">You must have BizTalk® Administrator privileges to use this tool.</span></span>  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a><span data-ttu-id="f141d-109">コマンド ライン ユーティリティから追跡プロファイルを展開するには</span><span class="sxs-lookup"><span data-stu-id="f141d-109">To deploy the tracking profile from the command-line utility</span></span>  
  
1.  <span data-ttu-id="f141d-110">コマンド プロンプトからディレクトリに移動します。\<インストール パス\>\Program Files\Microsoft BizTalk Server\<バージョン\>\Tracking\\します。</span><span class="sxs-lookup"><span data-stu-id="f141d-110">From a command prompt, move to the directory \<installation path\>\Program Files\Microsoft BizTalk Server \<version\>\Tracking\\.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f141d-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f141d-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="f141d-112">型**bttdeploy.exe\<プロファイル名\>.btt**します。</span><span class="sxs-lookup"><span data-stu-id="f141d-112">Type **bttdeploy.exe \<profile name\>.btt**.</span></span>  
  
3.  <span data-ttu-id="f141d-113">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f141d-113">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f141d-114">参照</span><span class="sxs-lookup"><span data-stu-id="f141d-114">See Also</span></span>  
 <span data-ttu-id="f141d-115">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="f141d-115">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="f141d-116">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="f141d-116">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="f141d-117">ビジネス アクティビティの監視 (BAM)</span><span class="sxs-lookup"><span data-stu-id="f141d-117">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)
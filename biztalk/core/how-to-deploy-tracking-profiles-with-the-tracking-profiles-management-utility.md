---
title: "プロファイル管理ユーティリティの追跡を使用して追跡プロファイルを展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dde3f351c583be9037127c060d02c98d12b2fcb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a><span data-ttu-id="bcca0-102">追跡プロファイル管理ユーティリティを使用して追跡プロファイルを展開する方法</span><span class="sxs-lookup"><span data-stu-id="bcca0-102">How to Deploy Tracking Profiles with the Tracking Profiles Management Utility</span></span>
<span data-ttu-id="bcca0-103">ビジネス マネージャーは、組織の特定のビジネス プロセスの管理や監視を強化するために、新しい追跡プロファイルの作成や既存のプロファイルの変更を行うようにソリューション開発者に依頼します。</span><span class="sxs-lookup"><span data-stu-id="bcca0-103">A business manager asks a solutions developer to create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span>  
  
 <span data-ttu-id="bcca0-104">ソリューション開発者は、追跡プロファイル エディター (TPE) を使用して、ビジネス アナリストが必要とするデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="bcca0-104">The solutions developer uses the Tracking Profile Editor (TPE) to define the data that the business analyst requires.</span></span>  
  
 <span data-ttu-id="bcca0-105">ソリューション開発者により、追跡プロファイルの作成または変更が行われたら、管理者はその変更を有効にしてデータを収集できるように、bttdeploy.exe コマンド ライン ユーティリティを使用して追跡プロファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="bcca0-105">After a solutions developer creates or modifies the tracking profile, an administrator uses the bttdeploy.exe command line utility to deploy it so that the changes take affect and the data is collected.</span></span> <span data-ttu-id="bcca0-106">ソリューション開発者は TPE を使用して追跡プロファイルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="bcca0-106">The solutions developer can deploy tracking profiles with the TPE.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bcca0-107">追跡プロファイルを展開するには、追跡プロファイルに関連付けられたアセンブリを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcca0-107">You must deploy the assemblies associated with the tracking profile before you deploy the tracking profile.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bcca0-108">このツールを使用するには、BizTalk® 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="bcca0-108">You must have BizTalk® Administrator privileges to use this tool.</span></span>  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a><span data-ttu-id="bcca0-109">コマンド ライン ユーティリティから追跡プロファイルを展開するには</span><span class="sxs-lookup"><span data-stu-id="bcca0-109">To deploy the tracking profile from the command-line utility</span></span>  
  
1.  <span data-ttu-id="bcca0-110">コマンド プロンプトでディレクトリに移動\<インストール パス\>\Program Files\Microsoft BizTalk Server\<バージョン\>\Tracking\\です。</span><span class="sxs-lookup"><span data-stu-id="bcca0-110">From a command prompt, move to the directory \<installation path\>\Program Files\Microsoft BizTalk Server \<version\>\Tracking\\.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcca0-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcca0-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="bcca0-112">型**bttdeploy.exe\<プロファイル名\>.btt**です。</span><span class="sxs-lookup"><span data-stu-id="bcca0-112">Type **bttdeploy.exe \<profile name\>.btt**.</span></span>  
  
3.  <span data-ttu-id="bcca0-113">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bcca0-113">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcca0-114">参照</span><span class="sxs-lookup"><span data-stu-id="bcca0-114">See Also</span></span>  
 <span data-ttu-id="bcca0-115">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="bcca0-115">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="bcca0-116">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="bcca0-116">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="bcca0-117">ビジネス アクティビティの監視 (BAM)</span><span class="sxs-lookup"><span data-stu-id="bcca0-117">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)
---
title: BAM 警告の実行の管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], executing alerts
- Notification Services, configuration files
- BAM Management utility
- alerts, executing
ms.assetid: 44bb738e-fa2c-4b32-9e8d-e756d6c3778e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d8dca3f99480b6875253eb6aca102977935160b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021984"
---
# <a name="managing-bam-alert-execution"></a><span data-ttu-id="d0635-102">BAM 警告の実行の管理</span><span class="sxs-lookup"><span data-stu-id="d0635-102">Managing BAM Alert Execution</span></span>
<span data-ttu-id="d0635-103">BAM 警告の実行は、BAM ポータル、BAM 管理ユーティリティ、および ProcessBamNSFiles.vbs スクリプトの 3 つの方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0635-103">BAM Alert execution can be modified through three avenues, The BAM Portal, the BAM management utility, and the ProcessBamNSFiles.vbs script.</span></span>  
  
## <a name="bam-portal"></a><span data-ttu-id="d0635-104">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="d0635-104">BAM Portal</span></span>  
 <span data-ttu-id="d0635-105">ナレッジ ワーカーおよび管理者は、警告の配信方法を BAM ポータルの警告マネージャーを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0635-105">Knowledge workers and administrators can modify the manner in which alerts are delivered by using the Alert Manager in the BAM portal.</span></span> <span data-ttu-id="d0635-106">BAM ポータルからは、警告の有効と無効の切り替え、しきい値レベルの変更、配信場所の変更を実行できます。また、警告の実行に影響を与えるようなその他の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="d0635-106">From the BAM portal, the Alert can be enabled or disabled, threshold levels can be modified, delivery locations can be modified, as well as other parameters the affect the execution of the alert.</span></span>  
  
 <span data-ttu-id="d0635-107">アラートを変更する方法の詳細については、[BAM ポータル ページで、警告マネージャー](../core/alert-manager-on-the-bam-portal-page.md)と[BAM ポータルのアラート](../core/alerts-in-the-bam-portal.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0635-107">For more information on modifying alerts, see [Alert Manager on the BAM Portal Page](../core/alert-manager-on-the-bam-portal-page.md) and [Alerts in the BAM Portal](../core/alerts-in-the-bam-portal.md).</span></span>  
  
### <a name="bam-management-utility"></a><span data-ttu-id="d0635-108">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d0635-108">BAM Management Utility</span></span>  
 <span data-ttu-id="d0635-109">管理者は、BAM 管理ユーティリティを使用して、警告の有効化、無効化、および削除を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d0635-109">Administrators can use the BAM Management utility to enable, disable, and remove alerts.</span></span>  
  
 <span data-ttu-id="d0635-110">BAM 管理ユーティリティを使用して警告を管理する方法については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0635-110">For information on using the BAM Management Utility to mange alerts, the following topics:</span></span>  
  
-   [<span data-ttu-id="d0635-111">アラートを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="d0635-111">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md) 
  
-   [<span data-ttu-id="d0635-112">アラートを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="d0635-112">How to Disable Alerts</span></span>](../core/how-to-disable-alerts.md)  
  
-   [<span data-ttu-id="d0635-113">BAM 警告を削除する方法</span><span class="sxs-lookup"><span data-stu-id="d0635-113">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)  
  
### <a name="modifying-notification-services-configuration-files"></a><span data-ttu-id="d0635-114">Notification Services 構成ファイルの変更</span><span class="sxs-lookup"><span data-stu-id="d0635-114">Modifying Notification Services Configuration Files</span></span>  
 <span data-ttu-id="d0635-115">管理者は、ProcessBamNSFiles.vbs スクリプトを使用して、Notification Services で警告を配信する方法を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0635-115">Administrators can use the ProcessBamNSFiles.vbs script to change the manner in which the Notification Services delivers alerts.</span></span> <span data-ttu-id="d0635-116">Notification Services の詳細については、アプリケーション定義ファイル (ADF)、[ http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0635-116">For more information the Application Definition File (ADF) for Notification Services, see [http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016).</span></span>  
  
 <span data-ttu-id="d0635-117">BAM に関連付けられた ADF を変更するには、次の一般的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0635-117">To modify the ADF associated with BAM you can follow these general steps:</span></span>  
  
1. <span data-ttu-id="d0635-118">スクリプトを実行して、現在の構成ファイルと ADF ファイルを入手します。</span><span class="sxs-lookup"><span data-stu-id="d0635-118">Run the script to obtain the current configuration and ADF files.</span></span>  
  
2. <span data-ttu-id="d0635-119">ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0635-119">Modify the files.</span></span>  
  
3. <span data-ttu-id="d0635-120">スクリプトを実行して、変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="d0635-120">Run the script to apply the changes.</span></span>  
  
   <span data-ttu-id="d0635-121">ProcessBamNSFiles.vbs スクリプトの詳細については、[通知サービス構成ファイル用の BAM コマンド ライン スクリプト](../core/bam-command-line-script-for-notification-services-configuration-files.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0635-121">For more information on the ProcessBamNSFiles.vbs script, see [BAM Command-Line Script for Notification Services Configuration Files](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0635-122">参照</span><span class="sxs-lookup"><span data-stu-id="d0635-122">See Also</span></span>  
 <span data-ttu-id="d0635-123">[BAM ポータルの管理](../core/managing-the-bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="d0635-123">[Managing the BAM Portal](../core/managing-the-bam-portal.md) </span></span>  
 <span data-ttu-id="d0635-124">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="d0635-124">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="d0635-125">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d0635-125">BAM Management Utility</span></span>](../core/bam-management-utility.md)
---
title: "チェックリスト: をバックアップし、BizTalk Server データベースを復元 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- restoring, checklists
- maintaining, restoring
- maintaining, checklists
- restoring, BizTalk Server
- maintaining, backing up
- checklists, backing up
- backing up, checklists
- BizTalk Server, backing up
- checklists, restoring
- BizTalk Server, restoring
ms.assetid: 12f7e02e-57b1-4e55-8e44-7fe2d7920f5a
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3c8c68eb62273562b0f703ae79c0db76ec837c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-back-up-and-restore-biztalk-server-databases"></a><span data-ttu-id="32918-102">チェックリスト: をバックアップし、BizTalk Server データベースの復元</span><span class="sxs-lookup"><span data-stu-id="32918-102">Checklist: Back Up and Restore BizTalk Server Databases</span></span>
<span data-ttu-id="32918-103">BizTalk Server をバックアップまたは復元する場合は、あらかじめ必要な作業を把握しておくことが大切です。</span><span class="sxs-lookup"><span data-stu-id="32918-103">Before attempting to back up or restore BizTalk Server, be sure to familiarize yourself with the processes involved.</span></span>  
  
## <a name="backing-up-biztalk-server"></a><span data-ttu-id="32918-104">BizTalk Server のバックアップ</span><span class="sxs-lookup"><span data-stu-id="32918-104">Backing Up BizTalk Server</span></span>  
  
|<span data-ttu-id="32918-105">手順</span><span class="sxs-lookup"><span data-stu-id="32918-105">Step</span></span>|<span data-ttu-id="32918-106">リファレンス</span><span class="sxs-lookup"><span data-stu-id="32918-106">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="32918-107">BizTalk Server のバックアップと復元の方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="32918-107">Learn how to back up and restore BizTalk Server.</span></span>|[<span data-ttu-id="32918-108">バックアップおよびデータベースを復元するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="32918-108">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)<br /><br /> [<span data-ttu-id="32918-109">BizTalk Server データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="32918-109">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|<span data-ttu-id="32918-110">BizTalk Server のバックアップと復元に必要なアクセス許可を取得します。</span><span class="sxs-lookup"><span data-stu-id="32918-110">Ensure that you have appropriate permissions to back up and restore BizTalk Server.</span></span>|[<span data-ttu-id="32918-111">セキュリティの最小ユーザー権限</span><span class="sxs-lookup"><span data-stu-id="32918-111">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)|  
|<span data-ttu-id="32918-112">BizTalk Server のバックアップ ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="32918-112">Configure the Backup BizTalk Server job.</span></span>|[<span data-ttu-id="32918-113">BizTalk Server のバックアップ ジョブを構成する方法</span><span class="sxs-lookup"><span data-stu-id="32918-113">How to Configure the Backup BizTalk Server Job</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|<span data-ttu-id="32918-114">バックアップの格納先サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="32918-114">Configure the server where backups will be stored.</span></span>|[<span data-ttu-id="32918-115">ログ配布用に送信先システムを構成する方法</span><span class="sxs-lookup"><span data-stu-id="32918-115">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|<span data-ttu-id="32918-116">ビジネス アクティビティ監視 (BAM) を使用している場合は、BAM データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="32918-116">If you are using Business Activity Monitoring (BAM), back up the BAM databases.</span></span>|[<span data-ttu-id="32918-117">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="32918-117">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)|  
|<span data-ttu-id="32918-118">エンタープライズ シングル サインオンを使用している場合は、マスター シークレットをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="32918-118">If you are using Enterprise Single Sign-on, back up the master secret.</span></span>|[<span data-ttu-id="32918-119">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="32918-119">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)|  
  
## <a name="restoring-biztalk-server"></a><span data-ttu-id="32918-120">BizTalk Server の復元</span><span class="sxs-lookup"><span data-stu-id="32918-120">Restoring BizTalk Server</span></span>  
  
|<span data-ttu-id="32918-121">手順</span><span class="sxs-lookup"><span data-stu-id="32918-121">Step</span></span>|<span data-ttu-id="32918-122">リファレンス</span><span class="sxs-lookup"><span data-stu-id="32918-122">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="32918-123">データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="32918-123">Restore your databases.</span></span>|[<span data-ttu-id="32918-124">データベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="32918-124">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)|  
|<span data-ttu-id="32918-125">BAM データベース名の参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="32918-125">Update references to the BAM database names.</span></span>|[<span data-ttu-id="32918-126">バックアップ方法、BAM 分析および Tracking Analysis Server データベース</span><span class="sxs-lookup"><span data-stu-id="32918-126">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [<span data-ttu-id="32918-127">BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="32918-127">How to Update References to the BAM Analysis Server and Star Schema Database Names</span></span>](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [<span data-ttu-id="32918-128">BAM アーカイブ データベース名への参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="32918-128">How to Update References to the BAM Archive Database Name</span></span>](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [<span data-ttu-id="32918-129">BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="32918-129">How to Update References to the BAM Primary Import Database Name and Connection String</span></span>](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [<span data-ttu-id="32918-130">Services データベース、BAM 通知への参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="32918-130">How to Update References to the BAM Notification Services Databases</span></span>](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [<span data-ttu-id="32918-131">不完全なアクティビティ インスタンスを解決する方法</span><span class="sxs-lookup"><span data-stu-id="32918-131">How to Resolve Incomplete Activity Instances</span></span>](../core/how-to-resolve-incomplete-activity-instances.md)|  
|<span data-ttu-id="32918-132">エンタープライズ シングル サインオンを使用している場合は、マスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="32918-132">If you are using Enterprise Single Sign-on, restore the master secret.</span></span>|[<span data-ttu-id="32918-133">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="32918-133">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)|  
  
## <a name="see-also"></a><span data-ttu-id="32918-134">参照</span><span class="sxs-lookup"><span data-stu-id="32918-134">See Also</span></span>  
 [<span data-ttu-id="32918-135">バックアップと、BizTalk Server データベースの復元</span><span class="sxs-lookup"><span data-stu-id="32918-135">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)
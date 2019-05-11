---
title: チェックリスト:アーカイブおよび BizTalk 追跡データベースの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], checklist
- checklists, purging [Tracking database]
- purging, checklist
- checklists, archiving [Tracking database]
ms.assetid: dccbf471-2add-498e-b292-287d9a94161b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59ceb1ed0c31f3b984a38f4a6890e42e289d10dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357461"
---
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a><span data-ttu-id="fd29f-102">チェックリスト:BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="fd29f-102">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>

|<span data-ttu-id="fd29f-103">手順</span><span class="sxs-lookup"><span data-stu-id="fd29f-103">Step</span></span>|<span data-ttu-id="fd29f-104">リファレンス</span><span class="sxs-lookup"><span data-stu-id="fd29f-104">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="fd29f-105">追跡データ アーカイブおよび削除のプロセスの理解を深め、アーカイブと削除の概要を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="fd29f-105">Read the Archiving and Purging overview to become more familiar with the process of archiving and purging tracking data.</span></span>|[<span data-ttu-id="fd29f-106">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="fd29f-106">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="fd29f-107">DTA Purge and Archive ジョブのセキュリティを高めるため、ログオン資格情報を使用して行うことができますが、DTA Purge and Archive ジョブを実行するために必要な SQL Server 資格情報を持つために BTS_BACKUP_USERS ロールを構成してください。</span><span class="sxs-lookup"><span data-stu-id="fd29f-107">Although you can run the DTA Purge and Archive job using your logon credentials, for added security, you should configure the BTS_BACKUP_USERS role with the necessary SQL Server credentials to run the DTA Purge and Archive job.</span></span> <span data-ttu-id="fd29f-108">これは、特権の昇格を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fd29f-108">This helps to prevent elevation of privileges.</span></span>|[<span data-ttu-id="fd29f-109">アーカイブおよび BizTalk 追跡データベースからデータを削除のために BTS_BACKUP_USERS ロールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="fd29f-109">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|<span data-ttu-id="fd29f-110">DTA Purge and Archive ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="fd29f-110">Configure the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="fd29f-111">構成の DTA Purge and Archive ジョブをする方法</span><span class="sxs-lookup"><span data-stu-id="fd29f-111">How to Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|<span data-ttu-id="fd29f-112">DTA Purge and Archive ジョブを BizTalk 追跡 (BizTalkDTADb) データベース内のデータをアーカイブして古いデータの削除を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd29f-112">Run the DTA Purge and Archive job, which archives the data in your BizTalk Tracking (BizTalkDTADb) database and purges old data.</span></span>|[<span data-ttu-id="fd29f-113">BizTalk 追跡データベースからデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="fd29f-113">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="fd29f-114">必要に応じて、BizTalk 追跡 (BizTalkDTADb) データベースからデータを手動で消去することができます。</span><span class="sxs-lookup"><span data-stu-id="fd29f-114">Optionally, you can manually purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="fd29f-115">BizTalk 追跡データベースからデータを手動で削除する方法</span><span class="sxs-lookup"><span data-stu-id="fd29f-115">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="fd29f-116">BizTalk 追跡 (BizTalkDTADb) データベースからアーカイブされたデータの自動検証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fd29f-116">Enable automatic validation of the archived data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="fd29f-117">アーカイブの自動検証を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="fd29f-117">How to Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)|  
|<span data-ttu-id="fd29f-118">追跡メッセージは、BizTalk 追跡 (BizTalkDTADb) データベースにコピーします。</span><span class="sxs-lookup"><span data-stu-id="fd29f-118">Copy tracked messages into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="fd29f-119">これは、DTA Purge and Archive ジョブを使用してデータを削除するために必要です。</span><span class="sxs-lookup"><span data-stu-id="fd29f-119">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="fd29f-120">追跡メッセージを BizTalk 追跡データベースにコピーする方法</span><span class="sxs-lookup"><span data-stu-id="fd29f-120">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  

## <a name="see-also"></a><span data-ttu-id="fd29f-121">参照</span><span class="sxs-lookup"><span data-stu-id="fd29f-121">See Also</span></span>  
 [<span data-ttu-id="fd29f-122">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="fd29f-122">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
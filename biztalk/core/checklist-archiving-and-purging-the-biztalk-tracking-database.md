---
title: "チェックリスト: がアーカイブ化および BizTalk 追跡データベースを削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], checklist
- checklists, purging [Tracking database]
- purging, checklist
- checklists, archiving [Tracking database]
ms.assetid: dccbf471-2add-498e-b292-287d9a94161b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22e97ac12e6b6b304318f57f309767ec7c63815f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a><span data-ttu-id="274f5-102">チェックリスト: がアーカイブ化および BizTalk 追跡データベースを削除</span><span class="sxs-lookup"><span data-stu-id="274f5-102">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>
|<span data-ttu-id="274f5-103">手順</span><span class="sxs-lookup"><span data-stu-id="274f5-103">Step</span></span>|<span data-ttu-id="274f5-104">リファレンス</span><span class="sxs-lookup"><span data-stu-id="274f5-104">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="274f5-105">アーカイブと削除の概要を読み、追跡データのアーカイブと削除を行う処理についての理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="274f5-105">Read the Archiving and Purging overview to become more familiar with the process of archiving and purging tracking data.</span></span>|[<span data-ttu-id="274f5-106">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="274f5-106">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="274f5-107">自分のログオン資格情報で DTA Purge and Archive ジョブを実行することもできますが、セキュリティを高めるため、DTA Purge and Archive ジョブを実行するために必要な SQL Server 資格情報を使用して BTS_BACKUP_USERS ロールを構成してください。</span><span class="sxs-lookup"><span data-stu-id="274f5-107">Although you can run the DTA Purge and Archive job using your logon credentials, for added security, you should configure the BTS_BACKUP_USERS role with the necessary SQL Server credentials to run the DTA Purge and Archive job.</span></span> <span data-ttu-id="274f5-108">そうすることで、特権の昇格を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="274f5-108">This helps to prevent elevation of privileges.</span></span>|[<span data-ttu-id="274f5-109">アーカイブおよび BizTalk 追跡データベースからデータを削除するために BTS_BACKUP_USERS ロールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="274f5-109">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|<span data-ttu-id="274f5-110">DTA Purge and Archive ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="274f5-110">Configure the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="274f5-111">DTA Purge and Archive ジョブを構成する方法</span><span class="sxs-lookup"><span data-stu-id="274f5-111">How to Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|<span data-ttu-id="274f5-112">BizTalk 追跡データベース (BizTalkDTADb) のデータをアーカイブして古いデータを削除するため、DTA Purge and Archive ジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="274f5-112">Run the DTA Purge and Archive job, which archives the data in your BizTalk Tracking (BizTalkDTADb) database and purges old data.</span></span>|[<span data-ttu-id="274f5-113">BizTalk 追跡データベースからデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="274f5-113">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="274f5-114">BizTalk 追跡データベース (BizTalkDTADb) から手動でデータを削除します (任意)。</span><span class="sxs-lookup"><span data-stu-id="274f5-114">Optionally, you can manually purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="274f5-115">BizTalk 追跡データベースからデータを手動で削除する方法</span><span class="sxs-lookup"><span data-stu-id="274f5-115">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="274f5-116">アーカイブした BizTalk 追跡データベース (BizTalkDTADb) のデータの自動検証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="274f5-116">Enable automatic validation of the archived data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="274f5-117">アーカイブの自動検証を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="274f5-117">How to Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)|  
|<span data-ttu-id="274f5-118">BizTalk 追跡 (BizTalkDTADb) データベースに追跡されるメッセージをコピーします。</span><span class="sxs-lookup"><span data-stu-id="274f5-118">Copy tracked messages into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="274f5-119">これは、DTA Purge and Archive ジョブを使用してデータを削除するために必要です。</span><span class="sxs-lookup"><span data-stu-id="274f5-119">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="274f5-120">BizTalk 追跡データベースに追跡されるメッセージをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="274f5-120">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  
  
## <a name="see-also"></a><span data-ttu-id="274f5-121">参照</span><span class="sxs-lookup"><span data-stu-id="274f5-121">See Also</span></span>  
 [<span data-ttu-id="274f5-122">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="274f5-122">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
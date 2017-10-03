---
title: "バックアップおよび Restore2 に関する詳細情報 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa6a3527-4889-40ae-aacb-b8ea75be0329
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6991e417afaee807d999f7123f7a853dbd955eb3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="advanced-information-about-backup-and-restore"></a><span data-ttu-id="980f2-102">バックアップおよび復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="980f2-102">Advanced Information About Backup and Restore</span></span>
<span data-ttu-id="980f2-103">ここに挙げたトピックが、バックアップを記述し、さらに復元プロセスの詳細およびの確実な理解と高度なユーザーが使用するものでは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="980f2-103">The topics listed here describe the backup and restore processes in more detail and are intended to be used by advanced users with a thorough understanding of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="980f2-104">マークされたトランザクション、完全バックアップ、およびログについては、次を参照してください。[マークされたトランザクションを、完全バックアップ、およびログ バックアップ](http://go.microsoft.com/fwlink/?LinkId=151565)(http://go.microsoft.com/fwlink/?LinkId=151565)。</span><span class="sxs-lookup"><span data-stu-id="980f2-104">For information about marked transaction, full backups, and logs, see [Marked Transactions, Full Backups, and Log Backups](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span></span>  
  
-   <span data-ttu-id="980f2-105">について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布を参照してください[BizTalk Server ログ配布](http://go.microsoft.com/fwlink/?LinkId=151566)(http://go.microsoft.com/fwlink/?LinkId=151566)。</span><span class="sxs-lookup"><span data-stu-id="980f2-105">For information about [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping, see [BizTalk Server Log Shipping](http://go.microsoft.com/fwlink/?LinkId=151566) (http://go.microsoft.com/fwlink/?LinkId=151566).</span></span>  
  
-   <span data-ttu-id="980f2-106">バックアップをスケジュール設定については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを参照してください[を BizTalk Server のバックアップ ジョブをスケジュールする方法](http://go.microsoft.com/fwlink/?LinkId=151568)(http://go.microsoft.com/fwlink/?LinkId=151568)。</span><span class="sxs-lookup"><span data-stu-id="980f2-106">For information about scheduling backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=151568) (http://go.microsoft.com/fwlink/?LinkId=151568).</span></span>  
  
-   <span data-ttu-id="980f2-107">カスタム データベースのバックアップの詳細については、次を参照してください。[戻るをカスタム データベース方法](http://go.microsoft.com/fwlink/?LinkId=151569)(http://go.microsoft.com/fwlink/?LinkId=151569)。</span><span class="sxs-lookup"><span data-stu-id="980f2-107">For information about backing up custom databases, see [How to Back Up Custom Databases](http://go.microsoft.com/fwlink/?LinkId=151569) (http://go.microsoft.com/fwlink/?LinkId=151569).</span></span>  
  
-   <span data-ttu-id="980f2-108">リンク サーバーを作成する方法の詳細については、次を参照してください。[リンク サーバーを作成する方法](http://go.microsoft.com/fwlink/?LinkId=151570)(http://go.microsoft.com/fwlink/?LinkId=151570)。</span><span class="sxs-lookup"><span data-stu-id="980f2-108">For information about creating a linked server, see [How to Create a Linked Server](http://go.microsoft.com/fwlink/?LinkId=151570) (http://go.microsoft.com/fwlink/?LinkId=151570).</span></span>  
  
-   <span data-ttu-id="980f2-109">復元されたバックアップの履歴を表示する方法については、次を参照してください。[復元するバックアップの履歴を表示する](http://go.microsoft.com/fwlink/?LinkId=151572)(http://go.microsoft.com/fwlink/?LinkId=151572)。</span><span class="sxs-lookup"><span data-stu-id="980f2-109">For information about viewing the history of restored backups, see [Viewing the History of Restored Backups](http://go.microsoft.com/fwlink/?LinkId=151572) (http://go.microsoft.com/fwlink/?LinkId=151572).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="980f2-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="980f2-110">In This Section</span></span>  
  
-   [<span data-ttu-id="980f2-111">BizTalk Server のログ配布の Windows クラスター名と IP アドレスを使用して</span><span class="sxs-lookup"><span data-stu-id="980f2-111">BizTalk Server Log Shipping Using a Windows Cluster Name and IP Address</span></span>](../technical-guides/biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address.md)  
  
-   [<span data-ttu-id="980f2-112">ウォーム バックアップから運用環境の復元</span><span class="sxs-lookup"><span data-stu-id="980f2-112">Restoring Production from a Warm Backup</span></span>](../technical-guides/restoring-production-from-a-warm-backup.md)
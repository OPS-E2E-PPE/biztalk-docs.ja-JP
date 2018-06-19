---
title: BAM ビューを削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, views
- managing [BAM definitions], deleting views
- Remove-View command [BAM]
ms.assetid: 1a43ec81-20b1-41f7-941f-753132ac9ed2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc49038c30cc6016c79f8e0d309f93217994327f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972184"
---
# <a name="how-to-remove-bam-views"></a><span data-ttu-id="6c2ac-102">BAM ビューを削除する方法</span><span class="sxs-lookup"><span data-stu-id="6c2ac-102">How to Remove BAM Views</span></span>
<span data-ttu-id="6c2ac-103">管理者を使用して、**削除ビュー** BAM プライマリ インポート データベースからビューを削除するコマンド。</span><span class="sxs-lookup"><span data-stu-id="6c2ac-103">Administrators use the **remove-view** command to remove a view from the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c2ac-104">ビューを削除すると、そのビューに定義された警告も自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="6c2ac-104">When you remove a view, you also automatically remove any alerts defined for that view.</span></span>  
  
### <a name="to-remove-bam-views"></a><span data-ttu-id="6c2ac-105">BAM ビューを削除するには</span><span class="sxs-lookup"><span data-stu-id="6c2ac-105">To remove BAM views</span></span>  
  
1.  <span data-ttu-id="6c2ac-106">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="6c2ac-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="6c2ac-107">」と入力して、追跡フォルダーに移動**C:\Program files \microsoft BizTalk Server 2009 \tracking**コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="6c2ac-107">Navigate to the tracking folder by typing **C:\Program Files\Microsoft BizTalk Server 2009\Tracking** at the command prompt.</span></span> <span data-ttu-id="6c2ac-108">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6c2ac-108">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="6c2ac-109">型**bm 削除ビューの名前:\<ビュー名\>** です。</span><span class="sxs-lookup"><span data-stu-id="6c2ac-109">Type **bm remove-view -Name:\<view name\>**.</span></span>  
  
4.  <span data-ttu-id="6c2ac-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6c2ac-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2ac-111">参照</span><span class="sxs-lookup"><span data-stu-id="6c2ac-111">See Also</span></span>  
 <span data-ttu-id="6c2ac-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="6c2ac-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="6c2ac-113">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="6c2ac-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 <span data-ttu-id="6c2ac-114">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="6c2ac-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="6c2ac-115">BAM 警告を削除する方法</span><span class="sxs-lookup"><span data-stu-id="6c2ac-115">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)
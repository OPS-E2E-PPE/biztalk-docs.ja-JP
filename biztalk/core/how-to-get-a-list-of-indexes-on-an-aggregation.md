---
title: 集計のインデックスの一覧を取得する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- indexes [BAM], listing indexes
- aggregations [BAM], listing indexes
- Get-Index command [BAM]
ms.assetid: 46a4a2fc-10f8-499c-bf2a-d0a19bb84151
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad7eabf54dc410ebed143641602599438f376a30
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970760"
---
# <a name="how-to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="43e83-102">集計のインデックスの一覧を取得する方法</span><span class="sxs-lookup"><span data-stu-id="43e83-102">How to Get a List of Indexes on an Aggregation</span></span>
<span data-ttu-id="43e83-103">管理者を使用して、 **get インデックス**コマンドを指定されたアクティビティですべてのインデックスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="43e83-103">Administrators use the **get-index** command to get a list of all the indexes on the specified activity.</span></span>  
  
### <a name="to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="43e83-104">集計のインデックスの一覧を取得するには</span><span class="sxs-lookup"><span data-stu-id="43e83-104">To get a list of indexes on an aggregation</span></span>  
  
1.  <span data-ttu-id="43e83-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="43e83-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="43e83-106">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="43e83-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="43e83-107">型**bm get インデックス-アクティビティ:\<アクティビティ名\>** です。</span><span class="sxs-lookup"><span data-stu-id="43e83-107">Type **bm get-index -Activity:\<activity name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43e83-108">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="43e83-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="43e83-109">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="43e83-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e83-110">参照</span><span class="sxs-lookup"><span data-stu-id="43e83-110">See Also</span></span>  
 <span data-ttu-id="43e83-111">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="43e83-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="43e83-112">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="43e83-112">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="43e83-113">[インデックスを削除する方法](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="43e83-113">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="43e83-114">インデックスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="43e83-114">How to Create an Index</span></span>](../core/how-to-create-an-index.md)
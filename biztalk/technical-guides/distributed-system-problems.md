---
title: "システムの問題を分散 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 287b0adb-d5f9-4e47-80f8-0ba5d90c7864
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24abe471a66e8bc0724ad731388c5a0e7c07b573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="distributed-system-problems"></a><span data-ttu-id="ea8e1-102">分散システムの問題</span><span class="sxs-lookup"><span data-stu-id="ea8e1-102">Distributed System Problems</span></span>
<span data-ttu-id="ea8e1-103">分散の送信先システムでのジョブは、復元は、他のコンピューター上の問題やエラーの認識しません。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-103">In a distributed destination system the restore jobs are not aware of errors or problems on the other computers.</span></span> <span data-ttu-id="ea8e1-104">たとえば、コンピューター A が BizTalk 管理データベースおよび BizTalk 追跡データベース、復元して、コンピューター B が BizTalk メッセージ ボックス データベースを復元することです。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-104">For example, suppose that computer A is restoring the BizTalk Management database and the BizTalk Tracking database, and computer B is restoring the BizTalk MessageBox database.</span></span> <span data-ttu-id="ea8e1-105">両方のコンピューターでは、1 ~ 25 のバックアップ セットが正常に復元します。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-105">Both computers successfully restore backup sets 1 through 25.</span></span> <span data-ttu-id="ea8e1-106">ただし、セット 26 には、BizTalk メッセージ ボックス データベースの破損したログ バックアップ ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-106">Set 26, however, has a corrupted log backup file of the BizTalk MessageBox database.</span></span> <span data-ttu-id="ea8e1-107">コンピューター A は、そのデータベースを正しく復元が、コンピューター B が破損したファイルの復元に失敗します。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-107">Computer A restores its databases correctly but computer B fails to restore the corrupted file.</span></span>  
  
 <span data-ttu-id="ea8e1-108">このような状況で元システムで完全バックアップを強制します。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-108">In this situation, force a full backup on the source system.</span></span> <span data-ttu-id="ea8e1-109">上記の例に続ける場合と、問題の診断セット 35 の完全バックアップが作成されました。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-109">Continuing the example above, assume that the problem was diagnosed and a full backup was created for set 35.</span></span> <span data-ttu-id="ea8e1-110">復元セット 34 26、その後、コンピューター A はコンピューター B のコンピューター上の問題を認識してないためされるまでは失敗が完全バックアップは 35 を設定し、それ以降のログのバックアップ セットの 36 (前述のとおり必要があるが常に復元する一連の 1 つの後続の完全なログ バックアップをします。d)。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-110">Computer A then restores sets 26 to 34, because it is not aware of the problem on Computer B. Computer B will fail until it sees full backup set 35 and subsequent log backup set 36 (remember that there must always be one subsequent complete log backup for a set to be restored).</span></span> <span data-ttu-id="ea8e1-111">コンピューター B で 35 と 36 のセットが届いたら、その 35 を使用してそれ自体を修復します。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-111">When sets 35 and 36 arrive on computer B, it will repair itself using 35.</span></span> <span data-ttu-id="ea8e1-112">修復が完了したら、コンピューター A と B が同期されます。</span><span class="sxs-lookup"><span data-stu-id="ea8e1-112">After the repair is complete, computer A and B will be in sync.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8e1-113">参照</span><span class="sxs-lookup"><span data-stu-id="ea8e1-113">See Also</span></span>  
 [<span data-ttu-id="ea8e1-114">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ea8e1-114">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)
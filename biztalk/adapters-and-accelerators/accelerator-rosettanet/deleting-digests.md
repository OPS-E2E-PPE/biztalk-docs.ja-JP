---
title: "ダイジェストの削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, digests
- messages, digests
- digests
- databases, deleting digests
- maintaining databases, deleting digests
ms.assetid: bcc7cb11-2f6a-4996-ad50-040d41993e09
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fefa59a7638b7dc4627d5d7a019d753b4f6290b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deleting-digests"></a><span data-ttu-id="b04ec-102">ダイジェストの削除</span><span class="sxs-lookup"><span data-stu-id="b04ec-102">Deleting Digests</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="b04ec-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]シグナル コンテンツとそれらを検証できるように、送信メッセージのダイジェストが格納されます。</span><span class="sxs-lookup"><span data-stu-id="b04ec-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores digests for outgoing messages, so it can validate them against signal content.</span></span> <span data-ttu-id="b04ec-104">ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]検証後に、ダイジェストは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b04ec-104">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not delete the digests after validation.</span></span> <span data-ttu-id="b04ec-105">定期的にこれらのダイジェストを削除して、システム パフォーマンスを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b04ec-105">Periodically, you may want to delete these digests to maintain system performance.</span></span>  
  
## <a name="when-and-how-to-delete-digests"></a><span data-ttu-id="b04ec-106">ダイジェストを削除する間隔と削除方法</span><span class="sxs-lookup"><span data-stu-id="b04ec-106">When and How to Delete Digests</span></span>  
 <span data-ttu-id="b04ec-107">ダイジェストは、BTARNDATA データベースの MessageDigestHelper テーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b04ec-107">Digests are stored in the MessageDigestHelper table of the BTARNDATA database.</span></span> <span data-ttu-id="b04ec-108">特定の期間以上経過したダイジェストだけを削除するストアド プロシージャを使用して、これらのダイジェストをテーブルから定期的に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b04ec-108">Periodically, you may want to delete these digests from the table by using a stored procedure that deletes only those digests that are older than a certain period.</span></span> <span data-ttu-id="b04ec-109">MessageDigestHelper テーブルには、この目的のために使用する `TimeCreated` プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b04ec-109">The MessageDigestHelper table contains a `TimeCreated` property that you can use for this purpose.</span></span>  
  
 <span data-ttu-id="b04ec-110">(として変更の目的で)、次の SQL ステートメントを使用してストアド プロシージャを作成し、古いダイジェストを削除するストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="b04ec-110">Create a stored procedure with the following SQL statement (as modified for your purposes), and run the stored procedure to delete old digests.</span></span> <span data-ttu-id="b04ec-111">このサンプル ステートメントでは、8 日以上経過したすべてのダイジェストが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b04ec-111">This sample statement deletes all digests more than seven days old:</span></span>  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  <span data-ttu-id="b04ec-112">ストアド プロシージャへの呼び出しを含める必要があります`getutcdate`ではなく、`getdate`ため、すべて[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース UTC (協定世界時) の時刻を使用します。</span><span class="sxs-lookup"><span data-stu-id="b04ec-112">The stored procedure must include a call to `getutcdate`, not `getdate`, because all [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] databases use UTC (Universal Time Coordinate) time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04ec-113">参照</span><span class="sxs-lookup"><span data-stu-id="b04ec-113">See Also</span></span>  
 [<span data-ttu-id="b04ec-114">BTARN データベースの保守</span><span class="sxs-lookup"><span data-stu-id="b04ec-114">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)
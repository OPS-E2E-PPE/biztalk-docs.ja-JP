---
title: ダイジェストの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, digests
- messages, digests
- digests
- databases, deleting digests
- maintaining databases, deleting digests
ms.assetid: bcc7cb11-2f6a-4996-ad50-040d41993e09
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3564b89c69183133bcc31e692aff5b1c85af80d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283739"
---
# <a name="deleting-digests"></a><span data-ttu-id="3000f-102">ダイジェストの削除</span><span class="sxs-lookup"><span data-stu-id="3000f-102">Deleting Digests</span></span>
<span data-ttu-id="3000f-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]シグナル コンテンツと突き合わせて検証できますので、送信メッセージのダイジェストが格納されます。</span><span class="sxs-lookup"><span data-stu-id="3000f-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores digests for outgoing messages, so it can validate them against signal content.</span></span> <span data-ttu-id="3000f-104">ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]検証後に、ダイジェストは削除されません。</span><span class="sxs-lookup"><span data-stu-id="3000f-104">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not delete the digests after validation.</span></span> <span data-ttu-id="3000f-105">定期的に、システムのパフォーマンスを維持するためにこれらのダイジェストを削除することがあります。</span><span class="sxs-lookup"><span data-stu-id="3000f-105">Periodically, you may want to delete these digests to maintain system performance.</span></span>  
  
## <a name="when-and-how-to-delete-digests"></a><span data-ttu-id="3000f-106">ダイジェストを削除するタイミングと方法</span><span class="sxs-lookup"><span data-stu-id="3000f-106">When and How to Delete Digests</span></span>  
 <span data-ttu-id="3000f-107">ダイジェストは、BTARNDATA データベースの MessageDigestHelper テーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3000f-107">Digests are stored in the MessageDigestHelper table of the BTARNDATA database.</span></span> <span data-ttu-id="3000f-108">定期的に、一定期間以上経過したダイジェストだけを削除するストアド プロシージャを使用して、テーブルからこれらのダイジェストを削除します。</span><span class="sxs-lookup"><span data-stu-id="3000f-108">Periodically, you may want to delete these digests from the table by using a stored procedure that deletes only those digests that are older than a certain period.</span></span> <span data-ttu-id="3000f-109">MessageDigestHelper テーブルが含まれています、`TimeCreated`プロパティをこの目的で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3000f-109">The MessageDigestHelper table contains a `TimeCreated` property that you can use for this purpose.</span></span>  
  
 <span data-ttu-id="3000f-110">(変更されたため、)、次の SQL ステートメントを使用してストアド プロシージャを作成し、古いダイジェストを削除するストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="3000f-110">Create a stored procedure with the following SQL statement (as modified for your purposes), and run the stored procedure to delete old digests.</span></span> <span data-ttu-id="3000f-111">このサンプル ステートメントは、7 日以上経過したすべてのダイジェストを削除します。</span><span class="sxs-lookup"><span data-stu-id="3000f-111">This sample statement deletes all digests more than seven days old:</span></span>  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  <span data-ttu-id="3000f-112">ストアド プロシージャの呼び出しを含める必要があります`getutcdate`ではなく、`getdate`ため、すべて[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース UTC (Universal Time Coordinate) 時刻を使用します。</span><span class="sxs-lookup"><span data-stu-id="3000f-112">The stored procedure must include a call to `getutcdate`, not `getdate`, because all [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] databases use UTC (Universal Time Coordinate) time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3000f-113">参照</span><span class="sxs-lookup"><span data-stu-id="3000f-113">See Also</span></span>  
 [<span data-ttu-id="3000f-114">BTARN データベースの保守</span><span class="sxs-lookup"><span data-stu-id="3000f-114">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)
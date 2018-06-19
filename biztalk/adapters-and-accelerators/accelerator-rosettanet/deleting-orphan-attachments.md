---
title: 孤立した添付ファイルの削除 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maintaining databases, deleting orphaned attachments
- databases, deleting orphaned attachments
- attachments
ms.assetid: 38280464-9c9d-4890-9fc5-4b8031dd3f88
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7660182793cc82ac938f0dd25011a7c4ad7d7e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209994"
---
# <a name="deleting-orphan-attachments"></a><span data-ttu-id="5e804-102">孤立した添付ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="5e804-102">Deleting Orphan Attachments</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="5e804-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信メッセージの添付ファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="5e804-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores attachments for received messages.</span></span> <span data-ttu-id="5e804-104">特定の状況で[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、添付ファイルを保存しますが、孤立した添付ファイルに結果として得られる、MessagesToLOB テーブルから関連するメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="5e804-104">In certain circumstances, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the attachment, but deletes the associated message from the MessagesToLOB table, resulting in an orphan attachment.</span></span> <span data-ttu-id="5e804-105">添付ファイルがある、マニフェストが無効な場合、メッセージ NumberOfAttachments に、マニフェストなどを送信するときに発生する可能性がこの 0 を = です。</span><span class="sxs-lookup"><span data-stu-id="5e804-105">This can occur when you submit a message that has an attachment and has a manifest that is not valid, for example, a manifest in which NumberOfAttachments = 0.</span></span> <span data-ttu-id="5e804-106">定期的に、システムのパフォーマンスを維持するために孤立した添付ファイルを削除することがあります。</span><span class="sxs-lookup"><span data-stu-id="5e804-106">Periodically, you may want to delete orphan attachments to maintain system performance.</span></span>  
  
## <a name="how-to-delete-orphan-attachments"></a><span data-ttu-id="5e804-107">孤立した添付ファイルを削除する方法</span><span class="sxs-lookup"><span data-stu-id="5e804-107">How to Delete Orphan Attachments</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5e804-108">添付ファイルを BTARNDATA データベースの Attachments テーブルに格納します。</span><span class="sxs-lookup"><span data-stu-id="5e804-108"> stores attachments in the Attachments table of the BTARNDATA database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5e804-109">関連するメッセージを MessagesToLOB テーブルに格納します。</span><span class="sxs-lookup"><span data-stu-id="5e804-109"> stores the associated messages in the MessagesToLOB table.</span></span> <span data-ttu-id="5e804-110">孤立添付ファイルは、添付ファイルの `outMessageID` プロパティが、MessagesToLOB テーブル内に格納されているメッセージの `MessageID` プロパティと対応しない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5e804-110">An orphan attachment results when the attachment has an `outMessageID` property that does not correspond to the `MessageID` property of a message in the MessagesToLOB table.</span></span>  
  
 <span data-ttu-id="5e804-111">MessagesToLOB テーブル内に対応するメッセージがない添付ファイルだけを削除するストアド プロシージャを使用して、定期的にテーブルから添付ファイルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5e804-111">Periodically, you may want to delete attachments from the table by using a stored procedure that deletes only those attachments that do not have a corresponding message in the MessagesToLOB table.</span></span> <span data-ttu-id="5e804-112">ストアド プロシージャのサンプル SQL ステートメントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e804-112">A sample SQL statement for the stored procedure is:</span></span>  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 <span data-ttu-id="5e804-113">さらに、特定の期間より古く、それ以上の追跡を必要としない添付ファイルは削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5e804-113">Additionally, it is recommended that you delete attachments that are older than a certain period, and do not require any more investigation.</span></span> <span data-ttu-id="5e804-114">Attachments テーブルには、古い添付ファイルの削除に使用できる `TimeCreated` プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e804-114">The Attachments table contains a `TimeCreated` property that you can use to delete old attachments.</span></span> <span data-ttu-id="5e804-115">このプロセスは、古いダイジェストの削除に使用するプロセスに似ています。</span><span class="sxs-lookup"><span data-stu-id="5e804-115">This process is similar to the process used to delete old digests.</span></span> <span data-ttu-id="5e804-116">サンプル SQL ステートメントがストアド プロシージャの古いダイジェストを削除するには、次を参照してください。[ダイジェストを削除する](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)です。</span><span class="sxs-lookup"><span data-stu-id="5e804-116">For a sample SQL statement for a stored procedure that deletes old digests, see [Deleting Digests](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md).</span></span>  
  
 <span data-ttu-id="5e804-117">また、それぞれの MessageID 列にある Attachments テーブルおよび MessagestoLOB テーブルにはインデックスを付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5e804-117">It is also recommended that you index the Attachments and MessagestoLOB tables on the respective MessageID columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e804-118">参照</span><span class="sxs-lookup"><span data-stu-id="5e804-118">See Also</span></span>  
 [<span data-ttu-id="5e804-119">BTARN データベースの保守</span><span class="sxs-lookup"><span data-stu-id="5e804-119">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)
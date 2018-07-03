---
title: 否認不可データベース テーブルの保守 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases, purging
- databases, non-repudiation database
- maintaining databases, purging
- purging databases
- databases, maintaining
- non-repudiation, database
ms.assetid: 29222510-325b-4cd7-854b-6f548a63fd08
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ceea893a49512167242eb6552e6a23c5a84cd18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966227"
---
# <a name="maintaining-the-non-repudiation-database-tables"></a><span data-ttu-id="a5f91-102">否認不可データベース テーブルの保守</span><span class="sxs-lookup"><span data-stu-id="a5f91-102">Maintaining the Non-Repudiation Database Tables</span></span>
<span data-ttu-id="a5f91-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]否認不可を目的として、BTARNArchive データベースの MessageStorageIn と MessageStorageOut テーブルでのメッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="a5f91-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores messages for non-repudiation purposes in the MessageStorageIn and MessageStorageOut tables of the BTARNArchive database.</span></span> <span data-ttu-id="a5f91-104">これらのテーブルに含まれるメッセージの多くは、システム パフォーマンスに影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5f91-104">Many messages in these tables can affect system performance.</span></span> <span data-ttu-id="a5f91-105">必要に応じてこれらのテーブルから定期的にメッセージを消去およびアーカイブすることにより、これらの否認不可データベース テーブルを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="a5f91-105">You may want to maintain these non-repudiation database tables by periodically purging and archiving messages from these tables, as appropriate.</span></span>  
  
## <a name="routine-database-maintenance"></a><span data-ttu-id="a5f91-106">データベースの定期メンテナンス</span><span class="sxs-lookup"><span data-stu-id="a5f91-106">Routine Database Maintenance</span></span>  
 <span data-ttu-id="a5f91-107">ときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、メッセージが常にメッセージを MessageStorageIn テーブルに保存され、最初に設定、 **ToBePurged**フィールドを「1」は、メッセージが否認不可を必要としないことを示します。</span><span class="sxs-lookup"><span data-stu-id="a5f91-107">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receives a message, it always saves the message in the MessageStorageIn table and initially sets the **ToBePurged** field to "1", which indicates that the message does not require non-repudiation.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="a5f91-108"> 復号化し、アグリーメントが何を決定する、メッセージをデコードします。</span><span class="sxs-lookup"><span data-stu-id="a5f91-108"> then decrypts and decodes the message to determine what the agreement is.</span></span> <span data-ttu-id="a5f91-109">暗号化を解除してデコードした後、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はアグリーメントを調べて、否認不可の目的でメッセージを保存する必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a5f91-109">After decrypting and decoding, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examines the agreement to see whether it must save the message for non-repudiation purposes.</span></span> <span data-ttu-id="a5f91-110">設定する場合、 **ToBePurged**フィールドを「0」と、メッセージの他のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="a5f91-110">If so, it sets the **ToBePurged** field to "0" and fills in the other fields of the message.</span></span> <span data-ttu-id="a5f91-111">ない場合、 **ToBePurged**フィールドを「1」、メッセージの他のフィールドがいっぱいにならないとします。</span><span class="sxs-lookup"><span data-stu-id="a5f91-111">If not, it leaves the **ToBePurged** field as "1" and does not fill in the other fields of the message.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="a5f91-112"> メッセージを自動的に削除されません、 **ToBePurged**フィールドが「1」に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5f91-112"> does not automatically delete messages with the **ToBePurged** field set to "1".</span></span> <span data-ttu-id="a5f91-113">さらに、否認不可の目的で保存されているメッセージは他のテーブルにアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="a5f91-113">In addition, it does not archive messages saved for non-repudiation to other tables.</span></span> <span data-ttu-id="a5f91-114">これら 2 つのメッセージ セットは、MessageStorageIn テーブルに蓄積されるため、パフォーマンスが低下する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5f91-114">These two sets of messages can build up in the MessageStorageIn table and affect performance.</span></span> <span data-ttu-id="a5f91-115">データベースの定期メンテナンスの一環として、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5f91-115">As part of routine maintenance on the database, you may want to do the following:</span></span>  
  
-   <span data-ttu-id="a5f91-116">次の SQL を含むストアド プロシージャを実行ステートメントをすべて削除するメッセージを MessageStorageIn テーブルに持つ**ToBePurged**フィールドは「0」と等しくありません。</span><span class="sxs-lookup"><span data-stu-id="a5f91-116">Run a stored procedure containing the following SQL statement to delete all messages in the MessageStorageIn table whose **ToBePurged** field is not equal to "0":</span></span>  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   <span data-ttu-id="a5f91-117">適切な期間 (期間は会社のポリシーに準拠) が経過したら、ストアド プロシージャを実行して、パフォーマンスに影響しないオフライン データベースに否認不可メッセージをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="a5f91-117">After an appropriate period (which company policy may dictate), run a stored procedure to archive non-repudiation messages to an offline database that will not affect performance.</span></span> <span data-ttu-id="a5f91-118">使用してこの期間を決定することができます、 **TimeCreated** MessageStorageIn テーブルのフィールド。</span><span class="sxs-lookup"><span data-stu-id="a5f91-118">You can determine this period by using the **TimeCreated** field in the MessageStorageIn table.</span></span> <span data-ttu-id="a5f91-119">メッセージの否認不可期間が終了したら、次の SQL ステートメント (8 日以上経過したメッセージを削除するためのステートメント) を使用してアーカイブ データベースからメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="a5f91-119">After the non-repudiation period for a message has expired, you can delete the message from the archive database by using the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="a5f91-120">**TimeCreated** MessageStorageIn テーブル内のフィールドは UTC です。</span><span class="sxs-lookup"><span data-stu-id="a5f91-120">The **TimeCreated** field in the MessageStorageIn table is in UTC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5f91-121">受信後 1 時間が経過していない着信メッセージは削除しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a5f91-121">You should not delete an incoming message that is less than one hour old.</span></span>  
  
 <span data-ttu-id="a5f91-122">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は送信メッセージを送信する際に、否認不可のアグリーメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a5f91-122">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sends an outgoing message, it has access to the non-repudiation agreement.</span></span> <span data-ttu-id="a5f91-123">アグリーメントに否認不可が必要である場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって MessageStorageOut テーブルにメッセージが保存されます。</span><span class="sxs-lookup"><span data-stu-id="a5f91-123">If the agreement requires non-repudiation, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the message in the MessageStorageOut table.</span></span> <span data-ttu-id="a5f91-124">否認不可が必要ない場合、テーブルにメッセージは保存されません。</span><span class="sxs-lookup"><span data-stu-id="a5f91-124">If not, it does not save the message in the table.</span></span> <span data-ttu-id="a5f91-125">つまり、必要はありません、 **ToBePurged**このテーブルのフィールド。</span><span class="sxs-lookup"><span data-stu-id="a5f91-125">This means that there is no need for a **ToBePurged** field in this table.</span></span> <span data-ttu-id="a5f91-126">MessageStorageOut テーブルに対して行うべき唯一の保守作業は、適切な期間経過後に否認不可メッセージをオフライン データベースにアーカイブし、否認不可期間の経過後に各メッセージを削除することです。</span><span class="sxs-lookup"><span data-stu-id="a5f91-126">The only maintenance required for the MessageStorageOut table is to archive non-repudiation messages to an offline database after an appropriate period, and to delete each message after its non-repudiation period has expired.</span></span> <span data-ttu-id="a5f91-127">これは次の SQL ステートメント (8 日以上経過したメッセージを削除するためのステートメント) で実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5f91-127">You can do so with the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5f91-128">参照</span><span class="sxs-lookup"><span data-stu-id="a5f91-128">See Also</span></span>  
 <span data-ttu-id="a5f91-129">[RNIF メッセージの処理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="a5f91-129">[RNIF Message Processing](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span></span>  
 [<span data-ttu-id="a5f91-130">構成、証明書、データベース、セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="a5f91-130">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)
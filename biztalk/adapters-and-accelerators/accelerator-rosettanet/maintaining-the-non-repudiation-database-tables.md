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
ms.openlocfilehash: e6e3ca48850aa06bdcfd392f8411c28a921df77e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283303"
---
# <a name="maintaining-the-non-repudiation-database-tables"></a><span data-ttu-id="06a9e-102">否認不可データベース テーブルの保守</span><span class="sxs-lookup"><span data-stu-id="06a9e-102">Maintaining the Non-Repudiation Database Tables</span></span>
<span data-ttu-id="06a9e-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]否認不可を目的として、BTARNArchive データベースの MessageStorageIn と MessageStorageOut テーブルでのメッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="06a9e-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores messages for non-repudiation purposes in the MessageStorageIn and MessageStorageOut tables of the BTARNArchive database.</span></span> <span data-ttu-id="06a9e-104">これらのテーブルに多数のメッセージ システムのパフォーマンスに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="06a9e-104">Many messages in these tables can affect system performance.</span></span> <span data-ttu-id="06a9e-105">これらの否認不可データベース テーブルを定期的に削除し、必要に応じて、これらのテーブルからメッセージをアーカイブして維持したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="06a9e-105">You may want to maintain these non-repudiation database tables by periodically purging and archiving messages from these tables, as appropriate.</span></span>  
  
## <a name="routine-database-maintenance"></a><span data-ttu-id="06a9e-106">日常的なデータベース メンテナンス</span><span class="sxs-lookup"><span data-stu-id="06a9e-106">Routine Database Maintenance</span></span>  
 <span data-ttu-id="06a9e-107">ときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、メッセージが常にメッセージを MessageStorageIn テーブルに保存され、最初に設定、 **ToBePurged**フィールドを「1」は、メッセージが否認不可を必要としないことを示します。</span><span class="sxs-lookup"><span data-stu-id="06a9e-107">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receives a message, it always saves the message in the MessageStorageIn table and initially sets the **ToBePurged** field to "1", which indicates that the message does not require non-repudiation.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="06a9e-108">復号化し、アグリーメントが何を決定する、メッセージをデコードします。</span><span class="sxs-lookup"><span data-stu-id="06a9e-108">then decrypts and decodes the message to determine what the agreement is.</span></span> <span data-ttu-id="06a9e-109">暗号化を解除して、デコード後[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]否認不可の目的でメッセージを保存する必要があるかどうかを確認するアグリーメントを調べます。</span><span class="sxs-lookup"><span data-stu-id="06a9e-109">After decrypting and decoding, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examines the agreement to see whether it must save the message for non-repudiation purposes.</span></span> <span data-ttu-id="06a9e-110">設定する場合、 **ToBePurged**フィールドを「0」と、メッセージの他のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="06a9e-110">If so, it sets the **ToBePurged** field to "0" and fills in the other fields of the message.</span></span> <span data-ttu-id="06a9e-111">ない場合、 **ToBePurged**フィールドを「1」、メッセージの他のフィールドがいっぱいにならないとします。</span><span class="sxs-lookup"><span data-stu-id="06a9e-111">If not, it leaves the **ToBePurged** field as "1" and does not fill in the other fields of the message.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="06a9e-112">メッセージを自動的に削除されません、 **ToBePurged**フィールドが「1」に設定します。</span><span class="sxs-lookup"><span data-stu-id="06a9e-112">does not automatically delete messages with the **ToBePurged** field set to "1".</span></span> <span data-ttu-id="06a9e-113">さらに、他のテーブルに非否認の保存されたメッセージはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="06a9e-113">In addition, it does not archive messages saved for non-repudiation to other tables.</span></span> <span data-ttu-id="06a9e-114">これら 2 つのメッセージのセットでは、MessageStorageIn テーブルを構築でき、パフォーマンスに影響することができます。</span><span class="sxs-lookup"><span data-stu-id="06a9e-114">These two sets of messages can build up in the MessageStorageIn table and affect performance.</span></span> <span data-ttu-id="06a9e-115">データベースの定期的なメンテナンスの一環として、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="06a9e-115">As part of routine maintenance on the database, you may want to do the following:</span></span>  
  
-   <span data-ttu-id="06a9e-116">次の SQL を含むストアド プロシージャを実行ステートメントをすべて削除するメッセージを MessageStorageIn テーブルに持つ**ToBePurged**フィールドは「0」と等しくありません。</span><span class="sxs-lookup"><span data-stu-id="06a9e-116">Run a stored procedure containing the following SQL statement to delete all messages in the MessageStorageIn table whose **ToBePurged** field is not equal to "0":</span></span>  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   <span data-ttu-id="06a9e-117">(どの会社のポリシーに準拠が) 適切な期間の後にオフライン データベースのパフォーマンスに影響を与えない、否認不可メッセージをアーカイブするストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="06a9e-117">After an appropriate period (which company policy may dictate), run a stored procedure to archive non-repudiation messages to an offline database that will not affect performance.</span></span> <span data-ttu-id="06a9e-118">使用してこの期間を決定することができます、 **TimeCreated** MessageStorageIn テーブルのフィールド。</span><span class="sxs-lookup"><span data-stu-id="06a9e-118">You can determine this period by using the **TimeCreated** field in the MessageStorageIn table.</span></span> <span data-ttu-id="06a9e-119">メッセージの否認不可期間の期限が切れた後は、(7 日間よりも古いメッセージを削除) する次の SQL ステートメントを使用して、アーカイブ データベースからメッセージを削除できます。</span><span class="sxs-lookup"><span data-stu-id="06a9e-119">After the non-repudiation period for a message has expired, you can delete the message from the archive database by using the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="06a9e-120">**TimeCreated** MessageStorageIn テーブル内のフィールドは UTC です。</span><span class="sxs-lookup"><span data-stu-id="06a9e-120">The **TimeCreated** field in the MessageStorageIn table is in UTC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06a9e-121">1 時間未満前である受信メッセージを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="06a9e-121">You should not delete an incoming message that is less than one hour old.</span></span>  
  
 <span data-ttu-id="06a9e-122">ときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、送信メッセージの送信、否認不可のアグリーメントにアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="06a9e-122">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sends an outgoing message, it has access to the non-repudiation agreement.</span></span> <span data-ttu-id="06a9e-123">契約書、否認が必要な場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]MessageStorageOut テーブルにメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="06a9e-123">If the agreement requires non-repudiation, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the message in the MessageStorageOut table.</span></span> <span data-ttu-id="06a9e-124">それ以外の場合は、表に、メッセージは保存されません。</span><span class="sxs-lookup"><span data-stu-id="06a9e-124">If not, it does not save the message in the table.</span></span> <span data-ttu-id="06a9e-125">つまり、必要はありません、 **ToBePurged**このテーブルのフィールド。</span><span class="sxs-lookup"><span data-stu-id="06a9e-125">This means that there is no need for a **ToBePurged** field in this table.</span></span> <span data-ttu-id="06a9e-126">MessageStorageOut テーブルに必要な唯一の保守作業は、後、適切な期間にわたってオフラインのデータベースに否認不可メッセージをアーカイブして、否認不可期間の後に各メッセージを削除する有効期限が切れた。</span><span class="sxs-lookup"><span data-stu-id="06a9e-126">The only maintenance required for the MessageStorageOut table is to archive non-repudiation messages to an offline database after an appropriate period, and to delete each message after its non-repudiation period has expired.</span></span> <span data-ttu-id="06a9e-127">(7 日間よりも古いメッセージを削除) する次の SQL ステートメントを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="06a9e-127">You can do so with the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a><span data-ttu-id="06a9e-128">参照</span><span class="sxs-lookup"><span data-stu-id="06a9e-128">See Also</span></span>  
 <span data-ttu-id="06a9e-129">[RNIF メッセージの処理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="06a9e-129">[RNIF Message Processing](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span></span>  
 [<span data-ttu-id="06a9e-130">構成、証明書、データベース、セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="06a9e-130">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)
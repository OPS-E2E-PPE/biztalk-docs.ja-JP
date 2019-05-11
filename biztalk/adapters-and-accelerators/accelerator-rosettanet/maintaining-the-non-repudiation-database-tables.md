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
# <a name="maintaining-the-non-repudiation-database-tables"></a>否認不可データベース テーブルの保守
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]否認不可を目的として、BTARNArchive データベースの MessageStorageIn と MessageStorageOut テーブルでのメッセージを格納します。 これらのテーブルに多数のメッセージ システムのパフォーマンスに影響を与えることができます。 これらの否認不可データベース テーブルを定期的に削除し、必要に応じて、これらのテーブルからメッセージをアーカイブして維持したい場合があります。  
  
## <a name="routine-database-maintenance"></a>日常的なデータベース メンテナンス  
 ときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、メッセージが常にメッセージを MessageStorageIn テーブルに保存され、最初に設定、 **ToBePurged**フィールドを「1」は、メッセージが否認不可を必要としないことを示します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 復号化し、アグリーメントが何を決定する、メッセージをデコードします。 暗号化を解除して、デコード後[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]否認不可の目的でメッセージを保存する必要があるかどうかを確認するアグリーメントを調べます。 設定する場合、 **ToBePurged**フィールドを「0」と、メッセージの他のフィールドに入力します。 ない場合、 **ToBePurged**フィールドを「1」、メッセージの他のフィールドがいっぱいにならないとします。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] メッセージを自動的に削除されません、 **ToBePurged**フィールドが「1」に設定します。 さらに、他のテーブルに非否認の保存されたメッセージはアーカイブされません。 これら 2 つのメッセージのセットでは、MessageStorageIn テーブルを構築でき、パフォーマンスに影響することができます。 データベースの定期的なメンテナンスの一環として、以下を実行します。  
  
-   次の SQL を含むストアド プロシージャを実行ステートメントをすべて削除するメッセージを MessageStorageIn テーブルに持つ**ToBePurged**フィールドは「0」と等しくありません。  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   (どの会社のポリシーに準拠が) 適切な期間の後にオフライン データベースのパフォーマンスに影響を与えない、否認不可メッセージをアーカイブするストアド プロシージャを実行します。 使用してこの期間を決定することができます、 **TimeCreated** MessageStorageIn テーブルのフィールド。 メッセージの否認不可期間の期限が切れた後は、(7 日間よりも古いメッセージを削除) する次の SQL ステートメントを使用して、アーカイブ データベースからメッセージを削除できます。  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  **TimeCreated** MessageStorageIn テーブル内のフィールドは UTC です。  
  
> [!NOTE]
>  1 時間未満前である受信メッセージを削除しないでください。  
  
 ときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、送信メッセージの送信、否認不可のアグリーメントにアクセス権があります。 契約書、否認が必要な場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]MessageStorageOut テーブルにメッセージを保存します。 それ以外の場合は、表に、メッセージは保存されません。 つまり、必要はありません、 **ToBePurged**このテーブルのフィールド。 MessageStorageOut テーブルに必要な唯一の保守作業は、後、適切な期間にわたってオフラインのデータベースに否認不可メッセージをアーカイブして、否認不可期間の後に各メッセージを削除する有効期限が切れた。 (7 日間よりも古いメッセージを削除) する次の SQL ステートメントを使用して行うことができます。  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a>参照  
 [RNIF メッセージの処理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md)   
 [構成、証明書、データベース、セキュリティの管理](manage-configuration-certificates-databases-security.md)
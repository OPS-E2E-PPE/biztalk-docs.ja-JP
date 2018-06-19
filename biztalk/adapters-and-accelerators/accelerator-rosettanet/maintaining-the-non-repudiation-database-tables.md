---
title: 否認不可データベース テーブルの保守 |Microsoft ドキュメント
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
ms.openlocfilehash: 182172eccddcaad684f35335708dce6027fb111f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210610"
---
# <a name="maintaining-the-non-repudiation-database-tables"></a>否認不可データベース テーブルの保守
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]否認不可を目的として、BTARNArchive データベースの MessageStorageIn と MessageStorageOut テーブルでのメッセージを格納します。 これらのテーブルに含まれるメッセージの多くは、システム パフォーマンスに影響する場合があります。 必要に応じてこれらのテーブルから定期的にメッセージを消去およびアーカイブすることにより、これらの否認不可データベース テーブルを維持することができます。  
  
## <a name="routine-database-maintenance"></a>データベースの定期メンテナンス  
 ときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]がメッセージを受信が常にメッセージを MessageStorageIn テーブルに保存され、最初に設定、 **ToBePurged**  フィールドを「1」は、メッセージが否認不可を必要がないことを示します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]復号化し、アグリーメントを確認するメッセージをデコードします。 暗号化を解除してデコードした後、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はアグリーメントを調べて、否認不可の目的でメッセージを保存する必要があるかどうかを判断します。 設定する場合、 **ToBePurged**フィールドを「0」と、メッセージの他のフィールドに入力します。 場合は、外に出て、 **ToBePurged**フィールドを「1」、メッセージの他のフィールドがいっぱいにならないとします。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]持つメッセージを自動的に削除されない、 **ToBePurged**フィールドが「1」に設定します。 さらに、否認不可の目的で保存されているメッセージは他のテーブルにアーカイブされません。 これら 2 つのメッセージ セットは、MessageStorageIn テーブルに蓄積されるため、パフォーマンスが低下する場合があります。 データベースの定期メンテナンスの一環として、次の操作を行う必要があります。  
  
-   次の SQL を含むストアド プロシージャを実行をすべて削除するステートメントにメッセージを MessageStorageIn テーブルが**ToBePurged**フィールドが「0」と等しくないです。  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   適切な期間 (期間は会社のポリシーに準拠) が経過したら、ストアド プロシージャを実行して、パフォーマンスに影響しないオフライン データベースに否認不可メッセージをアーカイブします。 使用して、この期間を指定できます、 **TimeCreated** MessageStorageIn テーブルにフィールドです。 メッセージの否認不可期間が終了したら、次の SQL ステートメント (8 日以上経過したメッセージを削除するためのステートメント) を使用してアーカイブ データベースからメッセージを削除します。  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  **TimeCreated** MessageStorageIn テーブル内のフィールドは UTC です。  
  
> [!NOTE]
>  受信後 1 時間が経過していない着信メッセージは削除しないようにしてください。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は送信メッセージを送信する際に、否認不可のアグリーメントにアクセスできます。 アグリーメントに否認不可が必要である場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって MessageStorageOut テーブルにメッセージが保存されます。 否認不可が必要ない場合、テーブルにメッセージは保存されません。 つまりの必要性がないこと、 **ToBePurged**このテーブルのフィールドです。 MessageStorageOut テーブルに対して行うべき唯一の保守作業は、適切な期間経過後に否認不可メッセージをオフライン データベースにアーカイブし、否認不可期間の経過後に各メッセージを削除することです。 これは次の SQL ステートメント (8 日以上経過したメッセージを削除するためのステートメント) で実行できます。  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a>参照  
 [RNIF メッセージの処理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md)   
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)
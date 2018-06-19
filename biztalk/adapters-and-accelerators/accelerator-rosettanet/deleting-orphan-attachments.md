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
# <a name="deleting-orphan-attachments"></a>孤立した添付ファイルを削除します。
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信メッセージの添付ファイルを格納します。 特定の状況で[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、添付ファイルを保存しますが、孤立した添付ファイルに結果として得られる、MessagesToLOB テーブルから関連するメッセージを削除します。 添付ファイルがある、マニフェストが無効な場合、メッセージ NumberOfAttachments に、マニフェストなどを送信するときに発生する可能性がこの 0 を = です。 定期的に、システムのパフォーマンスを維持するために孤立した添付ファイルを削除することがあります。  
  
## <a name="how-to-delete-orphan-attachments"></a>孤立した添付ファイルを削除する方法  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]添付ファイルを BTARNDATA データベースの Attachments テーブルに格納します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]関連するメッセージを MessagesToLOB テーブルに格納します。 孤立添付ファイルは、添付ファイルの `outMessageID` プロパティが、MessagesToLOB テーブル内に格納されているメッセージの `MessageID` プロパティと対応しない場合に発生します。  
  
 MessagesToLOB テーブル内に対応するメッセージがない添付ファイルだけを削除するストアド プロシージャを使用して、定期的にテーブルから添付ファイルを削除することができます。 ストアド プロシージャのサンプル SQL ステートメントは次のとおりです。  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 さらに、特定の期間より古く、それ以上の追跡を必要としない添付ファイルは削除することをお勧めします。 Attachments テーブルには、古い添付ファイルの削除に使用できる `TimeCreated` プロパティが含まれています。 このプロセスは、古いダイジェストの削除に使用するプロセスに似ています。 サンプル SQL ステートメントがストアド プロシージャの古いダイジェストを削除するには、次を参照してください。[ダイジェストを削除する](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)です。  
  
 また、それぞれの MessageID 列にある Attachments テーブルおよび MessagestoLOB テーブルにはインデックスを付けることをお勧めします。  
  
## <a name="see-also"></a>参照  
 [BTARN データベースの保守](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)
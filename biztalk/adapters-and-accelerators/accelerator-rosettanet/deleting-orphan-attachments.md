---
title: 孤立した添付ファイルの削除 |Microsoft Docs
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
ms.openlocfilehash: 99b31633c27aaed7cb8ae7289f383a5bfcac8d1b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971891"
---
# <a name="deleting-orphan-attachments"></a>孤立した添付ファイルを削除します。
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信するメッセージの添付ファイルを格納します。 特定の状況で[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、添付ファイルを保存しますが、孤立した添付ファイルに生成される、MessagesToLOB テーブルから関連するメッセージを削除します。 個の添付ファイルをマニフェストが無効なメッセージ numberofattachments マニフェストなどを送信するときに発生する可能性がこの 0 を = です。 定期的に、システムのパフォーマンスを維持するために孤立した添付ファイルを削除することがあります。  
  
## <a name="how-to-delete-orphan-attachments"></a>孤立した添付ファイルを削除する方法  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 添付ファイルを BTARNDATA データベースの Attachments テーブルに格納します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 関連付けられているメッセージを MessagesToLOB テーブルに格納します。 孤立添付ファイルは、添付ファイルの `outMessageID` プロパティが、MessagesToLOB テーブル内に格納されているメッセージの `MessageID` プロパティと対応しない場合に発生します。  
  
 MessagesToLOB テーブル内に対応するメッセージがない添付ファイルだけを削除するストアド プロシージャを使用して、定期的にテーブルから添付ファイルを削除することができます。 ストアド プロシージャのサンプル SQL ステートメントは次のとおりです。  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 さらに、特定の期間より古く、それ以上の追跡を必要としない添付ファイルは削除することをお勧めします。 Attachments テーブルには、古い添付ファイルの削除に使用できる `TimeCreated` プロパティが含まれています。 このプロセスは、古いダイジェストの削除に使用するプロセスに似ています。 古いダイジェストを削除するストアド プロシージャのサンプル SQL ステートメントの場合、次を参照してください。[ダイジェストを削除する](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)します。  
  
 また、それぞれの MessageID 列にある Attachments テーブルおよび MessagestoLOB テーブルにはインデックスを付けることをお勧めします。  
  
## <a name="see-also"></a>参照  
 [BTARN データベースの保守](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)
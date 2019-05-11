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
# <a name="deleting-digests"></a>ダイジェストの削除
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]シグナル コンテンツと突き合わせて検証できますので、送信メッセージのダイジェストが格納されます。 ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]検証後に、ダイジェストは削除されません。 定期的に、システムのパフォーマンスを維持するためにこれらのダイジェストを削除することがあります。  
  
## <a name="when-and-how-to-delete-digests"></a>ダイジェストを削除するタイミングと方法  
 ダイジェストは、BTARNDATA データベースの MessageDigestHelper テーブルに格納されます。 定期的に、一定期間以上経過したダイジェストだけを削除するストアド プロシージャを使用して、テーブルからこれらのダイジェストを削除します。 MessageDigestHelper テーブルが含まれています、`TimeCreated`プロパティをこの目的で使用することができます。  
  
 (変更されたため、)、次の SQL ステートメントを使用してストアド プロシージャを作成し、古いダイジェストを削除するストアド プロシージャを実行します。 このサンプル ステートメントは、7 日以上経過したすべてのダイジェストを削除します。  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  ストアド プロシージャの呼び出しを含める必要があります`getutcdate`ではなく、`getdate`ため、すべて[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース UTC (Universal Time Coordinate) 時刻を使用します。  
  
## <a name="see-also"></a>参照  
 [BTARN データベースの保守](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)
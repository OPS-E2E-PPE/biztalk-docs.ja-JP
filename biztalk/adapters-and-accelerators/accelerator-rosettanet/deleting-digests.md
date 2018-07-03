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
ms.openlocfilehash: 10e32f8d86d6723965e8a27ad51f7551fdda0b60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002403"
---
# <a name="deleting-digests"></a>ダイジェストの削除
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]シグナル コンテンツと突き合わせて検証できますので、送信メッセージのダイジェストが格納されます。 ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]検証後に、ダイジェストは削除されません。 定期的にこれらのダイジェストを削除して、システム パフォーマンスを維持する必要があります。  
  
## <a name="when-and-how-to-delete-digests"></a>ダイジェストを削除する間隔と削除方法  
 ダイジェストは、BTARNDATA データベースの MessageDigestHelper テーブルに格納されます。 特定の期間以上経過したダイジェストだけを削除するストアド プロシージャを使用して、これらのダイジェストをテーブルから定期的に削除する必要があります。 MessageDigestHelper テーブルには、この目的のために使用する `TimeCreated` プロパティが含まれています。  
  
 (変更されたため、)、次の SQL ステートメントを使用してストアド プロシージャを作成し、古いダイジェストを削除するストアド プロシージャを実行します。 このサンプル ステートメントでは、8 日以上経過したすべてのダイジェストが削除されます。  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  ストアド プロシージャの呼び出しを含める必要があります`getutcdate`ではなく、`getdate`ため、すべて[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース UTC (Universal Time Coordinate) 時刻を使用します。  
  
## <a name="see-also"></a>参照  
 [BTARN データベースの保守](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)
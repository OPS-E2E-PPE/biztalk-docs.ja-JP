---
title: ダイジェストの削除 |Microsoft ドキュメント
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
ms.openlocfilehash: fefa59a7638b7dc4627d5d7a019d753b4f6290b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206746"
---
# <a name="deleting-digests"></a>ダイジェストの削除
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]シグナル コンテンツとそれらを検証できるように、送信メッセージのダイジェストが格納されます。 ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]検証後に、ダイジェストは削除されません。 定期的にこれらのダイジェストを削除して、システム パフォーマンスを維持する必要があります。  
  
## <a name="when-and-how-to-delete-digests"></a>ダイジェストを削除する間隔と削除方法  
 ダイジェストは、BTARNDATA データベースの MessageDigestHelper テーブルに格納されます。 特定の期間以上経過したダイジェストだけを削除するストアド プロシージャを使用して、これらのダイジェストをテーブルから定期的に削除する必要があります。 MessageDigestHelper テーブルには、この目的のために使用する `TimeCreated` プロパティが含まれています。  
  
 (として変更の目的で)、次の SQL ステートメントを使用してストアド プロシージャを作成し、古いダイジェストを削除するストアド プロシージャを実行します。 このサンプル ステートメントでは、8 日以上経過したすべてのダイジェストが削除されます。  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  ストアド プロシージャへの呼び出しを含める必要があります`getutcdate`ではなく、`getdate`ため、すべて[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース UTC (協定世界時) の時刻を使用します。  
  
## <a name="see-also"></a>参照  
 [BTARN データベースの保守](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)
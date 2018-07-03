---
title: BTARN データベースの保守 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maintaining databases
- databases, maintaining
ms.assetid: b048f68c-1e12-42e3-b7bb-2a87fe977f4e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 496e83311c4ede6446bad8893fbe37b22cf8420d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000771"
---
# <a name="maintaining-btarn-databases"></a>BTARN データベースの保守
Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]データベースの規模が大きいため、サイズがシステム パフォーマンスに影響する拡張可能です。 これは、孤立した添付ファイルや未使用のダイジェストなど、使用されないエントリがテーブルに残っているためです。 テーブルの古いエントリが削除されていないことが原因の場合もあります。 このセクションの手順に従って [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] データベースの保守を行い、パフォーマンスに影響が出ないようにしてください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [否認不可データベース テーブルの保守](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-the-non-repudiation-database-tables.md)  
  
-   [ダイジェストの削除](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)  
  
-   [孤立した添付ファイルの削除](../../adapters-and-accelerators/accelerator-rosettanet/deleting-orphan-attachments.md)
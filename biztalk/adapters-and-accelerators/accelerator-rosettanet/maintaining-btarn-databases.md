---
title: "BTARN データベースの保守 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maintaining databases
- databases, maintaining
ms.assetid: b048f68c-1e12-42e3-b7bb-2a87fe977f4e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ba898931c4fe295c90d6eb94cad60b69d0910d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="maintaining-btarn-databases"></a>BTARN データベースの保守
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] のデータベースは、サイズが大きくなりすぎてシステム パフォーマンスが低下することがあります。 これは、孤立した添付ファイルや未使用のダイジェストなど、使用されないエントリがテーブルに残っているためです。 テーブルの古いエントリが削除されていないことが原因の場合もあります。 このセクションの手順に従って [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] データベースの保守を行い、パフォーマンスに影響が出ないようにしてください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [否認不可データベース テーブルの保守](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-the-non-repudiation-database-tables.md)  
  
-   [ダイジェストの削除](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)  
  
-   [孤立した添付ファイルを削除します。](../../adapters-and-accelerators/accelerator-rosettanet/deleting-orphan-attachments.md)
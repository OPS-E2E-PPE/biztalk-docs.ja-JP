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
ms.openlocfilehash: 09cfcebd3acd4a8b744bd14095f681f69e0c5e9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283271"
---
# <a name="maintaining-btarn-databases"></a><span data-ttu-id="10db4-102">BTARN データベースの保守</span><span class="sxs-lookup"><span data-stu-id="10db4-102">Maintaining BTARN Databases</span></span>
<span data-ttu-id="10db4-103">Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]データベースの規模が大きいため、サイズがシステム パフォーマンスに影響する拡張可能です。</span><span class="sxs-lookup"><span data-stu-id="10db4-103">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] databases can grow so large that their size can affect system performance.</span></span> <span data-ttu-id="10db4-104">これにより、孤立した添付ファイルや未使用のダイジェストなど、テーブルに含まれる未使用エントリのままにする特定の状況から。</span><span class="sxs-lookup"><span data-stu-id="10db4-104">This can result from specific circumstances that leave unused entries in the tables, such as orphan attachments or unused digests.</span></span> <span data-ttu-id="10db4-105">テーブルの古いエントリが削除されていないにも発生します。</span><span class="sxs-lookup"><span data-stu-id="10db4-105">It can also occur from not deleting old entries in the tables.</span></span> <span data-ttu-id="10db4-106">維持するためには、このセクションの手順に従って、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データベースのパフォーマンスに影響がありません。</span><span class="sxs-lookup"><span data-stu-id="10db4-106">Follow the procedures in this section to maintain your [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] databases so there is no effect on performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10db4-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="10db4-107">In This Section</span></span>  
  
-   [<span data-ttu-id="10db4-108">否認不可データベース テーブルの保守</span><span class="sxs-lookup"><span data-stu-id="10db4-108">Maintaining the Non-Repudiation Database Tables</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-the-non-repudiation-database-tables.md)  
  
-   [<span data-ttu-id="10db4-109">ダイジェストの削除</span><span class="sxs-lookup"><span data-stu-id="10db4-109">Deleting Digests</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)  
  
-   [<span data-ttu-id="10db4-110">孤立した添付ファイルの削除</span><span class="sxs-lookup"><span data-stu-id="10db4-110">Deleting Orphan Attachments</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/deleting-orphan-attachments.md)
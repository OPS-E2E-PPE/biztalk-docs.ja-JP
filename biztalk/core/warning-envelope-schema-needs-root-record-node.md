---
title: 警告 - エンベロープ スキーマには、ルート レコード ノードが必要です |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.envelopeSchemaNeedsRoot
ms.assetid: 3fbc1571-1270-4c5e-adcf-00633bf46efe
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4869a5a346e49d7febbccb628799430922dd8cb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393689"
---
# <a name="warning---envelope-schema-needs-root-record-node"></a><span data-ttu-id="ab0b2-102">警告 - エンベロープ スキーマには、ルート レコード ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="ab0b2-102">Warning - Envelope Schema Needs Root Record Node</span></span>
<span data-ttu-id="ab0b2-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="ab0b2-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ab0b2-104">BEC1010</span><span class="sxs-lookup"><span data-stu-id="ab0b2-104">BEC1010</span></span>  
  
 <span data-ttu-id="ab0b2-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="ab0b2-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ab0b2-106">エンベロープ スキーマは、少なくとも 1 つのルートに必要な**レコード**ノードの子としてその**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="ab0b2-106">Envelope schemas are required to have at least one root **Record** node as a child of its **Schema** node.</span></span>  
  
 <span data-ttu-id="ab0b2-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="ab0b2-107">**User Action**</span></span>  
  
 <span data-ttu-id="ab0b2-108">右クリックし、**スキーマ**ノード、をクリックして**子レコードの挿入**、挿入のわかりやすい名前を入力し、ショートカット メニューで**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="ab0b2-108">Right-click the **Schema** node, click **Insert Child Record** on the shortcut menu, and then type a descriptive name for the inserted **Record** node.</span></span> <span data-ttu-id="ab0b2-109">一般に、エンベロープ スキーマは、ルート内に挿入される追加のノードもあります**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="ab0b2-109">In general, envelope schemas will also have additional nodes inserted within the root **Record** node.</span></span>
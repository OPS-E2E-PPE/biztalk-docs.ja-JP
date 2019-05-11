---
title: エラー - プロパティ スキーマの構造が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.propSchemaStructNotValid<
ms.assetid: c5fd81a7-fa5a-4ec2-b895-00b280aca227
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbb305980357fba6c874ba816e6d942e4ba9a231
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388489"
---
# <a name="error---property-schema-structure-not-valid"></a><span data-ttu-id="a6239-102">エラー - プロパティ スキーマの構造が無効です。</span><span class="sxs-lookup"><span data-stu-id="a6239-102">Error - Property Schema Structure Not Valid</span></span>
<span data-ttu-id="a6239-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="a6239-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a6239-104">BEC2007</span><span class="sxs-lookup"><span data-stu-id="a6239-104">BEC2007</span></span>  
  
 <span data-ttu-id="a6239-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="a6239-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a6239-106">このプロパティ スキーマは、無効な構造を持つが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a6239-106">This property schema was found to have a structure that is not valid.</span></span> <span data-ttu-id="a6239-107">プロパティ スキーマの構造は 1 つ以上に制限されます**フィールド要素**ノードの子として、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="a6239-107">The structure of property schemas is limited to one or more **Field Element** nodes as children of the **Schema** node.</span></span>  
  
 <span data-ttu-id="a6239-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="a6239-108">**User Action**</span></span>  
  
 <span data-ttu-id="a6239-109">このプロパティ スキーマの構造を修正できるように、**スキーマ**ノードしか**フィールド要素**の子ノード。</span><span class="sxs-lookup"><span data-stu-id="a6239-109">Correct the structure of this property schema so that the **Schema** node only has **Field Element** nodes as children.</span></span>
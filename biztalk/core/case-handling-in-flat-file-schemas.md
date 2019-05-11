---
title: フラット ファイル スキーマにおける処理の場合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f2b56d2-03fa-41e9-ae28-3275b404d4db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4103b9f133ffac16b967832325effefba04b5ab2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357606"
---
# <a name="case-handling-in-flat-file-schemas"></a><span data-ttu-id="d7c77-102">ケースのフラット ファイル スキーマの処理</span><span class="sxs-lookup"><span data-stu-id="d7c77-102">Case Handling in Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="d7c77-103">概要</span><span class="sxs-lookup"><span data-stu-id="d7c77-103">Overview</span></span>
<span data-ttu-id="d7c77-104">使用することができます、**ケース**プロパティを XML 形式から変換時に、フラット ファイル データの大文字/小文字の変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7c77-104">You can use the **Case** property to perform case conversion of flat file data when being translated from its equivalent XML format.</span></span> <span data-ttu-id="d7c77-105">フラット ファイル アセンブラーが XML メッセージをその同等のフラット ファイル形式に変換するとき、**ケース**プロパティがいずれかに**大文字**または**小文字**、すべてのデータによって、対応する制御スキーマには、変換時に、それぞれ大文字または小文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="d7c77-105">When the flat file assembler translates an XML message into its equivalent flat file format, and the **Case** property is set to either **Uppercase** or **Lowercase**, all data governed by the corresponding schema will be converted to uppercase or lowercase, respectively, during the translation.</span></span>  
  
 <span data-ttu-id="d7c77-106">ときに、**ケース**プロパティに設定されて **(既定)**、大文字と小文字の変換は行われません。</span><span class="sxs-lookup"><span data-stu-id="d7c77-106">When the **Case** property is set to **(Default)**, no case conversion is performed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c77-107">参照</span><span class="sxs-lookup"><span data-stu-id="d7c77-107">See Also</span></span>  
 <span data-ttu-id="d7c77-108">**ファイル メッセージ スキーマをフラットを作成する際の考慮事項**と**ケース (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="d7c77-108">**Considerations When Creating Flat File Message Schemas** and **Case (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
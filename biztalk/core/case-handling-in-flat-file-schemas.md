---
title: "フラット ファイル スキーマでの処理をケース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f2b56d2-03fa-41e9-ae28-3275b404d4db
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2312f00a6dab18fa92c0fed05c5c9fa182d500f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="case-handling-in-flat-file-schemas"></a><span data-ttu-id="46199-102">フラット ファイル スキーマでの処理の場合</span><span class="sxs-lookup"><span data-stu-id="46199-102">Case Handling in Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="46199-103">概要</span><span class="sxs-lookup"><span data-stu-id="46199-103">Overview</span></span>
<span data-ttu-id="46199-104">使用することができます、**ケース**プロパティと同等の XML 形式から変換されているときに、フラット ファイル データの大文字/小文字の変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="46199-104">You can use the **Case** property to perform case conversion of flat file data when being translated from its equivalent XML format.</span></span> <span data-ttu-id="46199-105">フラット ファイル アセンブラー、XML メッセージを同等のフラット ファイル形式に変換されるときに、**ケース**プロパティに設定されている**大文字**または**小文字**、すべてのデータ対応する制約を受けるスキーマには、変換中にそれぞれ、大文字または小文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="46199-105">When the flat file assembler translates an XML message into its equivalent flat file format, and the **Case** property is set to either **Uppercase** or **Lowercase**, all data governed by the corresponding schema will be converted to uppercase or lowercase, respectively, during the translation.</span></span>  
  
 <span data-ttu-id="46199-106">ときに、**ケース**プロパティに設定されている**(既定)**、大文字/小文字変換は行われません。</span><span class="sxs-lookup"><span data-stu-id="46199-106">When the **Case** property is set to **(Default)**, no case conversion is performed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46199-107">参照</span><span class="sxs-lookup"><span data-stu-id="46199-107">See Also</span></span>  
 <span data-ttu-id="46199-108">**ファイル メッセージ スキーマをフラットを作成する際の考慮事項**と**ケース (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="46199-108">**Considerations When Creating Flat File Message Schemas** and **Case (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
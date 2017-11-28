---
title: "区切られたレコードの考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f93dd94-6ab1-4ae0-801d-e44e722d6f09
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc6cbd642717b485a1be5cefab07f6a8298d638a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="delimited-record-considerations"></a><span data-ttu-id="8ff67-102">区切り記号付きレコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="8ff67-102">Delimited Record Considerations</span></span>
<span data-ttu-id="8ff67-103">おかなければならないことに注意を操作するときに区切り記号付きの考慮事項の数がある**レコード**スキーマ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="8ff67-103">There are a number of considerations that you should keep in mind when working with delimited **Record** nodes within your schemas.</span></span> <span data-ttu-id="8ff67-104">注意事項には、区切り記号に関連した下位ノードの順序、フラット ファイル形式のメッセージをアセンブルするときに区切り記号を省略してよいかどうかの判断、区切り記号付きレコードと位置指定レコードを混在させる際の制約などがあります。</span><span class="sxs-lookup"><span data-stu-id="8ff67-104">This includes the considerations about the order of subordinate nodes relative to their delimiters, cases in which you can choose to omit delimiters when assembling the flat file representation of a message, and restrictions regarding the intermixing of delimited and positional records.</span></span> <span data-ttu-id="8ff67-105">このセクションでは、これらの注意事項に関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ff67-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ff67-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8ff67-106">In This Section</span></span>  
  
-   [<span data-ttu-id="8ff67-107">区切られたレコードのタグ処理</span><span class="sxs-lookup"><span data-stu-id="8ff67-107">Tag Handling in Delimited Records</span></span>](../core/tag-handling-in-delimited-records.md)  
  
-   [<span data-ttu-id="8ff67-108">子の順序に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="8ff67-108">Child Order Considerations</span></span>](../core/child-order-considerations.md)  
  
-   [<span data-ttu-id="8ff67-109">区切り記号の保存および非表示</span><span class="sxs-lookup"><span data-stu-id="8ff67-109">Delimiter Preservation and Suppression</span></span>](../core/delimiter-preservation-and-suppression.md)
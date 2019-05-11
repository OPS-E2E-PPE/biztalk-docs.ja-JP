---
title: 区切りのレコードの考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f93dd94-6ab1-4ae0-801d-e44e722d6f09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98c42d1307340dfad47933fbe1e9bfcc1c2256dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352186"
---
# <a name="delimited-record-considerations"></a><span data-ttu-id="a3ba6-102">区切り記号付きレコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="a3ba6-102">Delimited Record Considerations</span></span>
<span data-ttu-id="a3ba6-103">おく必要がありますに注意を使用する場合で区切られた考慮事項がいくつか**レコード**スキーマ内のノード。</span><span class="sxs-lookup"><span data-stu-id="a3ba6-103">There are a number of considerations that you should keep in mind when working with delimited **Record** nodes within your schemas.</span></span> <span data-ttu-id="a3ba6-104">これにより、その区切り記号の場合、メッセージのフラット ファイル表現をアセンブルするときに、区切り記号を省略することもでき、の混在に関する制限事項が区切られた関連した下位ノードの順序に関する考慮事項が含まれます。位置指定レコード。</span><span class="sxs-lookup"><span data-stu-id="a3ba6-104">This includes the considerations about the order of subordinate nodes relative to their delimiters, cases in which you can choose to omit delimiters when assembling the flat file representation of a message, and restrictions regarding the intermixing of delimited and positional records.</span></span> <span data-ttu-id="a3ba6-105">このセクションでは、これらの考慮事項についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a3ba6-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3ba6-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a3ba6-106">In This Section</span></span>  
  
-   [<span data-ttu-id="a3ba6-107">区切られたレコードのタグ処理</span><span class="sxs-lookup"><span data-stu-id="a3ba6-107">Tag Handling in Delimited Records</span></span>](../core/tag-handling-in-delimited-records.md)  
  
-   [<span data-ttu-id="a3ba6-108">子の順序に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="a3ba6-108">Child Order Considerations</span></span>](../core/child-order-considerations.md)  
  
-   [<span data-ttu-id="a3ba6-109">区切り記号の保存および非表示</span><span class="sxs-lookup"><span data-stu-id="a3ba6-109">Delimiter Preservation and Suppression</span></span>](../core/delimiter-preservation-and-suppression.md)
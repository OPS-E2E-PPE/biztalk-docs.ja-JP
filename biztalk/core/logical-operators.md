---
title: "論理演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8aaceb64-a5a0-462a-a0eb-8352bed999e5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3b3c187e353babafd86590fdeacdc19fc115b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="logical-operators"></a><span data-ttu-id="1ad4f-102">論理演算子</span><span class="sxs-lookup"><span data-stu-id="1ad4f-102">Logical Operators</span></span>
<span data-ttu-id="1ad4f-103">ビジネス ルール フレームワークは、ビジネス ルールを作成する際の論理演算子の AND、OR、および NOT の使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-103">The Business Rules Framework supports using the logical AND, logical OR, and logical NOT operators in creating business rules.</span></span> <span data-ttu-id="1ad4f-104">次の表では、論理演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-104">The following table describes the logical operators.</span></span>  
  
|<span data-ttu-id="1ad4f-105">論理演算子</span><span class="sxs-lookup"><span data-stu-id="1ad4f-105">Logical Operator</span></span>|<span data-ttu-id="1ad4f-106">Description</span><span class="sxs-lookup"><span data-stu-id="1ad4f-106">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="1ad4f-107">**AND**</span><span class="sxs-lookup"><span data-stu-id="1ad4f-107">**AND**</span></span>|<span data-ttu-id="1ad4f-108">返します**true**に両方のオペランドが評価される場合**true**; を返しますそれ以外の場合**false**です。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-108">Returns **true** if both the operands evaluate to **true**; otherwise returns **false**.</span></span>|  
|<span data-ttu-id="1ad4f-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="1ad4f-109">**OR**</span></span>|<span data-ttu-id="1ad4f-110">返します**true**に評価されると、オペランドの 1 つ**true**、それ以外の場合**false**です。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-110">Returns **true** if one of the operands evaluates to **true**, otherwise returns **false**.</span></span>|  
|<span data-ttu-id="1ad4f-111">**NOT**</span><span class="sxs-lookup"><span data-stu-id="1ad4f-111">**NOT**</span></span>|<span data-ttu-id="1ad4f-112">返します**true**にオペランドが評価された場合**false**、それ以外の場合を返します**false**です。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-112">Returns **true** if the operand evaluates to **false**, otherwise returns **false**.</span></span>|  
  
 <span data-ttu-id="1ad4f-113">オペランドが異なる型である場合は、式の評価の前に、ルール エンジンによって 1 つのパラメーターの型がもう 1 つのパラメーターの型と一致するように変換されるか、両方のパラメーターの型が共通の型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-113">When operands are of different types, the rule engine converts type of one of the parameters to match the type of the other parameter or converts types of both the parameters to a common type before evaluating the expression.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="1ad4f-114">ビジネス ルールで論理演算子を使用するには</span><span class="sxs-lookup"><span data-stu-id="1ad4f-114">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="1ad4f-115">ビジネス ルールで論理演算子を使用するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-115">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="1ad4f-116">**IF**のビジネス ルール作成ツール ウィンドウを右クリックし、**条件**ノード、および論理式に追加する論理演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-116">In the **IF** pane of Business Rule Composer, right-click the **Conditions** node, and then select the logical operator that you wish to add to the logical expression.</span></span>  
  
2.  <span data-ttu-id="1ad4f-117">論理演算子を右クリックし、追加する述語または入れ子になった論理演算子を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ad4f-117">Right-click the logical operator, and add the predicates or nested logical operators you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad4f-118">参照</span><span class="sxs-lookup"><span data-stu-id="1ad4f-118">See Also</span></span>  
 [<span data-ttu-id="1ad4f-119">算術演算子</span><span class="sxs-lookup"><span data-stu-id="1ad4f-119">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)
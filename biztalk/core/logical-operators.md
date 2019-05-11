---
title: 論理演算子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aaceb64-a5a0-462a-a0eb-8352bed999e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 940f9a1c3604108de58a44aa6998dcdd82e86abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380574"
---
# <a name="logical-operators"></a><span data-ttu-id="ca411-102">論理演算子</span><span class="sxs-lookup"><span data-stu-id="ca411-102">Logical Operators</span></span>
<span data-ttu-id="ca411-103">ビジネス ルール フレームワークでは、論理 AND、OR を使用し、論理ビジネス ルールの作成に NOT 演算子。</span><span class="sxs-lookup"><span data-stu-id="ca411-103">The Business Rules Framework supports using the logical AND, logical OR, and logical NOT operators in creating business rules.</span></span> <span data-ttu-id="ca411-104">次の表では、論理演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca411-104">The following table describes the logical operators.</span></span>  
  
|<span data-ttu-id="ca411-105">論理演算子</span><span class="sxs-lookup"><span data-stu-id="ca411-105">Logical Operator</span></span>|<span data-ttu-id="ca411-106">説明</span><span class="sxs-lookup"><span data-stu-id="ca411-106">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="ca411-107">**AND**</span><span class="sxs-lookup"><span data-stu-id="ca411-107">**AND**</span></span>|<span data-ttu-id="ca411-108">返します**true**に両方のオペランドが評価される場合**true**; を返しますそれ以外の場合**false**します。</span><span class="sxs-lookup"><span data-stu-id="ca411-108">Returns **true** if both the operands evaluate to **true**; otherwise returns **false**.</span></span>|  
|<span data-ttu-id="ca411-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="ca411-109">**OR**</span></span>|<span data-ttu-id="ca411-110">返します**true**に評価されると、オペランドの 1 つ**true**、それ以外の場合を返します**false**。</span><span class="sxs-lookup"><span data-stu-id="ca411-110">Returns **true** if one of the operands evaluates to **true**, otherwise returns **false**.</span></span>|  
|<span data-ttu-id="ca411-111">**NOT**</span><span class="sxs-lookup"><span data-stu-id="ca411-111">**NOT**</span></span>|<span data-ttu-id="ca411-112">返します**true**にオペランドが評価された場合**false**、それ以外の場合**false**します。</span><span class="sxs-lookup"><span data-stu-id="ca411-112">Returns **true** if the operand evaluates to **false**, otherwise returns **false**.</span></span>|  
  
 <span data-ttu-id="ca411-113">オペランドは、さまざまな種類が、ルール エンジンには、式を評価する前に、他のパラメーターまたは変換型の共通の型に、両方のパラメーターの型に一致するパラメーターのいずれかの型に変換します。</span><span class="sxs-lookup"><span data-stu-id="ca411-113">When operands are of different types, the rule engine converts type of one of the parameters to match the type of the other parameter or converts types of both the parameters to a common type before evaluating the expression.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="ca411-114">ビジネス ルールで論理演算子を使用するには</span><span class="sxs-lookup"><span data-stu-id="ca411-114">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="ca411-115">ビジネス ルールで論理演算子を使用するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca411-115">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="ca411-116">**場合**ビジネス ルール作成ツールのウィンドウを右クリックし、**条件**ノード、および論理式を追加する論理演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca411-116">In the **IF** pane of Business Rule Composer, right-click the **Conditions** node, and then select the logical operator that you wish to add to the logical expression.</span></span>  
  
2.  <span data-ttu-id="ca411-117">論理演算子を右クリックし、述語または追加する、入れ子になった論理演算子を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca411-117">Right-click the logical operator, and add the predicates or nested logical operators you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca411-118">参照</span><span class="sxs-lookup"><span data-stu-id="ca411-118">See Also</span></span>  
 [<span data-ttu-id="ca411-119">算術演算子</span><span class="sxs-lookup"><span data-stu-id="ca411-119">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)
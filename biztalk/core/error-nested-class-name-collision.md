---
title: "エラー - 入れ子になったクラス、名前の衝突 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a9fa7a9f57088b3fb93e2eb6024e9b6aad49c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---nested-class-name-collision"></a><span data-ttu-id="74d4c-102">エラー - 入れ子になったクラス名の競合</span><span class="sxs-lookup"><span data-stu-id="74d4c-102">Error - Nested Class Name Collision</span></span>
<span data-ttu-id="74d4c-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="74d4c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="74d4c-104">BEC2017</span><span class="sxs-lookup"><span data-stu-id="74d4c-104">BEC2017</span></span>  
  
 <span data-ttu-id="74d4c-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="74d4c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="74d4c-106">**型名**と同じであるこのスキーマのプロパティが見つかりました、 **RootNode TypeName**スキーマのルート ノードのいずれかのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="74d4c-106">The **Type Name** property of this schema was found to be the same as the **RootNode TypeName** property of one of the root nodes in the schema.</span></span> <span data-ttu-id="74d4c-107">C# では同じ名前のクラスを入れ子にすることが許可されないため、この状態が原因でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="74d4c-107">C# disallows nested classes with the same names; therefore this condition causes an error.</span></span>  
  
 <span data-ttu-id="74d4c-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="74d4c-108">**User Action**</span></span>  
  
 <span data-ttu-id="74d4c-109">名前の競合を避けるために、関連するプロパティ値の 1 つまたは両方を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74d4c-109">You must change one or both of the relevant property values so that you avoid the name collision.</span></span> <span data-ttu-id="74d4c-110">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="74d4c-110">Either:</span></span>  
  
-   <span data-ttu-id="74d4c-111">Microsoft では、関連するスキーマ ファイルを選択して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**型名**プロパティを一意の有効な値にします。</span><span class="sxs-lookup"><span data-stu-id="74d4c-111">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a unique valid value.</span></span>  
  
     <span data-ttu-id="74d4c-112">\- - または -</span><span class="sxs-lookup"><span data-stu-id="74d4c-112">\- or -</span></span>  
  
-   <span data-ttu-id="74d4c-113">対象のルート ノードを選択し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで変更、 **RootNode TypeName**プロパティを一意の有効な値にします。</span><span class="sxs-lookup"><span data-stu-id="74d4c-113">Select the indicated root node, and then in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a unique valid value.</span></span>
---
title: エラー - ネストされたクラス名の競合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37edc5012d2298e9516e766743b58f7d5448cf6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388619"
---
# <a name="error---nested-class-name-collision"></a><span data-ttu-id="92090-102">エラー - ネストされたクラス名の競合</span><span class="sxs-lookup"><span data-stu-id="92090-102">Error - Nested Class Name Collision</span></span>
<span data-ttu-id="92090-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="92090-103">**Error Code**</span></span>  

 <span data-ttu-id="92090-104">BEC2017</span><span class="sxs-lookup"><span data-stu-id="92090-104">BEC2017</span></span>  

 <span data-ttu-id="92090-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="92090-105">**Explanation**</span></span>  

 <span data-ttu-id="92090-106">**型名**このスキーマのプロパティが同じである見つかりました、 **RootNode TypeName**のスキーマのルート ノードのいずれかのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="92090-106">The **Type Name** property of this schema was found to be the same as the **RootNode TypeName** property of one of the root nodes in the schema.</span></span> <span data-ttu-id="92090-107">C# では入れ子になったクラスと同じ名前です。そのためこの条件では、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="92090-107">C# disallows nested classes with the same names; therefore this condition causes an error.</span></span>  

 <span data-ttu-id="92090-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="92090-108">**User Action**</span></span>  

 <span data-ttu-id="92090-109">名前の競合を避けるために、関連するプロパティ値の一方または両方を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92090-109">You must change one or both of the relevant property values so that you avoid the name collision.</span></span> <span data-ttu-id="92090-110">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="92090-110">Either:</span></span>  

- <span data-ttu-id="92090-111">Microsoft では、関連するスキーマ ファイルを選択します。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**型名**プロパティを一意の有効な値にします。</span><span class="sxs-lookup"><span data-stu-id="92090-111">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a unique valid value.</span></span>  

   <span data-ttu-id="92090-112">\- - または -</span><span class="sxs-lookup"><span data-stu-id="92090-112">\- or -</span></span>  

- <span data-ttu-id="92090-113">対象のルート ノードを選択し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、変更、 **RootNode TypeName**プロパティを一意の有効な値にします。</span><span class="sxs-lookup"><span data-stu-id="92090-113">Select the indicated root node, and then in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a unique valid value.</span></span>

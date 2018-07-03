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
ms.openlocfilehash: 856841093c37848924dc6e9b6d160186e03ad304
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003331"
---
# <a name="error---nested-class-name-collision"></a><span data-ttu-id="c4e00-102">エラー - ネストされたクラス名の競合</span><span class="sxs-lookup"><span data-stu-id="c4e00-102">Error - Nested Class Name Collision</span></span>
<span data-ttu-id="c4e00-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="c4e00-103">**Error Code**</span></span>  

 <span data-ttu-id="c4e00-104">BEC2017</span><span class="sxs-lookup"><span data-stu-id="c4e00-104">BEC2017</span></span>  

 <span data-ttu-id="c4e00-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="c4e00-105">**Explanation**</span></span>  

 <span data-ttu-id="c4e00-106">**型名**このスキーマのプロパティが同じである見つかりました、 **RootNode TypeName**のスキーマのルート ノードのいずれかのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c4e00-106">The **Type Name** property of this schema was found to be the same as the **RootNode TypeName** property of one of the root nodes in the schema.</span></span> <span data-ttu-id="c4e00-107">C# では同じ名前のクラスを入れ子にすることが許可されないため、この状態が原因でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c4e00-107">C# disallows nested classes with the same names; therefore this condition causes an error.</span></span>  

 <span data-ttu-id="c4e00-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="c4e00-108">**User Action**</span></span>  

 <span data-ttu-id="c4e00-109">名前の競合を避けるために、関連するプロパティ値の 1 つまたは両方を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e00-109">You must change one or both of the relevant property values so that you avoid the name collision.</span></span> <span data-ttu-id="c4e00-110">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c4e00-110">Either:</span></span>  

- <span data-ttu-id="c4e00-111">Microsoft では、関連するスキーマ ファイルを選択します。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**型名**プロパティを一意の有効な値にします。</span><span class="sxs-lookup"><span data-stu-id="c4e00-111">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a unique valid value.</span></span>  

   <span data-ttu-id="c4e00-112">\- または -</span><span class="sxs-lookup"><span data-stu-id="c4e00-112">\- or -</span></span>  

- <span data-ttu-id="c4e00-113">対象のルート ノードを選択し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、変更、 **RootNode TypeName**プロパティを一意の有効な値にします。</span><span class="sxs-lookup"><span data-stu-id="c4e00-113">Select the indicated root node, and then in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a unique valid value.</span></span>

---
title: 連結 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e21a773d-a9cc-4a6f-b548-46badcd92aab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4766f65fb0cbe26c8f3c545c38235d83abb283a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231698"
---
# <a name="concatenate"></a><span data-ttu-id="3fb71-102">連結</span><span class="sxs-lookup"><span data-stu-id="3fb71-102">Concatenate</span></span>
<span data-ttu-id="3fb71-103">スタックから上位 2 項目を削除し、その 2 つの項目を連結して、結果をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="3fb71-103">Removes the top two items from the stack, concatenates them, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb71-104">構文</span><span class="sxs-lookup"><span data-stu-id="3fb71-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fb71-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3fb71-105">Parameters</span></span>  
 <span data-ttu-id="3fb71-106">スタックの上位 2 項目。</span><span class="sxs-lookup"><span data-stu-id="3fb71-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="3fb71-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="3fb71-107">Pushed Value</span></span>  
 <span data-ttu-id="3fb71-108">連結操作の結果の文字列。</span><span class="sxs-lookup"><span data-stu-id="3fb71-108">String result of the concatenation operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fb71-109">解説</span><span class="sxs-lookup"><span data-stu-id="3fb71-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb71-110">例</span><span class="sxs-lookup"><span data-stu-id="3fb71-110">Example</span></span>  
 <span data-ttu-id="3fb71-111">次に示す更新された式の例では、定数文字列 "Start:" が "EventTime" コンテキスト プロパティの値と連結され、データベース列 NewOrderCreateTime に保存されます。</span><span class="sxs-lookup"><span data-stu-id="3fb71-111">In the following example update expression, the constant string "Start:" is concatenated with the value of the "EventTime" context property and persisted to the database column NewOrderCreateTime.</span></span>  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fb71-112">参照</span><span class="sxs-lookup"><span data-stu-id="3fb71-112">See Also</span></span>  
 [<span data-ttu-id="3fb71-113">インターセプタの操作</span><span class="sxs-lookup"><span data-stu-id="3fb71-113">Interceptor Operations</span></span>](../core/interceptor-operations.md)
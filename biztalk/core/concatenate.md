---
title: 連結 |Microsoft Docs
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
ms.openlocfilehash: 4d47db49e60b95071b48393735b3b4b0e7cee528
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391629"
---
# <a name="concatenate"></a><span data-ttu-id="c0db5-102">連結</span><span class="sxs-lookup"><span data-stu-id="c0db5-102">Concatenate</span></span>
<span data-ttu-id="c0db5-103">スタックから上位 2 項目を削除し、その 2 つの項目を連結して、結果をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="c0db5-103">Removes the top two items from the stack, concatenates them, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0db5-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0db5-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0db5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0db5-105">Parameters</span></span>  
 <span data-ttu-id="c0db5-106">スタックの上位 2 項目。</span><span class="sxs-lookup"><span data-stu-id="c0db5-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c0db5-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="c0db5-107">Pushed Value</span></span>  
 <span data-ttu-id="c0db5-108">連結操作の結果の文字列。</span><span class="sxs-lookup"><span data-stu-id="c0db5-108">String result of the concatenation operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0db5-109">コメント</span><span class="sxs-lookup"><span data-stu-id="c0db5-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0db5-110">例</span><span class="sxs-lookup"><span data-stu-id="c0db5-110">Example</span></span>  
 <span data-ttu-id="c0db5-111">次に示す更新された式の例では、定数文字列 "Start:" が "EventTime" コンテキスト プロパティの値と連結され、データベース列 NewOrderCreateTime に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c0db5-111">In the following example update expression, the constant string "Start:" is concatenated with the value of the "EventTime" context property and persisted to the database column NewOrderCreateTime.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c0db5-112">参照</span><span class="sxs-lookup"><span data-stu-id="c0db5-112">See Also</span></span>  
 [<span data-ttu-id="c0db5-113">インターセプターの操作</span><span class="sxs-lookup"><span data-stu-id="c0db5-113">Interceptor Operations</span></span>](../core/interceptor-operations.md)
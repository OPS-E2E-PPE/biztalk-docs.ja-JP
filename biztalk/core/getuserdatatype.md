---
title: "GetUserDataType |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0605919-a733-4a9d-a725-109346db11a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5525dba034571acd91d1f3dd99f2b56069f81fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="getuserdatatype"></a><span data-ttu-id="91ab1-102">GetUserDataType</span><span class="sxs-lookup"><span data-stu-id="91ab1-102">GetUserDataType</span></span>
<span data-ttu-id="91ab1-103">現在のユーザー データ型の名前をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="91ab1-103">Pushes the name of the current user data type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91ab1-104">構文</span><span class="sxs-lookup"><span data-stu-id="91ab1-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91ab1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91ab1-105">Parameters</span></span>  
 <span data-ttu-id="91ab1-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="91ab1-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="91ab1-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="91ab1-107">Pushed Value</span></span>  
 <span data-ttu-id="91ab1-108">アセンブリ修飾形式の現在のユーザー データ型を格納している文字列。</span><span class="sxs-lookup"><span data-stu-id="91ab1-108">String containing the current user data type in assembly-qualified format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91ab1-109">解説</span><span class="sxs-lookup"><span data-stu-id="91ab1-109">Remarks</span></span>  
 <span data-ttu-id="91ab1-110">異なり**GetActivityType**、この操作は、アセンブリ修飾クラス名の形式を使用しません。 代わりに、タイプ名のみをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="91ab1-110">Unlike **GetActivityType**, this operation does not use the assembly-qualified class name format; instead, it pushes only the type name:</span></span>  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  <span data-ttu-id="91ab1-111">アセンブリ修飾クラス名形式は、値を比較するときに定数として使用すると、常に `false` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="91ab1-111">If you use the assembly-qualified class name format as a constant when comparing values it will always evaluate to `false`.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="91ab1-112">特殊なフィルタの動作</span><span class="sxs-lookup"><span data-stu-id="91ab1-112">Special Filter Behavior</span></span>  
 <span data-ttu-id="91ab1-113">この演算がフィルタ内で実行されると、派生するユーザー データ型も常に照合されます。</span><span class="sxs-lookup"><span data-stu-id="91ab1-113">When this operation is performed inside of a filter, derived user data types are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91ab1-114">例</span><span class="sxs-lookup"><span data-stu-id="91ab1-114">Example</span></span>  
 <span data-ttu-id="91ab1-115">次のサンプルには、`true` インスタンスと、`MyLibrary.MyObject` から派生したクラスのすべてのインスタンスで `MyLibrary.MyObject` に評価されるイベント フィルタ式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="91ab1-115">The following sample contains an event filter expression that will evaluate to `true` for `MyLibrary.MyObject` instances and for any instances from classes that derive from `MyLibrary.MyObject`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyLibrary.MyObject</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```
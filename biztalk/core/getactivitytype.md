---
title: GetActivityType |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65a5aae3-9688-4c49-a78e-1d9c1cc85fea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67e6f31331907e20e810c11e82002fb08b89abe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246418"
---
# <a name="getactivitytype"></a><span data-ttu-id="b1986-102">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="b1986-102">GetActivityType</span></span>
<span data-ttu-id="b1986-103">現在のアクティビティの種類をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="b1986-103">Pushes the name of the current activity type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1986-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1986-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1986-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1986-105">Parameters</span></span>  
 <span data-ttu-id="b1986-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b1986-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="b1986-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="b1986-107">Pushed Value</span></span>  
 <span data-ttu-id="b1986-108">現在のアクティビティの種類を、アセンブリ修飾クラス名形式で格納している文字列。</span><span class="sxs-lookup"><span data-stu-id="b1986-108">String containing the current activity type in assembly-qualified class name format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1986-109">解説</span><span class="sxs-lookup"><span data-stu-id="b1986-109">Remarks</span></span>  
 <span data-ttu-id="b1986-110">`GetActivityType` 操作では、現在のアクティビティの種類を取得し、アセンブリ修飾クラス名形式でスタックに格納します。</span><span class="sxs-lookup"><span data-stu-id="b1986-110">The `GetActivityType` operation retrieves the current activity type and places it on the stack in assembly-qualified class name format:</span></span>  
  
```  
TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08, processorArchitecture=MSIL  
```  
  
 <span data-ttu-id="b1986-111">比較の際は、個々の検索要件に応じて、アクティビティの種類の特性を必要なだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="b1986-111">When comparing, you can specify as much of the type as necessary to satisfy your specific search needs.</span></span> <span data-ttu-id="b1986-112">たとえば、GetActivityType の結果を次のような定数と比較できます。</span><span class="sxs-lookup"><span data-stu-id="b1986-112">For example, you might compare the result of GetActivityType with the constant:</span></span>  
  
 <span data-ttu-id="b1986-113">TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0</span><span class="sxs-lookup"><span data-stu-id="b1986-113">TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0</span></span>  
  
 <span data-ttu-id="b1986-114">この方が、アセンブリ修飾クラス名形式よりも制限が緩やかです。</span><span class="sxs-lookup"><span data-stu-id="b1986-114">This is less restrictive than the assembly-qualified class name format.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="b1986-115">特殊なフィルタの動作</span><span class="sxs-lookup"><span data-stu-id="b1986-115">Special Filter Behavior</span></span>  
 <span data-ttu-id="b1986-116">この演算がフィルタ内で実行されると、派生するアクティビティも常に照合されます。</span><span class="sxs-lookup"><span data-stu-id="b1986-116">When this operation is performed inside of a filter, derived activities are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1986-117">例</span><span class="sxs-lookup"><span data-stu-id="b1986-117">Example</span></span>  
 <span data-ttu-id="b1986-118">次のサンプルには、`true` インスタンス、および `System.Workflow.ComponentModel.Activity` から派正するすべてのインスタンスで `System.Workflow.ComponentModel.Activity` に評価されるイベント フィルタ式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1986-118">The following sample contains an event filter expression that will evaluate to `true` for `System.Workflow.ComponentModel.Activity` instances and any instances from classes that derive from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
```  
<ic:Expression>  
  <wf:Operation Name="GetActivityType" />  
  <ic:Operation Name="Constant">  
    <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
  </ic:Operation>  
  <ic:Operation Name="Equals" />  
</ic:Expression>  
```
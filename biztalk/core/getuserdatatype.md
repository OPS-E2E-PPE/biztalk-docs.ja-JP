---
title: GetUserDataType |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0605919-a733-4a9d-a725-109346db11a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78fb7766363b212e6d913565d43f07500b0d1340
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387637"
---
# <a name="getuserdatatype"></a><span data-ttu-id="5cd80-102">GetUserDataType</span><span class="sxs-lookup"><span data-stu-id="5cd80-102">GetUserDataType</span></span>
<span data-ttu-id="5cd80-103">スタックには、現在のユーザー データ型の名前をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="5cd80-103">Pushes the name of the current user data type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd80-104">構文</span><span class="sxs-lookup"><span data-stu-id="5cd80-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cd80-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5cd80-105">Parameters</span></span>  
 <span data-ttu-id="5cd80-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="5cd80-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="5cd80-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="5cd80-107">Pushed Value</span></span>  
 <span data-ttu-id="5cd80-108">アセンブリ修飾の形式では、現在のユーザー データ型を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="5cd80-108">String containing the current user data type in assembly-qualified format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cd80-109">コメント</span><span class="sxs-lookup"><span data-stu-id="5cd80-109">Remarks</span></span>  
 <span data-ttu-id="5cd80-110">異なり**GetActivityType**、この操作では、アセンブリ修飾クラス名の形式を使用しません。 代わりに、型名のみをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="5cd80-110">Unlike **GetActivityType**, this operation does not use the assembly-qualified class name format; instead, it pushes only the type name:</span></span>  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  <span data-ttu-id="5cd80-111">アセンブリ修飾クラス名の形式を使用するように定数値を比較するときは常に評価されるかどうか`false`します。</span><span class="sxs-lookup"><span data-stu-id="5cd80-111">If you use the assembly-qualified class name format as a constant when comparing values it will always evaluate to `false`.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="5cd80-112">特殊なフィルタの動作</span><span class="sxs-lookup"><span data-stu-id="5cd80-112">Special Filter Behavior</span></span>  
 <span data-ttu-id="5cd80-113">この操作がフィルタ内で実行されると、ユーザーのデータ型はも常に照合を派生します。</span><span class="sxs-lookup"><span data-stu-id="5cd80-113">When this operation is performed inside of a filter, derived user data types are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cd80-114">例</span><span class="sxs-lookup"><span data-stu-id="5cd80-114">Example</span></span>  
 <span data-ttu-id="5cd80-115">次の例に評価されるイベント フィルタ式が含まれています`true`の`MyLibrary.MyObject`インスタンスおよびすべてのインスタンスから派生するクラスから`MyLibrary.MyObject`します。</span><span class="sxs-lookup"><span data-stu-id="5cd80-115">The following sample contains an event filter expression that will evaluate to `true` for `MyLibrary.MyObject` instances and for any instances from classes that derive from `MyLibrary.MyObject`.</span></span>  
  
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
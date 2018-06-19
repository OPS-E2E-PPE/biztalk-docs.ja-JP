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
# <a name="getactivitytype"></a>GetActivityType
現在のアクティビティの種類をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetActivityType" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のアクティビティの種類を、アセンブリ修飾クラス名形式で格納している文字列。  
  
## <a name="remarks"></a>解説  
 `GetActivityType` 操作では、現在のアクティビティの種類を取得し、アセンブリ修飾クラス名形式でスタックに格納します。  
  
```  
TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08, processorArchitecture=MSIL  
```  
  
 比較の際は、個々の検索要件に応じて、アクティビティの種類の特性を必要なだけ指定できます。 たとえば、GetActivityType の結果を次のような定数と比較できます。  
  
 TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0  
  
 この方が、アセンブリ修飾クラス名形式よりも制限が緩やかです。  
  
## <a name="special-filter-behavior"></a>特殊なフィルタの動作  
 この演算がフィルタ内で実行されると、派生するアクティビティも常に照合されます。  
  
## <a name="example"></a>例  
 次のサンプルには、`true` インスタンス、および `System.Workflow.ComponentModel.Activity` から派正するすべてのインスタンスで `System.Workflow.ComponentModel.Activity` に評価されるイベント フィルタ式が含まれます。  
  
```  
<ic:Expression>  
  <wf:Operation Name="GetActivityType" />  
  <ic:Operation Name="Constant">  
    <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
  </ic:Operation>  
  <ic:Operation Name="Equals" />  
</ic:Expression>  
```
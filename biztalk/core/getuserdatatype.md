---
title: GetUserDataType |Microsoft ドキュメント
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
ms.openlocfilehash: 5525dba034571acd91d1f3dd99f2b56069f81fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246466"
---
# <a name="getuserdatatype"></a>GetUserDataType
現在のユーザー データ型の名前をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 アセンブリ修飾形式の現在のユーザー データ型を格納している文字列。  
  
## <a name="remarks"></a>解説  
 異なり**GetActivityType**、この操作は、アセンブリ修飾クラス名の形式を使用しません。 代わりに、タイプ名のみをプッシュします。  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  アセンブリ修飾クラス名形式は、値を比較するときに定数として使用すると、常に `false` に評価されます。  
  
## <a name="special-filter-behavior"></a>特殊なフィルタの動作  
 この演算がフィルタ内で実行されると、派生するユーザー データ型も常に照合されます。  
  
## <a name="example"></a>例  
 次のサンプルには、`true` インスタンスと、`MyLibrary.MyObject` から派生したクラスのすべてのインスタンスで `MyLibrary.MyObject` に評価されるイベント フィルタ式が含まれています。  
  
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
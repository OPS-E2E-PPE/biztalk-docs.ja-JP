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
# <a name="getuserdatatype"></a>GetUserDataType
スタックには、現在のユーザー データ型の名前をプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 アセンブリ修飾の形式では、現在のユーザー データ型を表す文字列です。  
  
## <a name="remarks"></a>コメント  
 異なり**GetActivityType**、この操作では、アセンブリ修飾クラス名の形式を使用しません。 代わりに、型名のみをプッシュします。  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  アセンブリ修飾クラス名の形式を使用するように定数値を比較するときは常に評価されるかどうか`false`します。  
  
## <a name="special-filter-behavior"></a>特殊なフィルタの動作  
 この操作がフィルタ内で実行されると、ユーザーのデータ型はも常に照合を派生します。  
  
## <a name="example"></a>例  
 次の例に評価されるイベント フィルタ式が含まれています`true`の`MyLibrary.MyObject`インスタンスおよびすべてのインスタンスから派生するクラスから`MyLibrary.MyObject`します。  
  
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
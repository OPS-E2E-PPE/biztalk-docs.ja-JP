---
title: GetUserKey |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9353a7f0-9bbd-4cfa-92e6-ed2b86e3a88e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0701ff1df912cc113205bad573b6cebc0f02a13a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246122"
---
# <a name="getuserkey"></a>GetUserKey
現在のユーザー キーをスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetUserKey" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のユーザー キーが含まれた文字列です。  
  
## <a name="remarks"></a>解説  
 この操作は、ユーザー追跡ポイントでのみ有効です。  
  
## <a name="example"></a>例  
 次のサンプルには、ユーザー キーが "DocumentUrl" と等しいときに `true` と評価されるイベント フィルタ式が含まれています。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```
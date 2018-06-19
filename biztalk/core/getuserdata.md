---
title: GetUserData |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c243555b-109f-47e3-8084-ab13a8e22ac5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57bc0ffcefc00e9fae20c7b2c8449c21c549b377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246386"
---
# <a name="getuserdata"></a>GetUserData
現在のユーザー データをスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetUserData" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のユーザー データが含まれた文字列です。  
  
## <a name="remarks"></a>解説  
 この操作は、フィルタ内では無効です。  
  
## <a name="example"></a>例  
 次のサンプルには、`GetUserData` 操作を使用したデータ項目 "UserData" の更新された式が含まれています。  
  
```  
<ic:Update DataItemName="UserData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetUserData" />  
  </ic:Expression>  
</ic:Update>  
```
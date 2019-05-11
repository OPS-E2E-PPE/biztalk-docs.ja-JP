---
title: GetUserData |Microsoft Docs
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
ms.openlocfilehash: 8348e510d168725bf61ab05075162f15768915d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344899"
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
  
## <a name="remarks"></a>コメント  
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
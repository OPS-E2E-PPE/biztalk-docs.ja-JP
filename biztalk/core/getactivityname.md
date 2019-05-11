---
title: GetActivityName |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 479552fa-1535-4f3d-90ff-4615f14c88b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 597b08fc9ea9f19b6c3d7f7e3488ae7f77b2c62f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387739"
---
# <a name="getactivityname"></a>GetActivityName
現在のアクティビティの名前をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetActivityName"/>  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のアクティビティの名前を表す文字列。  
  
## <a name="remarks"></a>コメント  
 Windows Workflow Foundation では、開発者によって構成された一連のアクティビティとして処理が実行されます。 これらのアクティビティにはそれぞれワークフロー内で一意の名前が割り当てられます。 アクティビティの一意の名前に基づいてフィルタ処理を行うことにより、特定のアクティビティのデータを傍受できます。  
  
## <a name="example"></a>例  
 次のサンプルには、Closed ワークフロー内の FoodAndDrinksPolicy という特定のアクティビティを検出するように構成されたイベント フィルタ式が含まれています。 この処理は、`GetActivityName`、`GetActivityEvent`、論理演算などの演算の組み合わせを使用して実行されます。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 このフィルタ パターンは、Windows Workflow Foundation インターセプタ構成ファイルで共通です。  
  
> [!NOTE]
>  引用符を含む文字列を明示的に照合する場合を除いて、引数に引用符は必要ありません。
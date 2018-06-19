---
title: GetActivityEvent |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fe824c9-4cea-44da-b830-5520d67988e0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb039c0e9946091214a52fbb605753a212c233c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246250"
---
# <a name="getactivityevent"></a>GetActivityEvent
現在のアクティビティ イベントの名前をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetActivityEvent"/>  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のアクティビティ イベントを表す文字列です。  
  
## <a name="remarks"></a>解説  
 ワークフロー アクティビティは、ワークフローの有効期間中にいくつかの状態の段階を経る場合があります。 Windows Workflow Foundation BAM インターセプタは、`System.Workflow.ComponentModel.ActivityExecutionStatus` 列挙体に定義された、次の表に示すような大部分の実行状態の値をサポートします。  
  
|実行状態|Description|  
|----------------------|-----------------|  
|Canceling|アクティビティが取り消されているときの状態を表します。|  
|Closed|アクティビティが終了したときの状態を表します。|  
|Compensating|アクティビティを補正しているときの状態を表します。|  
|Executing|アクティビティを実行しているときの状態を表します。|  
|Faulting|アクティビティでエラーが発生しているときの状態を表します。|  
  
> [!NOTE]
>  同じ OnEvent 要素で `GetActivityEvent` と `GetWorkflowEvent` の両方を使用することはできません。  
  
## <a name="example"></a>例  
 次のサンプルには、Closed ワークフロー内の FoodAndDringPolicy という特定のアクティビティを検出するように構成されたイベント フィルタ式が含まれています。 この処理は、`GetActivityEvent`、`GetActivityName`、論理演算などの演算の組み合わせを使用して実行されます。  
  
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
  
## <a name="see-also"></a>参照  
 [System.Workflow.ComponentModel.ActivityExecutionStatus 列挙体](http://go.microsoft.com/fwlink/?LinkId=119570)
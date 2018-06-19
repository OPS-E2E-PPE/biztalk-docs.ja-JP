---
title: GetWorkflowEvent |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dc753bd45452af6ab586a11f216bc65f9539fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246610"
---
# <a name="getworkflowevent"></a>GetWorkflowEvent
現在のワークフロー イベントの名前をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のワークフロー イベントを表す文字列です。  
  
## <a name="remarks"></a>解説  
 ワークフロー インスタンスは、その実行の過程でいくつかの状態の段階を経る場合があります。 たとえば、ワークフロー インスタンスはアイドル状態になったり、中断されたりします。 ワークフロー インスタンスの状態が変化するたびに、ワークフロー ステータス イベントがランタイム追跡インフラストラクチャに送信されます。 Windows Workflow Foundation BAM インターセプターは、`System.Workflow.Runtime.Tracking.TrackingWorkflowEvent` 列挙体に定義された、次の表に示すような大部分のイベントをサポートします。  
  
|アクティビティ イベント|Description|  
|--------------------|-----------------|  
|変更|ワークフロー インスタンスでは、ワークフローの変更が発生しました。|  
|[完了]|ワークフロー インスタンスが完了しました。|  
|Created|ワークフロー インスタンスが作成されました。|  
|例外|処理されない例外が発生しました。|  
|Idle|ワークフロー インスタンスがアイドル状態です。|  
|読み込まれました。|ワークフロー インスタンスがメモリに読み込まれました。|  
|永続化|ワークフロー インスタンスが保存されました。|  
|再開|以前に中断されているワークフロー インスタンスの実行が再開されました。|  
|Started|ワークフロー インスタンスが開始されました。|  
|中断|ワークフロー インスタンスが中断されました。|  
|終了|ワークフロー インスタンスが終了されました。|  
|アンロード|ワークフロー インスタンスがメモリからアンロードされました。|  
  
> [!NOTE]
>  同じ OnEvent 要素で `GetWorkflowEvent` と `GetActivityEvent` の両方を使用することはできません。  
  
## <a name="example"></a>例  
 次の例には、特定のアクティビティを検索するように構成するフィルターが含まれています:"FoodAndDrinksPolicy": ワークフロー内で。 このサンプルでは、閉じたワークフロー内で "FoodAndDrinksPolicy" という名前のアクティビティを検出するようにフィルターが構成されています。 この処理は、`GetWorkflowEvent` によって返された値を定数 "作成" と比較することにより実行されます。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowEvent" />   
      <ic:Operation Name="Constant">  
        <ic:Argument>Created</ic:Argument>   
      </ic:Operation>  
    <ic:Operation Name="Equals" />   
  </ic:Expression>  
</ic:Filter>  
```  
  
 この操作は、ワークフローの有効期間を追跡する場合、およびワークフローで発生する例外またはその他の問題を検出する場合に役立ちます。  
  
## <a name="see-also"></a>参照  
 [System.Workflow.Runtime.Tracking.TrackingWorkflowEvent 列挙体](http://go.microsoft.com/fwlink/?LinkId=119568)
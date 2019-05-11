---
title: GetWorkflowEvent |Microsoft Docs
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
ms.openlocfilehash: 68cf89a168606ae64a83c67b29eb058770b67f44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387645"
---
# <a name="getworkflowevent"></a>GetWorkflowEvent
スタックには、現在のワークフロー イベントの名前をプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のワークフロー イベントを表す文字列です。  
  
## <a name="remarks"></a>コメント  
 ワークフロー インスタンスは、その実行の進行中にいくつかの状態を通過できます。 たとえば、ワークフロー インスタンスがアイドル状態になる可能性があります。 または、中断する可能性があります。 ワークフロー インスタンス状態が変わるたびに、ランタイム追跡インフラストラクチャにワークフロー ステータス イベントを出力します。 Windows Workflow Foundation BAM インターセプタは、によって定義されたイベントのほとんどをサポートしています、`System.Workflow.Runtime.Tracking.TrackingWorkflowEvent`列挙体では、次の表に示すようにします。  
  
|アクティビティ イベント|説明|  
|--------------------|-----------------|  
|変更|ワークフロー インスタンスのワークフローの変更が発生しました。|  
|[完了]|ワークフロー インスタンスが完了しました。|  
|Created|ワークフロー インスタンスが作成されました。|  
|例外|ハンドルされない例外が発生しました。|  
|Idle|ワークフロー インスタンスがアイドル状態です。|  
|読み込まれました。|ワークフロー インスタンスがメモリに読み込まれました。|  
|永続化|ワークフロー インスタンスが永続化されています。|  
|再開|中断状態のワークフロー インスタンスが再開を実行します。|  
|Started|ワークフロー インスタンスが開始されました。|  
|中断|ワークフロー インスタンスが中断されました。|  
|終了|ワークフロー インスタンスを終了しました。|  
|アンロード|ワークフロー インスタンスがメモリからアンロードされました。|  
  
> [!NOTE]
>  同じ OnEvent 要素で `GetWorkflowEvent` と `GetActivityEvent` の両方を使用することはできません。  
  
## <a name="example"></a>例  
 次のサンプルには、特定のアクティビティを検出するように構成するフィルターが含まれています:"FoodAndDrinksPolicy": ワークフロー内で。 サンプルでは、closed ワークフロー内の"FoodAndDrinksPolicy"をという名前のアクティビティを検索するフィルターを構成します。 によって返される値を比較することによってこれは、`GetWorkflowEvent`定数「作成」します。  
  
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
  
 この操作は、ワークフローの有効期間を追跡するため、例外、またはワークフローとその他の問題を検出するために便利です。  
  
## <a name="see-also"></a>参照  
 [System.Workflow.Runtime.Tracking.TrackingWorkflowEvent 列挙体](http://go.microsoft.com/fwlink/?LinkId=119568)
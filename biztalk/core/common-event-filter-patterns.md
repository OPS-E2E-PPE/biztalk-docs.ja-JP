---
title: 一般的なイベント フィルタ パターン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc80168b-25bd-4228-b84c-d38bf4e2fe4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5e5b7ad34a8b87bebe88e21630b178fb7ee35c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012979"
---
# <a name="common-event-filter-patterns"></a>一般的なイベント フィルタ パターン
Windows Workflow Foundation (WF) 用の BAM インターセプタを使用すると、インターセプタ構成ファイル内で頻繁に使用する、一般的なフィルタ パターンがあることに気付きます。 これらのフィルタ パターンの一部はアプリケーションと環境に固有ですが、多くのパターンは、環境にまたがりさまざまなアプリケーションで使用できます。  
  
 このトピックでは、WF アプリケーション用に記述されたインターセプタ構成ファイルで使用する、一般的なフィルタ パターンを多数示します。 各パターンは、以下の Windows Workflow Foundation 追跡イベントでグループ化されています。  
  
- アクティビティ状態イベント  
  
- ワークフロー状態イベント  
  
- ユーザー イベント  
  
  各パターンをインターセプタ構成ファイルにコピーし、アプリケーションに合わせて変更することができます。  
  
## <a name="activity-status-event-filter-patterns"></a>アクティビティ状態イベントのフィルタ パターン  
 アクティビティは、ワークフローの基本的なビルディング ブロックです。 ワークフローは、ツリー状に階層化された一連のアクティビティです。 1 つのアクティビティは、ワークフロー内の 1 つのアクションを表します。 遅延などの単純なアクションのこともあれば、複数の子アクティビティで構成される複合的なアクティビティの場合もあります。  
  
 このセクションのフィルタは、アクティビティに対してフィルタを適用し、以下の BAM インターセプタの 1 つ以上を使用して、WF の操作をカスタマイズします。  
  
-   GetActivityName  
  
-   GetActivityEvent  
  
-   GetActivityType  
  
-   GetActivityProperty  
  
-   GetWorkflowProperty  
  
-   GetContextProperty  
  
> [!NOTE]
>  フィルタ内で GetActivityEvent 操作を使用しない場合は、終了したアクティビティ イベントだけがフィルタの対象となります。  
  
### <a name="filter-by-activity-name-closed-activity"></a>アクティビティ名によるフィルタ (終了したアクティビティ)  
 終了したアクティビティ イベントに対し、アクティビティ名によってフィルタを適用する必要になることが頻繁にあります。 これは、ファイルの受信やデータベースへのデータの書き込みなど、特定のアクティビティからのデータをキャプチャする必要があるときに便利です。  
  
 以下のコード例は、"MyActivity" という名前の終了したアクティビティをフィルタします。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-closed-activity-event"></a>アクティビティ タイプによるフィルタ (終了したアクティビティ イベント)  
 名前ではなくタイプでアクティビティをフィルタしたい場合があります。 たとえば、ワークフロー内のすべてのアクティビティに対して、アクティビティ名と日付/タイムスタンプを保存したいことがあります。 使用してこれを実現する、`GetActivityType`操作。 `GetActivityType` 一致を判断するには、基本データ型とすべての派生型に対して指定された型を比較します。 `System.Workflow.ComponentModel.Activity` に対する比較は一致します。これは、すべてのワークフロー アクティビティがそこから派生する必要があるためです。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-event-any-activity-type"></a>アクティビティ イベントによるフィルタ (任意のアクティビティ タイプ)  
 このフィルタは GetActivityEvent 操作を使用して、終了したアクティビティを探します。 これは、すべての終了したイベントに関する情報をキャプチャするのに (名前やタイプでイベントをフィルタするよりも) 便利です。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a>アクティビティ名とタイプによるフィルタ (終了したアクティビティ イベント)  
 対象とするアクティビティのタイプ (プロセッサ アーキテクチャを含む) を正確に指定したい場合は、アクティビティ名とアクティビティ タイプでアクティビティをフィルタすることができます。 以下の例は、`System.Workflow.ComponentModel.Activity` から派生した "MyActivity" を探します。派生タイプに変更すると、より条件を厳しくすることができます。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
<ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a>アクティビティ名とイベントによるフィルタ (任意のアクティビティ タイプ)  
 この式は、アクティビティ名とアクティビティ イベントに基づいてフィルタを適用します。 これは、特定のアクティビティとイベントに対する情報をキャプチャする場合や、特定のアクティビティに対する複数のアクティビティ イベントからデータをキャプチャする場合に便利です。 たとえば、実行中の MyActivity に対する要素と、Closed に対する要素の、2 つの異なる OnEvent 要素が必要になることがあります。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-event"></a>アクティビティ タイプとイベントによるフィルタ  
 このフィルタは、単一のアクティビティ イベント中に特定のタイプから派生したすべてのアクティビティに関する情報をキャプチャするのに便利です。 たとえば、ワークフロー内を流れる注文書から注文書 ID と日付/タイムスタンプを追跡したいことがあります。 使用してこれを実現する、`GetActivityEvent`と`GetActivityType`操作。 `GetActivityType` 一致を判断するには、基本データ型とすべての派生型に対して指定された型を比較します。 `System.Workflow.ComponentModel.Activity` に対する比較は一致します。これは、すべてのワークフロー アクティビティがそこから派生する必要があるためです。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-type-and-event"></a>アクティビティ名、タイプ、イベントによるフィルタ  
 名前、タイプ、イベントによるアクティビティのフィルタは、追跡したいアクティビティをさらに絞り込みたい場合に便利です。 たとえば、以下のフィルタは、タイプが `System.Workflow.ComponentModel.Activity` と同じか、またはそこから派生した、終了したアクティビティ "MyActivity" を探します。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="workflow-status-event-filter-patterns"></a>ワークフロー状態イベントのフィルタ パターン  
 このセクションのフィルタは、ワークフロー イベントをフィルタし、以下の BAM インターセプタの 1 つ以上を使用して、WF の操作をカスタマイズします。  
  
-   GetWorkflowEvent  
  
-   GetContextProperty  
  
### <a name="filter-by-workflow-event"></a>ワークフロー イベントによるフィルタ  
 この式は、ワークフロー イベントによってフィルタを適用します。  
  
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
  
## <a name="user-event-filter-patterns"></a>ユーザー イベントのフィルタ パターン  
 アプリケーションが、TrackData メソッドを使用してカスタム情報を追跡する場合、以下の BAM インターセプタを 1 つ以上使用して、WF のユーザー データ操作をカスタマイズするために、データの特性に基づいてフィルタをすることができます。  
  
- GetUserDataType  
  
- GetUserKey  
  
- GetUserData  
  
  フィルタでは、これらの操作を以下の操作と組み合わせて、より複雑な式を作成することができます。  
  
- GetActivityName  
  
- GetActivityType  
  
- GetActivityProperty  
  
- GetWorkflowProperty  
  
- GetContextProperty  
  
  フィルタにユーザー データ操作が 1 つも含まれていない場合、フィルタはユーザー イベント フィルタではなく、それを含んでいる OnEvent はエラーになるか (ユーザー操作が対応する更新式に現れる場合)、ユーザー追跡点ではなくアクティビティ追跡点として識別されます。  
  
### <a name="filter-by-activity-name-and-user-data-type"></a>アクティビティ名とユーザー データ型によるフィルタ  
 アクティビティ名とユーザー データ型でイベントを識別することが頻繁にあります。 以下の式は、"MyActivity" という名前と、`System.Object` から派生するユーザー データ型でアクティビティをフィルタします。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-data-type"></a>アクティビティ タイプとユーザー データ型によるフィルタ  
 アクティビティ タイプとユーザー データ型に基づいてフィルタすることができます。 `GetActivityType` と `GetUserDataType` はどちらも指定されたタイプとすべての派生タイプに対して比較を行うため、これにより、派生元のタイプに基づいてイベントをフィルタするための自由度が得られます。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a>アクティビティ名、アクティビティ タイプ、ユーザー データ型によるフィルタ  
 このフィルターは、アクティビティ名を含めることで、アクティビティ タイプとユーザー データ型のフィルター パターンの条件をさらに絞り込みます。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-user-key"></a>アクティビティ名とユーザー キーによるフィルタ  
 アプリケーションに、実行時に決定されるキーを使用して `TrackData` を呼び出すアクティビティがある場合は、アクティビティ名とユーザー キーでフィルタしたいことがあります。 これにより、特定のキー値に基づいて `OnEvent` をトリガできます。 たとえば、アプリケーションで複数のキーが定義され、アクティビティ内で動的に 1 つを選択することがあります。  
  
 以下の式は、ユーザー キー "ItemKey" を含む "MyActivity" をフィルタします。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-key"></a>アクティビティ タイプとユーザー キーによるフィルタ  
 アプリケーションに、実行時に決定されるキーを使用して `TrackData` を呼び出すアクティビティが複数ある場合は、アクティビティ名とユーザー キーでフィルタしたいことがあります。 これにより、特定のキー値に基づいて `OnEvent` をトリガできます。 たとえば、アプリケーションで複数のキーが定義され、アクティビティ内で動的に 1 つを選択することがあります。  
  
 以下の式は、ユーザー キー "ItemKey" を含む、`System.Workflow.ComponentModel.Activity` から派生したすべてのアクティビティをフィルタします。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a>アクティビティ名、アクティビティ タイプ、ユーザー キーによるフィルタ  
 このフィルタ パターンは、アクティビティ名をフィルタに含めることで、アクティビティ タイプとユーザー キーのフィルタ パターンの条件をさらに絞込みます。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a>アクティビティ名、ユーザー データ型、ユーザー キーによるフィルタ  
 このフィルタは、特定のユーザー キーを持ち、特定のデータ型から派生した、指定した名前のアクティビティのフィルタ条件を絞り込む場合に便利です。 たとえば、アクティビティがキー "Item" と、項目の種類に応じて文字列または整数のデータ値を使用して TrackData を呼び出すことがあります。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a>アクティビティ タイプ、ユーザー データ型、ユーザー キーによるフィルタ  
 このフィルタは、特定のユーザー キーを持ち、特定のデータ型から派生した、アクティビティ タイプのフィルタ条件を絞り込む場合に便利です。 使用するタイプに応じて、アクティビティ名、ユーザー データ型、ユーザー キーを使用した場合よりも条件が厳しくなることも緩くなることもあります。 最も派生したタイプを指定するとより条件が厳しくなり、ルート ベース タイプを指定すると条件が緩くなります。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a>アクティビティ名、アクティビティ タイプ、ユーザー データ型、ユーザー キーによるフィルタ  
 このフィルタは、アクティビティ名を追加することで、アクティビティ タイプとユーザー データ型、ユーザー キーのパターンの条件をさらに絞り込みます。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>   
```
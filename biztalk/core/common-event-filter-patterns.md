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
ms.openlocfilehash: 05a81dcac4e7bd43a0a60e042d285c56a9fcc35c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357131"
---
# <a name="common-event-filter-patterns"></a>一般的なイベント フィルタ パターン
BAM インターセプターの Windows Workflow Foundation (WF) を操作するときは、するで、インターセプタ構成ファイルが頻繁に使用がパターンの一般的なフィルターのセットがある可能性がありますに注意してください。 これらのフィルタ パターンの一部は、アプリケーションと環境に対して一意では、中に、環境間で、さまざまなアプリケーションで多数のパターンを使用できます。  
  
 このトピックでは、WF アプリケーション用に記述されたインターセプタ構成ファイルで使用される一般的なフィルタ パターンの多くを収集します。 パターンは、Windows Workflow Foundation 追跡イベントでグループ化されます。  
  
- アクティビティ ステータス イベント  
  
- ワークフロー ステータス イベント  
  
- ユーザー イベント  
  
  各パターンをインターセプタ構成ファイルにコピーし、アプリケーションに合うように変更できます。  
  
## <a name="activity-status-event-filter-patterns"></a>アクティビティ ステータス イベントのフィルタ パターン  
 アクティビティは、ワークフローの基本的な構成要素です。 ワークフローは、ツリー構造で階層的に編成されているアクティビティのセットです。 アクティビティは、ワークフローのアクションを表します。 おくと、遅延などの単純な操作または複数の子アクティビティで構成される複合アクティビティであることができます。  
  
 このセクションではフィルターには、活動と WF カスタム操作の 1 つ以上の次の BAM インターセプターの使用がフィルター処理します。  
  
-   GetActivityName  
  
-   GetActivityEvent  
  
-   GetActivityType  
  
-   GetActivityProperty  
  
-   GetWorkflowProperty  
  
-   GetContextProperty  
  
> [!NOTE]
>  フィルターで GetActivityEvent 操作を使用しない場合、フィルターは終了したアクティビティ イベントのみになります。  
  
### <a name="filter-by-activity-name-closed-activity"></a>アクティビティ名 (終了したアクティビティ) でフィルター処理します。  
 頻繁に終了したアクティビティ イベントのアクティビティ名でフィルター処理する必要があります。 これは、機能は、ファイルの受信やデータベースへのデータの書き込みなどの特定のアクティビティからデータをキャプチャする必要がある場合に便利です。  
  
 終了したアクティビティのフィルターの下のフラグメントでは、"MyActivity"という名前です。  
  
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
  
### <a name="filter-by-activity-type-closed-activity-event"></a>アクティビティの種類 (終了したアクティビティ イベント) でフィルター処理します。  
 名前ではなく型によるアクティビティをフィルター処理に必要な場合があります。 たとえば、ワークフローでアクティビティ名とすべてのアクティビティの日付/時刻スタンプを保存する場合があります。 使用してこれを実現する、`GetActivityType`操作。 `GetActivityType` 一致を判断するには、基本データ型とすべての派生型に対して指定された型を比較します。 比較対象`System.Workflow.ComponentModel.Activity`すべてのワークフロー アクティビティがそこから派生する必要がありますが、一致します。  
  
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
  
### <a name="filter-by-activity-event-any-activity-type"></a>(任意のアクティビティ タイプ) のアクティビティ イベントによるフィルタします。  
 このフィルターでは、GetActivityEvent 操作を使用して、閉じたアクティビティを検索します。 (名前や種類によって、特定のイベント) とすべての closed イベントに関する情報をキャプチャするため便利です。  
  
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
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a>アクティビティの名前でフィルター処理し、(終了したアクティビティ イベント) を入力  
 検索の関心をアクティビティ (プロセッサ アーキテクチャを含む) の正確な型を指定する場合は、アクティビティ名とアクティビティの種類別の活動をフィルター処理することができます。 次のサンプルでは"myactivity"から派生する`System.Workflow.ComponentModel.Activity`; より制限の厳しいする派生型に変更することができます。  
  
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
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a>アクティビティ名とイベント (アクティビティの種類) でフィルター処理します。  
 アクティビティ名とアクティビティ イベントに基づいて、この式のフィルター。 これは、機能は、特定のアクティビティとイベントの情報をキャプチャするとき、または、特定のアクティビティの 1 つ以上のアクティビティ イベントからのデータをキャプチャするときに便利です。 たとえば、中の MyActivity Executing とに 1 つが閉じられる次のように 1 つずつ 2 つの異なる OnEvent 要素たい場合があります。  
  
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
  
### <a name="filter-by-activity-type-and-event"></a>アクティビティの種類とイベントによるフィルタします。  
 このフィルターは、1 つのアクティビティ イベント中に特定の型から派生するすべてのアクティビティに関する情報をキャプチャするために便利です。 たとえば、注文書 ID を追跡したいしてワークフロー内を流れるに注文書からスタンプを日付/時刻。 使用してこれを実現する、`GetActivityEvent`と`GetActivityType`操作。 `GetActivityType` 一致を判断するには、基本データ型とすべての派生型に対して指定された型を比較します。 比較対象`System.Workflow.ComponentModel.Activity`すべてのワークフロー アクティビティがそこから派生する必要がありますが、一致します。  
  
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
  
### <a name="filter-by-activity-name-type-and-event"></a>アクティビティ名、型、イベントによるフィルタします。  
 アクティビティをフィルター処理、名前、タイプとイベントできます追跡興味のあるアクティビティをさらに絞り込みたい場合。 たとえば次のフィルターでは、終了したアクティビティ"MyActivity"に等しいかから派生する型を持つ`System.Workflow.ComponentModel.Activity`します。  
  
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
  
## <a name="workflow-status-event-filter-patterns"></a>ワークフロー ステータス イベントのフィルタ パターン  
 このセクションでは、フィルターは、WF の操作をカスタムの使用を次の BAM インターセプタの 1 つ以上のワークフロー イベントとフィルター処理します。  
  
-   GetWorkflowEvent  
  
-   GetContextProperty  
  
### <a name="filter-by-workflow-event"></a>ワークフロー イベントによるフィルタします。  
 この式は、ワークフロー イベントをフィルター処理します。  
  
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
 フィルター処理できるアプリケーションでは、TrackData メソッドを使用してカスタム情報を追跡している場合、次の BAM インターセプタの 1 つ以上を使用して、WF カスタム ユーザー データの操作のデータの特性に基づき。  
  
- GetUserDataType  
  
- GetUserKey  
  
- GetUserData  
  
  フィルターより複雑な式を作成するには、次のようにこれらの操作を組み合わせることができます。  
  
- GetActivityName  
  
- GetActivityType  
  
- GetActivityProperty  
  
- GetWorkflowProperty  
  
- GetContextProperty  
  
  フィルターには少なくとも 1 人のユーザー データの操作は含まれません場合は、フィルターには、ユーザー イベントのフィルターはできませんユーザー操作は、対応する更新式に表示されます) であれば、それを囲む OnEvent のエラーが発生するか、アクティビティ追跡ポイントとして識別されます。およびユーザー追跡ポイントではありません。  
  
### <a name="filter-by-activity-name-and-user-data-type"></a>アクティビティ名とユーザー データ型によるフィルタします。  
 頻繁にアクティビティ名とユーザー データ型でイベントを識別できます。 "MyActivity"という名前のユーザーのデータ型から派生したアクティビティの次の式フィルター`System.Object`します。  
  
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
  
### <a name="filter-by-activity-type-and-user-data-type"></a>アクティビティ タイプとユーザー データ型によるフィルタします。  
 フィルター処理できますアクティビティ タイプとユーザー データ型に基づいています。 イベントをフィルター処理の緯度の種類に基づいて、派生元ため、これを許可両方`GetActivityType`と`GetUserDataType`指定された型とすべての派生型を比較します。  
  
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
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a>アクティビティ名、アクティビティの種類、ユーザー データ型によるフィルタします。  
 さらに、このフィルターは、アクティビティ名を含めることによって、アクティビティ タイプとユーザー データ型のフィルター パターンを制限します。  
  
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
  
### <a name="filter-by-activity-name-and-user-key"></a>アクティビティ名とユーザー キーによるフィルタします。  
 アプリケーションにアクティビティを呼び出す場合`TrackData`実行時に決定するキーを持つアクティビティ名とユーザー キーでフィルター処理することがあります。 これはトリガーすることにより、`OnEvent`特定のキー値に基づいて。 たとえば、アプリケーションは、複数のキーを定義し、アクティビティ内で 1 つを動的に選択します。  
  
 ユーザー キーを含む"myactivity"は、以下のフィルターの式では、"ItemKey"という名前です。  
  
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
  
### <a name="filter-by-activity-type-and-user-key"></a>アクティビティ タイプとユーザー キーによるフィルタします。  
 アプリケーションには、複数のアクティビティを呼び出すことが含まれている場合`TrackData`実行時に決定するキーを持つアクティビティ名とユーザー キーでフィルター処理することがあります。 これはトリガーすることにより、`OnEvent`特定のキー値に基づいて。 たとえば、アプリケーションは、複数のキーを定義し、アクティビティ内で 1 つを動的に選択します。  
  
 フィルターから派生する任意のアクティビティを以下の式`System.Workflow.ComponentModel.Activity`"ItemKey"をという名前のユーザー キーを格納します。  
  
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
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a>アクティビティ名、アクティビティの種類、ユーザー キーによるフィルタします。  
 さらに、このフィルタ パターンは、フィルターにアクティビティ名を含めることでアクティビティ タイプとユーザー キーのフィルタ パターンを細分化します。  
  
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
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a>アクティビティ名、ユーザー データ型、ユーザー キーによるフィルタします。  
 このフィルターは、特定のユーザー キーを持つ名前付きのアクティビティに、フィルターを制限する場合に有用と特定のデータ型から派生します。 たとえば、アクティビティは、キー"Item"と、データの文字列または整数の項目の種類に応じて値を使用して TrackData を呼び出すことができます。  
  
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
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a>アクティビティの種類、ユーザー データ型、ユーザー キーによるフィルタします。  
 このフィルターは、特定のユーザー キーを使用して、フィルターをアクティビティの種類に制限する場合に有用と特定のデータ型から派生します。 制限の厳しいまたはアクティビティ名、ユーザー データ型、および使用の種類に基づくユーザー キーを使用するよりも少ないを使用できます。 最も多く派生された型を指定する場合が考えられます。 より制限の厳しいルートの基本型を指定する場合より制限の少ないが考えられます。  
  
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
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a>アクティビティ名、アクティビティの種類、ユーザー データ型、ユーザー キーによるフィルタします。  
 さらに、このフィルターは、アクティビティ名を追加して、アクティビティの種類、ユーザー データ型、およびユーザー キーのパターンを制限します。  
  
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
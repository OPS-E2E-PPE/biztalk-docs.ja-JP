---
title: パイプライン コンポーネントを使用して、既存のスケジュールを選択する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b93c5cb6-071f-485d-b0bb-22f95bafa3d0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aceef4385652918ee7326709e7838776501e885
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975499"
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a>パイプライン コンポーネントを使用して、既存のスケジュールを選択するには
## <a name="esb-itinerary-selector-pipeline-component"></a>ESB スケジュール セレクターのパイプライン コンポーネント  
 スケジュール オンランプのヘッダーを使用せず、汎用的なスケジュール オンランプを使用して送信されたメッセージが送信されます。 適切なスケジュールを解決し、受信メッセージに添付に着手が中央リポジトリからスケジュールにアクセスするように構成できるメカニズムを提供する必要があります。  

 ESB スケジュール セレクター パイプライン コンポーネントは、(既定では SQL Server) の中央リポジトリに格納されているサーバー側の旅行プランの内容を解決するのには、特殊な競合回避モジュールと組み合わせて、競合回避モジュールの接続文字列を使います。  

 (SOAP ヘッダーで表される) ように、クライアントによって要求されたスケジュールのバージョンと名前を取得して、メッセージ コンテキストから WCF オンランプ行程静的競合回避モジュールと組み合わせてで ESB スケジュール セレクターのパイプライン コンポーネントを使用するときに、適切なスケジュールの選択に使用されます。  

 既定では、ESB スケジュール セレクターのパイプライン コンポーネントは次のパイプラインに存在します。  

- ItinerarySelectReceive  

- ItinerarySelectReceivePassthrough  

- ItinerarySelectReceiveXml  

- ItinerarySelectSendReceive  

  次のセクションでは、各コンポーネントによって実行される手順を説明します。  

## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a>ESB スケジュール セレクター パイプライン コンポーネントの処理手順  
 ESB スケジュール セレクターのパイプライン コンポーネントは、次の手順を実行します。  

- 送信パーティは、処理対象のメッセージを送信します。 スケジュール セレクター コンポーネントは、開発者によって構成された、プロパティの接続文字列として指定された競合回避モジュールを使用してメッセージの内容またはコンテキストに基づいて、スケジュールのストアから適切な旅行プランを選択します。  

- 旅行プランを検証し、日程; でそれらが null の場合、既定値を事前に特定のプロパティを設定します例えば：  

  - サービスの数が 1 未満の場合、コンポーネントは例外をスローします。  

  - コンポーネント サービスの数、識別子の値を使用して、itinerary ルート属性を設定する (**Uuid**)、開始時刻 (**BeginTime**)、および一方向または双方向の要求かどうか (**IsRequestResponse**)。  

  - コンポーネントで、サービスを検証します、識別子を設定、現在のサービス インスタンス (次に処理するサービス) を設定、および関連付けられているすべての競合回避モジュールを検証します。  

  - コンポーネントは、Microsoft BizTalk Server のセグメントの次のプロパティを使用してスケジュールを設定します。  

    -   **correlationToken**  

    -   **reqRespTransmitPipelineID**  

    -   **interchangeId**  

    -   **receiveInstanceId**  

    -   **epmRRCorrelationToken**  

  - コンポーネントは、システム Properties.xsd スキーマで定義されたプロパティを使用して次の表に、BizTalk メッセージ コンテキスト プロパティを変更後の日程を書き込みます。  


    |                                           [プロパティ]                                           |
    |------------------------------------------------------------------------------------------------|
    |                                   **名前 = ItineraryHeader**                                   |
    | **Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties** |


  - コンポーネントは、システム Properties.xsd スキーマで定義されている値を使用して次の表に示す 4 つの BizTalk コンテキスト プロパティを昇格させます。  

    |プロパティ|値|  
    |--------------|-----------|  
    |**サービス名**|旅行プランで定義されている現在のサービス インスタンスの名前。|  
    |**ServiceType**|いずれかに設定**オーケストレーション**または**メッセージング**します。|  
    |**IsRequestResponse**|いずれかに設定**True**または**False**します。|  
    |**ServiceState**|設定**保留**します。|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a>ESB ディスパッチャー パイプライン コンポーネントのプロセスの手順  
 ESB ディスパッチャー パイプライン コンポーネントは、次の手順を実行します。  

-   型の任意のスケジュール オンランプ手順の実行を管理**メッセージング**旅行計画を進めます。 ESB ディスパッチャー コンポーネントは位置認識され、ある可能性があるメッセージの処理サイクルでその場所に基づくロジックを実行**入力方向の受信**、**送信送信**、**送信受信**、または**送信受信**します。 ESB ディスパッチャー パイプライン コンポーネントは、ESB スケジュール メッセージング サービス Esb.config ファイルで指定されたを呼び出します。 既定では、ルーティングと変換のためには、このコンポーネントの構成プロパティは、次のサービスに関連付けられました。  

    -   **Microsoft.Practices.ESB.Services.Transform**します。 このサービスは、受信メッセージのペイロードに対して BizTalk マップを実行します。 サービスは、変換要件を検証し、ドキュメント仕様の名前とメッセージの種類が含まれている BizTalk コンテキスト プロパティを更新します。 ESB ディスパッチャーは、変換サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。  

    -   **Microsoft.Practices.ESB.Services.Routing します。** このサービスでは、リゾルバーとアダプターのプロバイダー フレームワークを使用して、適切なエンドポイントのルーティング情報を設定します。 ESB ディスパッチャーは、ルーティング サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。
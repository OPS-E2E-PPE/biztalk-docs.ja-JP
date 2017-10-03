---
title: "パイプライン コンポーネントを使用して、既存の日程を選択する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b93c5cb6-071f-485d-b0bb-22f95bafa3d0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a733da2348de13120ce37a205b77d2e8194c7790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a>パイプライン コンポーネントを使用して、既存の日程を選択するには
## <a name="esb-itinerary-selector-pipeline-component"></a>ESB Itinerary セレクター パイプライン コンポーネント  
 Itinerary ヘッダーなしジェネリック itinerary での傾斜を使用して送信されたメッセージが送信されます。 適切な旅程を解決し、受信メッセージにアタッチのランプは日程を中央のリポジトリからアクセスするように構成するメカニズムを提供する必要があります。  
  
 ESB 行程セレクター パイプライン コンポーネントでは、(既定では、SQL Server)、中央リポジトリに格納されているサーバー側行程の内容を解決するのには、特殊な競合回避モジュール、と共に競合回避モジュールの接続文字列を使用します。  
  
 (SOAP ヘッダーで表される) ように、クライアントによって要求された行程のバージョンと名前を取得してメッセージ コンテキストから使用すると、ESB 行程セレクター パイプライン コンポーネントは、WCF での傾斜、行程静的競合回避モジュールと組み合わせて、および適切な行程の選択に使用します。  
  
 既定では、ESB 行程セレクター パイプライン コンポーネントは、次のパイプラインに存在します。  
  
-   ItinerarySelectReceive  
  
-   ItinerarySelectReceivePassthrough  
  
-   ItinerarySelectReceiveXml  
  
-   ItinerarySelectSendReceive  
  
 次のセクションでは、各コンポーネントの実行手順について説明します。  
  
## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a>ESB Itinerary セレクター パイプライン コンポーネントの処理手順  
 ESB 行程セレクター パイプライン コンポーネントは、次の手順を実行します。  
  
-   送信パーティは、処理対象のメッセージを送信します。 行程セレクター コンポーネントは、決定し、メッセージの内容またはコンテキストに基づいて、itinerary ストアから適切な旅程を選択する、開発者によって構成されている、プロパティの接続文字列として指定された競合回避モジュールを使用します。  
  
-   旅行計画を検証して itinerary; は null の場合は、既定値を事前設定する特定のプロパティを設定例えば：  
  
    -   サービスの数が 1 未満の場合は、コンポーネントは、例外をスローします。  
  
    -   コンポーネント サービスの数、識別子の値を使用して itinerary ルート属性を設定します (**Uuid**)、開始時刻 (**BeginTime**)、およびこれは一方向または双方向の要求かどうか (**IsRequestResponse**)。  
  
    -   コンポーネントは、サービスを検証、識別子を設定および現在のサービス インスタンス (次に処理するサービス) を設定したうえで、すべての関連するリゾルバーを検証します。  
  
    -   コンポーネントは、次のプロパティを使用して itinerary の Microsoft BizTalk Server のセグメントを設定します。  
  
        -   **correlationToken**  
  
        -   **reqRespTransmitPipelineID**  
  
        -   **interchangeId**  
  
        -   **receiveInstanceId**  
  
        -   **epmRRCorrelationToken**  
  
    -   コンポーネントは、システム Properties.xsd スキーマで定義されたプロパティを使用して次の表に、BizTalk メッセージ コンテキスト プロパティを変更した日程を書き込みます。  
  
        |[プロパティ]|  
        |----------------|  
        |**名前 ItineraryHeader を =**|  
        |**Namespace http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties を =**|  
  
    -   コンポーネントは、システム Properties.xsd スキーマで定義されている値を使用して次の表に示す 4 つの BizTalk コンテキスト プロパティを昇格させます。  
  
        |プロパティ|値|  
        |--------------|-----------|  
        |**サービス名**|旅行計画で定義されている現在のサービス インスタンスの名前。|  
        |**ServiceType**|いずれかに設定**オーケストレーション**または**メッセージング**です。|  
        |**IsRequestResponse**|いずれかに設定**True**または**False**です。|  
        |**ServiceState**|設定**保留**です。|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a>ESB ディスパッチャー パイプライン コンポーネント プロセスがステップ実行  
 ESB ディスパッチャー パイプライン コンポーネントは、次の手順を実行します。  
  
-   型の任意の itinerary ステップの実行を管理する**メッセージング**旅行計画を進めます。 ESB ディスパッチャー コンポーネントの場所に対応してロジックを実行生じる可能性があるメッセージの処理サイクルでの場所に基づく**受信受信**、**送信送信**、**送信受信**、または**送信受信**です。 ESB ディスパッチャー パイプライン コンポーネントでは、Esb.config ファイルで指定された itinerary メッセージング サービスを ESB を開始します。 既定では、ルーティングと変換のためには、このコンポーネントの構成プロパティは、次のサービスに関連付けられました。  
  
    -   **Microsoft.Practices.ESB.Services.Transform**です。 このサービスは、受信メッセージのペイロードに対して BizTalk マップを実行します。 サービスは、変換要件を検証し、ドキュメント仕様の名前とメッセージの種類を含む BizTalk コンテキスト プロパティを更新します。 ESB ディスパッチャーは、変換サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。  
  
    -   **Microsoft.Practices.ESB.Services.Routing です。** このサービスでは、競合回避モジュールとアダプターのプロバイダー フレームワークを使用して、適切なエンドポイントのルーティング情報を設定します。 ESB ディスパッチャーは、これは、ルーティング サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合にのみ、このサービスを実行します。
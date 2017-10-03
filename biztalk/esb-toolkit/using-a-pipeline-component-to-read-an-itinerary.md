---
title: "パイプライン コンポーネントを使用して、日程を読み取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e3b40c7-0f17-4d33-a26f-f51346a98be5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bceec4df732247be043e006b52c7abbfbf6a6b24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a>パイプライン コンポーネントを使用して、日程を読み取る
受信パイプラインで受信するメッセージには、その処理要件 (クライアント側行程) を定義する SOAP ヘッダー内のメタデータを含めることができます。 図 1 は、ESB 行程 ESB ディスパッチャー パイプライン コンポーネントの使用方法を示します。  
  
 ![パイプライン コンポーネントの読み取り](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4 PipelineComponentRead")  
  
 **図 1**  
  
 **ESB 行程パイプライン コンポーネントの例**  
  
 ESB 行程パイプライン コンポーネントを使用して、ESB によって適用される処理を定義するコンテキスト プロパティとしてメッセージからのメタデータをキャプチャできます。  
  
 次のセクションでは、各コンポーネントの実行手順について説明します。  
  
## <a name="esb-itinerary-pipeline-component-process-steps"></a>ESB Itinerary パイプライン コンポーネント プロセスがステップ実行  
 図 1 の例では、ESB 行程パイプライン コンポーネントは、次の手順を実行します。  
  
-   行程 SOAP ヘッダーを読み取ります。 送信パーティは、そのユーザーは、メッセージを送信するときに、SOAP ヘッダーを設定することで、日程を設定します。 一連の BizTalk メッセージ コンテキスト プロパティを表す SOAP ヘッダーです。これらのプロパティは、使用されている Web サービス アダプターの種類によって異なります。 関連する Web サービス アダプターを次に示します。  
  
    -   **WCF アダプター。** このアダプターは、SOAP ヘッダーを解析し、次の表に、BizTalk メッセージ コンテキスト プロパティを設定します。  
  
        |[プロパティ]|  
        |----------------|  
        |**名前旅程を =**|  
        |**Namespace http://schemas.microsoft.biztalk.practices.esb.com/itinerary を =**|  
  
        > [!NOTE]
        >  既定では、Windows Communication Foundation (WCF) アダプターは BizTalk コンテキストとして ItineraryDescription.xsd (ESB 行程 SOAP ヘッダーを生成するこのスキーマが使用されます) という名前のスキーマのルート名を使用して**名前**引数BizTalk コンテキストとして、スキーマのターゲットの名前空間を使用して**Namespace**引数。  
  
    -   **SOAP アダプター。** このアダプターは、SOAP ヘッダーを解析し、次の表に、BizTalk メッセージ コンテキスト プロパティを設定します。  
  
        |[プロパティ]|  
        |----------------|  
        |**名前旅程を =**|  
        |**Namespace http://schemas.microsoft.com/BizTalk/2003/SOAPHeader を =**|  
  
        > [!NOTE]
        >  既定では、SOAP アダプターは BizTalk コンテキストとして Itinerary.xsd (ESB 行程 SOAP ヘッダーを生成するこのスキーマが使用されます) という名前のスキーマのルート名を使用**名前**に SOAP ヘッダーの名前空間を使用して、引数、BizTalk コンテキスト**Namespace**引数。  
  
-   メッセージ コンテキストから元の itinerary 値を削除します。  
  
-   旅行計画を検証して itinerary; は null の場合は、既定値を事前設定する特定のプロパティを設定例えば：  
  
    -   サービスの数が 1 未満の場合は、コンポーネントは、例外をスローします。  
  
    -   コンポーネント サービスの数、識別子の値を使用して itinerary ルート属性を設定します (**Uuid**)、開始時刻 (**BeginTime**)、およびこれは一方向または双方向の要求かどうか (**IsRequestResponse**)。  
  
    -   コンポーネントは、サービスを検証、識別子を設定および現在のサービス インスタンス (次に処理するサービス) を設定したうえで、すべての関連するリゾルバーを検証します。  
  
    -   コンポーネントは、次のプロパティを使用して itinerary の BizTalk セグメントを設定します。  
  
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
        |**ServiceType**|いずれかに設定**オーケストレーション**または**メッセージング**|  
        |**IsRequestResponse**|いずれかに設定**True**または**False**|  
        |**ServiceState**|設定**保留中**|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a>ESB ディスパッチャー パイプライン コンポーネント プロセスがステップ実行  
 図 1 の例では、ESB ディスパッチャー パイプライン コンポーネントは、次の手順を実行します。  
  
-   型の任意の itinerary ステップの実行を管理する**メッセージング**旅行計画を進めます。 ESB ディスパッチャー コンポーネントの場所に対応してロジックを実行生じる可能性があるメッセージの処理サイクルでの場所に基づく**受信の受信、送信する送信**、**受信送信**、または**送信受信**です。 ESB ディスパッチャー パイプライン コンポーネントでは、Esb.config ファイルで指定された itinerary メッセージング サービスを ESB を開始します。 既定では、ルーティングと変換のためには、このコンポーネントの構成プロパティは、次のサービスに関連付けられました。  
  
    -   **Microsoft.Practices.ESB.Services.Transform です。** このサービスは、受信メッセージのペイロードに対して BizTalk マップを実行します。 サービスは、変換要件を検証し、ドキュメント仕様の名前とメッセージの種類を含む BizTalk コンテキスト プロパティを更新します。 ESB ディスパッチャーは、変換サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。  
  
    -   **Microsoft.Practices.ESB.Services.Routing です。**このサービスは、適切なエンドポイントのルーティング情報を設定するアダプター プロバイダーのフレームワークとの競合回避モジュールを使用します。 ESB ディスパッチャーは、これは、ルーティング サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合にのみ、このサービスを実行します。
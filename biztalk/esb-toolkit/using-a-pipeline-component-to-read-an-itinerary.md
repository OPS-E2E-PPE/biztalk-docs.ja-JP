---
title: パイプライン コンポーネントを使用して、スケジュールを読み取るを |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e3b40c7-0f17-4d33-a26f-f51346a98be5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03e4e48b125d7a8236c66ce36e458dd2d51a6f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991131"
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a>パイプライン コンポーネントを使用して、スケジュールを読み取るに
受信パイプラインで受信するメッセージは、その処理の要件 (クライアント側の旅程) を定義する SOAP ヘッダー内のメタデータを含めることができます。 図 1 は、ESB 行程および ESB ディスパッチャー パイプライン コンポーネントの使用を示しています。  

 ![パイプライン コンポーネントの読み取り](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4 PipelineComponentRead")  

 **図 1**  

 **ESB 行程のパイプライン コンポーネントの例**  

 ESB によって適用される処理を定義できますコンテキスト プロパティとしてメッセージからメタデータをキャプチャする ESB 行程のパイプライン コンポーネントを使用できます。  

 次のセクションでは、各コンポーネントによって実行される手順を説明します。  

## <a name="esb-itinerary-pipeline-component-process-steps"></a>ESB スケジュール オンランプ パイプライン コンポーネントのプロセスの手順  
 図 1 に示す例では、ESB 行程のパイプライン コンポーネントは、次の手順を実行します。  

- SOAP ヘッダーの旅程を読み取ります。 送信パーティは、そのユーザーは、メッセージを送信するときに SOAP ヘッダーを設定することにより、スケジュールを設定します。 SOAP ヘッダーを表す一連の BizTalk メッセージ コンテキスト プロパティこれらのプロパティは、使用されている Web サービス アダプターの種類によって異なります。 以下は、関連する Web サービス アダプタです。  

  - **WCF アダプター。** このアダプターは、SOAP ヘッダーを解析し、次の表に、BizTalk メッセージ コンテキスト プロパティを設定します。  


    |                                  [プロパティ]                                  |
    |------------------------------------------------------------------------------|
    |                             **名前の旅程を =**                             |
    | **Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary** |

    > [!NOTE]
    >  既定では、Windows Communication Foundation (WCF) アダプターは BizTalk コンテキストとして ItineraryDescription.xsd (このスキーマは ESB 行程 SOAP ヘッダーの生成に使用されます) という名前のスキーマのルート名を使用して**名前**引数BizTalk コンテキストとして、スキーマのターゲット名前空間を使用して**Namespace**引数。  

  - **SOAP アダプター。** このアダプターは、SOAP ヘッダーを解析し、次の表に、BizTalk メッセージ コンテキスト プロパティを設定します。  


    |                              [プロパティ]                              |
    |----------------------------------------------------------------------|
    |                         **名前の旅程を =**                         |
    | **Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** |

    > [!NOTE]
    >  既定では、SOAP アダプタは BizTalk コンテキストとして Itinerary.xsd (このスキーマは ESB 行程 SOAP ヘッダーの生成に使用されます) という名前のスキーマのルート名を使用**名前**引数とそれに SOAP ヘッダーの名前空間を使用して、BizTalk コンテキスト**Namespace**引数。  

- メッセージ コンテキストから、元のスケジュールの値を削除します。  

- 旅行プランを検証し、日程; でそれらが null の場合、既定値を事前に特定のプロパティを設定します例えば：  

  - サービスの数が 1 未満の場合、コンポーネントは例外をスローします。  

  - コンポーネント サービスの数、識別子の値を使用して、itinerary ルート属性を設定する (**Uuid**)、開始時刻 (**BeginTime**)、および一方向または双方向の要求かどうか (**IsRequestResponse**)。  

  - コンポーネントで、サービスを検証します、識別子を設定、現在のサービス インスタンス (次に処理するサービス) を設定、および関連付けられているすべての競合回避モジュールを検証します。  

  - コンポーネントは、BizTalk のセグメントの次のプロパティを使用してスケジュールを設定します。  

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
    |**ServiceType**|いずれかに設定**オーケストレーション**または**メッセージング**|  
    |**IsRequestResponse**|いずれかに設定**True**または**False**|  
    |**ServiceState**|設定**保留中**|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a>ESB ディスパッチャー パイプライン コンポーネントのプロセスの手順  
 図 1 に示す例では、ESB ディスパッチャー パイプライン コンポーネントは、次の手順を実行します。  

- 型の任意のスケジュール オンランプ手順の実行を管理**メッセージング**旅行計画を進めます。 ESB ディスパッチャー コンポーネントは位置認識され、ある可能性があるメッセージの処理サイクルでその場所に基づくロジックを実行**入力方向の受信、送信転送**、**受信送信**、または**送信受信**します。 ESB ディスパッチャー パイプライン コンポーネントは、ESB スケジュール メッセージング サービス Esb.config ファイルで指定されたを呼び出します。 既定では、ルーティングと変換のためには、このコンポーネントの構成プロパティは、次のサービスに関連付けられました。  

  - **Microsoft.Practices.ESB.Services.Transform します。** このサービスは、受信メッセージのペイロードに対して BizTalk マップを実行します。 サービスは、変換要件を検証し、ドキュメント仕様の名前とメッセージの種類が含まれている BizTalk コンテキスト プロパティを更新します。 ESB ディスパッチャーは、変換サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。  

  - <strong>Microsoft.Practices.ESB.Services.Routing します。</strong>このサービスは適切なエンドポイントのルーティング情報を設定するリゾルバーとアダプターのプロバイダー フレームワークを使用します。 ESB ディスパッチャーは、ルーティング サービスの名前、ESB ディスパッチャー パイプライン コンポーネントの対応するプロパティに表示される場合のみ、このサービスを実行します。

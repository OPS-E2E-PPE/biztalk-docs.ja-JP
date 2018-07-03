---
title: BAM インターセプターについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc78c5ae3f653e76652373767e60ec1dcaefba8c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013443"
---
# <a name="what-is-the-bam-interceptor"></a>BAM インターセプターについて
## <a name="overview"></a>概要 

BAM インターセプターは、アプリケーションをインストルメント化して対象のデータを取得するためのオブジェクトです。 次の図は、BAM インターセプターの役割と、他の BAM コンポーネントとのやり取りを示しています。  
  
 ![](../core/media/bam-config-api.gif "bam_config_api")  
BAM インターセプター  
  
 ユーザーは、対象のデータが発生するアプリケーションのステップごとにインターセプター OnStep を呼び出し、ステップの識別子を指定して、アプリケーションで使用するデータや任意のオブジェクトを指定します。  
  
 コールバックが発生した場合に現在のステップ ID およびデータ オブジェクトをコールバック プロシージャで取得するためのコールバック関数を実装する必要があります。 BAM インターセプターの役割は基本的に、データ オブジェクトをコールバック関数に渡すという単純なものです。 データを抽出する実際のロジックはアプリケーション内に存在しています。 たとえば、データが XML メッセージの形式である場合、コールバックは XPath を使用します。 Xpath の詳細については、次を参照してください。[メッセージ割り当てにおける Xpath の使用](../core/using-xpaths-in-message-assignments.md)します。  
  
 BAM インターセプターは、構成に基づいて各ステップでどのデータを要求するかを判断します。この構成はプログラムで作成できます。 次に BAM インターセプターは取得したデータを使用して DirectEventStream または BufferedEventStream を呼び出します。これらのクラスを保持し、引数として OnStep インターセプターに渡す必要があります。  
  
 ステップごとにインターセプターを呼び出しても、リソースを消耗することはありません。 このステップでインターセプターを呼び出し、何も登録しなければ、インターセプターは直ちに戻ります。 つまり、ディスク操作、トランザクション、メモリの割り当てが行われないため、パフォーマンスは影響をほとんど受けません。 また、必要に応じて BAM が使用するためのデータを抽出することもできます。 データの抽出とデータの可用性に関連する手順のパフォーマンスに影響の実装によって異なります、`IBAMDataExtractor Interface`します。  
  
 次のコード例は、構成時および実行時のインターセプターの使用例を示しています。  
  
## <a name="configuration-time"></a>構成時  
 次のコードは、アプリケーションの recvPO ステップでインターセプターを停止し、Customer Name および Customer SSN を要求するようにインターセプターを構成する方法を示しています。  
  
```  
ActivityInterceptorConfiguration cfg= new ActivityInterceptorConfiguration ("PurchaseOrder");  
...  
cfg.RegisterDataExtraction("CustomerName",recvPO,XpathName);  
cfg.RegisterDataExtraction("CustomerSSN",recvPO,XpathSSN);  
...  
BAMInterceptor interceptor=new BAMInterceptor();  
cfg.UpdateInterceptor(interceptor);  
...  
// The interceptor instance is ready.  
```  
  
 インターセプター インスタンスを一度作成すると、インスタンスを保存して後続の実行時に使用できます。  
  
 BAM で使用するデータやマイルストーンについて、さまざまな環境設定を表すインターセプターをあらかじめ作成しておくことができます。 最高のパフォーマンスを得るには、BinaryFormatter クラスを使用してインターセプター インスタンスをシリアル化してください。  
  
## <a name="run-time"></a>実行時  
 実稼働環境で実行時にインターセプターを使用するには、次のコードを使用します。  
  
```  
// Deserialize the Interceptor that was prepared before  
...  
es=new DirectEventStream(...)  
...  
Interceptor.OnStep(recvPO, data1, es, callback)  
...  
Interceptor.OnStep(approvePO, data2, es, callback)  
...  
```  
  
 各要素の説明は次のとおりです。  
  
- *recvPO*と*approvePO*は、アプリケーションでのステップの識別に使用する任意のオブジェクトです。  
  
- *data1*と*data2*は任意のオブジェクトがその時点でして注文書の XML ドキュメントの対象のデータを含めることができます。  
  
- *es*はパフォーマンスの要件に応じて、DirectEventStream または BufferedEvent ストリーム。  
  
- *コールバック*の実装には、`IBAMDataExtractor Interface`します。  
  
  SDK サンプル[BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)、両方の構成ツール、および例ランタイム アプリケーションを含む、インターセプターの使用方法を示します。  
  
  BizTalk オーケストレーション エンジンは、BAM の追跡プロファイル エディターを使用して実行時に収集されるデータに変更できます傍受に対応します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [決定し、アクティビティ イベント ライター ロールを設定する方法](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a>参照  
 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)
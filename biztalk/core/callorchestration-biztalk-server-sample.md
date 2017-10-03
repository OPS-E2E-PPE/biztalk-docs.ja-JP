---
title: "CallOrchestration (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, calling
- examples, orchestrations
ms.assetid: 0c4194f0-c1e2-419a-8a1a-a3c96e8d2667
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6460091297e34609365989739f58ed1f04204c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="callorchestration-biztalk-server-sample"></a>CallOrchestration (BizTalk Server サンプル)
CallOrchestration サンプルは、1 つの BizTalk オーケストレーションから別のオーケストレーションを呼び出す方法を示すものです。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、1 つのオーケストレーションから別のオーケストレーションを呼び出すために、次の一連の手順を実行します。  
  
1.  1 番目のオーケストレーションで、注文書 (PO) メッセージを受信します。  
  
2.  PO の出荷金額を決定するため、1 番目のオーケストレーションから 2 番目のオーケストレーションを呼び出します。  
  
3.  2 番目のオーケストレーションで、要求された出荷金額を計算し、結果を 1 番目のオーケストレーションに返します。  
  
4.  1 番目のオーケストレーションで、返された出荷金額を PO メッセージに反映します。  
  
5.  1 番目のオーケストレーションで、更新した PO メッセージを確認用のフォルダに格納します。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルの主な目的は、1 つのオーケストレーション内から別のオーケストレーションを呼び出す方法を示すことです。 オーケストレーションの呼び出しは、ビジネス プロセスを再利用可能なコンポーネントに分割する 1 つの方法であり、 頻繁に使用するプロセスを取り出して個別のオーケストレーションを作成すれば、他でも再利用できるようになります。  
  
 このサンプルでは、**オーケストレーションの呼び出し**receivePO.odx 内の図形が findShippingPrice.odx を呼び出し、入れ子になったオーケストレーション findShippingPrice.odx を計算して、注文書を送信する前に出荷金額を返す待機順序です。 オーケストレーション findShippingPrice.odx での出荷金額の計算には、次のロジックを使用します。  
  
```  
If ( weight * shippingRate ) < minShippingPrice Then  
    shippingPrice = minShippingPrice  
Else  
    shippingPrice = weight * shippingRate  
End If  
```  
  
 サンプルの入力 PO ファイル InputPO.xml では、重みが 20 と指定されています。このため、出力 PO メッセージでは出荷金額が 10 から 20 に変更されます。  
  
> [!NOTE]
>  アトミック オーケストレーションから、長時間実行されるトランザクションを呼び出すことはできません。  
  
> [!NOTE]
>  使用方法の相違、**オーケストレーションの呼び出し**図形および**オーケストレーションの開始**図形がオーケストレーションを呼び出すときに返されるまでにネストされているオーケストレーションの呼び出し元が待機続行しています。 後者の場合、呼び出し元のオーケストレーションは別のオーケストレーションを開始した後すぐプロセス フローの次の手順に進む点です。 後者の場合、呼び出されたオーケストレーションは呼び出し元とは独立して、自身のプロセス フローを最後まで実行します。 詳細については、次を参照してください。[オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md)です。 参照してください[オーケストレーションの開始図形を構成する方法](../core/how-to-configure-the-start-orchestration-shape.md)です。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*> \Orchestrations\CallOrchestration\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|CallOrchestration.btproj、CallOrchestration.sln|このサンプルのプロジェクト ファイルとソリューション ファイルです。|  
|CallOrchestrationBinding.xml|ポートのバインドなど、自動化されたセットアップに使用されます。|  
|Cleanup.bat|アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|findShippingPrice.odx|2 番目のオーケストレーションとして動作する BizTalk オーケストレーションです。1 番目のオーケストレーション receivePO.odx から呼び出されます。|  
|InputPO.xml|ファイル PO.xsd で定義されているスキーマに準拠した、サンプルの入力 PO メッセージです。|  
|PO.xsd|サンプルの入力ファイル InputPO.xml などの受信 PO メッセージの構造を定義するスキーマです。このスキーマでは、スキーマ内の 3 つの要素すべてに対してプロパティの昇格が定義されています。|  
|PropertySchema.xsd|スキーマ PO.xsd 内の 3 つの要素すべてに対するプロパティの昇格に参加している、プロパティ スキーマ ファイルです。|  
|receivePO.odx|このサンプルで、1 番目のオーケストレーションとして動作する BizTalk オーケストレーションです。 PO メッセージを受信フォルダから取得した後、他のオーケストレーション findShippingPrice.odx を呼び出して、計算された出荷金額をメッセージに反映します。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-callorchestration-sample"></a>CallOrchestration サンプルをビルドおよび初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*> \Orchestrations\CallOrchestration\  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   CallOrchestration フォルダに、このサンプルの入力 (In) フォルダと出力 (Out) フォルダを作成します。  
  
    -   このサンプルの両方のオーケストレーションを含む [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし展開します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
    -   受信場所を有効にし、送信ポートを開始します。  
  
> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-callorchestration-sample"></a>CallOrchestration サンプルを実行するには  
  
1.  ファイル InputPO.xml を In フォルダにコピーします。  
  
2.  更新された XML PO ファイルが Out フォルダに作成されることを確認します。 このファイルには元の PO メッセージが含まれます。このメッセージには、前述のように計算後の出荷費用が反映されています。 このファイルの名前の形式が\< *MessageID*> .xml、場所 *\<MessageID >*メッセージを一意に識別する GUID が生成されます。  
  
## <a name="uninstalling-this-sample"></a>このサンプルのアンインストール  
  
#### <a name="to-uninstall-the-callorchestration-sample"></a>CallOrchestration サンプルをアンインストールするには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*> \Orchestrations\CallOrchestration\  
  
2.  Cleanup.bat を実行します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション (BizTalk Server Samples フォルダ)](../core/orchestrations-biztalk-server-samples-folder.md)
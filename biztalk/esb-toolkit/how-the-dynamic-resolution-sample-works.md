---
title: 動的解決サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bab7a46a02dc080fa27b9df2b30614bc8a45c6e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976435"
---
# <a name="how-the-dynamic-resolution-sample-works"></a>動的解決サンプルのしくみ
動的解決サンプルでは、前のセクションで説明されているすべてのメッセージの例の ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントを使用します。  

 一方向メッセージング シナリオでは、例は、STATIC、BRE、または XPATH 競合回避モジュールを使用してエンドポイントを解決し、ファイル、FTP、または MQSeries ファイルからのプロトコルを仲介します。  

 双方向メッセージング シナリオでは、例は、STATIC、BRE、UDDI、または XPATH 競合回避モジュールを使用してエンドポイントを解決しを SOAP または Wcf-basichttp SOAP からプロトコルを仲介します。 さらに、例は解決して、解決の結果を確認するメッセージ コンテキスト プロパティとメッセージ本文に含まれているファクトを使用して BRE リゾルバーを使用して、Microsoft BizTalk マップを実行します。  

 解決プロセスの結果は、双方向のすべての例が、ESB を自分のメッセージを送信します。CanadianServices Web サービスがあるhttp://localhost/ESB.CanadianServices/SubmitPOService.asmxします。 さらに、解決の結果に応じて、例を実行しますか、 **submitOrder**または**submitPurchase**アクション。 さらに、ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントには、BizTalk マップを指定されているか、解決操作に応じて動的に実行します。  

 図 1 は、構成されている、DynamicResolutionReqResp_SOAP のパイプラインは受信場所を示します。  

 ![動的解決のパイプライン](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6 DynamicResolutionPipelines")  

 **図 1**  

 **動的解決サンプル アプリケーションの場所を受信する、DynamicResolutionReqResp_SOAP の構成済みのパイプライン**  

 図 2 は、ESB ディスパッチャー逆アセンブラーを使用する ESBReceiveXML コンポーネントのインスタンスごとにプロパティを示します。  

 ![動的解決の受信 XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6 DynamicResolutionReceiveXML")  

 **図 2**  

 **動的解決サンプル アプリケーションの ESBReceiveXML パイプラインでコンポーネントのインスタンスごとのプロパティ**  

 図 2 に、次のプロパティが表示されます。  

- **有効になっている**します。 このプロパティは、パイプラインがアクティブかどうかを決定します。 設定されている場合**False**メッセージが処理を行わなくても通過します。  

- **エンドポイント**します。 このプロパティは、接続文字列を読み込むには、どの競合回避モジュールを判断するために使用して、エンドポイント構成を指定します。  

- **MapName**します。 このプロパティは、どの競合回避モジュールを読み込むとを実行するには、どの BizTalk マップを決定するために使用する接続文字列です。 競合回避モジュールの接続文字列ではなく、マップの完全修飾名を指定できます。  

- **検証**です。 設定すると**True** (既定の設定、)、ESB ディスパッチャー逆アセンブラー コンポーネントに指示するマップで定義されている送信元スキーマに対してソース メッセージの検証に ESB 変換サービスは解決され、実行します。  

  図 3 は、ESB ディスパッチャーを使用する ESBSendPassthrough コンポーネントのインスタンスごとにプロパティを示します。  

  ![動的解決の送信パススルー](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6 DynamicResolutionSendPassthrough")  

  **図 3**  

  **動的解決サンプル アプリケーションの ESBSendPassthrough パイプラインでコンポーネントのインスタンスごとのプロパティ**  

  図 3 に、次のプロパティが表示されます。  

- **有効になっている**します。 このプロパティは、パイプラインがアクティブかどうかを決定します。 設定されている場合**False**メッセージが処理を行わなくても通過します。  

- **エンドポイント**します。 このプロパティは、どの競合回避モジュールをロードし、エンドポイント構成を決定するために使用する接続文字列です。  

- **MapName**します。 このプロパティは、どの競合回避モジュールを読み込むとを実行するには、どの BizTalk マップを決定するために使用する接続文字列です。 マップの完全修飾名は、競合回避モジュールの接続文字列の代わりに使用できます。  

- **検証**です。 設定すると**True** (既定の設定、)、ESB ディスパッチャー逆アセンブラー コンポーネントに指示するマップで定義されている送信元スキーマに対してソース メッセージの検証に ESB 変換サービスは解決され、実行します。

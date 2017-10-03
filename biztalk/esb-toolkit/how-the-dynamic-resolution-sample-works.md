---
title: "動的解決のサンプルの動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe7d7b473482c432c8e3ae9ca48cab414a9e9573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-dynamic-resolution-sample-works"></a>動的解決のサンプルのしくみ
動的解決サンプルでは、前のセクションで説明されているすべてのメッセージ例については、ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントを使用します。  
  
 一方向のメッセージング シナリオでは、この例は、STATIC、BRE、または XPATH 競合回避モジュールを使用してエンドポイントを解決し、ファイル、FTP、または MQSeries には、ファイルからのプロトコルを仲介する機能します。  
  
 双方向のメッセージング シナリオでは、この例は、STATIC、BRE、UDDI、または XPATH 競合回避モジュールを使用してエンドポイントを解決し、SOAP または Wcf-basichttp SOAP からプロトコルを仲介する機能します。 さらに、例は解決し、メッセージ コンテキスト プロパティと、メッセージ本文に含まれるファクトを使用して、解決の結果を決定する BRE リゾルバーを使用して、Microsoft BizTalk マップを実行します。  
  
 解決プロセスの結果は、双方向のすべての例が、ESB にそのメッセージを送信します。Http://localhost/ESB.CanadianServices/SubmitPOService.asmx にある CanadianServices Web サービスです。 さらに、解決の結果に応じて、例を実行するか、 **submitOrder**または**submitPurchase**アクション。 さらに、ESB ディスパッチャーの逆アセンブラー パイプライン コンポーネントでは、動的に指定されたまたは解決済みのアクションによって、BizTalk マップを実行します。  
  
 図 1 は、構成されたパイプライン、DynamicResolutionReqResp_SOAP の受信場所を示します。  
  
 ![動的解決のパイプライン](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6 DynamicResolutionPipelines")  
  
 **図 1**  
  
 **構成されたパイプライン、DynamicResolutionReqResp_SOAP の受信動的解決のサンプル アプリケーションの場所**  
  
 図 2 は、ESB ディスパッチャー逆アセンブラーを使用する ESBReceiveXML コンポーネントのインスタンスごとにプロパティを示します。  
  
 ![動的解決の受信 XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6 DynamicResolutionReceiveXML")  
  
 **図 2**  
  
 **動的解決のサンプル アプリケーションの ESBReceiveXML パイプライン内のコンポーネントのインスタンスごとにプロパティ**  
  
 図 2 には、次のプロパティを示します。  
  
-   **有効になっている**です。 このプロパティは、パイプラインがアクティブかどうかを判断します。 設定されている場合**False**、処理されずにメッセージが通過します。  
  
-   **エンドポイント**です。 このプロパティは、接続文字列を読み込むには、どの競合回避モジュールを決定するために使用し、エンドポイントの構成を指定します。  
  
-   **MapName**です。 このプロパティは、どの競合回避モジュールを読み込むと、BizTalk マップを実行するために使用する接続文字列です。 競合回避モジュールの接続文字列の代わりに、マップの完全修飾名があります。  
  
-   **検証**です。 設定すると**True** (既定の設定) を ESB ディスパッチャー逆アセンブラー コンポーネントに指示、ESB 変換サービスは、マップで定義されている送信元スキーマに対してソース メッセージの検証には解決し、実行します。  
  
 図 3 は、ESB ディスパッチャーを使用する ESBSendPassthrough コンポーネントのインスタンスごとにプロパティを示します。  
  
 ![動的解決の送信パススルー](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6 DynamicResolutionSendPassthrough")  
  
 **図 3**  
  
 **動的解決のサンプル アプリケーションの ESBSendPassthrough パイプライン内のコンポーネントのインスタンスごとにプロパティ**  
  
 図 3 に、次のプロパティを示します。  
  
-   **有効になっている**です。 このプロパティは、パイプラインがアクティブかどうかを判断します。 設定されている場合**False**、処理されずにメッセージが通過します。  
  
-   **エンドポイント**です。 このプロパティは、ロード テストとエンドポイント構成にどの競合回避モジュールを決定するために使用する接続文字列です。  
  
-   **MapName**です。 このプロパティは、どの競合回避モジュールを読み込むと、BizTalk マップを実行するために使用する接続文字列です。 マップの完全修飾名は、競合回避モジュールの接続文字列の代わりに使用できます。  
  
-   **検証**です。 設定すると**True** (既定の設定) を ESB ディスパッチャー逆アセンブラー コンポーネントに指示、ESB 変換サービスは、マップで定義されている送信元スキーマに対してソース メッセージの検証には解決し、実行します。
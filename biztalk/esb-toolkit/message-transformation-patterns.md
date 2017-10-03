---
title: "メッセージ変換パターン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aef41642-d33b-4878-be65-ef336530647f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: badfb450b51aebbdf81b2beccdeac98fc549bcb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-transformation-patterns"></a>メッセージ変換パターン
メッセージ変換パターンは、追加の処理、またはメッセージの送信先となるサービスの必要なドキュメント形式に一致するメッセージを変換するための実証済みのガイドラインを定義します。 メッセージは、受信したメッセージの構造が、予想される標準ではないため、または、メッセージは、標準以外の形式から XML に変換する必要がありますので、変換を必要があります。  
  
## <a name="message-translator"></a>メッセージ トランスレーター  
 メッセージ トランスレーター パターンでは、互換性のないデータ形式を使用するシステム間の通信用のソリューションを定義します。 たとえば、クライアント アプリケーションは、追加の処理を行う前に、XML に変換する必要がありますフラット ファイル要求メッセージを送信することがあります。 このパターンの詳細については、次を参照してください。[メッセージ トランスレーター](http://go.microsoft.com/fwlink/?LinkId=186845) ([http://go.microsoft.com/fwlink/?LinkId=186845](http://go.microsoft.com/fwlink/?LinkId=186845)) エンタープライズ統合パターン サイトです。  
  
 行程デザイナーでは、このパターンの実装の組み合わせでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]変換サービスと 1 つの競合回避モジュール。 Itinerary 変換サービスは、変換に必要な成果物を定義する競合回避モジュールのプロパティを使用してメッセージに変換するためです。 リゾルバーの実装は、変換の設定は、競合回避モジュールの構成によって静的または動的に定義できますを提供する責任です。  
  
 メッセージ トランスレーター パターンの実装例については、次のリソースを参照してください。  
  
-   [インストールして、Itinerary ランプでサンプルを実行します。](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [方法: メッセージを変換して、要求-応答メッセージ交換パターンを使用してサービス エンドポイントへのルート](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
## <a name="normalizer"></a>ノーマライザー  
 ノーマライザー パターンは、データ モデルの変換パターンの拡張機能です。 このパターンは、さまざまな形式で複数のソースから受信したメッセージは意味は同じですが、メッセージが到着したソリューションを定義します。 このパターンの詳細については、次を参照してください。[ノーマライザー](http://go.microsoft.com/fwlink/?LinkId=186847) ([http://go.microsoft.com/fwlink/?LinkId=186847](http://go.microsoft.com/fwlink/?LinkId=186847)) エンタープライズ統合パターン サイトです。  
  
 行程デザイナーでは、このパターンの実装の組み合わせでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]変換サービスと 1 つの競合回避モジュール。 Itinerary 変換サービスは、変換に必要な成果物を定義する競合回避モジュールのプロパティを使用してメッセージに変換するためです。 リゾルバーの実装は、動的にメッセージの指定した型の適切な Microsoft BizTalk マップを解決します。  
  
 ノーマライザーのパターンの実装例については、次を参照してください。、[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。  
  
## <a name="content-enricher"></a>コンテンツ Enricher  
 コンテンツ Enricher パターンでは、メッセージを適切に処理する、ターゲット システムに必要なすべてのデータが受信したメッセージに含まれませんソリューションを定義します。 たとえば、送信側のサービスは、冗長な状態コードを使わずに ZIP コードを含めることができますが、受信側サービスは状態コードと郵便; の両方を含むメッセージが必要です。受信側のサービスが受信したメッセージを処理する前に、追加のデータが必要です。 このパターンの詳細については、次を参照してください。[コンテンツ Enricher](http://go.microsoft.com/fwlink/?LinkId=186848) ([http://go.microsoft.com/fwlink/?LinkId=186848](http://go.microsoft.com/fwlink/?LinkId=186848)) エンタープライズ統合パターン サイトです。  
  
 コンテンツ Enricher パターンの実装例については、次を参照してください。、[をインストールすると、メッセージ強化サンプルを実行している](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)アプリケーションです。
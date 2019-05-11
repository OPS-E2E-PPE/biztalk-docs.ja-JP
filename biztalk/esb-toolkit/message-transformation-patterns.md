---
title: メッセージ変換パターン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aef41642-d33b-4878-be65-ef336530647f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87df85f41e15857cf73e82e437009574861345df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395900"
---
# <a name="message-transformation-patterns"></a>メッセージ変換パターン
メッセージ変換パターンでは、追加の処理、またはメッセージの送信先となるサービスの必要なドキュメント形式と一致するメッセージを変換するための実績のあるガイドラインを定義します。 メッセージは、受信したメッセージの構造が予想される標準ではないため、または、メッセージは、非標準形式から XML に変換する必要がありますので、変換を必要があります。  
  
## <a name="message-translator"></a>メッセージ トランスレーター  
 メッセージ トランスレーター パターンでは、互換性のないデータ形式を使用するシステム間の通信用のソリューションを定義します。 たとえば、クライアント アプリケーションは、追加の処理を行う前に、XML に変換する必要がありますフラット ファイル要求メッセージを送信することがあります。 このパターンの詳細については、次を参照してください。[メッセージ トランスレーター](http://go.microsoft.com/fwlink/?LinkId=186845) ([http://go.microsoft.com/fwlink/?LinkId=186845](http://go.microsoft.com/fwlink/?LinkId=186845))、エンタープライズ統合パターン サイト。  
  
 旅行プラン デザイナーでは、このパターンの実装の組み合わせでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]変換サービスと 1 つの競合回避モジュール。 スケジュール オンランプ変換サービスは、変換に必要な成果物を定義する競合回避モジュール プロパティを使用して、メッセージの変換を行います。 リゾルバーの実装は、変換の設定は、競合回避モジュールの構成によっては静的または動的に定義できますを提供する責任を負います。  
  
 メッセージ トランスレーター パターンの実装例については、次のリソースを参照してください。  
  
-   [スケジュール オンランプ サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [方法: メッセージと要求-応答のメッセージ交換パターンを使用してサービス エンドポイントへのルートを変換します。](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
## <a name="normalizer"></a>ノーマライザー  
 ノーマライザー パターンは、モデルのデータ変換パターンの拡張機能です。 このパターンは、さまざまな形式で複数のソースから受信したメッセージと同じ意味ですが、メッセージの到着のソリューションを定義します。 このパターンの詳細については、次を参照してください。[ノーマライザー](http://go.microsoft.com/fwlink/?LinkId=186847) ([http://go.microsoft.com/fwlink/?LinkId=186847](http://go.microsoft.com/fwlink/?LinkId=186847))、エンタープライズ統合パターン サイト。  
  
 旅行プラン デザイナーでは、このパターンの実装の組み合わせでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]変換サービスと 1 つの競合回避モジュール。 スケジュール オンランプ変換サービスは、変換に必要な成果物を定義する競合回避モジュール プロパティを使用して、メッセージの変換を行います。 リゾルバーの実装は、メッセージの種類を指定の適切な Microsoft BizTalk マップを動的に解決を担当します。  
  
 ノーマライザーのパターンの実装例については、次を参照してください。、[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。  
  
## <a name="content-enricher"></a>コンテンツのエンリッチャー  
 コンテンツ エンリッチャー パターンでは、メッセージを適切に処理する、ターゲット システムに必要なすべてのデータが受信したメッセージに含まれませんソリューションを定義します。 たとえば、送信側のサービスは、冗長な状態コードを使わずに ZIP コードを含めることができますが、受信側のサービスに必要な状態コードと ZIP コード; の両方が含まれるメッセージ受信側のサービスが受信メッセージを処理する前に、追加のデータが必要です。 このパターンの詳細については、次を参照してください。[コンテンツ エンリッチャー](http://go.microsoft.com/fwlink/?LinkId=186848) ([http://go.microsoft.com/fwlink/?LinkId=186848](http://go.microsoft.com/fwlink/?LinkId=186848))、エンタープライズ統合パターン サイト。  
  
 コンテンツのエンリッチャー パターンの実装例については、次を参照してください。、[をインストールすると、メッセージ強化サンプルを実行している](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)アプリケーション。
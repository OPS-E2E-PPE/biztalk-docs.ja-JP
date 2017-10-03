---
title: "ESB Itinerary フォワーダー コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 607cc8a0-4964-4751-baca-c3329983c98b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61643423021701186745ab4275520cb14d3ceca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-itinerary-forwarder-component"></a>ESB Itinerary フォワーダー コンポーネント
日程が複数の Web サービスを呼び出す必要があります順番に、ESB 行程フォワーダー コンポーネントが使用されます。 コンポーネントを使用するのには、受信パイプライン、双方向出口の応答側に関連付けられています。  
  
## <a name="installation"></a>インストール  
 ESB コアを自動的にインストールするとインストール、**行程フォワーダー**コンポーネントを BizTalk Server パイプライン コンポーネント フォルダーでします。  
  
## <a name="how-it-works"></a>しくみ  
 Microsoft BizTalk の受信のように、メッセージは、メッセージ ボックス データベースに公開を介して、双方向メッセージ受信ポート、インスタンスのサブスクリプションを作成します。 このサブスクリプションから成る、 **EpmRRCorrelationToken**昇格されたプロパティと**RouteDirectToTP**プロパティを昇格します。 サブスクライバー (オーケストレーションまたは双方向の送信ポート) には、応答メッセージが返されますとこれらの昇格させたプロパティ、サブスクリプションに一致応答が受信ポートの送信パイプラインを通じて直ちに返されます。  
  
 ESB 行程フォワーダー必要がありますパイプラインで使用、応答を双方向出口のオフ ランプが要求-応答の Web サービスを呼び出すことです。 コンポーネントが変更することによって、一般的な BizTalk プロセスに干渉、 **RouteDirectToTP**応答は返されません、開始するようになり、False に昇格させたプロパティがポートを受信します。 旅行計画の最後の手順に達すると、 **RouteDirectToTP**にプロパティが変更された**True**、発信側で増加する結果を返すためです。  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a>ESB Itinerary フォワーダー コンポーネントを使用します。  
 ESB ItineraryForwarder コンポーネントは、受信パイプラインに追加し、双方向出口の応答部分でパイプラインを使用します。 作成日程複数の Web サービスのチェーンされている変換 itinerary のサービスの有無前に、または、サービス間でします。 ESB 行程フォワーダー コンポーネントを使用する方法の例は、次を参照してください。、[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)です。
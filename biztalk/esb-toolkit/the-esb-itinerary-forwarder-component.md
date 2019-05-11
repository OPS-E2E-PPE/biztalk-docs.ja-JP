---
title: ESB スケジュール フォワーダー コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 607cc8a0-4964-4751-baca-c3329983c98b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e23368b1d74a2842659332d2c545b93e24386455
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399787"
---
# <a name="the-esb-itinerary-forwarder-component"></a>ESB スケジュール フォワーダー コンポーネント
ESB スケジュール フォワーダー コンポーネントは、スケジュールは、複数の Web サービスを呼び出す必要があります順番に使用されます。 コンポーネントを使用するのには、受信パイプラインは双方向オフ-ごとの傾斜増加の応答側に関連付けられています。  
  
## <a name="installation"></a>インストール  
 ESB コアを自動的にインストールするインストール、**スケジュール フォワーダー**コンポーネントを BizTalk Server パイプライン コンポーネント フォルダーでします。  
  
## <a name="how-it-works"></a>しくみ  
 Microsoft BizTalk が受信すると、メッセージがメッセージ ボックス データベースに公開されると、双方向でメッセージを受信ポート、インスタンスのサブスクリプションが作成されます。 このサブスクリプションから成る、 **EpmRRCorrelationToken**プロパティを昇格と**RouteDirectToTP**プロパティを昇格します。 サブスクライバー (オーケストレーションまたは双方向の送信ポート) には、応答メッセージが返される、ときにこれらの昇格させたプロパティは、サブスクリプションを照合し、応答がすぐに受信ポートの送信パイプラインを通じて返されます。  
  
 ESB スケジュール フォワーダーを付ける応答パイプラインでの双方向オフ-ごとの傾斜増加オフ ランプが要求-応答 Web サービスを呼び出すことです。 変更することで、一般的な BizTalk プロセス コンポーネントと競合、 **RouteDirectToTP**確認応答を開始する返されませんが、昇格させたプロパティを False、受信ポート。 旅行プランの最後の手順に達すると、 **RouteDirectToTP**にプロパティが変更された**True**、発信側に着手する結果を返すためです。  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a>ESB スケジュール フォワーダー コンポーネントを使用します。  
 ESB ItineraryForwarder コンポーネントを受信パイプラインに追加し、双方向オフ-ごとの傾斜増加の応答部分でパイプラインを使用します。 スケジュールを作成チェーンされている複数の Web サービスは、変換のスケジュール サービスの有無の前に、またはサービスの間で。 ESB スケジュール フォワーダー コンポーネントを使用する方法の例は、次を参照してください。、[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)します。
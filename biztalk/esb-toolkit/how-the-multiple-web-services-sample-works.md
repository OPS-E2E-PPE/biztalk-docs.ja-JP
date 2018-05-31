---
title: 複数の Web サービスのサンプルの動作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16680ca7-16cc-47df-8c39-a3311d468a46
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3d9faf350654be69015ea940b6b4f034d4de74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294162"
---
# <a name="how-the-multiple-web-services-sample-works"></a>複数の Web サービス サンプルのしくみ
複数の Web サービス サンプルでは、2 つの独立した手法を使用して、呼び出し元に適切な結果を返す直列に複数の Web サービスを呼び出します。 1 つのメソッドでは、応答パイプラインのカスタム パイプライン コンポーネントとその他のメソッド、カスタム双方向ルーティング オーケストレーションに基づく itinerary サービスを使用して web 要求/応答呼び出しを完了する出口呼び出しの要件をバイパスします。サービス。  
  
 カスタム パイプライン コンポーネントのメソッドは、フォワーダーのパイプライン コンポーネントを使用します。 このコンポーネントは、条件付きで、Microsoft BizTalk が itinerary のすべてのサービスが処理されるまで、入り口の送信パイプラインにメッセージをルーティングすることを防止するプロパティを昇格させます。  
  
 カスタム オーケストレーションに基づくサービス メソッドは、ESB に含まれている TwoWayRouting オーケストレーションを使用します。\Source\Samples\MultipleWebSerivces\Source\ESB MultipleWebServices.Orchestrations プロジェクトです。MultipleWebServices.Orchestrations フォルダーです。 このサービスは、双方向の Web サービスのエンドポイント アドレスを決定する関連付けの競合回避モジュールを処理します。 という名前を Web サービスにメッセージを送信し、オーケストレーションに結果を返す RoutingPort 動的 Solict-応答送信ポートを構成します。 オーケストレーションは、旅行計画を進めるし、メッセージ ボックスに、結果のメッセージを返します。  
  
 サンプルに含まれている旅程は、メッセージ フローの次の旅行計画を維持するのにこれらのメソッドの一方または両方を使用します。 詳細については、次を参照してください。 [、サンプル複数 Web Services 旅程](../esb-toolkit/the-sample-multiple-web-services-itineraries.md)です。
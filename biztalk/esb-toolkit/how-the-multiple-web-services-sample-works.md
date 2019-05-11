---
title: 複数の Web サービスのサンプルのしくみ |Microsoft Docs
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
ms.openlocfilehash: 2a67e14115d404f523219b2e171f1abfba38b220
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249774"
---
# <a name="how-the-multiple-web-services-sample-works"></a>複数の Web サービス サンプルのしくみ
複数の Web サービス サンプルでは、2 つの独立した手法を使用して、シリアルでを呼び出し元に適切な結果を返すことながら複数の Web サービスを呼び出します。 1 つのメソッドが応答パイプラインでは、カスタム パイプライン コンポーネントを使用し、もう一方のメソッドをカスタム双方向ルーティング オーケストレーションに基づく itinerary サービスを使用して web 要求/応答の呼び出しを完了するランプ オフ呼び出しの要件をバイパスします。サービス。  
  
 カスタム パイプライン コンポーネントのメソッドは、フォワーダーのパイプライン コンポーネントを使用します。 このコンポーネントは、条件付きで Microsoft BizTalk がスケジュールのすべてのサービスが処理されるまでのランプの送信パイプラインにメッセージをルーティングするを防ぐためのプロパティを昇格させます。  
  
 カスタム オーケストレーションに基づくサービスのメソッドは、ESB に含まれている TwoWayRouting オーケストレーションを使用します。\Source\Samples\MultipleWebSerivces\Source\ESB MultipleWebServices.Orchestrations プロジェクトです。MultipleWebServices.Orchestrations フォルダーです。 このサービスは、双方向の Web サービスのエンドポイント アドレスを決定する関連付けの競合回避モジュールを処理します。 という名前の Web サービスにメッセージを送信し、オーケストレーションに結果を返す RoutingPort 動的 Solict-応答送信ポートを構成します。 オーケストレーションは、旅行計画を進めるし、メッセージ ボックスに、結果のメッセージを返します。  
  
 サンプルに含まれているスケジュールは、旅行プランを次のメッセージ フローを維持すること、これらのメソッドの一方または両方を使用します。 詳細については、次を参照してください。 [、サンプル複数 Web Services 日程](../esb-toolkit/the-sample-multiple-web-services-itineraries.md)します。
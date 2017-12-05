---
title: "日程を使用するカスタム オーケストレーション サービスの実行を定義する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9336969db2c90168bf7c398276205043b06504ce
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a>日程を使用するカスタム オーケストレーション サービスの実行を定義します。
このユース ケースでは、処理のために送信メッセージには、サービスを実行して、解決の要件の一覧を記述する itinerary の SOAP ヘッダーが含まれています。 旅行計画は、1 つ以上のカスタム オーケストレーションまたはメッセージが通過する、処理中のプロセスを指定します。 カスタム オーケストレーションでは、旅行計画し、メッセージ コンテキストで公開されるその他のカスタム プロパティのフル コントロール アクセスを許可します。 必要に応じて、itinerary は変換の要件およびメッセージのエンドポイントを決定する動的な解決策の情報を含めることができます。 図 1 は、プロセスの概略を示します。  
  
 ![カスタム オーケストレーションを定義する](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3 DefiningCustomOrchestration")  
  
 **図 1**  
  
 **日程を使用するカスタム オーケストレーション サービスの実行を定義します。**  
  
 含まれている行程入り口サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 一連の ESB と BizTalk Server が、入力メッセージを処理する方法を定義する手順は itinerary 解像度、ルーティング、およびサービスの呼び出し命令が含まれる日程を作成する方法を示します。 一方向と要求-応答のサンプルが含まれます。  
  
 詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。
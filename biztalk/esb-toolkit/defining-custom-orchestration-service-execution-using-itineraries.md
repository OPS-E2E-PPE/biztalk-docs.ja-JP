---
title: カスタム オーケストレーション実行スケジュールを定義する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5c475178865f0ebe990dd75c87b29e75ab47753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394648"
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a>カスタム オーケストレーション実行スケジュールを定義します。
このユース ケースでは、処理のために送信されたメッセージには、サービスを実行して、解決の要件の一覧を記述するスケジュールの SOAP ヘッダーが含まれています。 旅行プランは、1 つまたは複数のカスタム オーケストレーションまたはメッセージが処理サイクルの間に通過するプロセスを指定します。 カスタム オーケストレーションでは、旅行プランとその他のカスタム プロパティをメッセージ コンテキストで公開されているフル コントロールがあります。 必要に応じて、旅行プランは、変換の要件と、メッセージのエンドポイントを決定する動的解決の情報を含めることができます。 図 1 は、プロセスの概略を示します。  
  
 ![カスタム オーケストレーションを定義する](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3 DefiningCustomOrchestration")  
  
 **図 1**  
  
 **カスタム オーケストレーション実行スケジュールを定義します。**  
  
 含まれている行程導入サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 一連の ESB と BizTalk Server が、入力メッセージを処理する方法を定義するスケジュールのステップとして解像度、ルーティング、およびサービスの呼び出し命令を含むスケジュールを作成する方法を示します。 一方向および要求-応答のサンプルが含まれています。  
  
 詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。
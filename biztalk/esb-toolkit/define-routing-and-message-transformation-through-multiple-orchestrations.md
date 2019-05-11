---
title: ルーティングの定義と、メッセージにより、スケジュールを使用して複数のオーケストレーションの変換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63141b83-798e-40d0-908d-6b7649923e69
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb39d156827dd88d043c86cf3fa27cf82889d9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394654"
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a>定義のルーティングとスケジュールを使用して複数のオーケストレーションによるメッセージの変換
このユース ケースでは、処理のために送信されたメッセージには、サービスを実行して、解決の要件の一覧を記述するスケジュールの SOAP ヘッダーが含まれています。 旅行プランでは、メッセージが処理サイクルの間に通過する 1 つまたは複数の Microsoft BizTalk Server オーケストレーションを指定します。 必要に応じて、旅行プランは、エンドポイントまたはメッセージの変換の要件を決定するため、動的なルーティング情報を含めることができます。 図 1 は、プロセスの概略を示します。  
  
 ![複数のオーケストレーションのルーティングを定義する](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3 DefiningRoutingMultipleOrchestrations")  
  
 **図 1**  
  
 **スケジュールを使用して複数のオーケストレーションによるルーティングおよびメッセージの変換を定義します。**  
  
 含まれている行程導入サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 解像度、ルーティングが含まれているスケジュールを作成し、呼び出し命令をサービスとして、一連のスケジュールの手順を定義する方法を示す方法、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]し、BizTalk Server は、入力メッセージを処理します。 一方向および要求-応答のサンプルが含まれています。  
  
 詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。
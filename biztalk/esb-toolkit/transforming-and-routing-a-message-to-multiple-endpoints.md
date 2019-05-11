---
title: 変換と、複数のエンドポイントへのメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c05d76c9f964ccfd326ed5091152545ee647a64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399613"
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a>変換と、複数のエンドポイントへのメッセージのルーティング
このユース ケースで、ESB は、旅行プランの Web サービスに着手を通じて送信されるメッセージの変換を実行します。 動的解決の参照は、マップの名前を決定し、受信メッセージを変換します。 さらに、旅行計画には、n 個のスケジュール サービスを動的に解決して、変換されたメッセージをルーティングするターゲット エンドポイントを指定します。 図 1 に示すように、すべての操作は、メッセージング層で発生します。  
  
 ![複数のエンドポイントの変換](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3 TransformingMultipleEndpoints")  
  
 **図 1**  
  
 **変換と、複数のエンドポイントへのメッセージのルーティング**  
  
 動的解決サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 ESB ディスパッチの逆アセンブラー コンポーネントでは具体的には、ESB パイプライン コンポーネントを使用する方法を示しますを使用せず、メッセージング レベルでのマップを動的にエンドポイントの場所を解決するには、ルーティング プロパティを設定し、解決して BizTalk Server を実行します。オーケストレーションです。 一方向と双方向の両方のメッセージング パターンも示します。  
  
 詳細については、次を参照してください。[をインストールすると、動的解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)と[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)します。
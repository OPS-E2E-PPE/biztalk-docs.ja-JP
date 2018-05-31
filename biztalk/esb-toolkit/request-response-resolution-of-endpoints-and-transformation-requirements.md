---
title: 要求-応答の解決エンドポイントおよび変換の要件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1bfdae-2651-402c-b164-16db663aaa95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72f442f1d9df457a3c1384f1d717e29c17b433f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294570"
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a>要求-応答の解決エンドポイントおよび変換の要件
このユース ケースでは、クライアント アプリケーションは、ランプで要求メッセージを送信し、応答を受信します。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]クライアントとターゲットのサービス エンドポイント間の媒介として機能し、図に示すように、動的なメッセージの変換と、入り口構成に従ってルーティングを実行する、ESB 競合回避モジュールとアダプター フレームワークを使用1。  
  
 ![要求 &#45;エンドポイントの応答の解決](../esb-toolkit/media/ch3-requestresponse.gif "Ch3 RequestResponse")  
  
 **図 1**  
  
 **要求-応答の解決エンドポイントおよび変換の要件**  
  
 動的解決サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 動的な変換と XML Path Language (XPath)、Universal Description, Discovery, and Integration (UDDI)、静的を使用する双方向のシナリオまたは BizTalk Server のビジネス ルール エンジンのポリシーの解決を適用する方法を示します。  
  
 詳細についてで説明する双方向のメッセージング シナリオを参照してください。[をインストールすると、動的の解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)です。
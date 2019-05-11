---
title: エンドポイントと変換の要件の要求-応答の解決 |Microsoft Docs
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
ms.openlocfilehash: 01ef1004d922fa8933ad021e958207ee36c91db6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400211"
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a>エンドポイントと変換の要件の要求-応答の解決
このユース ケースでは、クライアント アプリケーションは、ランプの要求メッセージを送信して、応答を受信します。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は、クライアントとターゲット サービスのエンドポイント間の媒介として機能し、ESB リゾルバーとアダプター フレームワークを使用して、図に示すように、動的なメッセージの変換と、ランプの構成に従ってルーティングを実行するには1。  
  
 ![要求&#45;エンドポイントの応答の解決](../esb-toolkit/media/ch3-requestresponse.gif "Ch3 RequestResponse")  
  
 **図 1**  
  
 **エンドポイントと変換の要件の要求-応答の解決**  
  
 動的解決サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 動的変換と XML Path Language (XPath)、Universal Description, Discovery, and Integration (UDDI)、静的を使用して双方向のシナリオまたは BizTalk Server ビジネス ルール エンジンでのポリシーの解決を適用する方法を示します。  
  
 詳細については、双方向メッセージング シナリオで説明を参照してください。[をインストールすると、動的解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)します。
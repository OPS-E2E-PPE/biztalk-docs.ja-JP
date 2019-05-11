---
title: サービス仲介パターン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfda54db-75fa-4bc2-9f48-11d8b3cde65b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b11d58393ea90f840a1193106c4c01376a5c1a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268943"
---
# <a name="service-mediation-patterns"></a>サービス仲介パターン
## <a name="vetovetro"></a>拒否/VETRO  
 VETRO パターンは、受信したときに、メッセージで行われた複数の操作を結合する一般的な複合パターンです。 用語 VETRO は、検証、強化、変換、ルート操作を表す頭字語です。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、受信場所に関連付けられたパイプライン内の個々 の段階としてこれらのアクションを処理することができます。 これらの各段階を実装する方法の詳細については、主要なシナリオおよび開発タスクを参照してください。  
  
## <a name="request-response"></a>要求-応答  
 要求-応答パターンでは、要求をサービス、またはパーティに送信しますがメッセージし、応答メッセージを転送先サービスからの戻り値が必要ですが、ソリューションを定義します。 このパターンの詳細については、次を参照してください。[要求/応答](http://go.microsoft.com/fwlink/?LinkId=186849)([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849))、エンタープライズ統合パターン サイト。  
  
 このパターンを実装する方法の詳細については、次のリソースを参照してください。  
  
-   [方法: メッセージと要求-応答のメッセージ交換パターンを使用してサービス エンドポイントへのルートを変換します。](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
-   [スケジュール オンランプ サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)
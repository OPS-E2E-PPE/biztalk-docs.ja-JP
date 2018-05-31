---
title: 仲介のパターンをサービス |Microsoft ドキュメント
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
ms.openlocfilehash: af76e6c123a3a273bc2e100b1008f40523762695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294634"
---
# <a name="service-mediation-patterns"></a>仲介のパターンでサービス
## <a name="vetovetro"></a>拒否/VETRO  
 VETRO パターンを受信すると、メッセージで実行される複数の操作を結合する一般的な複合パターンです。 用語 VETRO は、検証、強化、変換、ルート操作を表す頭字語です。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、受信場所に関連付けられているパイプライン内の個々 の段階としてこれらのアクションを処理することができます。 これらの各段階を実装する方法の詳細については、主要なシナリオと開発タスクを参照してください。  
  
## <a name="request-response"></a>要求-応答  
 要求-応答パターンでは、要求をサービスまたはパーティの送信がメッセージし、転送先サービスから応答メッセージを戻り値が必要ですが、ソリューションを定義します。 このパターンの詳細については、次を参照してください。[要求/応答](http://go.microsoft.com/fwlink/?LinkId=186849)([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849)) エンタープライズ統合パターン サイトです。  
  
 このパターンを実装する方法の詳細については、次のリソースを参照してください。  
  
-   [方法: メッセージを変換して、要求-応答メッセージ交換パターンを使用してサービス エンドポイントへのルート](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
-   [インストールして、Itinerary ランプでサンプルを実行します。](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)
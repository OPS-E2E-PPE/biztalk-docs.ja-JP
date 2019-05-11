---
title: HTTP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, receive adapters
- HTTP adapters, send adapters
- HTTP adapters
- receive adapters, HTTP adapters
- send adapters, HTTP adapters
- HTTP adapters, about HTTP adapters
ms.assetid: a9423052-8392-4006-ab46-79834169c796
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d9bfc533222dad9411c6c56e67c37b5c9a37212
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382878"
---
# <a name="http-adapter"></a>HTTP アダプター
HTTP プロトコルを使用して、Microsoft BizTalk Server とアプリケーション間で情報を交換するのにには、HTTP アダプターを使用します。 HTTP は、企業間のメッセージ交換の主要なプロトコルです。 アプリケーションは、指定された HTTP URL に HTTP POST 要求または HTTP GET 要求を送信することで、サーバーにメッセージを送信できます。 HTTP アダプターは、HTTP 要求を受け取り、処理のための BizTalk Server に送信します。 同様に、BizTalk Server では、指定された HTTP URL に HTTP POST 要求を送信してリモート アプリケーションにメッセージを送信することができます。  
  
 HTTP アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。 HTTP 受信アダプターは、Microsoft インターネット インフォメーション サービス (IIS) インターネット サーバー アプリケーション プログラミング インターフェイス (ISAPI) 拡張機能、IIS のプロセスをホスト、および HTTP アダプターを使用する受信場所を制御します。 HTTP では、HTTP アダプターを使用する送信ポート アダプタのコントロールを送信します。  
  
 このセクションでは、ワークフローを説明し、バッチ処理の両方のサポート、HTTP 受信アダプタと HTTP 送信アダプター。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [HTTP 受信アダプター](../core/http-receive-adapter.md)  
  
-   [HTTP 送信アダプター](../core/http-send-adapter.md)  
  
-   [HTTP アダプターの構成](../core/configuring-the-http-adapter.md)  
  
-   [HTTP アダプターのセキュリティに関する推奨事項](../core/http-adapter-security-recommendations.md)
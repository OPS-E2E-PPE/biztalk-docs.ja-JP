---
title: HTTP アダプター |Microsoft ドキュメント
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
ms.openlocfilehash: 6d9be9fac6fdb65c4516c671b6c0e30096e83a27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256050"
---
# <a name="http-adapter"></a>HTTP アダプター
HTTP アダプタは、Microsoft BizTalk Server とアプリケーション間で HTTP プロトコルを介して情報を交換するために使用します。 HTTP は、企業間のメッセージ交換にとって主要なプロトコルです。 アプリケーションは、指定された HTTP URL に HTTP POST 要求または HTTP GET 要求を送信することで、サーバーにメッセージを送信できます。 HTTP アダプタは、HTTP 要求を受信し、その要求を処理するために BizTalk Server に送信します。 同様に、BizTalk Server は、指定された HTTP URL に HTTP POST 要求を送信することで、リモート アプリケーションにメッセージを送信できます。  
  
 HTTP アダプタは、2 つのアダプタ (受信アダプタと送信アダプタ) で構成されます。 HTTP 受信アダプタは、IIS プロセスでホストされる Microsoft インターネット インフォメーション サービス (IIS) の ISAPI (Internet Server API) 拡張で、HTTP アダプタを使用する受信場所を制御します。 HTTP 送信アダプタでは、HTTP アダプタを使用する送信ポートを制御します。  
  
 このセクションでは、HTTP 受信アダプタと HTTP 送信アダプタ両方のワークフローおよびバッチ処理のサポートについて説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [HTTP 受信アダプター](../core/http-receive-adapter.md)  
  
-   [HTTP 送信アダプタ](../core/http-send-adapter.md)  
  
-   [HTTP アダプタの構成](../core/configuring-the-http-adapter.md)  
  
-   [HTTP アダプタのセキュリティに関する推奨事項](../core/http-adapter-security-recommendations.md)
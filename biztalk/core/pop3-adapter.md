---
title: POP3 アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, about POP3 adapters
- authenticating, POP3 adapters
- POP3 adapters
- POP3 adapters, receive adapters
- POP3 adapters, authenticating
- receive adapters, POP3 adapters
ms.assetid: 008f7fa7-60c3-4ea3-b90d-821e4029a04c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1be3efdd18efa46213ffc9511bd4bd795a946bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394903"
---
# <a name="pop3-adapter"></a>POP3 アダプター
POP3 メールボックスの POP3 プロトコル経由の Microsoft BizTalk Server を実行するサーバーにあるサーバーからデータを取得するのにには、Post Office Protocol 3 (POP3) アダプタを使用します。  
  
 POP3 アダプターは、1 つだけアダプター、受信アダプターで構成されます。 受信アダプターは、POP3 アダプターを使用する受信場所を制御します。  
  
 このトピックで、POP3 のワークフローを説明する受信アダプター。  
  
 **POP3 受信アダプタ**  
  
 POP3 は、指定した POP3 サーバー上の指定したメールボックスからアダプターを取得しますの電子メールを受信します。 既定で、POP3 受信アダプターが MIME 処理をダウンロードし、これらのメッセージをマルチパート BizTalk メッセージとして BizTalk Server に送信する電子メール メッセージに適用されます。 POP3 受信アダプターが受信し、次の形式で電子メールを処理します。  
  
- プレーン テキスト  
  
- MIME エンコード  
  
- MIME 暗号化  
  
- MIME エンコードおよび署名  
  
- MIME 暗号化および署名  
  
  **バッチ処理の POP3 受信アダプタのサポート**  
  
  POP3 受信アダプターはバッチ処理をサポートしていません。  
  
  **POP3 サーバーでの認証**  
  
  POP3 アダプターの使用は、次の認証方法がサポートされています。  
  
- **基本的な。** POP3 サーバーでは、ユーザーの認証のための資格情報の指定を使用します。  これらの資格情報はクリア テキストで送信されます。  
  
- **ダイジェスト (APOP)。** POP3 サーバーは、認証、ダイジェスト文字列を使用します。  
  
- **セキュリティで保護されたパスワード認証 (SPA) です。** POP3 サーバーでは、現在のプロセスの資格情報を使用して認証。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [POP3 アダプターについて](../core/what-is-the-pop3-adapter.md)  
  
-   [POP3 アダプターの構成](../core/configuring-the-pop3-adapter.md)  
  
-   [チュートリアル: POP3 アダプタを使用する BizTalk アプリケーションの作成](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [POP3 アダプターでのマルチパート メッセージの処理](../core/processing-multi-part-messages-with-the-pop3-adapter.md)
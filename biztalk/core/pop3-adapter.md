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
ms.openlocfilehash: 34a5f6a73f30ba831256ce1699b9a6a77b75c102
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982795"
---
# <a name="pop3-adapter"></a>POP3 アダプタ
Post Office Protocol 3 (POP3) アダプタを使用すると、POP3 メールボックスのあるサーバーから、Microsoft BizTalk Server を実行しているサーバーに、POP3 プロトコル経由でデータを取得できます。  
  
 POP3 アダプタは、1 つの受信アダプタのみで構成されています。 受信アダプタでは、POP3 アダプタを使用する受信場所を制御します。  
  
 このトピックでは、POP3 受信アダプタのワークフローについて説明します。  
  
 **POP3 受信アダプタ**  
  
 POP3 受信アダプタは、指定した POP3 サーバー上の特定のメールボックスから電子メールを取得します。 既定では、ダウンロードする電子メール メッセージに MIME 処理を適用し、これらのメッセージをマルチパート BizTalk メッセージとして BizTalk Server に送信します。 POP3 受信アダプタは、次の形式の電子メールを受信および処理できます。  
  
- プレーンテキスト  
  
- MIME エンコード  
  
- MIME 暗号化  
  
- MIME エンコードおよび署名  
  
- MIME 暗号化および署名  
  
  **バッチ処理の POP3 受信アダプタのサポート**  
  
  POP3 受信アダプタは、バッチ処理をサポートしていません。  
  
  **POP3 サーバーでの認証**  
  
  POP3 アダプタでは、次の認証方法がサポートされています。  
  
- **基本的な。** POP3 サーバーでは、ユーザーの認証のための資格情報の指定を使用します。  これらの資格情報はクリア テキストで送信されます。  
  
- **ダイジェスト (APOP)。** : ダイジェスト文字列を使用して認証を行います。  
  
- **セキュリティで保護されたパスワード認証 (SPA) です。** : 現在のプロセスの資格情報を使用して認証を行います。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [POP3 アダプターについて](../core/what-is-the-pop3-adapter.md)  
  
-   [POP3 アダプターの構成](../core/configuring-the-pop3-adapter.md)  
  
-   [チュートリアル: POP3 アダプターを使用する BizTalk アプリケーションの作成](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [POP3 アダプターでのマルチパート メッセージの処理](../core/processing-multi-part-messages-with-the-pop3-adapter.md)
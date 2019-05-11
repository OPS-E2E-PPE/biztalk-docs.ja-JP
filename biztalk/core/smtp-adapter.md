---
title: SMTP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, about SMTP adapters
- SMTP adapters, authenticating
- send adapters, SMTP adapters
- authenticating, SMTP adapters
- SMTP adapters
- SMTP adapters, send adapters
ms.assetid: b712f76d-3ce4-4780-9627-951e5951bd8a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d3451ab6eb6d9dc52538f5b1b9289e2cb99d7a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314496"
---
# <a name="smtp-adapter"></a>SMTP アダプター
簡易メール転送プロトコル (SMTP) アダプターを使用して、SMTP プロトコルを使用して、Microsoft BizTalk Server と他のアプリケーションを実行するサーバーの間で情報を交換します。 BizTalk Server は、電子メール メッセージを作成し、指定した電子メール アドレスに配信して、他のアプリケーションにメッセージを送信できます。 内部的には、SMTP 送信アダプターは、SMTP ベースの電子メール メッセージを作成し、対象の電子メール アドレスに送信します。 ターゲットの電子メール アドレスは、SMTP アダプタのプロパティです。 BizTalk エクスプ ローラーは、SMTP 送信ポートを構成するときに、このプロパティを公開します。  
  
 SMTP アダプターでワイルドカード文字をサポートしている、 **TO**、 **FROM**、 **CC**と**サブジェクト**プロパティを実際に解決されます値。 ワイルドカード文字の場合、 **TO**、 **FROM**、および**CC**プロパティを解決することはできません、SMTP トランスポートのエラーが記録され、メッセージを保留キューに配置またはバックアップ トランスポートにメッセージをリダイレクトします。 ワイルドカード文字を解決できない場合、**サブジェクト**プロパティ、メッセージが送信されると、**サブジェクト**プロパティ (たとえば、「メッセージ MessageID %」) のように正確に指定されたプロパティ。  
  
 既定では、SMTP メッセージのメッセージ テキストはプレーン テキストです。 メッセージ本文で HTML を使用するには、メッセージ テキストを HTML ファイルの内容を使用するアダプターを構成できます。  
  
 SMTP のセキュリティの問題に関する詳細については、次を参照してください。 [SMTP アダプタのセキュリティに関する推奨事項](../core/smtp-adapter-security-recommendations.md)します。  
  
 SMTP アダプタは、1 つだけアダプター、送信アダプターで構成されます。 送信アダプターは、SMTP アダプタを使用する送信ポートを制御します。  
  
 このトピックでは、SMTP 送信アダプターを通過するメッセージのフローについて説明します。  
  
 **SMTP 送信アダプタ**  
  
 SMTP では、サーバーからアダプターを取得しますメッセージを送信し、電子メール受信者に送信する SMTP サーバーに投稿します。 SMTP 送信 BizTalk メッセージ オブジェクトのボディ部、指定されたファイルまたはアダプターの構成時に表示されるダイアログ ボックスに入力したテキストに、メッセージの内容になるようにアダプターを取得します。  
  
 SMTP 送信アダプターには、SMTP サーバーにメッセージを正常に投稿記事、後に、SMTP 送信アダプターはメッセージ ボックス データベースからメッセージを削除します。  
  
 SMTP 送信アダプターでは、配信通知を要求でき、開封確認メッセージが SMTP 送信アダプター経由で送信することができます。 SMTP アダプターは、SMTP で指定したアドレスに通知と読み取り受信確認を配信**から**ヘッダー。  
  
 **SMTP サーバーでの認証**  
  
 SMTP サーバー認証が必要な場合、SMTP 送信アダプタで使用認証の種類のいずれか。  
  
-   **基本的な。** SMTP サーバーでは、ユーザーの資格情報を使用して認証。  
  
-   **プロセス アカウント (NTLM)。** SMTP サーバーでは、現在のプロセスの資格情報を使用して認証。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SMTP アダプターの構成](../core/configuring-the-smtp-adapter.md)  
  
-   [SMTP アダプター構成時の制限事項](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [SMTP アダプターのセキュリティに関する推奨事項](../core/smtp-adapter-security-recommendations.md)
---
title: "SMTP アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, about SMTP adapters
- SMTP adapters, authenticating
- send adapters, SMTP adapters
- authenticating, SMTP adapters
- SMTP adapters
- SMTP adapters, send adapters
ms.assetid: b712f76d-3ce4-4780-9627-951e5951bd8a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0d0d16bf266d0b636aa9955b5c25b37d9ab54d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter"></a>SMTP アダプター
簡易メール転送プロトコル (SMTP) アダプタは、Microsoft BizTalk Server を実行しているサーバーと他のアプリケーション間で SMTP を介して情報を交換するために使用します。 BizTalk Server から他のアプリケーションにメッセージを送信するには、電子メール メッセージを作成し、指定した電子メール アドレスに配信します。 内部的には、SMTP 送信アダプタで SMTP ベースの電子メール メッセージを作成し、送信先の電子メール アドレスに送信します。 送信先電子メール アドレスは、SMTP アダプタのプロパティです。 このプロパティは、SMTP 送信ポートを構成するとき、BizTalk エクスプローラに表示されます。  
  
 SMTP アダプターでのワイルドカード文字をサポートしている、**に**、 **FROM**、 **CC**と**サブジェクト**プロパティ、し、実際に解決します。値。 ワイルドカード文字は、場合、 **TO**、 **FROM**、および**CC**プロパティを解決することはできません、SMTP トランスポートのエラーが記録され、メッセージを保留キューに配置またはバックアップ トランスポートにメッセージをリダイレクトします。 ワイルドカード文字を解決できない場合、**サブジェクト**プロパティでメッセージの送信、**サブジェクト**プロパティ (たとえば、「メッセージ MessageID %」) のように正確に指定されたプロパティ。  
  
 既定では、SMTP メッセージのメッセージ テキストはプレーンテキストです。 メッセージ本文で HTML を使用するために、メッセージ テキストに HTML ファイルの内容を使用するようアダプタを構成できます。  
  
 SMTP のセキュリティの問題に関する詳細については、次を参照してください。 [SMTP アダプタのセキュリティに関する推奨事項](../core/smtp-adapter-security-recommendations.md)です。  
  
 SMTP アダプタは、1 つの送信アダプタのみで構成されています。 SMTP 送信アダプタでは、SMTP アダプタを使用する送信ポートを制御します。  
  
 このトピックでは、SMTP 送信アダプタを通過するメッセージ フローについて説明します。  
  
 **SMTP 送信アダプタ**  
  
 SMTP 送信アダプタは、サーバーからメッセージを取得して、電子メール受信者に送信するための SMTP サーバーに送信します。 SMTP 送信アダプタで取得するメッセージの内容の取得元は、BizTalk メッセージ オブジェクトのボディ部、指定したファイル、またはアダプタ構成時に表示されるダイアログ ボックスに入力したテキストです。  
  
 SMTP サーバーに正常にメッセージが送信されると、メッセージ ボックス データベースからメッセージが削除されます。  
  
 SMTP 送信アダプタ経由で送信するメッセージについては、配信通知および開封確認メッセージを要求できます。 SMTP アダプターは、SMTP で指定したアドレスに、通知および配信確認メッセージを配信**から**ヘッダー。  
  
 **SMTP サーバーでの認証**  
  
 SMTP サーバーでの認証を要求した場合、SMTP 送信アダプタによって、以下のいずれかの認証の種類が使用されます。  
  
-   **基本的な。** : ユーザーが指定した資格情報を使用して認証を行います。  
  
-   **プロセス アカウント (NTLM)。** 現在のプロセスの資格情報を使用して認証を行います。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SMTP アダプタの構成](../core/configuring-the-smtp-adapter.md)  
  
-   [SMTP アダプタの構成時の制限事項](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [SMTP アダプタのセキュリティに関する推奨事項](../core/smtp-adapter-security-recommendations.md)
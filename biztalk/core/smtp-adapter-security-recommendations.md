---
title: "SMTP アダプタのセキュリティに関する推奨事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca1aeed0ad8c80cc32d333aeef37d1da6feabfc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-security-recommendations"></a>SMTP アダプタのセキュリティに関する推奨事項
SMTP アダプタは、BizTalk Server を実行しているサーバーと他のアプリケーション間で簡易メール転送プロトコル (SMTP) を介して情報を交換するために使用します。 BizTalk Server から他のアプリケーションにメッセージを送信するには、電子メール メッセージを作成し、指定した電子メール アドレスに配信します。 SMTP アダプタは、メッセージの送信のみに使用できます。 SMTP アダプターに関する詳細については、次を参照してください。 [SMTP アダプター](../core/smtp-adapter.md)です。  
  
 SMTP アダプタを実行しているホスト インスタンス用のサービス アカウントを構成する場合、リモートの SMTP サーバーで使用する認証の種類を指定する必要があります。 認証オプションには、基本認証 (クリア テキスト)、NTLM (現在の資格情報を使用) があります。SMTP サーバーで認証が不要な場合には指定しません。  
  
 SMTP アダプタを使用してメッセージを送信する場合、既定では、メッセージはクリア テキストで送信されます。 S/MIME エンコーダ コンポーネントのあるパイプラインを使用する場合、メッセージは暗号化してから SMTP サーバーに送信できます。 ただし、SMTP ヘッダーはクリア テキストのままです。  
  
 BizTalk Server から送信される電子メール メッセージを監査する場合、SMTP アダプタを使用して、独自の SMTP サーバーに接続する必要があります。接続したら、メッセージを監査できるようになります。  
  
 SMTP アダプタは、Secure Sockets Layer (SSL) をサポートしていません。  
  
## <a name="see-also"></a>参照  
 [受信と送信サーバーのポート](../core/ports-for-the-receive-and-send-servers.md)   
 [セキュリティの最小ユーザー権限](../core/minimum-security-user-rights.md)
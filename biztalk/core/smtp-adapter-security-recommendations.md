---
title: SMTP アダプタのセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b89406529c2a112d667888a67df02e9ab9a693
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314409"
---
# <a name="smtp-adapter-security-recommendations"></a>SMTP アダプタのセキュリティに関する推奨事項
簡易メール転送プロトコル (SMTP) プロトコルを使用して BizTalk Server と他のアプリケーションを実行するサーバーの間で情報を交換するのにには、SMTP アダプタを使用します。 BizTalk Server は、電子メール メッセージを作成し、指定した電子メール アドレスに配信して、他のアプリケーションにメッセージを送信できます。 SMTP アダプタは、メッセージの送信のみ使用できます。 SMTP アダプターに関する詳細については、次を参照してください。 [SMTP アダプター](../core/smtp-adapter.md)します。  
  
 SMTP アダプタを実行するホスト インスタンスのサービス アカウントを構成するときに、リモートの SMTP サーバーで使用する認証の種類を指定する必要があります。 認証オプションは、SMTP サーバーで認証が不要な場合は基本認証 (クリア テキスト)、NTLM (を現在の資格情報を使用)、または none。  
  
 SMTP アダプターを使用してメッセージを送信するときに BizTalk Server は、既定ではクリア テキストでメッセージを送信します。 S/MIME エンコーダー コンポーネントを含むパイプラインを使用する場合は、SMTP サーバーに送信する前に、メッセージを暗号化できます。 ただし、SMTP ヘッダーはクリア テキストです。  
  
 BizTalk Server が送信する電子メール メッセージを監査する場合は、する必要がありますアダプターを使用する、SMTP、独自の SMTP サーバーへの接続にメッセージを監査できます。  
  
 SMTP アダプタは、Secure Sockets Layer (SSL) をサポートしていません。  
  
## <a name="see-also"></a>参照  
 [受信と送信サーバーのポート](../core/ports-for-the-receive-and-send-servers.md)   
 [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)
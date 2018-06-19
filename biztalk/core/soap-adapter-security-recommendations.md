---
title: SOAP アダプタのセキュリティに関する推奨事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, security
- security, SOAP adapters
ms.assetid: f869bd82-df93-45e1-b747-b538820253fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3053bccde7830d2e8275c8e2f6f668c428709860
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279594"
---
# <a name="soap-adapter-security-recommendations"></a>SOAP アダプタのセキュリティに関する推奨事項
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、SOAP アダプターを使用して Web サービスを公開 (受信) および使用 (送信) できます。 SOAP アダプターに関する詳細については、次を参照してください。 [SOAP アダプター](../core/soap-adapter.md)です。 Web サービスの詳細については、次を参照してください。 [Web サービスを使用する](../core/using-web-services.md)です。 SOAP アダプターをセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。  
  
-   Web サービスを公開するためのセキュリティの推奨事項については、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。  
  
-   SOAP アダプターでは、HTTP (Hypertext Transfer Protocol) を利用して、BizTalk Server との間でメッセージを送受信できます。 そのため、インターネット インフォメーション サービス (IIS) を保護するためのセキュリティの推奨事項に従ってください。 IIS 7.0 を使用している場合、アプリケーション分離を構成する方法について IIS 7.0 の推奨事項に従ってください。 詳細については、次を参照してください。[アプリケーション プール (IIS 7) を作成して](http://go.microsoft.com/fwlink/?LinkId=196674)です。  
  
-   SOAP 受信場所用のアプリケーション プールを作成する場合、SOAP 受信アダプターを実行している分離ホストの Windows グループおよびインターネット インフォメーション サービスのワーカー プロセス グループ (IIS_WPG グループ) のメンバーであるアカウントで実行するように構成する必要があります。 その後、SOAP 受信アダプターのホスト インスタンスを、このアカウントを使用するように構成してください。 IIS_WPG グループのアカウントを変更する場合は、新しいアカウントで実行されるようにホスト インスタンスを更新する必要もあります。  
  
-   SOAP 送信アダプターで SSL (Secure Sockets Layer) クライアント証明書を使用する場合は、これらの証明書を手動で構成する必要があります。  
  
-   Web サービスを利用する場合、認証のために、匿名認証、基本認証、ダイジェスト認証、Windows 統合認証、またはクライアント証明書に基づく認証を使用できます。 基本認証を使用して Web サービスを利用する場合、未認証のユーザーがメッセージからユーザーの資格情報を読み取ることができないように、SSL を使用することをお勧めします。  
  
-   フロントエンド ユーザーのコンテンツをバックエンド システムの資格情報にマップする必要がある場合、エンタープライズ シングル サインオン (SSO) を使用できます。 詳細については、次を参照してください。[マップ シングル サインオン資格情報を方法](../core/how-to-map-single-sign-on-credentials.md)です。  
  
-   基本認証を使用する場合、またはメッセージ レベルでの暗号化を使用しない場合、未認証のユーザーがユーザーの資格情報を読み取ることができないように、メッセージの送受信に SSL を使用することをお勧めします。  
  
-   メッセージの送受信に Windows 統合認証を使用することをお勧めします。  
  
-   SOAP アダプターを実行しているコンピューターには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムも含まれています。 SOAP アダプターを境界ネットワークに配置しないことをお勧めします。 配置する場合は、境界ネットワークのポートを、メッセージ ボックス データベースへの SQL Server トラフィック用のデータ ドメインに開く必要があります。ただし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムが攻撃の対象になる可能性があります。 SOAP アダプターは、処理ドメイン (つまり、境界ネットワーク以外) で構成することをお勧めします。 処理ドメインを構成したら、最も外側のファイアウォールを、処理ドメイン内のファイアウォール経由で SOAP 要求を転送するように構成できます。 このメカニズムはリバース プロキシと呼ばれます (Forefront Threat Management Gateway (TMG) 2010 サーバー実装では「Web 公開」と呼ばれます)。  
  
## <a name="see-also"></a>参照  
 [受信と送信サーバーのポート](../core/ports-for-the-receive-and-send-servers.md)   
 [セキュリティの最小ユーザー権限](../core/minimum-security-user-rights.md)
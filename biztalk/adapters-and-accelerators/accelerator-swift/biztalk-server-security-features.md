---
title: "BizTalk Server のセキュリティ機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication
- security, authentication
- security, BizTalk Server
- security, security features
- BizTalk Server, security features
ms.assetid: db356439-1898-4c09-86de-458a9bd21b18
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58f87bab3118f824843167a7be97d831cecc0b7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-security-features"></a>BizTalk Server のセキュリティ機能
財務アプリケーションはサービスとの統合ソリューションを使用して開発された[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]は[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ネイティブによって保護されたアプリケーションとは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ機能です。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションが通常メッセージング機能の構成 (メッセージの処理、変換、ルーティング) とワークフローの自動化 (ビジネス プロセスの自動化、ビジネス ルールおよびロジックの評価)。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]一般的なワークフローのメッセージングとオートメーションのセキュリティを提供します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]エンドユーザー メッセージ エントリ、修復、承認、および送信のセキュリティ保護に固有の追加のセキュリティ機能を提供します。 詳細については[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]-特定のセキュリティを参照してください[Message Repair and New Submission のセキュリティ機能によって A4SWIFT](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージング イベントに基づいて、モデル (メッセージ ボックス データベースとパブリッシャーとサブスクライバーのデザイン パターンに中央揃え) をメッセージとドキュメントでは、だけでなく、これらと対話処理コンポーネントは XML と Web サービスに基づいて設計されていますテクノロジです。 を任意のシステム構成情報、参加要素、およびプロセスの整合性を保護するのには、次の主要要件は、セキュリティ メカニズムを説明します。  
  
-   **システムの各要素のプライバシーを保護します。** 開いているコンピューティングでの通信のプライバシーを保護して、環境のネットワークは、暗号化の機能です。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サポートは、公開キー基盤 (PKI)、Secure Multipurpose Internet Mail Extensions (S/MIME)、および Secure Sockets Layer (SSL) を使用して通信を暗号化します。 認証し、メッセージのプライバシーの保護を強化[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]デジタル証明書 (キー) を広範に使用します。  
  
     PKI は、一連のキー、プロシージャ、およびキー、および次の目的で展開されているアルゴリズムを認証するための権限の階層のセキュリティで保護された exchange を促進する方法に対応するインターネット プロトコルです。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]S/MIME プロトコルを使用して暗号化およびデータ暗号化標準 (DES)、3 des、RC2 暗号化アルゴリズムのサポートと、複数のステップ、マルチパーティのプロセスで送受信されるメッセージの暗号化を解除します。 Web クライアントと Web サーバーの間で暗号化されたポイント ツー ポイント通信の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SSL プロトコルを使用します。  
  
-   **については、参加要素、およびプロセスを認証します。** については、参加要素、およびプロセスを認証するために[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]署名証明書、依存[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、および拡張の実装[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]で認証[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]エンタープライズ シングルと呼ばれるサインオン (SSO)。 署名証明書は、デジタル証明書 (またはキー)、メッセージ交換で相互に 2 つのパーティを識別します。 署名証明書は、メッセージが転送中に改ざんされたかどうかにも決定します。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]秘密キーを使用して生成された送信メッセージに署名およびデジタル署名された受信メッセージのデコード ストアドの公開キーを使用できます。 SSO は、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]拡張機能を[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]パーティと複数の手順を行っているメッセージングのイベントは、認証[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]せずステップ プロセスでは、任意のリソースへのプロセスのいずれかで、認証プロセス複数のログオンを必要とします。  
  
-   **リソースの利用状況を承認します。** 承認とは、割り当てと、システムのリソースへの使用権限の管理です。 プライマリ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]承認のメカニズムは、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ロール、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびメッセージ ボックス データベースです。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーション プロセスと、オーケストレーションが送信パイプラインにメッセージを送信した後、それらを送信する前に、そのメッセージ ボックス データベースにすべての受信および送信メッセージを格納します。 アクセスを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]データベースなどのリソースは、管理者、ユーザーに割り当てられていて、ホストを使用してアカウント[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ロール。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ アーキテクチャは堅牢な一連の全体で実装されるメカニズムに基づいて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]さまざまなセキュリティを強化するように設計手法を使用します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンポーネント セキュリティ メカニズムが組み込まれた送信と受信アダプター、パイプライン、メッセージ ボックス データベース、オーケストレーション、され、メッセージのセキュリティ コンテキストのプロパティです。  
  
 これらのコンポーネントは、セキュリティ メカニズムを展開するのにために必要な認証のパイプライン、論理の複数のホストと、「信頼されている認証」プロパティ、およびパブリッシュとサブスクライブ/受信承認方法論を使用します。 この複数ファセット セキュリティ アーキテクチャの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]支援設計し、詳細を実行するためのさまざまなオプションをセキュリティで保護メッセージングの金融サービスとワークフローを自動化するアプリケーションを提供します。
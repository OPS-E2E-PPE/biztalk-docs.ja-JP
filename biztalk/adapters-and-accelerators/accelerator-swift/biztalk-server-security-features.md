---
title: BizTalk Server のセキュリティ機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authentication
- security, authentication
- security, BizTalk Server
- security, security features
- BizTalk Server, security features
ms.assetid: db356439-1898-4c09-86de-458a9bd21b18
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45d541138d566eb6791385cdb23413187d2e68ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971131"
---
# <a name="biztalk-server-security-features"></a>BizTalk Server のセキュリティ機能
金融サービス アプリケーションとの統合ソリューションを使用して開発[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]は[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ネイティブで保護されたアプリケーションとは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ機能。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] アプリケーションが通常メッセージング機能の構成 (メッセージの処理、変換、ルーティング) とワークフローの自動化 (ビジネス プロセスの自動化、ビジネス ルール、およびロジックの評価)。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 一般的なメッセージングとワークフロー オートメーションのセキュリティを提供します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] エンドユーザーのメッセージのエントリ、修復、承認、および送信のセキュリティ保護に固有の追加のセキュリティ機能を提供します。 詳細については[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]-特定のセキュリティを参照してください[Message Repair and New Submission のセキュリティ機能を A4SWIFT](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] メッセージング イベントに基づいてモデルを (メッセージ ボックス データベース、パブリッシャーとサブスクライバーのデザイン パターンに中央揃え) をメッセージ、ドキュメント、とともに、それらと対話するコンポーネントの処理は XML と Web サービスに設計されました。テクノロジ。 任意のシステム構成情報、参加者、およびプロセスの整合性を保護するため、次の主な要件は、セキュリティ メカニズムを紹介します。  
  
- **システムの各要素のプライバシーを保護します。** 開いているコンピューティングでの通信のプライバシーを保護して、環境のネットワークは、暗号化の機能です。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] サポートするには、公開キー基盤 (PKI) や Secure Multipurpose Internet Mail Extensions (S/MIME)、Secure Sockets Layer (SSL) 通信が暗号化されます。 認証、メッセージのプライバシーの保護を強化し[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]デジタル証明書 (キー) を広範に使用します。  
  
   PKI は、一連のキー、プロシージャ、およびキー、およびこれらの目的で展開されているアルゴリズムを認証するための権限の階層を安全に交換を促進するための方法論に対応するインターネット プロトコルです。  
  
   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] S/MIME プロトコルを使用して、暗号化し、データ暗号化標準 (DES)、3 des、RC2 暗号化アルゴリズムのサポートと、複数のステップ、マルチパーティのプロセスで送受信されるメッセージの暗号化を解除します。 Web クライアントと Web サーバーでは、通信の暗号化された point-to-point [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SSL プロトコルを使用します。  
  
- **については、参加者、およびプロセスを認証します。** については、参加者、およびプロセスを認証するために[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]署名証明書、依存[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、および拡張の実装[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]で認証[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]エンタープライズ シングルと呼ばれるシングル サインオン (SSO)。 署名証明書はデジタル証明書 (またはキー)、メッセージ交換で相互に 2 つのパーティを識別します。 署名証明書は、メッセージが転送中に改ざんされたかどうかにも決定します。  
  
   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ストアドの公開キーを使用して、デジタル署名された受信メッセージをデコードすることができ、秘密キーを使用して生成される送信メッセージに署名します。 SSO は、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]拡張機能を[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]パーティとは、複数の手順を行ってメッセージングのイベントは、認証[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]せずステップの処理で、任意のリソースへのプロセスで、いずれかで認証するプロセス複数のログオンを必要とします。  
  
- **リソースの使用状況を承認します。** 承認とは、割り当てと、システムのリソースへの使用権限の管理です。 プライマリ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の承認メカニズム[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ロール、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびメッセージ ボックス データベースです。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] オーケストレーション プロセスとオーケストレーションが送信パイプラインにメッセージを送信した後、それらを送信する前に、メッセージ ボックス データベースにすべての受信および送信メッセージを格納します。 アクセスを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]データベースおよびリソースは、管理者、ユーザーに割り当てられているし、ホストを使用してアカウント[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ロール。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ アーキテクチャは全体で実装されるメカニズムの堅牢なセットに基づいて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]さまざまなセキュリティを高めるための方法論を使用します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ メカニズムを組み込むコンポーネントが送信アダプター、パイプライン、メッセージ ボックス データベース、オーケストレーション、受信し、メッセージのセキュリティ コンテキストのプロパティ。  
  
  これらのコンポーネントは、セキュリティ メカニズムを導入するのにのに必要な認証パイプライン、論理の複数のホストと、「認証が信頼済み」のプロパティおよびパブリッシュとサブスクライブ/受信承認方法論を使用します。 場合は、この複数ファセットのセキュリティ アーキテクチャ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の設計と複数の実行に役立つさまざまなオプションとセキュリティで保護金融サービス メッセージング ワークフローを自動化するアプリケーションを提供します。
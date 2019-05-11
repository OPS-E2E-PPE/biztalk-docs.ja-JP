---
title: セキュリティに関するケース スタディ:会社 B |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 48bbb347-919a-435e-b7b1-34a4c0e65e59
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 650b05a10ae1cc6958e36e8184894de881cdc280
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251066"
---
# <a name="security-case-studies-company-b"></a>セキュリティに関するケース スタディ:会社 B
会社 B は、ソフトウェア会社です。 そのビジネス モデルは、主要な顧客とサプライヤーの電子商取引に依存しています。 会社 B を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]そのトランザクションの実装。  
  
 会社 B は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]トランザクションと内部および外部のアプリケーション間の通信を管理します。 会社 B は、約 85 の内部アプリケーションと 2300 に及ぶ取引と通信します。 現在、毎月約 250万ドキュメントを処理し、2007年年末に毎月 600万のドキュメントを処理することを推定します。  
  
## <a name="potential-threats-and-security-concerns"></a>潜在的な脅威とセキュリティに関する注意事項  
 会社 B は、受信および認証された送信元からのメッセージのみを処理するかどうかを確認する必要があります。 また、会社 B は、受信してから、企業ネットワークの外部のドキュメントをできるだけ安全に取得されていることを確認したいと考えているとします。 会社 B の企業ネットワークでは、インターネットから分離する、ファイアウォールはポート 80 とポート 443 からのトラフィックをのみできます。 ファイアウォールは、その他のすべてのトラフィックを拒否します。  
  
## <a name="security-architecture"></a>セキュリティのアーキテクチャ  
 次の図は、会社 B を使用するアーキテクチャを示します。 会社 B は、内部アプリケーション間の通信に、メッセージ ブローカーとして BizTalk Server を使用し、処理、送信、および正しく受信してそのサプライヤーや顧客からメッセージを書式設定します。 会社 B は、さまざまな形式での内部および外部のドキュメントを処理する必要があります。 これには、フラット ファイルや XML ドキュメントが含まれます。  
  
 **図 1. 会社 B のセキュリティ アーキテクチャ**  
  
 ![会社 B のアーキテクチャ](../core/media/bpi-cp-pc-company-b.gif "BPI_CP_PC_COMPANY_B")  
  
 会社 B は単一のファイアウォールを使用して、社内のコンピュータをインターネットから分離します。 セキュリティの層を追加、会社 B には、すべての企業内のサーバーとワークステーション、企業ネットワーク内に存在する間のインターネット プロトコル セキュリティ (IPsec) 通信が組み込まれています。 会社 B は、IPsec を使用して、内部ドメイン内のすべての通信を暗号化します。  
  
 会社 B は、ファイル共有サーバーを使用して、フラット ファイルを受信します。 このファイル共有サーバーは、企業ネットワークとドメインの外部存在します。 ファイアウォールは、企業ネットワークから、ファイル共有サーバーを区切ります。 会社 B の外部のパートナーは、このファイル共有サーバー上のフラット ファイル ドキュメントを投稿しするとき、暗号化された Point-to-Point トンネリング プロトコル (PPTP) パイプラインを介してファイル共有サーバーと通信します。 会社 B は、パートナーのパスワード有効期限が切れる 30 日おきで、ファイル共有サーバーへのアクセスを保護します。  
  
 会社 B が、ファイル共有サーバーからフラット ファイル ドキュメントを取得し、追加処理用の BizTalk Server に送信するカスタム ファイル移動アプリケーションを作成します。 会社 B の内部アプリケーションは、カスタム ファイル移動アプリケーションを使用しても BizTalk Server にフラット ファイルを渡します。 BizTalk Server では、これらのドキュメントを変換し、会社 B の取引先パートナーに送信します。  
  
 BizTalk Server には、内部のアプリケーション形式にパートナーのデータを変換する前に、送信者、受信者、およびドキュメントの種類のエントリがあることを検証します。 BizTalk Server では、送信者、受信者、またはドキュメントの種類のエントリのないメッセージを受信する場合は、BizTalk Server は、メッセージを拒否し、会社 B の運用チームは、メッセージを確認します。 内部のアプリケーションでは、さまざまな EDIFACT、フラット ファイル、XML、および ANSI X12 を含む形式でメッセージを送信します。  
  
 会社 B は、内部および外部ソースから HTTPS 経由のドキュメントも受信します。 外部のパートナーは、企業ネットワークの外部の Web サーバーに自分のドキュメントを投稿します。 ファイアウォールは、企業ネットワークからこの Web サーバーを区切ります。 カスタム ファイル移動アプリケーションには、HTTPS 経由で投稿されたドキュメントも取得します。 会社 B は、暗号化、取引先にメッセージに署名し、サード パーティの製品を使用します。 セキュリティの追加、としては、会社 B は、適切なセキュリティ設定があるかどうかを確認するすべてのサーバー上で夜間の監査を実行します。 会社 B は、確認のためのすべての例外を記録します。  
  
## <a name="see-also"></a>参照  
 
 [中小規模の企業のセキュリティのケース スタディ](../core/security-case-studies-for-small-to-medium-sized-companies.md)   
 
 [中小企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)
---
title: 'セキュリティに関するケース スタディ: 企業 B |Microsoft ドキュメント'
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
ms.openlocfilehash: ef0e37d4acda263822a2cf06095f2c8fd9989afe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270482"
---
# <a name="security-case-studies-company-b"></a>会社 B のセキュリティに関するケース スタディ:
会社 B はソフトウェア会社です。 この会社のビジネス モデルは、主要な顧客および業者との電子商取引に依存しています。 会社 B は、取引に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の実装を使用しています。  
  
 会社 B は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、内外のアプリケーション間のトランザクションと通信を管理しています。 会社 B は約 85 個の内部アプリケーションと 2300 に及ぶ取引先と通信します。 現在は、毎月約 250 万のドキュメントを処理していますが、2007 年の終わりまでに毎月 600 万のドキュメントを処理することになると見込んでいます。  
  
## <a name="potential-threats-and-security-concerns"></a>潜在的な脅威とセキュリティの問題  
 会社 B は、認証された送信元からのメッセージのみを受信および処理したいと考えています。 また、企業ネットワークの外部からできる限り安全にドキュメントを受信および取得できるようにすることも考えています。 会社 B の企業ネットワークをインターネットから分離するファイアウォールは、ポート 80 とポート 443 からのトラフィックでのみ使用できます。 ファイアウォールは、その他のすべてのトラフィックを拒否します。  
  
## <a name="security-architecture"></a>セキュリティのアーキテクチャ  
 次の図は、会社 B が使用するアーキテクチャを示しています。 会社 B はメッセージの仲介に BizTalk Server を使用し、内部のアプリケーション間の通信と、業者および顧客との適切な形式のメッセージの処理、送信、受信を行っています。 内部と外部のドキュメントは、異なる形式で処理する必要があります。 これには、フラット ファイルや XML ドキュメントが含まれます。  
  
 **図 1. 会社 B のセキュリティ アーキテクチャ**  
  
 ![会社 B のアーキテクチャ](../core/media/bpi-cp-pc-company-b.gif "BPI_CP_PC_COMPANY_B")  
  
 会社 B は 1 つのファイアウォールを使用して、社内のコンピュータをインターネットから切り離しています。 セキュリティのための追加層として、企業ネットワーク内に存在するすべての企業サーバーとワークステーション間にインターネット プロトコル セキュリティ (IPsec) 通信を導入しています。 また、IPsec を使用して、内部ドメイン内のすべての通信を暗号化しています。  
  
 会社 B はファイル共有サーバーを使用して、フラット ファイルを受信しています。 このファイル共有サーバーは企業ネットワークおよびドメインの外部に存在します。 ファイアウォールによって、ファイル共有サーバーと企業ネットワークを切り離しています。 社外のパートナーはこのファイル共有サーバーにフラット ファイル ドキュメントを投稿し、暗号化された Point-to-Point トンネリング プロトコル (PPTP) パイプラインを使用してファイル共有サーバーと通信します。 会社 B ではパートナーによるファイル共有サーバーへのアクセスを、パートナーのパスワードの有効期限を 30 日間にすることによって保護しています。  
  
 会社 B は、カスタム ファイル移動アプリケーションを作成しました。このアプリケーションは、ファイル共有サーバーからフラット ファイル ドキュメントを取得し、追加処理を行うために BizTalk Server に送信します。 社内アプリケーションも、このカスタム ファイル移動アプリケーションを使用して、BizTalk Server にフラット ファイルを渡します。 BizTalk Server はこれらのドキュメントを変換し、会社 B の取引先に送信します。  
  
 BizTalk Server はパートナーのデータを社内アプリケーションの形式に変換する前に、送信者、受信者、ドキュメントの種類の各エントリがあるかどうかを検証します。 BizTalk Server は送信者、受信者、ドキュメントの種類のいずれかのエントリがないことを示すメッセージを受け取った場合、BizTalk Server はメッセージを拒否し、会社 B の運用チームがメッセージを調査します。 内部アプリケーションは EDIFACT、フラット ファイル、XML、および ANSI X12 など、さまざまな形式のメッセージを送信します。  
  
 会社 B は内部と外部の送信元から HTTPS 経由のドキュメントも受信します。 社外のパートナーはドキュメントを企業ネットワークの外部にある Web サーバーに投稿します。 ファイアウォールによって、この Web サーバーと企業ネットワークは切り離されています。 また、カスタム ファイル移動アプリケーションは HTTPS 経由で投稿されたドキュメントも受信します。 会社 B はサード パーティ製品を使用して、取引先へのメッセージを暗号化し、そのメッセージに署名します。 セキュリティのための追加作業として、会社 B は毎晩すべてのサーバーの監査を実行し、セキュリティ設定が適切であることを確認しています。 また、確認用にすべての例外をログに記録しています。  
  
## <a name="see-also"></a>参照  
 
 [中小規模の企業のセキュリティのケース スタディ](../core/security-case-studies-for-small-to-medium-sized-companies.md)   
 
 [小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)
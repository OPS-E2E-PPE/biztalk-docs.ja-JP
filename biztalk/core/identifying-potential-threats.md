---
title: 潜在的な脅威を識別する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, potential threats
- security, planning
ms.assetid: 1d70a0c1-6daf-47bb-af15-a4b35a7bafc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd2feb0b6a09905efb7275b1cc6f0e6ef2b13d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972571"
---
# <a name="identifying-potential-threats"></a>潜在的な脅威を識別します。
STRIDE モデルを使用すると、BizTalk Server の展開に存在する可能性がある脅威を特定できます。 STRIDE は、次のカテゴリから派生した頭字語: *S*poofing identity、 *T*データ、ampering *R*、これが否認*は*情報漏えい、 *D*サービス、および特権の昇格のービスを拒否します。 このセクションには、BizTalk Server 環境に存在する可能性がある脅威の例と、脅威を緩和するメカニズムが含まれています。  
  
 **Id を偽装**  
  
- バインド ファイルにパスワードを格納して保存すると、未認証のユーザーがパスワードを読み取り、そのパスワードを使用して BizTalk Server に接続することがあります。そのため、悪影響が及ぶ可能性があります。 バインド ファイルにパスワードを格納しないでください。また、随意アクセス制御リスト (DACL) を使用して、機密データを含んでいると考えられるファイルへのアクセスを制限してください。  
  
  **データの改ざん**  
  
- 悪意のあるユーザーが、パートナーから BizTalk Server に送信されたメッセージを傍受し、メッセージの内容を変更することがあります。 デジタル署名を使用すると、悪意のあるユーザーがメッセージの送信中にメッセージを改ざんするのを防ぐことができます。  
  
  **否認不可**  
  
- BizTalk で送受信するメッセージを追跡する必要があります。 デジタル署名を使用すると、ユーザーがメッセージを送信したこと、およびパートナーがメッセージを送信したことを証明できます。  
  
  **情報漏えいが起こる**  
  
- 悪意のあるユーザーが、BizTalk Server と Microsoft SQL Server™ 間のクリア テキスト形式の通信を読み取ることがあります。 サーバー間の通信をセキュリティで保護するのにインターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を使用できます。 各サーバーへのアクセスを制限するには、ファイアウォールを使用できます。 メッセージの送信中にメッセージのプライバシーを保証するには、暗号化を使用できます。  
  
- 未認証のユーザーが、ネットワーク共有またはディレクトリ上の情報にアクセスすることがあります。 強力な随意アクセス制御リスト (DACL) を使用すると、リソースを使用するアカウントへのアクセスを制限できます。  
  
- BizTalk ホスト インスタンスを実行しているコンピュータの Windows 管理者が、不正を行ってさまざまなレベルの攻撃 (情報の漏えいやサービスの拒否など) を実行することがあります。 ただし、ほとんどの場合、このような攻撃は攻撃者が侵入したコンピュータの特定のホストに制限できます。  
  
  **サービス拒否が起こる**  
  
- 悪意のあるユーザーが、BizTalk Server に大量のメッセージを送信し、BizTalk が有効なメッセージを受信できなくなることがあります。 この脅威を緩和する方法の詳細については、次を参照してください。[拒否のサービス攻撃の緩和](../core/mitigating-denial-of-service-attacks.md)します。  
  
  **特権の昇格**  
  
- 権限の昇格という脅威は通常、信頼していないコードが信頼されている環境で実行されたとき、または悪意のあるユーザーがソフトウェアや構成の不具合を悪用したときに発生します。 環境に展開しているアセンブリやその他のコンポーネントが信頼されていることを確認する必要があります。 権限の昇格攻撃の可能性を最小限に抑えるには、最小限のアクセス許可が与えられた一意のアカウントを使用し、ランタイム サービスやランタイム操作に管理者アカウントを使用しないようにする必要があります。 また、環境内で実行するコンポーネント、アプリケーション、サービスの数を最小限にしてください。  
  
## <a name="see-also"></a>参照  
 [攻撃のサービス拒否攻撃の緩和](../core/mitigating-denial-of-service-attacks.md)   
 [BizTalk Server の展開のセキュリティに関する推奨事項](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [セキュリティの計画](../core/planning-for-security.md)
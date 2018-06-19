---
title: セキュリティで保護されたアーキテクチャの設計 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- firewalls
- architecture, security
- installation, firewalls
- installation, security
ms.assetid: 93df6a3f-396c-4767-99c8-2145bddf8fdf
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 157c11477efb9dec455e9ac2de81736cd4ea72ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239450"
---
# <a name="designing-a-secure-architecture"></a>セキュリティ保護アーキテクチャの設計
BizTalk Server の展開のシステム アーキテクチャに関する詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 トピックで示すアーキテクチャ[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk 環境を脆弱なセキュリティ上の潜在的な脅威の多くに対処します。 ただし、ビジネス資産、ビジネスにとって問題である脅威、および資産の保護や脅威が起きた場合の緩和に使用できるリソースを評価し、最適なアーキテクチャを決定する必要があります。 このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アーキテクチャの設計時に検討する追加のセキュリティ オプションについて説明します。  
  
## <a name="firewalls"></a>ファイアウォール  
 物理的な (ハードウェア) ファイアウォールまたはソフトウェア ファイアウォールを使用して、環境内のリソースへのアクセスを制限できます。 トピックの中に[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)Forefront Threat Management Gateway (TMG) 2010 を使用して、サーバーを作成できますのようなアーキテクチャ ハードウェアまたはサード パーティのソフトウェア ファイアウォールを使用する開くと、別の BizTalk Server コンポーネント間の通信に必要なポートを構成します。 BizTalk Server で使用するポートに関する詳細については、次を参照してください。 [BizTalk Server の必須ポートの](../core/required-ports-for-biztalk-server.md)します。  
  
## <a name="active-directory"></a>Active Directory  
 サンプルの展開では、Active Directory® ディレクトリ サービスを使用して、各サーバー グループの周囲に強力なセキュリティの境界を作成します。 一方向の信頼により、データ ドメインで作成したアカウントで BizTalk Server アプリケーションを実行する場合、処理サーバーで実行している BizTalk Server 以外のアプリケーションの不具合による攻撃から BizTalk Server 環境をさらに保護できます。 データ ドメインはその他のドメインのアカウントを信頼しないため、別のドメインのアカウントが危険にさらされても、BizTalk Server 環境は脅かされないように保護されています。  
  
## <a name="ipsec-and-ssl"></a>IPSec および SSL  
 使用する環境で、ファイアウォールによって提供されるセキュリティ レベルを必要とする重大な脅威が発生していなくても、データ ドメイン、処理ドメイン、サービス ドメインに接続するネットワーク セグメントがさまざまなネットワーク上の攻撃 (パケット スニッフィングや改ざんなど) から物理的に保護されていない場合は、データをあるサーバーから別のサーバーに移動するときに保護する必要があります。 この場合、インターネット プロトコル セキュリティ (IPsec) または Secure Sockets Layer (SSL) を使用して、あるサーバーから別のサーバーへのトラフィックを暗号化できます。  
  
## <a name="see-also"></a>参照  
 [分散アーキテクチャの設計](../core/designing-a-distributed-architecture.md)   
 [セキュリティの計画](../core/planning-for-security.md)   
 [BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)
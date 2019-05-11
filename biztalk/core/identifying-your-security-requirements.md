---
title: セキュリティ要件の確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, configuring
- planning, security
- security, planning
ms.assetid: 5a12c959-59b5-4d44-b2f4-e1ed7053ffd5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80810f6c93102539091076a7b27fb1b4730a3ee0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382827"
---
# <a name="identifying-your-security-requirements"></a>セキュリティ要件を確認します。
次の質問に対する回答では、BizTalk Server 環境内に展開する最善の方法を計画するのに役立ちます。  
  
|質問|推奨|  
|--------------|--------------------|  
|セキュリティで保護された環境で BizTalk Server をデプロイする推奨される方法とは何ですか。|この質問に対する回答は、実際に、環境、会社の資産、これらの資産が潜在的な脅威に対して脆弱である、およびそれらを保護する方法の特定のニーズに依存します。 保護するメインの資産を理解する脅威モデル分析を行うには重要です。<br /><br /> [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk Server 環境をセキュリティで保護するための推奨事項を提供します。 脅威のモデル化するには後、は、このセクションでは、情報を使用して、BizTalk Server のセキュリティで保護された展開の設計。|  
|ビジネス アクティビティ監視 (BAM) を使用する予定ですか。|BAM では、企業ネットワーク内のビジネス ユーザーが BizTalk Server リソースにアクセスする必要があります。 この機能を使用する場合、BizTalk Server の展開を設計するときに留意する追加のセキュリティに関する推奨事項があります。 詳細については、次を参照してください。[インフォメーション ワーカー サービスでの大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)します。|  
|BizTalk Server の機能を使用するセキュリティで保護する最善の方法とは何ですか。|BizTalk Server 環境をセキュリティで保護する方法の一般的な推奨事項は、次を参照してください。 [BizTalk Server の展開のセキュリティに関する推奨事項](../core/security-recommendations-for-a-biztalk-server-deployment.md)します。<br /><br /> BizTalk Server のさまざまな機能を保護する方法に関する推奨事項は、その機能の適切なセキュリティ トピックを参照してください。|  
|BizTalk 環境が公開される潜在的な脅威とは|詳細については、次を参照してください。[潜在的な脅威を識別する](../core/identifying-potential-threats.md)します。|  
|BizTalk Server の実装の潜在的な脅威を緩和する方法とか。|それらを軽減する方法と、環境内の潜在的脅威を特定するには、脅威モデル分析を行う必要があります。 脅威のモデル化の詳細については、Microsoft MSDN Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=25224](http://go.microsoft.com/fwlink/?LinkId=25224)します。|  
|サービス拒否攻撃から環境を保護するにはどうできますか。|サービス拒否攻撃は、軽減するために最も困難な脅威の 1 つです。 これらの攻撃から環境を完全に保護することはできません、中に、環境への影響を軽減するために行えるいくつかのアクションがあります。 詳細については、次を参照してください。[拒否のサービス攻撃の緩和](../core/mitigating-denial-of-service-attacks.md)します。|  
|BizTalk サービスのファイアウォールでは、どのポートを開く必要がありますか。|詳細については、次を参照してください。 [BizTalk Server の必須ポートの](../core/required-ports-for-biztalk-server.md)します。|  
|分散型 BizTalk Server 展開どのようなアカウントを使用する必要がありますか。|環境内で使用する特定のアカウントは、サービスによって異なります。 を使用する、さまざまなサービスの異なるグループおよびアカウントを使用することをお勧めします。 詳細については、次を参照してください。 [Windows アカウントをセキュリティで保護された分散 BizTalk Server 展開の](../core/windows-accounts-for-a-secure-distributed-biztalk-server-deployment.md)します。|  
  
## <a name="see-also"></a>参照  
 [セキュリティの計画](../core/planning-for-security.md)   
 [BizTalk Server の展開のセキュリティに関する推奨事項](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [潜在的な脅威を識別します。](../core/identifying-potential-threats.md)   
 [攻撃のサービス拒否攻撃の緩和](../core/mitigating-denial-of-service-attacks.md)
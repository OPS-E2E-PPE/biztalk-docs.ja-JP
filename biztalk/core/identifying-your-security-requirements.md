---
title: "セキュリティ要件を確認する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, configuring
- planning, security
- security, planning
ms.assetid: 5a12c959-59b5-4d44-b2f4-e1ed7053ffd5
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea9b21cfdfe722d80779dcf9098355b9a5ae3727
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="identifying-your-security-requirements"></a>セキュリティ要件を確認します。
次の質問への回答を参照すると、環境内に BizTalk Server を展開する最善の方法を計画できます。  
  
|質問|推奨|  
|--------------|--------------------|  
|BizTalk Server をセキュリティで保護された環境に展開するための推奨方法を教えてください。|この質問への回答は、実際には環境固有のニーズ、会社の資産、会社の資産が潜在的な脅威の影響をどの程度受けやすいか、資産をどのように保護するかによって異なります。 重要なのは、脅威モデル分析を実行して保護する必要のある主要な資産を見極めることです。<br /><br /> [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk Server 環境をセキュリティで保護するための推奨事項を提供します。 脅威モデリングを実行した後、このセクション内の情報を使用して、セキュリティで保護された独自の BizTalk Server の展開を設計してください。|  
|ビジネス アクティビティ監視 (BAM) を使用する予定ですか?|BAM を使用するには、企業ネットワーク内のビジネス ユーザーが BizTalk Server リソースにアクセスすることが必要になります。 この機能を使用する場合、BizTalk Server の展開を設計する際に注意すべき、セキュリティに関する追加の推奨事項があります。 詳細については、次を参照してください。[インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)です。|  
|使用する予定がある BizTalk Server の機能をセキュリティで保護するための最善の方法を教えてください。|BizTalk Server 環境を保護する方法の一般的な推奨事項は、次を参照してください。 [BizTalk Server 展開のセキュリティに関する推奨事項](../core/security-recommendations-for-a-biztalk-server-deployment.md)です。<br /><br /> BizTalk Server のさまざまな機能をセキュリティで保護する方法の詳細については、該当する機能のセキュリティに関するトピックを参照してください。|  
|BizTalk 環境にはどのような脅威があると考えられますか?|詳細については、次を参照してください。[潜在的な脅威を識別する](../core/identifying-potential-threats.md)です。|  
|BizTalk Server の実装に対して考えられる脅威はどのようなものですか、またその脅威を緩和する方法はありますか?|環境への潜在的な脅威と、その脅威を緩和する方法を特定するには、脅威モデル分析を実行する必要があります。 脅威モデリングの詳細については、Microsoft MSDN Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=25224](http://go.microsoft.com/fwlink/?LinkId=25224)です。|  
|サービスの拒否攻撃から環境を保護するにはどうすればいいですか?|サービスの拒否攻撃は、緩和するのが最も困難な脅威の 1 つです。 このような攻撃から環境を完全に保護することはできませんが、環境への影響を軽減するために実行できる操作がいくつかあります。 詳細については、次を参照してください。[拒否のサービス攻撃の緩和](../core/mitigating-denial-of-service-attacks.md)です。|  
|BizTalk サービスのファイアウォールで開く必要があるポートはどれですか?|詳細については、次を参照してください。 [BizTalk Server の必須ポートの](../core/required-ports-for-biztalk-server.md)します。|  
|分散型 BizTalk Server の展開に使用する必要があるアカウントはどれですか?|環境で使用する特定のアカウントは使用するサービスによって異なりますが、それぞれのサービスに別のグループおよびアカウントを使用することをお勧めします。 詳細については、次を参照してください。[にセキュリティで保護された分散 BizTalk Server の展開用に Windows アカウント](../core/windows-accounts-for-a-secure-distributed-biztalk-server-deployment.md)です。|  
  
## <a name="see-also"></a>参照  
 [セキュリティの計画](../core/planning-for-security.md)   
 [BizTalk Server の展開のセキュリティに関する推奨事項](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [潜在的な脅威を識別します。](../core/identifying-potential-threats.md)   
 [攻撃のサービス拒否攻撃の緩和](../core/mitigating-denial-of-service-attacks.md)
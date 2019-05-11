---
title: BizTalk Server のシステム アーキテクチャの設計 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, security
- security, deploying
ms.assetid: b7ded72a-2487-4bb7-9894-cd13235a52c7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e201f408303ef5a45d512bfbdcafda4c4732a73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351685"
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a>BizTalk Server のシステム アーキテクチャの設計
Microsoft® BizTalk® Server 配置のセキュリティ、パフォーマンス、可用性、および操作の要件は、ビジネス ニーズ、要件、パートナー、会社の規模、および具合に大きく依存します。 一般的な BizTalk Server コンポーネントのいずれかの構成を検討し、そのための規範ガイダンスを提供することは困難です、このセクションではガイダンスと推奨事項を BizTalk Server のさまざまな機能を構成する方法、大規模な企業の運用環境の分散、セキュリティで保護された構成。  
  
 このセクションで紹介するアーキテクチャは、防御について考慮対象として行う高度な分散環境で BizTalk Server の展開に関する参照情報を提供することを目指します。 BizTalk Server のすべてのアプリケーションが問題ドメイン、使用されているプロトコルに基づくセキュリティ要件の独自セットがあり、特定の環境ソリューションで動作します。 パフォーマンス、可用性、およびコストの注意点は、これらの要件に影響します。 独自のニーズ、脅威と、会社の資産に応じた BizTalk Server の展開を作成するのに構成要素としてこれらのアーキテクチャと、このドキュメント内の推奨事項を使用する必要があります。  
  
 このセクションにはでサーバーを配置する方法と、BizTalk Server のさまざまな機能をセキュリティで保護する BizTalk Server のシステム アーキテクチャを設計し、その結果、サーバーの処理や保存、データをセキュリティで保護する方法の詳細情報が含まれています、分散環境の重要なデータとサーバーが、攻撃や災害が発生した場合に侵害される可能性が最小限にします。 このセクションでは、構成、開発に関する推奨事項を提供またはテスト環境を運用環境にアセンブリを展開するための詳細はできません。 アセンブリの展開の詳細については、次を参照してください。 [Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [セキュリティ保護アーキテクチャの設計](../core/designing-a-secure-architecture.md)  
  
-   [分散アーキテクチャの設計](../core/designing-a-distributed-architecture.md)  
  
-   [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)
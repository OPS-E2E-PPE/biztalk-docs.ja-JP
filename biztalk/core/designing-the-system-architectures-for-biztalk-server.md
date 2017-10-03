---
title: "BizTalk Server のシステム アーキテクチャの設計 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, security
- security, deploying
ms.assetid: b7ded72a-2487-4bb7-9894-cd13235a52c7
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a18656a2d4d3827cd38a3f791af2ac856df8ce36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a>BizTalk Server のシステム アーキテクチャの設計
セキュリティ、パフォーマンス、可用性、および運用に関する Microsoft® BizTalk® Server 展開の要件は、ビジネス ニーズ、要件、パートナー、企業規模などにより大きく異なります。 BizTalk Server コンポーネントのいずれかの構成を典型としてとらえたり、その構成のための規範的なガイダンスを示すことは困難ですが、このセクションでは、大規模なエンタープライズの実稼動環境において、セキュリティで保護された分散構成で BizTalk Server のさまざまな機能を構成する方法に関するガイダンスおよび推奨事項について説明します。  
  
 このセクションで紹介するアーキテクチャは、多層防御を考慮に入れた高度な分散環境での BizTalk Server の展開に関する参照情報を提供することを目的としています。 BizTalk Server の各アプリケーションには、問題ドメイン、使用するプロトコル、およびソリューションを運用する特定の環境に基づいたセキュリティに関する固有の要件があります。 さらに、パフォーマンス、可用性、およびコストに関する検討事項によっても要件は異なります。 このドキュメントで説明するアーキテクチャおよび推奨事項は、実際の企業のニーズ、脅威、および資産に合わせてカスタマイズした独自の BizTalk Server 展開を作成する際の構成要素として使用してください。  
  
 このセクションには、BizTalk Server のさまざまな機能と、サーバーが処理および格納するデータをセキュリティで保護するために BizTalk Server のシステム アーキテクチャを設計する方法と、攻撃や災害などの際に重要なデータとサーバーが危険にさらされる可能性を最小限に抑える分散環境にサーバーを配置する方法について説明します。 このセクションでは、開発環境やテスト環境を構成するための推奨事項と、実稼動環境にアセンブリを展開するための詳細については説明しません。 アセンブリの展開の詳細については、次を参照してください。 [Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md)  
  
-   [分散アーキテクチャの設計](../core/designing-a-distributed-architecture.md)  
  
-   [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)
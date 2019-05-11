---
title: 小規模のアーキテクチャのサンプル&amp;規模の企業 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
ms.assetid: fc8c2fdd-bcb1-481c-b351-03092dd48540
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81bde6f78cad46e0c1346ec1ca705f44014d4cb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271064"
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a>小規模のアーキテクチャのサンプル&amp;中規模企業
このセクションでは、小規模または中規模の会社の資産を保護する場合に、Microsoft BizTalk Server をデプロイするサンプル アーキテクチャを提供します。 これらのアーキテクチャでは、縦深防御や攻撃の影響を最小限にサービスの分離を促進、中に、ハードウェア、ソフトウェア、および大企業に一般に利用人事の数量と仮定します。  
  
 ただし、小規模および中規模企業 (または小規模な BizTalk Server 展開に持つ大企業) する必要がありますも考慮する環境を保護する方法。 企業の展開または展開する予定に考えた後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション、中小規模の企業に最大限のセキュリティと使用可能なリソースのバランスを取るサンプル アーキテクチャを導き出しました。 このセクションで情報を使用して、独自の展開を計画する必要があります。 お客様のビジネス ニーズと資産を評価した後、BizTalk Server の展開のさまざまなアーキテクチャを決定する可能性があります。  
  
 アーキテクチャを確認する方法を容易にできるように、このセクションでは、環境内で使用するさまざまなアダプタに基づいたサンプル アーキテクチャを提供します。 図では、BizTalk Server 環境で使用すると、トポロジのコンポーネントがアダプタに依存せずとして、アダプターに依存するコンポーネントを表示します。  
  
 BizTalk Server で使用できるアダプターの一部に基づいた使用シナリオを考察します。 計画して、独自のアーキテクチャを設計するために、このサンプル アーキテクチャの脅威モデル分析を提供します。 この分析を使用すると、パートナーとの通信に使用するアダプタに応じて、企業に影響を与える可能性のあるセキュリティの問題について詳しく説明できます。  
  
 このセクションでは、のセキュリティで保護された展開を設計するのに役立つ情報を提供するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、環境内のサーバー間の通信をセキュリティで保護することも検討環境内のセキュリティを強化します。  
  
> [!IMPORTANT]
>  このセクションでは、ビジネス アクティビティ監視 (BAM) を使用していないことを前提としています。 この機能には、追加のセキュリティに関する考慮事項が必要です。 詳細については[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。  
  
> [!NOTE]
>  このドキュメントに記載されていないアダプタの詳細については、BizTalk Server デベロッパー センターを参照してください ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420)。)。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [サンプル アーキテクチャ:基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)  
  
-   [サンプル アーキテクチャ:HTTP アダプターと SOAP アダプター](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [サンプル アーキテクチャ:BizTalk メッセージ キュー](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [サンプル アーキテクチャ:FTP アダプター](../core/sample-architecture-ftp-adapter.md)  
  
-   [サンプル アーキテクチャ:ファイル アダプター](../core/sample-architecture-file-adapter.md)
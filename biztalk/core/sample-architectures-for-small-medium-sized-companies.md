---
title: サンプル アーキテクチャの小規模&amp;規模の企業 |Microsoft ドキュメント
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
ms.openlocfilehash: 0fa7911b7b2da942d559f2c85ad32e896c79d174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269554"
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a>サンプル アーキテクチャの小規模&amp;中規模企業
このセクションでは、中小企業の資産を保護する必要がある場合に、Microsoft BizTalk Server を展開するためのサンプル アーキテクチャについて説明します。 これらのアーキテクチャでは、重層的な防御とサービスの分離を使用して、攻撃の影響を最小限に抑えていますが、ハードウェア、ソフトウェア、および人材の数量は大企業で一般的に必要であるとされる数量を想定しています。  
  
 ただし、中小企業 (または小規模な BizTalk Server の展開を使用する大企業) では、既存の環境を保護する方法について検討する必要もあります。 そこで、企業が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションをどのように展開したか、または展開する予定であるかを調査し、使用可能なリソースと実現できる最善のセキュリティとのバランスを考えた中小企業向けのサンプル アーキテクチャを導き出しました。 このセクションに記載されている情報は、独自の展開を計画する際に役立ててください。 実際に BizTalk Server を展開する際には、ビジネスのニーズと資産の評価結果に応じたアーキテクチャの使用が必要になります。  
  
 どのようなアーキテクチャを使用するのが適しているのかを簡単に確認できるようにするために、このセクションでは環境で使用することが考えられるさまざまなアダプタに基づいたサンプル アーキテクチャを提供します。 図では、トポロジのどのコンポーネントがアダプタに依存しないコンポーネントであるか、およびどのコンポーネントが BizTalk Server 環境で使用するアダプタに依存しているかを示します。  
  
 また、BizTalk Server で使用できるいくつかのアダプタに基づいた使用シナリオについても見ていきます。 独自のアーキテクチャの計画および設計に役立つように、このサンプル アーキテクチャの脅威モデル分析を提供します。 この分析によって、パートナーとの通信に使用するアダプタに応じて、企業に影響を与える可能性があるセキュリティ上の潜在的な問題の理解を深めることができます。  
  
 このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセキュリティで保護された展開を設計するための情報を提供しますが、実環境でのセキュリティを強化するには、その環境に含まれるサーバーどうしの通信をセキュリティで保護する方法についても検討する必要があります。  
  
> [!IMPORTANT]
>  ここでは、ビジネス アクティビティ監視 (BAM) を使用していない前提で説明します。 この機能を使用する場合は、セキュリティについて別途考慮する必要があります。 これは、後ほど[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
> [!NOTE]
>  このドキュメントに記載されていないアダプタの詳細については、BizTalk Server デベロッパー センターを参照してください ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420))。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)  
  
-   [サンプル アーキテクチャ: HTTP アダプタと SOAP アダプタ](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [BizTalk メッセージ キューのサンプル アーキテクチャ:](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [FTP アダプターのサンプル アーキテクチャ:](../core/sample-architecture-ftp-adapter.md)  
  
-   [ファイル アダプターのサンプル アーキテクチャ:](../core/sample-architecture-file-adapter.md)
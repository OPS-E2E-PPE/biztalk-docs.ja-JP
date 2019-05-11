---
title: アプリケーションへの成果物の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9b5e92e-2e55-41d7-9959-f62753bbeb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ac647201a834d90d745564076b040954c1c3667
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401418"
---
# <a name="adding-artifacts-to-an-application"></a>成果物をアプリケーションに追加します。
追加できますと送信などの成果物を構成し、受信ポート、受信場所、オーケストレーション、管理を使用してコンソールします。 バインド ファイルを生成します。 また、異なる環境にアプリケーションをインポートするごとに異なるバインドを適用する場合、アプリケーションに追加します。  
  
 さらに追加することができます (通常は BizTalk Server 以外の) スクリプト、証明書、およびアプリケーションのリソース ノードの下に、Readme ファイルなどの成果物。 これを行うには、管理コンソールまたは BTSTask を使用します。  
  
 成果物の詳細については、次を参照してください[成果物を追加または作成する方法](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)、[管理成果物](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)と[バインド ファイルとアプリケーションの展開。](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a>成果物を複数の BizTalk アプリケーションにファクタリング  
 開発プロセス中に、利便性のためにアセンブリを単一のアプリケーションに展開することがあります。 さまざまな理由により、実稼働環境に展開する前にアセンブリを複数のアプリケーションにファクタリングする必要が生じる場合があります。  
  
 を展開する前に、アセンブリのファクタリングの徹底的な分析を行う必要があります。 かどうかを実行するありませんファクタリング、完全なファクタリング、または最適なファクタリングを決定します。  
  
 **なしのファクタリング**  
  
 すべての BizTalk アイテムは、1 つのアセンブリには。 これは、最も理解し、デプロイしますが、最小限の柔軟性を提供します。  
  
 **完全なファクタリング**  
  
 各 BizTalk アイテムが、独自のアセンブリです。 これにより、最高の柔軟性を提供しますが、最も複雑なデプロイを理解するには。  
  
 **最適なファクタリング**  
  
 No ファクタリングと、BizTalk アプリケーションの詳細な分析に基づく完全なファクタリングが最適なファクタリングします。 バージョン管理、に加えては、BizTalk ホストの設計を簡単に実装するこのできます。 これは、BizTalk アイテム間の関係を探すことによって実現されます。 可能であれば、常に同じアセンブリ内でまとめてバージョン管理される成果物を配置します。 成果物の独立したバージョン管理が必要な場合は、異なるアセンブリに配置する必要があります。 これは実現するレベルを取り除いたものです。
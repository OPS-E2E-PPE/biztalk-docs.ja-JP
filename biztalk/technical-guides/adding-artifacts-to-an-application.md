---
title: "成果物をアプリケーションに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9b5e92e-2e55-41d7-9959-f62753bbeb04
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c08fa95dddad06efb2c51d93df56b757ae4caca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-artifacts-to-an-application"></a>成果物をアプリケーションに追加します。
追加し送信などのアイテムを構成して受信ポート、受信場所、オーケストレーションを管理を使用してコンソールします。 バインド ファイルを生成し、アプリケーションをインポートする、さまざまな環境ごとに異なるバインドを適用する場合、アプリケーションに追加できます。  
  
 追加することができます (通常 BizTalk Server 以外の) スクリプト、証明書、およびリソース ノードの下のアプリケーションに、Readme ファイルなどのアイテムです。 これを行うには、管理コンソールまたは BTSTask を使用します。  
  
 成果物の詳細については、次を参照してください[成果物を追加または作成する方法](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?。LinkID = 154724)、[成果物の管理](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID = 154725) および[バインド ファイルとアプリケーションの配置](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID = 154726)。  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a>成果物の複数の BizTalk アプリケーションにファクタリング  
 開発プロセス中に、利便性のためにアセンブリを単一のアプリケーションに展開することがあります。 さまざまな理由により、実稼働環境に展開する前にアセンブリを複数のアプリケーションにファクタリングする必要が生じる場合があります。  
  
 を展開する前に、アセンブリのファクタリングの詳細な分析を実行してください。 かどうか行う必要がありますいないファクタリング、完全ファクタリング、または最適なファクタリングを決定します。  
  
 **ありませんファクタリング**  
  
 すべての BizTalk アイテムは、1 つのアセンブリでです。 これは、最も理解および展開するが最低限の柔軟性を提供します。  
  
 **完全ファクタリング**  
  
 各 BizTalk 成果物は、独自のアセンブリでです。 これは、最大限の柔軟性を提供が複雑では、最もを展開し、理解します。  
  
 **最適なファクタリング**  
  
 最適なファクタリングいいえファクタリングと、BizTalk アプリケーションの詳細な分析に基づく完全ファクタリングの間に使用されます。 バージョン管理、に加えてこれにより、BizTalk ホストの設計を簡単に実装します。 これは、BizTalk アイテム間の関係を探すことにより実現されます。 可能であれば、同じアセンブリ内で一緒にバージョン管理は、常にアイテムを配置します。 成果物の独立したバージョンが必要な場合は、異なるアセンブリに配置する必要があります。 これは、達成したいをファクタリングのレベルです。
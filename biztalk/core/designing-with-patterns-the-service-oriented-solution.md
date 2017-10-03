---
title: "パターンを使用したデザイン: サービス指向ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], examples
- examples, programming patterns
- patterns [service solutions], designing
- designing, programming patterns
ms.assetid: c196cd9d-2b2d-4548-bc7d-26196f7c2878
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcfa7f7e4f492de139ae3f5a10f6cb39abaa73be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="designing-with-patterns-the-service-oriented-solution"></a>パターンを使用したデザイン: サービス指向ソリューション
サービス指向ソリューションは、BizTalk アプリケーションを、他のアプリケーションが使用するサービスとして提供する方法を示します。 アプリケーションをサービスとして提供すると、他のアプリケーションは情報を簡単に取り込み、自ら提供するサービスで利用できるようになります。 インターフェイスはサービスの詳細についてで「Service Interface」を参照して[http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185)です。 サービス指向の統合の詳細についてはの「Service-Oriented Integration」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186)です。  
  
 このソリューションは、その他の 3 つのアプリケーションから関連情報を集約した後に、Web サービス応答として情報を提供するクレジット情報アプリケーションです。 このアプリケーションは、結果を統合し、まとめられたクレジット情報を含んでいる 1 つのメッセージを返します。 3 つのバックエンド システムは次のとおりです。  
  
-   **SAP Enterprise システム:** SAP バックエンドは、顧客の総合的なクレジット限度額を提供します。 ソリューションは、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 内の SAP アダプターを使用してこのバックエンド システムと通信します。  
  
-   **Pending Transactions システム。** Pending Transactions システムは、アカウントの未処理トランザクションの合計額を報告します。 このソリューションでは、Windows Server からメインフレームとのやりとりに、Microsoft Host Integration Server (HIS) を使用します。 また、HIS のトランザクション インテグレータ技術も使用します。 これらの技術によって、システムは Web サービスとしてのメインフレームと連携できるようになります。 BizTalk オーケストレーションではこの Web サービスを使用します。  
  
-   **Payment Tracking システム。** Payment Tracking システムは、個人から最後に支払われた金額を報告します。 このシステムでは MQSeries を使用します。  
  
 ソリューションの概要で説明されているように、MQSeries キューを経由して Web サービス以外のインターフェイスを使用することもできます (アプリケーションの一般的な構造の詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md))。 Web サービスは、最も一般的なサービス指向アーキテクチャ作成手段ですが、すべてのアプリケーションが Web サービスを使用できるわけではありません。 BizTalk Server ソリューションでは、Web サービスのほかに、レガシ アプリケーションでサービスを使用するための代替手段も提供できます。  
  
 MQSeries アクセスは、レガシ音声自動応答装置 (IVR) がソリューションを使用する方法をシミュレートします。 MQSeries アクセスは、Web サービス アクセスと共に、レガシ アプリケーションと新しいアプリケーションの両方が 1 つのソリューションを利用できる方法を示します。  
  
## <a name="patterns-used-in-the-service-oriented-solution"></a>サービス指向ソリューションで使用されるパターン  
 次の図は、サービス指向ソリューションのパターンを簡単に示しています。  
  
 ![サービス &#45; 指向のソリューション パターン](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
 ソリューションは、パターンを表す 4 つの主要な部分で構成されています。 サービス インターフェイス、コンテンツ ベースのルーター、受信者の一覧、およびアグリゲーター。 サービス インターフェイスは、ソリューションに接続するためのインターフェイス メカニズムを表します。 コンテンツベースのルーターは、メッセージの有効性を検証し、無効な場合にエラー メッセージを送信します。 受信者一覧は、メッセージを 3 つのバックエンド アプリケーションに送信します。 バックエンド アプリケーションの応答後、アグリゲータではこれらの応答を 1 つの応答メッセージに組み合わせます。 応答メッセージは、サービス インターフェイスを経由して要求元に返されます。  
  
 図ではロットは指定されていません。  
  
-   この図では、メッセージ トランスレータが省略されています。メッセージ トランスレータは、外部システムと通信するためにソリューションが必要とするものです。  
  
-   この図では、バックエンド プロセッサとの通信方法は指定されていません。  
  
-   また、サービス インターフェイスの特性も指定されていません。  
  
-   さらに、同期通信と非同期通信のどちらを使用するかも示されていません。  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのサービスの開発](../core/developing-a-service-oriented-solution.md)   
 [指向ソリューションのパターンのサービスの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)
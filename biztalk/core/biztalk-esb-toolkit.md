---
title: BizTalk ESB Toolkit |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08035518-17ad-44d2-ab06-90d725c95ced
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ba628683b5ae54b407fc30e655a462a87e18957
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358093"
---
# <a name="biztalk-esb-toolkit"></a>BizTalk ESB Toolkit
Microsoft BizTalk ESB Toolkit は、疎結合のメッセージング アーキテクチャをサポートするために Microsoft BizTalk Server を使用します。 BizTalk Server には、サービス指向アーキテクチャ (SOA) アプリケーションの効率性と拡張性の高いプラットフォームを提供するメッセージング アプリケーションを作成して動作して、いっぱいになるサブスクリプションの強力なパブリッシュ/サブスクライブ メカニズムが含まれています。 BizTalk ESB Toolkit は、さまざまな軽量のサービスのスケジュールに基づくサービス呼び出しが組み込まれた堅牢な接続されている、サービス指向のアプリケーションの構築に重点を置いた新しい機能を提供する BizTalk Server の機能を拡張します。合成、動的解決のエンドポイントやマップ Web サービスと ws-* の統合、障害管理とレポート、およびサードパーティの SOA 管理ソリューションとの統合。  
  
## <a name="overview"></a>概要  
 BizTalk ESB Toolkit は、アーキテクチャに関するガイダンス、パターン、および Microsoft プラットフォームでエンタープライズ サービス バス (ESB) の開発を簡略化し、Microsoft のお客様に拡張を許可する、BizTalk Server と .NET Framework のコンポーネントのコレクションを提供します。独自のメッセージングとの統合ソリューションです。  
  
## <a name="common-scenarios"></a>一般的なシナリオ  
 サービス指向アーキテクチャ (SOA) を有効にするためのインフラストラクチャの実装のコンテキストで Enterprise Service Bus (ESB) が広く使用されているターム。 ただし、Soa のデプロイによって現実エクスペリエンスでは、ESB は包括的なサービス指向インフラストラクチャ (SOI) を構成する多くの構成要素の 1 つだけが表示されます。 ESB がさまざまな異なる方向で変化したという用語とその定義は、個々 の ESB との統合プラットフォーム ベンダーの解釈および特定の SOA イニシアティブの要件によって異なります。 Microsoft が成功した多くの現実 SOI 実装から収集された経験に基づき、考えることができます、ESB の従来のエンタープライズ アプリケーション統合 (EAI)、メッセージ指向ミドルウェア、に基づいてアーキテクチャのパターンのコレクションWeb サービス、.NET と Java の相互運用性、ホスト システム統合、およびサービス レジストリおよび資産リポジトリとの相互運用。  
  
## <a name="audience-requirements"></a>対象ユーザーの要件  
 BizTalk ESB Toolkit は、Microsoft BizTalk Server ソリューション、または BizTalk ESB Toolkit コンポーネントを使用する他のソリューションを作成する開発者を対象としています。 BizTalk ESB Toolkit の完全な利用、開発者は、知識を持っているし、次の操作が発生します。  
  
1.  Microsoft BizTalk Server  
  
2.  Microsoft Visual Studio  
  
3.  Microsoft .NET 開発手法、ASP.NET Web サービスと .NET Framework コンポーネントの開発など  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB Toolkit の動作  
 BizTalk ESB Toolkit が受信メッセージを受け入れるし、おそらく (が常にではありません) には、動作など、変換、配信、またはその他のカスタム定義プロセスのプロセスを実行することによって。 演算を指定するために必要な中心となる処理コンポーネントには、メッセージの内容を実行するには、関連付けられている手順またはを適用するプロセスを定義するメタデータとタスクを格納するメッセージが必要です。   
このアプローチは、サービス間の疎結合を提供します。これは、ESB メッセージごとに、特定の処理に関する予備知識が必要ないことを意味します。 考えられる範囲のプロセスと各プロセスを適用する方法を知るだけがあります。 広範囲の可能なプロセスのプロセスとメッセージ内の指示のマッピングを指定するためのオプションは、構成およびコードを再デプロイを変更しなくても、動作を調整するための柔軟なメカニズムを提供します。コンポーネント。  
  
## <a name="getting-started"></a>作業の開始  
 BizTalk ESB Toolkit をインストールすると、「はじめに」のトピックをお読みください、 [BizTalk ESB Toolkit のドキュメント](http://go.microsoft.com/fwlink/?LinkId=193578)アーキテクチャ、メッセージ フロー、および BizTalk ESB Toolkit のコア コンポーネントを理解します。 インストールして、「はじめに」のトピックとその他のメッセージング シナリオで説明されている一般的なユース ケースの例を示す、BizTalk ESB Toolkit に含まれているサンプルを実行する必要があります。 このアプローチを使用すると、BizTalk ESB Toolkit の動作方法、および独自の SOA アプリケーションでその機能の活用を行うことができますをすばやく把握できます。  
  
## <a name="see-also"></a>参照  
 [BizTalk エンタープライズ サービスのガイダンス](http://go.microsoft.com/fwlink/?LinkId=193577)   
 [サービス指向ソリューション](../core/service-oriented-solution.md)   
 [Web サービスの使用](../core/using-web-services.md)
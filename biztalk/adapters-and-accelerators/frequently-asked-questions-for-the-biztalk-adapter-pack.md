---
title: よく寄せられる質問の BizTalk Adapter Pack |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cdaf09a-50fe-4f30-bd9d-60e316351846
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dc6c4c318889ad078106c805591adaeedd5ee7d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989155"
---
# <a name="frequently-asked-questions"></a>よく寄せられる質問
よく寄せられる質問 (Faq)、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  


## <a name="general-questions"></a>一般的な質問

### <a name="what-are-the-supported-biztalk-versions-for-the-biztalk-adapter-pack"></a>BizTalk Adapter Pack のサポートされているバージョンの BizTalk とは  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Microsoft に含まれている[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 含まれているバージョンをインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョン。 インストール、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]別[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョンがサポートされていません。 

### <a name="in-which-user-context-should-the-setup-be-run"></a>ユーザー コンテキストをセットアップ実行するでしょうか。  
実行、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ローカルの administrators グループのメンバーであるアカウントを使用した設定と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 

関連リンク:[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)

### <a name="how-do-i-get-started-using-the-adapter"></a>方法は開始するには、アダプタを使用しますか。  
慣れている場合[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、インストールし、 [BAP 2016](../adapters-and-accelerators/install-the-biztalk-adapter-pack-2016.md)または[BAP 2013 R2 および 2013](../adapters-and-accelerators/install-biztalk-adapter-pack-2013-r2-and-2013.md)、し始める、[異なるアダプター](../adapters-and-accelerators/biztalk-adapter-pack.md).

まったく新しい場合[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]または[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]get を見て、トピックを開始して、チュートリアルの手順。 

[Oracle データベース用 BizTalk アダプターの概要します。](../adapters-and-accelerators/adapter-oracle-database/get-started-with-the-oracle-database-adapter.md)  
[Oracle E-business Suite 用 BizTalk アダプターの概要します。](../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)  
[BizTalk Adapter for mySAP Business Suite の概要します。](../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)  
[BizTalk Adapter for Siebel eBusiness Applications の概要します。](../adapters-and-accelerators/adapter-siebel/get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[SQL 用 BizTalk アダプターを概要します。](../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)

### <a name="does-the-microsoft-biztalk-adapter-pack-support-tracing"></a>Microsoft BizTalk Adapter Pack は、トレースをサポートしますか。  
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]によりアダプターでクライアントに Windows Communication Foundation (WCF) トレースとアダプター固有のトレースを有効にします。 トレースを有効にする場合は、フォルダーのパスとファイル名を選択します。 そのため、トレースを使用する、格納されます。 トレースを表示するには、WCF サービス トレース ビューアー ツールを使用します。 参照してください[相関トレースの表示は、サービス トレース ビューアーを使用して、トラブルシューティング](https://msdn.microsoft.com/library/aa751795.aspx)します。

トレース、およびその他のトラブルシューティングの方法を紹介する方法の詳細については、次を参照してください。 

[Oracle データベース アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[Oracle EBS アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)  
[SAP アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)  
[Siebel アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)  
[SQL アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)  

### <a name="are-performance-counters-available-for-the-adapters"></a>アダプターのパフォーマンス カウンターがあるでしょうか。  
可能。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供、 **LOB 時間 (累積)** LOB クライアント ライブラリがアダプターによって開始された操作が完了するには、ミリ秒単位の時間を測定するパフォーマンス カウンター。  設定して、パフォーマンス カウンターを有効にすることができます、`EnablePerformanceCounters`プロパティをバインド**True**します。 パフォーマンス カウンターを無効にするには設定`EnablePerformanceCounters`に**False** (既定値)。   

## <a name="biztalk-server-questions"></a>BizTalk Server に関する質問

### <a name="which-biztalk-server-tools-are-used-while-working-with-adapters-where-can-i-find-more-information-about-these-tools"></a>アダプターの操作中に使用される BizTalk Server のツールですか。 これらのツールの詳細についてはどこで入手できますか。  
これらのアダプターを使用するアイテムに役立ついくつかのツールがあります。 


|                                  ツール                                  |                                                                                                                                                                                           トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コア ドキュメント                                                                                                                                                                                            |
|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] | -   [Visual Studio を使用](../core/using-visual-studio.md) <br />-   [BizTalk プロジェクトでの作業](../core/working-with-biztalk-projects.md)<br />-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> 詳細についての Visual Studio のソリューション、プロジェクト、およびにある項目について説明します[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)します。 |
|                         オーケストレーション デザイナー                         |                                                                                                                                                                                       [オーケストレーション デザイナーを使用してオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                        |
|                           パイプライン デザイナー                            |                                                                                                                                                                                                 [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                  |
|                             BizTalk マッパー                             |                                                                                                                                                                                                         [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                          |
|                 BizTalk Server 管理コンソール                  |                                                                                                                                                                                            [BizTalk Server 管理コンソールの使用](../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                             |

### <a name="can-i-reuse-bindings-of-a-biztalk-application-how"></a>BizTalk アプリケーションのバインドを再利用できますか。 どう。  
可能。 バインディングは、オーケストレーション ポートなど、ロール リンクの論理エンドポイントとの送信などの物理的なエンドポイント間のマッピングを作成し、受信ポート。 これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。 バインド情報は、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルに格納されます。 BizTalk アセンブリ、アプリケーション、またはグループのバインドをエクスポートし、その他の BizTalk アプリケーションまたはグループにインポートすることで再利用できます。 詳細については、「 

[Oracle DB アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)  
[Oracle EBS アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
[SAP アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)  
[Siebel アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)  
[SQL アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)

### <a name="what-is-the-transaction-isolation-level-how-can-i-configure-it"></a>「トランザクション分離レベル」とは何ですか。 構成するにはどうできますか。  
 トランザクション分離レベルは、トランザクションを他のトランザクションによって行われたデータ変更から分離レベルを指定します。 基幹業務 (LOB) システムへの接続で発行された TRANSACT-SQL コマンドのロック動作を定義します。 

一部のアダプターの構成が可能になります。 次のチュートリアルを参照してください。 

[Oracle データベース: トランザクション分離レベルとトランザクションのタイムアウトを構成します。](../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)  
[Oracle E-business Suite: トランザクション分離レベルとトランザクションのタイムアウトを構成します。](../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)  
[SQL: トランザクション分離レベルとトランザクションのタイムアウトを構成します。](../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)

[SQL データベース エンジンにおける分離レベル](https://technet.microsoft.com/library/ms189122.aspx)SQL でさまざまなレベルについて説明します。 

## <a name="wcf-based-adapter-faqs"></a>WCF ベース アダプターに関する Faq

### <a name="what-is-wcf"></a>WCF とは何ですか。
 WCF は、Windows Communication Foundation の略です。 WCF は、サービス指向アプリケーションを構築するために、Microsoft が開発したプログラミング フレームワークです。 WCF では、.NET framework の一部であるし、プラットフォーム間で統合して、既存の投資との相互運用する、セキュリティで保護された信頼性の高いトランザクション処理されたソリューションを構築することができます。  

関連リンク:[内容は、Windows Communication Foundation](https://msdn.microsoft.com/library/ms731082.aspx)  

### <a name="what-is-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK とは何ですか。  
 WCF LOB Adapter SDK は、基幹業務システムの再利用可能なメタデータが豊富なアダプターを開発するための一貫したフレームワークを提供するツールやコンポーネントのコレクションです。 WCF LOB Adapter SDK を使用して記述アダプターでは、カスタム WCF バインドとして表示され、WCF 対応クライアントで使用できます。 

関連リンク: [Business Adapter SDK の行の WCF のドキュメント](../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md) 

### <a name="what-is-the-wcf-service-model"></a>WCF サービス モデルとは何ですか。  
 WCF サービス モデルは、WCF の WCF サービスとして公開されます (Oracle や SAP) などの LOB システムに用意されたプログラミング モデルです。 サービス コントラクト、クライアントとサービス間に存在するは .NET インターフェイスとして表され、操作はこのインターフェイスのメソッドとして表されます。 WCF サービス モデルには、プロキシ クラスが生成されます: WCF クライアント クラス-コードで操作を呼び出すし、アダプターを使用してデータを受信します。 

 すべてのアダプターで、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] WCF サービスのモデルをサポートします。

 ### <a name="what-is-the-wcf-channel-model"></a>WCF チャネル モデルとは何ですか。  
 WCF チャネル モデルとは、クライアントとサービス間で SOAP メッセージ交換の低レベルの抽象化です。 インターフェイスおよびチャネル スタックと呼ばれる複数層のプロトコル スタックを使用してメッセージを送受信するための型を提供します。 チャネルのスタックの各層がで構成され、WCF バインドから各チャネルが作成されます。 各アダプターは、WCF サービスとしての LOB システムを公開する WCF カスタム トランスポート バインドです。 

  すべてのアダプターで、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] WCF チャネル モデルをサポートします。

### <a name="when-should-i-use-the-wcf-service-model-or-the-wcf-channel-model"></a>WCF サービス モデルまたは WCF チャネル モデルを使用する必要がありますは場合でしょうか。  
 WCF サービス モデルは、.NET プログラマにとって馴染み深いをチャネル経由で基になる SOAP メッセージ交換の複雑さが隠蔽されますモデルを表示します。 さらに、Add Adapter Service Reference プラグインを使用して、Visual Studio のデザイン エクスペリエンスの統合は、強力な閲覧と検索、アダプターによって公開される操作の機能を提供する標準の Microsoft Windows インターフェイスを表示します。 したがって、WCF サービス モデルは、任意の WCF ベース アダプター用のプログラミングのソリューションの開発に最適な選択肢では多くの場合です。  

 WCF サービス上で WCF チャネル モデルを使用するモデルします。  

-   WCF チャネル モデルでは、WCF チャネル モデルで制御するため直接チャネル経由で送信するメッセージの内容には、LOB システムで実行する操作のきめの細かい制御を提供します。  

-   WCF チャネル モデルには、WCF サービスのモデルよりも、ラージ オブジェクト (LOB) データ型のストリーミングは、エンド ツー エンドのより包括的なサポートが用意されています。 これは、ため、WCF チャネル モデルで直接制御する送信メッセージにメッセージ本文を提供する方法と、受信メッセージでメッセージ本文を処理する方法です。 

### <a name="how-do-i-get-started-with-the-wcf-service-model"></a>方法は開始するには、WCF サービス モデルですか。  
 サービス メタデータからコードを WCF クライアント クラスまたは WCF サービス コントラクトと関連付けられているヘルパーを生成する WCF サービス モデルでは、各アダプターによって公開されている提供された、次のツールのいずれかを使用することができます。  

- ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)、WCF に付属します。  

- アダプター サービス参照を Visual Studio プラグインの追加、付属している、[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]します。  

### <a name="how-do-i-get-started-with-the-wcf-channel-model"></a>方法は開始するには、WCF チャネル モデルですか。  
 WCF チャネル モデルを使用して、操作を呼び出すし、アダプターを使用した WCF チャネル経由で SOAP メッセージを交換することでポーリング クエリの結果を受信できます。 開始するには、(クライアント) の送信と受信 (サービス) チャネルを作成する必要があります。

## <a name="see-also"></a>参照  
[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)
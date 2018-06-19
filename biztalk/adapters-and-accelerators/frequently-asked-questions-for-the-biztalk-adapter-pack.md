---
title: よく寄せられる質問、BizTalk Adapter Pack の |Microsoft ドキュメント
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
ms.openlocfilehash: 7c9d6e28a5839bafb135285b90d8174a3fa18f49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227090"
---
# <a name="frequently-asked-questions"></a>よく寄せられる質問
よく寄せられる質問 (Faq)、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。  
 

## <a name="general-questions"></a>一般的な質問

### <a name="what-are-the-supported-biztalk-versions-for-the-biztalk-adapter-pack"></a>BizTalk アダプター パックのサポートされているバージョンの BizTalk は?  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]が Microsoft に含まれる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 付属するバージョンをインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョン。 インストール、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]別[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョンがサポートされていません。 
  
### <a name="in-which-user-context-should-the-setup-be-run"></a>ユーザー コンテキスト、セットアップ実行してください。  
実行、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ローカルの administrators グループのメンバーであるアカウントを使用した設定と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 

関連リンク:[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)

### <a name="how-do-i-get-started-using-the-adapter"></a>どのようにすれば開始アダプターを使用しますか。  
慣れている場合[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、インストールし、 [BAP 2016](../adapters-and-accelerators/install-the-biztalk-adapter-pack-2016.md)または[BAP 2013 R2 と 2013](../adapters-and-accelerators/install-biztalk-adapter-pack-2013-r2-and-2013.md)、し始めると、[異なるアダプター](../adapters-and-accelerators/biztalk-adapter-pack.md).

まったく経験がない場合[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]または[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、get 見て開始トピック、およびステップ チュートリアルでは、実行。 

[Oracle データベースの BizTalk アダプターの概要します。](../adapters-and-accelerators/adapter-oracle-database/get-started-with-the-oracle-database-adapter.md)  
[BizTalk adapter for Oracle E-business Suite 作業を開始します。](../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)  
[BizTalk Adapter 用 mySAP Business Suite の概要します。](../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)  
[BizTalk Adapter for Siebel eBusiness Applications の概要します。](../adapters-and-accelerators/adapter-siebel/get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[SQL 用 BizTalk アダプターを概要します。](../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)
   
### <a name="does-the-microsoft-biztalk-adapter-pack-support-tracing"></a>Microsoft BizTalk Adapter Pack は、トレースをサポートしますか。  
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Windows Communication Foundation (WCF) のトレースとアダプター固有のトレースを有効にするアダプターのクライアントを有効にします。 トレースを有効にする場合は、フォルダーのパスとファイル名を選択します。 そのため、トレースを使用する、格納されます。 トレースを表示するには、WCF サービス トレース ビューアー ツールを使用します。 参照してください[相関トレースの表示は、サービス トレース ビューアーを使用して、トラブルシューティング](https://msdn.microsoft.com/library/aa751795.aspx)です。

詳細については、トレース、およびその他のトラブルシューティングのアイデアを参照してください。 

[Oracle データベース アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[Oracle EBS アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)  
[SAP アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)  
[Siebel アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)  
[SQL アダプターをトラブルシューティングします。](../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)  
  
### <a name="are-performance-counters-available-for-the-adapters"></a>アダプターのパフォーマンス カウンターを利用しますか。  
可能。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供、 **LOB 時間 (累積)** LOB クライアント ライブラリは、アダプターによって開始された操作が完了する時間をミリ秒単位で、時間を測定するパフォーマンス カウンター。  設定して、パフォーマンス カウンターを有効にすることができます、`EnablePerformanceCounters`にプロパティのバインド**True**です。 パフォーマンス カウンターを無効にする設定`EnablePerformanceCounters`に**False** (既定値)。   

## <a name="biztalk-server-questions"></a>BizTalk Server に関する質問

### <a name="which-biztalk-server-tools-are-used-while-working-with-adapters-where-can-i-find-more-information-about-these-tools"></a>アダプターの操作中に使用される BizTalk Server ツールですか。 これらのツールの詳細についてはどこで入手できますか  
これらのアダプターを使用している成果物に役立つツールがいくつかあります。 
 
 |ツール|トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主要マニュアル|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]|-   [Visual Studio の使用](../core/using-visual-studio.md) <br />-   [BizTalk プロジェクトでの作業](../core/working-with-biztalk-projects.md)<br />-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> 詳細についての Visual Studio ソリューション、プロジェクトでは、ある項目の[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)です。|  
|オーケストレーション デザイナー|[オーケストレーション デザイナーを使用してオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md)|  
|パイプライン デザイナー| [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)|  
|BizTalk マッパー| [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)|  
|BizTalk Server 管理コンソール|[BizTalk Server 管理コンソールの使用](../core/using-the-biztalk-server-administration-console.md)|  
  
### <a name="can-i-reuse-bindings-of-a-biztalk-application-how"></a>BizTalk アプリケーションのバインドを再利用できますか。 どう。  
可能。 バインディングは、オーケストレーション ポートなど、ロール リンクの論理エンドポイントとの送信などの物理的なエンドポイント間のマッピングを作成し、受信ポートをします。 これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。 バインド情報は、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルに格納されます。 BizTalk アセンブリ、アプリケーション、またはグループのバインドをエクスポートし、その他の BizTalk アプリケーションまたはグループにインポートすることによって再利用できます。 詳細については、「 

[Oracle データベース アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)  
[Oracle EBS アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
[SAP アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)  
[Siebel アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)  
[SQL アダプターのバインドを再利用します。](../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)
  
### <a name="what-is-the-transaction-isolation-level-how-can-i-configure-it"></a>「トランザクション分離レベル」とは何ですか。 構成する方法にしますか。  
 トランザクション分離レベルでは、トランザクションは、その他のトランザクションによって行われたデータ変更から分離する度合いを判断します。 基幹業務 (LOB) システムへの接続で発行された TRANSACT-SQL コマンドのロック動作を定義します。 
  
これは、一部のアダプターの構成が可能です。 次のチュートリアルを参照してください。 

[Oracle データベース: トランザクション分離レベルとトランザクションのタイムアウトを構成します。](../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)  
[Oracle E-business Suite: トランザクション分離レベルとトランザクションのタイムアウトを構成します。](../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)  
[SQL: トランザクション分離レベルとトランザクションのタイムアウトを構成します。](../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)

[SQL データベース エンジンにおける分離レベル](https://technet.microsoft.com/library/ms189122.aspx)SQL のさまざまなレベルについて説明します。 

## <a name="wcf-based-adapter-faqs"></a>WCF ベース アダプターに関する Faq

### <a name="what-is-wcf"></a>WCF とは何ですか。
 WCF は、Windows Communication Foundation を表しています。 WCF は、サービス指向アプリケーションを構築するために、Microsoft によって開発されたプログラミング フレームワークです。 WCF では、.NET framework の一部であるし、プラットフォーム間を統合し、既存の投資と相互運用をセキュリティで保護された、信頼性、およびトランザクションのソリューションを構築することができます。  
  
関連リンク:[新機能は、Windows Communication Foundation](https://msdn.microsoft.com/library/ms731082.aspx)  
  
### <a name="what-is-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK とは何ですか。  
 WCF LOB Adapter SDK は、一連のツールや基幹業務システムを再利用可能なメタデータが豊富なアダプターを開発するための一貫したフレームワークを提供するコンポーネントです。 WCF LOB Adapter SDK を使用して作成されたアダプターは、カスタム WCF バインドとして公開され、WCF 対応クライアントで利用できます。 
 
関連リンク:[ビジネス アダプター SDK の行の WCF ドキュメント](../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md) 

### <a name="what-is-the-wcf-service-model"></a>WCF サービス モデルは何ですか。  
 WCF サービス モデルは、(Oracle や SAP) などの LOB システムが WCF サービスとして公開されている WCF に用意されたプログラミング モデルです。 .NET インターフェイス、クライアントとサービス間に存在するサービス コントラクトが表示され、操作は、このインターフェイスのメソッドとして表されます。 WCF サービス モデルは、プロキシ クラスを生成: WCF クライアント クラス —、コードで操作を呼び出すし、アダプターを使用してデータを受信する、します。 
 
 すべてのアダプター、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] WCF サービス モデルをサポートします。
 
 ### <a name="what-is-the-wcf-channel-model"></a>WCF チャネル モデルとは何ですか。  
 WCF チャネル モデルは、クライアントとサービス間で SOAP メッセージ交換の低レベルの抽象化です。 インターフェイスとすると、チャネル スタックと呼ばれる階層状のプロトコル スタックを使用してメッセージを送受信できるようにする型を提供します。 スタックの各層は、チャネルから成るされ、WCF バインドから各チャネルが作成されます。 各アダプターは、WCF サービスとしての LOB システムを公開する WCF カスタム トランスポート バインディングです。 
 
  すべてのアダプター、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] WCF チャネル モデルをサポートします。
  
### <a name="when-should-i-use-the-wcf-service-model-or-the-wcf-channel-model"></a>WCF サービス モデルまたは WCF チャネル モデルを使用する必要がありますは場合ですか。  
 WCF サービス モデルでは、.NET プログラマに慣れており、チャネル経由で SOAP メッセージ交換の基になる複雑さを非表示にするモデルを表示します。 さらに、アダプター サービス参照の追加プラグインを使用して、Visual Studio のデザイン エクスペリエンスが統合されており、強力な参照および検索アダプターによって公開される操作の機能を提供する標準的な Microsoft Windows インターフェイスを提供します。 そのため、WCF サービス モデルは、いずれかの WCF ベース アダプター プログラミングのソリューションを開発する最適な選択肢では多くの場合です。  

 WCF サービス経由で WCF チャネル モデルを使用するモデルの場合。  
  
-   WCF チャネル モデルでは、WCF チャネル モデルで制御するため直接チャネル経由で送信するメッセージの内容、LOB システムで実行する操作をより詳細に制御を提供します。  
  
-   WCF チャネル モデルでは、WCF サービスのモデルよりもラージ オブジェクト (LOB) データ型のエンド ツー エンドのストリーミングをサポートする包括的なを指定します。 これは、ため、WCF チャネル モデルで直接制御する送信メッセージにメッセージ本文を指定する方法と、受信メッセージでメッセージ本文を処理する方法です。 
  
### <a name="how-do-i-get-started-with-the-wcf-service-model"></a>どのようにすれば開始 WCF サービス モデルでですか。  
 サービス メタデータからコードを WCF クライアント クラスまたは WCF サービス コントラクトと関連付けられているヘルパーを生成する WCF サービス モデルでは、各アダプターによって公開されている指定された、次のツールのいずれかを使用できます。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF に付属します。  
  
-   アダプター サービス参照を Visual Studio プラグインの追加に付属している、[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]です。  
  
### <a name="how-do-i-get-started-with-the-wcf-channel-model"></a>どのようにすれば開始 WCF チャネル モデルとしますか。  
 WCF チャネル モデルを使用して、操作を呼び出すし、アダプターで WCF チャネル経由で SOAP メッセージを交換することによって、ポーリング クエリの結果を受信できます。 、作業を開始するには、(クライアント) の送信と受信 (サービス) チャネルを作成する必要があります。
  
## <a name="see-also"></a>参照  
[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)
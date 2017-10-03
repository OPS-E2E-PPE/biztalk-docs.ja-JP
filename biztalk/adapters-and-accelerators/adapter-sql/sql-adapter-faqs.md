---
title: "SQL アダプターに関する Faq |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25369e6b-d1f2-4abc-9ffc-4cb9aef1d3fb
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dee4b402e548f55dd8eab4583215d879c98186b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sql-adapter-faqs"></a>SQL アダプターに関する Faq
次は一部よく寄せられる質問 (Faq) に関連する[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]と[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]一般にします。  
  
## <a name="how-can-i-use-the-sql-adapter-to-communicate-with-the-sql-server-database"></a>SQL Server データベースと通信するために、SQL アダプターを使用する方法は?  
 SQL アダプタを使用すると、BizTalk アプリケーションを開発、WCF サービス モデルを使用してまたは WCF チャネル モデルを使用して、SQL Server データベースと通信します。 詳細については、次を参照してください。[概要の BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)です。  
  
## <a name="what-interfaces-are-supported-by-the-sql-adapter-for-retrieving-metadata"></a>SQL アダプターでは、メタデータの取得をどのようなインターフェイスがサポートしますか。  
 SQL アダプターには、メタデータを取得するための 2 つのインターフェイスがサポートされています。  
  
-   WCF に用意された MetadataExchange です。 WCF は、クライアントが、SQL Server データベースからメタデータを取得することができますにすべての WCF バインドをメタデータ交換エンドポイントに提供します。  
  
-   WCF LOB アダプター SDK、参照および検索機能を備えたアダプターのメタデータをサポートするによって提供される IMetadataRetrievalContract です。  
  
## <a name="how-does-the-sql-adapter-support-high-availability-of-data"></a>SQL アダプターがデータの高可用性をサポートする方法  
 指定する際に、 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)SQL Server データベースに接続する場合、SQL アダプターを指定できますフェールオーバー SQL Server データベースに接続する場合は、プライマリ SQL Server データベースの名前ではありません使用できます。 パラメーターを使用して、省略可能な FailoverPartner 接続 URI でフェールオーバーの SQL Server データベースが指定されました。  
  
## <a name="can-i-migrate-biztalk-projects-created-using-the-previous-version-of-the-sql-adapter-to-use-the-wcf-based-sql-adapter-how"></a>WCF ベースの SQL アダプターを使用して、SQL アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを移行できますか。 どう。  
 可能。 WCF ベースの SQL アダプターを使用して、SQL アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトの移行の手順を確認する「 [SQL アダプタ チュートリアル](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)です。  
  
## <a name="does-the-sql-adapter-provide-a-secure-way-of-communicating-with-the-sql-server-database--are-there-any-best-practices-to-ensure-security-of-data"></a>SQL アダプターは、SQL Server データベースとの通信のセキュリティで保護された方法を提供しますか。  データのセキュリティを確保するのベスト プラクティスはありますか。  
 SQL アダプターは、SQL Server データベースに、確立された接続での認証にエンタープライズ シングル サインオン (SSO) と統合セキュリティをサポートします。 SSO を使用して資格情報は暗号化し、レジストリに格納されています。 システムでは、これらの資格情報を使用して、未承認のアクターによって認識がそれらを入力するユーザーを要求する代わりに、アクセスを決定します。 統合セキュリティは、SQL server へのアクセスにログオンしたユーザーの資格情報を使用します。 これは、ユーザーが資格情報を入力する必要もなくなります。 データベース管理者を正常に動作する統合セキュリティ用のユーザーの資格情報を受け入れるように SQL を構成する必要があります。  
  
 SQL アダプターもできない、アダプター サービス参照を Visual Studio プラグインの追加とアダプター サービス BizTalk プロジェクトを使用する追加を防ぐために作業中に、SQL Server データベースの接続 URI でユーザーの資格情報を入力します。クリア テキストで表示されないように資格情報です。 さらに、パスワードは、(、アダプター サービス参照を Visual Studio プラグインの追加によって生成された) 構成ファイルと (アダプター サービスの使用する BizTalk プロジェクト アドインで生成)、バインド ファイルには書き込まれません。  
  
 詳細については。  
  
-   データのセキュリティ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)です。  
  
-   ベスト プラクティスでデータのセキュリティを確保する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[ベスト プラクティスは、SQL アダプタをセキュリティで保護する](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)です。  
  
## <a name="is-there-a-gui-provided-by-the-sql-adapter-to-view-and-perform-operations-on-the-artifacts-in-my-underlying-sql-server-database"></a>SQL アダプターによって提供される GUI を表示し、基になる SQL Server データベースのアイテムに対して操作を実行ではありますか。  
 アダプター サービスの使用する BizTalk プロジェクト アドインと、アダプター サービス参照を Visual Studio プラグインの追加は、確認し、基になる SQL Server データベースのアイテムに対して操作を実行する場所 ダイアログ ボックスを提供します。 SQL アダプターによって提供される GUI の詳細については、次を参照してください。[参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)です。  
  
## <a name="what-are-binding-properties-in-the-sql-adapter-where-can-i-find-information-about-all-the-binding-properties-in-sql-adapter"></a>新機能は、バインドのプロパティ、SQL アダプターのですか。 SQL アダプターのすべてのバインドのプロパティに関する情報を検索する場所は?  
 アダプターのクライアントが使用できるは、バインディングのプロパティに、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を構成し、アダプターの動作を制御します。 すべてのバインドのプロパティに関する情報が表示されるため、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
## <a name="what-is-msdtc-do-i-need-to-bother-about-it-before-using-sql-adapter"></a>MSDTC は何ですか。 SQL アダプタを使用する前に、について悩む必要がありますか。  
 MSDTC は、Microsoft 分散トランザクション コーディネーターを表しています。 MSDTC では、データベース、ファイル システム、およびメッセージ キューなどの複数のリソース マネージャーの間でさまざまなトランザクションを調整します。 使用する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC を有効にする必要があります。 MSDTC を構成する方法の詳細については、次を参照してください。 [SQL サーバーとアダプターのクライアントで MSDTC を構成する](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)です。  
  
## <a name="where-can-i-find-information-about-the-sql-server-data-types-that-are-supported-in-the-sql-adapter"></a>SQL アダプタでサポートされている SQL Server データ型に関する情報はどこにしますか。  
 調べるには、SQL アダプターでサポートされている SQL Server データ型は、次を参照してください。[基本的な SQL Server データ型](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)です。  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-sql-adapter"></a>SQL アダプターを使用してさまざまな操作を実行する (BizTalk Server で WCF サービス モデルまたは WCF チャネル モデル) は、どの方法を使用できますか。  
 SQL アダプターを使用してさまざまな操作の実行に使用できる方法は次のトピックを参照してください[SQL アプリケーションの開発](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)です。  
  
 
## <a name="see-also"></a>参照  
 [よく寄せられる質問](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
 
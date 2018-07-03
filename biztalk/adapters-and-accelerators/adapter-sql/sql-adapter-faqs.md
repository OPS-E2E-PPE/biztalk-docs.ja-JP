---
title: SQL アダプターに関する Faq |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25369e6b-d1f2-4abc-9ffc-4cb9aef1d3fb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83d94b47a7475e53d15e4f7866dea36bf1fcf08b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978483"
---
# <a name="sql-adapter-faqs"></a>SQL アダプターに関する Faq
次はいくつかよく寄せられる質問 (Faq) に関連する[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]一般にします。  
  
## <a name="how-can-i-use-the-sql-adapter-to-communicate-with-the-sql-server-database"></a>SQL Server データベースと通信するために、SQL アダプターを使用する方法は?  
 SQL アダプタを使用すると、BizTalk アプリケーションを開発、WCF サービス モデルを使用して、または WCF チャネル モデルを使用していずれかの SQL Server データベースと通信します。 詳細については、次を参照してください。 [SQL Server 用 BizTalk アダプターの概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)します。  
  
## <a name="what-interfaces-are-supported-by-the-sql-adapter-for-retrieving-metadata"></a>SQL アダプターでは、メタデータの取得をどのようなインターフェイスがサポートしますか。  
 SQL アダプターには、メタデータを取得するための 2 つのインターフェイスがサポートされています。  
  
-   WCF に用意された MetadataExchange します。 WCF は、クライアントが SQL Server データベースからメタデータを取得できるようにするにすべての WCF バインドのメタデータ交換エンドポイントに提供します。  
  
-   IMetadataRetrievalContract、WCF LOB Adapter SDK、参照および検索機能を備えたアダプターのメタデータをサポートするによって提供されます。  
  
## <a name="how-does-the-sql-adapter-support-high-availability-of-data"></a>SQL アダプターが、データの高可用性をサポートする方法  
 指定するときに、 [SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)SQL Server データベースに接続する場合、SQL アダプターを使用すると、場合に、プライマリ SQL Server データベースの接続にフェールオーバー SQL Server データベースの名前を指定ご利用いただけます。 パラメーターを使用して、省略可能な FailoverPartner 接続 URI で、フェールオーバー SQL Server データベースが指定されました。  
  
## <a name="can-i-migrate-biztalk-projects-created-using-the-previous-version-of-the-sql-adapter-to-use-the-wcf-based-sql-adapter-how"></a>WCF ベースの SQL アダプタを使用して、SQL アダプターの以前のバージョンを使用して作成される BizTalk プロジェクトを移行できますか。 どう。  
 可能。 WCF ベースの SQL アダプタを使用して、SQL アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトの移行の手順を知るには、次を参照してください。 [SQL アダプタ チュートリアル](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)します。  
  
## <a name="does-the-sql-adapter-provide-a-secure-way-of-communicating-with-the-sql-server-database--are-there-any-best-practices-to-ensure-security-of-data"></a>SQL アダプターは、SQL Server データベースとの通信のセキュリティで保護された方法を提供しますか。  データのセキュリティを確保するときのベスト プラクティスはありますか。  
 SQL アダプターは、SQL Server データベースと、確立された接続での認証に、エンタープライズ シングル サインオン (SSO) と統合セキュリティをサポートしています。 Sso、資格情報が暗号化され、レジストリに格納されています。 システムでは、これらの資格情報を使って、不正なアクターによって表示される可能性を入力するように求めるのではなくアクセスを決定します。 統合セキュリティは、SQL server へのアクセスにログオンしたユーザーの資格情報を使用します。 これもユーザー資格情報を入力する必要はありません。 データベース管理者は、正常に動作する統合セキュリティのユーザーの資格情報を受け入れるように SQL を構成する必要があります。  
  
 SQL アダプターもないすることは、Add Adapter Service Reference Visual Studio プラグインとアドインのアダプター サービスの BizTalk プロジェクトの使用を防ぐための操作中に、SQL Server データベースの接続 URI のユーザーの資格情報を入力します。クリア テキストで表示されないように資格情報。 さらに、パスワードは、(、Add Adapter Service Reference Visual Studio プラグインによって生成された) 構成ファイルを (消費アダプター サービスの BizTalk プロジェクト アドインによって生成される)、バインド ファイルは書き込まれません。  
  
 詳細については。  
  
- データのセキュリティ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)します。  
  
- ベスト プラクティスでデータのセキュリティを確保する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[ベスト プラクティスは、SQL アダプターをセキュリティで保護する](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)します。  
  
## <a name="is-there-a-gui-provided-by-the-sql-adapter-to-view-and-perform-operations-on-the-artifacts-in-my-underlying-sql-server-database"></a>表示し、基になる SQL Server データベースのアイテムに対して操作を実行するための SQL アダプターによって提供される GUI がありますか。  
 アダプター サービスの使用 BizTalk プロジェクト アドインと、アダプター サービス参照を Visual Studio プラグインの追加、確認し、基になる SQL Server データベースで、アーティファクトに対する操作を実行する場所のダイアログ ボックスを提供します。 SQL アダプターによって提供される GUI の詳細については、次を参照してください。[参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)します。  
  
## <a name="what-are-binding-properties-in-the-sql-adapter-where-can-i-find-information-about-all-the-binding-properties-in-sql-adapter"></a>SQL アダプタのプロパティをバインド何でしょうか。 SQL アダプタのすべてのバインドのプロパティに関する情報はどこで入手できますか。  
 アダプター クライアントのバインドのプロパティを使用できます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を構成して、アダプターの動作を制御します。 すべてのバインドのプロパティに関する情報が表示されるため、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
## <a name="what-is-msdtc-do-i-need-to-bother-about-it-before-using-sql-adapter"></a>MSDTC とは何ですか。 SQL アダプタを使用する前に、それについて悩む必要がありますか。  
 MSDTC は、Microsoft 分散トランザクション コーディネーターの略です。 MSDTC では、データベース、ファイル システム、およびメッセージ キューなどの複数のリソース マネージャーの間でさまざまなトランザクションを調整します。 使用する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC を有効にする必要があります。 MSDTC を構成する方法の詳細については、次を参照してください。 [SQL サーバーとアダプターのクライアントで MSDTC を構成する](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)します。  
  
## <a name="where-can-i-find-information-about-the-sql-server-data-types-that-are-supported-in-the-sql-adapter"></a>SQL アダプターでサポートされている SQL Server データ型に関する情報はどこで入手できますか。  
 SQL アダプターでサポートされている SQL Server データ型について知るには、次を参照してください。[基本的な SQL Server データ型](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)します。  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-sql-adapter"></a>SQL アダプターを使用してさまざまな操作を実行する方法 (BizTalk Server、WCF サービス モデルまたは WCF チャネル モデル) を使えますか。  
 SQL アダプターを使用してさまざまな操作を実行するのに使用できる方法について知るには、次を参照してください。 [SQL アプリケーションの開発](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)します。  
  
 
## <a name="see-also"></a>参照  
 [よく寄せられる質問](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
 
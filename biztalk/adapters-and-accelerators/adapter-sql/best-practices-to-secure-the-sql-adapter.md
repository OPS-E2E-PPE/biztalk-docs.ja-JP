---
title: ベスト プラクティスは、SQL アダプタをセキュリティで保護する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e32379d7-800a-49b7-a09a-6b3f04a6e5ef
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd3f60d95c7e642dc456b6e860b3cde32ab9f59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225554"
---
# <a name="best-practices-to-secure-the-sql-adapter"></a>SQL アダプタをセキュリティで保護するベスト プラクティス
使用または使用するアプリケーションを開発するときに機密データの保護の詳細を完全に従う必要のあるベスト プラクティス、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]です。  
  
## <a name="security-best-practices-for-the-connection-between-the-sql-adapter-and-the-sql-server-database"></a>SQL アダプタと SQL Server データベース間の接続のセキュリティ ベスト プラクティス  
  
-   [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支援と SQL Server データベースの間の通信を保護するためのサポートはありません。 十分なレベルで、アダプタと SQL Server データベース間で交換されるデータのセキュリティを確保するためのメカニズムを提供する必要があります。  
  
-   セキュリティ上の理由、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI の SQL Server データベースのユーザー名パスワードの資格情報を提供することはできません。 資格情報を提示するための別の方法は、このトピックの残りの部分を参照してください、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メタデータを生成し、使用するか、操作を実行する SQL Server への接続中に Windows 認証を使用することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 Windows 認証を使用する前に、SQL Server Management Studio でのユーザーとして Windows ユーザーを追加する必要があります。 詳細については、次を参照してください。 [SQL アダプターと Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
 詳細については、次を参照してください。 [SQL サーバーとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)です。
  
## <a name="security-best-practices-for-consuming-the-sql-adapter-with-biztalk-server"></a>BizTalk Server と SQL アダプタを使用するためのセキュリティのベスト プラクティス  
  
-   [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI の SQL Server データベースのユーザー名パスワードの資格情報を提供することはできません。  
  
-   使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から、SQL Server データベースのユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   BizTalk Wcf-custom アダプターを構成するとき、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]送信ポートから、SQL Server データベースのユーザー名パスワード資格情報を入力してください、**資格情報**のタブ、 **WCF カスタム トランスポート。プロパティ** ダイアログ ボックス。  
  
-   BizTalk Wcf-custom アダプターを構成するとき、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、受信場所に、SQL Server データベースのユーザー名パスワード資格情報を入力してください、**他の**のタブ、 **WCF カスタム トランスポート。プロパティ** ダイアログ ボックス。  
  
-   使用しているときに[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータを生成するを構成する送信ポート、受信ポートの構成、または Windows 認証を使用することもできます。 Windows 認証を使用する前に、SQL Server Management Studio でのユーザーとして Windows ユーザーを追加する必要があります。 詳細については、次を参照してください。 [SQL アダプターと Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
 詳細については、次を参照してください。 [SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。
  
## <a name="security-best-practices-for-consuming-the-sql-adapter-with-programming-solutions"></a>プログラミング ソリューションと SQL アダプタを使用するためのセキュリティのベスト プラクティス  
  
-   SQL Server データベースの接続 URI です。 ユーザー名パスワードの資格情報を提供する必要があります。ただし、可能であれば、しないでこのです。  
  
-   使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]から、SQL Server データベースのユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   WCF チャネル モデルのプログラミングで使用して、**資格情報**を SQL Server データベースのユーザー名パスワード資格情報を設定するチャネル ファクトリのプロパティです。  
  
-   WCF サービス モデルのプログラミングで使用して、 **ClientCredentials**を SQL Server データベースのユーザー名パスワード資格情報を設定する WCF クライアントのプロパティです。  
  
-   使用するアプリケーションの場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密データベースの情報を含む送信メッセージは、これらのメッセージに適用十分なデータを提供するための十分なセキュリティ対策があることを確認してください。環境内での保護。  
  
-   使用しているときに[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または .NET アプリケーションから SQL Server に接続することができますも Windows 認証を使用します。 Windows 認証を使用する前に、SQL Server Management Studio でのユーザーとして Windows ユーザーを追加する必要があります。 詳細については、次を参照してください。 [SQL アダプターと Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
 詳細については、次を参照してください。 [SQL アダプタをセキュリティで保護された使用したプログラミング](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)です。 
  
## <a name="security-best-practices-for-hosting-the-sql-adapter-in-iis"></a>IIS での SQL アダプターをホストするためのセキュリティのベスト プラクティス  
 ホストしている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で Microsoft インターネット インフォメーション サービス (IIS) web サービスは公開操作によって表示される、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Web クライアントにします。 これらの操作は、このデータが可能な限り安全であることを確認のための対策を行う必要がありますので、インターネット経由で機密データを交換する必要があります。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]HTTP トランスポートの 2 つの標準バインディングは、: **BasicHttpBinding**なしのセキュリティ機構の基本的な HTTP トランスポートを提供、 **WSHttpBinding**トランスポート レベルの双方をサポートしているとメッセージ レベルのセキュリティ メカニズム。  
  
 使用するか、 **BasicHttpBinding** over HTTPS 接続またはを使用して、 **WSHttpBinding**データを保護するためにします。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれています、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]を WCF サービスの LOB アーティファクトを生成します。 このウィザードでは、使用のみがサポート**BasicHttpBinding**です。  
  
 お客様の環境を提供する追加のセキュリティ メカニズムを活用するカスタム HTTP バインディングを作成することもできます。 詳細については、セキュリティ機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[セキュリティで保護するサービスとクライアント](https://msdn.microsoft.com/library/ms734736.aspx)です。 
  
 ホストしているときに、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Web サービスとして、Web 開発者講じる必要がありますから SQL Server データベースに直接渡されるユーザーによって入力された文字列を防ぐためにします。 たとえば、Web サイトでは、ユーザーが SELECT ステートメントの WHERE 句の一部となる値を入力できるように、ステートメントに他のコマンドを追加することを防ぐために、入力文字列をスキャンした必要があります。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF の診断トレースとメッセージ ログのセキュリティ ベスト プラクティス  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースとメッセージ ログをサポートしています。 構成ファイルまたは Windows Management Instrumentation (WMI) を使用して診断トレースとメッセージ ログを構成します。 設定すると、構成オプションに応じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースまたはログ記録が機密情報をログを出力メッセージ ファイルをここで、可能性のある公開することを監視する未承認ユーザーがします。  
  
 これらの機能を有効にすることによって公開される可能性のあるセキュリティ上の脅威を軽減するために、WCF ドキュメントで提供される推奨事項に従ってください。 少なくともには、診断トレースとメッセージ ログの次のベスト プラクティスに従う必要があります。  
  
-   "Verbose"または実稼働環境での「情報」のトレースを有効にしないでください。 これは、パフォーマンスが低下する可能性があります。 ただし、「警告」と"error"のトレース、運用環境で有効にする必要があります。 トレースを有効にした場合は、データを保護する適切なセキュリティ対策を行う必要があります。 詳細については、WCF ドキュメントを参照してください。  
  
-   ログ ファイルと構成ファイルがアクセス制御リスト (Acl) によって保護されていることを確認します。  
  
 クライアント アプリケーション間で交換されるメッセージに具体的には、次の警告を適用し、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
-   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレース ログに記録できますで交換されるメッセージのヘッダー (は本文ではない) で、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 メッセージのアクションは、メッセージ ヘッダーにあるため、これで呼び出された操作によってがわかります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]クライアントによってです。  
  
-   場合[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージのログ記録が有効になっていると`logMessagesAtServiceLevel`は`true`、アダプター クライアント間で交換されるメッセージのメッセージ ヘッダー (ただし、メッセージ本文ではない)、および[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ログに記録されます。 メッセージのアクションは、メッセージ ヘッダーにあるため、これで呼び出されるクライアントの操作によってがわかります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 場合`logEntireMessage`も`true`メッセージの本文をログに記録されます。 機密性の高いデータベース情報を明らかにこのことができます。  
  
 診断トレースを有効にするとセキュリティの向上の詳細については、次を参照してください。[セキュリティに関する注意事項とトレース用の便利なヒント](https://msdn.microsoft.com/library/ms733053.aspx)です。 メッセージのログ記録を有効にするとセキュリティの向上の詳細については、次を参照してください。[メッセージ ログのセキュリティに関する注意事項](https://msdn.microsoft.com/library/ms730318.aspx)です。
  
## <a name="see-also"></a>参照  
[SQL アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)
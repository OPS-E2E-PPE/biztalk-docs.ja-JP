---
title: "ベスト プラクティス、Oracle データベース アダプターをセキュリティで保護する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, best practices for connection between the Oracle Database adapter and the Oracle database
- security, best practices for WCF diagnostic tracing and message logging
- security, best practices for hosting the Oracle Database adapter in IIS
- credentials
- security, best practices
- security
- security, best practices for consuming the Oracle Database adapter with BizTalk Server
- security, protecting sensitive data
- user name password credential
- security, best practices for consuming the Oracle Database adapter with programming solutions
ms.assetid: 689e8442-91c9-4fe0-a0a0-ce5f5a98ab38
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7fcebeb32d4eee9d0e98367d6a852056fe5a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-to-secure-the-oracle-database-adapter"></a>Oracle データベース アダプターをセキュリティで保護するベスト プラクティス
このセクションより的確に機密データの保護を使用してまたはを使用するアプリケーションを開発するときに従う必要のあるベスト プラクティスを説明、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。  
  
## <a name="security-best-practices-for-the-connection-between-the-oracle-database-adapter-and-the-oracle-database"></a>Oracle データベース アダプターと Oracle データベースの間の接続セキュリティのベスト プラクティス  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支援と Oracle データベースとの通信を保護するためのサポートはありません。 十分なレベルで、アダプターと Oracle データベース間で交換されるデータのセキュリティを確保するためのメカニズムを提供する必要があります。  
  
-   URI の接続で Oracle データベースのユーザー名パスワードの資格情報は提供しません。 資格情報を提示するための別の方法を以下のセクションを参照してください、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メタデータを生成し、使用するか、操作を実行する Oracle データベースへの接続中に Windows 認証を使用することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 Windows 認証を使用する前に記載された手順を実行する必要があります[Oracle データベースを使用して Windows 認証に接続する](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)です。  
  
 詳細については、次を参照してください。 [Oracle データベースとアダプター間でセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)です。  
  
## <a name="security-best-practices-for-consuming-the-oracle-database-adapter-with-biztalk-server"></a>BizTalk Server と Oracle データベース アダプターを使用するためのセキュリティのベスト プラクティス  
  
-   URI の接続で Oracle データベースのユーザー名パスワードの資格情報は提供しません。  
  
-   使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から Oracle データベースのユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   BizTalk Wcf-custom アダプターを構成するとき、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]送信ポートから Oracle データベースのユーザー名パスワード資格情報を入力してください、**資格情報**のタブ、 **WCF カスタム トランスポートの構成。**  ダイアログ ボックス。  
  
-   BizTalk Wcf-custom アダプターを構成するとき、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 、受信場所に、Oracle データベースからのユーザー名パスワード資格情報を入力してください、**他の**のタブ、 **WCF カスタム トランスポートの構成。**  ダイアログ ボックス。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メタデータを生成してから操作を実行する Oracle データベースへの接続中に Windows 認証を使用することもできます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 Windows 認証を使用する前に記載された手順を実行する必要があります[Oracle データベースを使用して Windows 認証に接続する](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)です。  
  
 詳細については、次を参照してください。 [Oracle データベース アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)です。
  
## <a name="security-best-practices-for-consuming-the-oracle-database-adapter-with-programming-solutions"></a>プログラミング ソリューションと Oracle データベース アダプターを使用するためのセキュリティのベスト プラクティス  
  
-   Oracle データベースの接続 URI です。 ユーザー名パスワードの資格情報を提供する必要があります。ただし、可能であれば、しないでこのです。  
  
-   使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]から Oracle データベースのユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   WCF チャネル モデルのプログラミングを使用して、**資格情報**Oracle データベースのユーザー名パスワード資格情報を設定するチャネル ファクトリのプロパティです。  
  
-   WCF サービス モデルのプログラミングを使用して、 **ClientCredentials** Oracle データベースのユーザー名パスワード資格情報を設定する WCF クライアントのプロパティです。  
  
-   使用するアプリケーションの場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密データベースの情報を含む送信メッセージは、これらのメッセージに適用十分なデータを提供するための十分なセキュリティ対策があることを確認してください。環境内での保護。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メタデータを生成してから操作を実行する Oracle データベースへの接続中に Windows 認証を使用することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 Windows 認証を使用する前に記載された手順を実行する必要があります[Oracle データベースを使用して Windows 認証に接続する](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)です。  
  
 詳細については、「 [Oracle データベース アダプターを使用したプログラミング セキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md)です。  
  
## <a name="security-best-practices-for-hosting-the-oracle-database-adapter-in-iis"></a>IIS での Oracle データベース アダプターをホストするためのセキュリティのベスト プラクティス  
 ホストしている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で Microsoft インターネット インフォメーション サービス (IIS) web サービスは公開操作によって表示される、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Web クライアントにします。 これらの操作は、このデータが可能な限り安全であることを確認のための対策を行う必要がありますので、インターネット経由で機密データを交換する必要があります。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]HTTP トランスポートの 2 つの標準バインディングは、: **BasicHttpBinding**なしのセキュリティ機構の基本的な HTTP トランスポートを提供、 **WSHttpBinding**トランスポート レベルの双方をサポートしているとメッセージ レベルのセキュリティ メカニズム。  
  
 使用するか、 **BasicHttpBinding** over HTTPS 接続またはを使用して、 **WSHttpBinding**データを保護するためにします。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれています、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]を WCF サービスの LOB アーティファクトを生成します。 このウィザードでは、使用のみがサポート**BasicHttpBinding**です。  
  
 お客様の環境を提供する追加のセキュリティ メカニズムを活用するカスタム HTTP バインディングを作成することもできます。 詳細については、セキュリティ機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[セキュリティで保護するサービスとクライアント](https://msdn.microsoft.com/library/ms734736.aspx)です。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF の診断トレースとメッセージ ログのセキュリティ ベスト プラクティス  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースとメッセージ ログをサポートしています。 構成ファイルまたは Windows Management Instrumentation (WMI) を使用して診断トレースとメッセージ ログを構成します。 設定すると、構成オプションに応じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースまたはログ記録が機密情報をログを出力メッセージ ファイルをここで、可能性のある公開することを監視する未承認ユーザーがします。  
  
 これらの機能を有効にすることによって公開される可能性のあるセキュリティ上の脅威を軽減するために、WCF ドキュメントで提供される推奨事項に従ってください。 少なくともには、診断トレースとメッセージ ログの次のベスト プラクティスに従う必要があります。  
  
-   "Verbose"または実稼働環境での「情報」のトレースを有効にしないでください。 これは、パフォーマンスが低下する可能性があります。 ただし、「警告」と"error"のトレース、運用環境で有効にする必要があります。 トレースを有効にした場合は、データを保護する適切なセキュリティ対策を行う必要があります。 詳細については、WCF ドキュメントを参照してください。  
  
-   ログ ファイルと構成ファイルがアクセス制御リスト (Acl) によって保護されていることを確認します。  
  
 クライアント アプリケーション間で交換されるメッセージに具体的には、次の警告を適用し、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレース ログに記録できますで交換されるメッセージのヘッダー (は本文ではない) で、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 メッセージのアクションは、メッセージ ヘッダーにあるため、これで呼び出された操作によってがわかります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]クライアントによってです。  
  
-   場合[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージのログ記録が有効になっていると`logMessagesAtServiceLevel`は`true`、アダプター クライアント間で交換されるメッセージのメッセージ ヘッダー (ただし、メッセージ本文ではない)、および[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ログに記録されます。 メッセージのアクションは、メッセージ ヘッダーにあるため、これで呼び出されるクライアントの操作によってがわかります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 場合`logEntireMessage`も`true`メッセージの本文をログに記録されます。 機密性の高いデータベース情報を明らかにこのことができます。  
  
 診断トレースを有効にするとセキュリティの向上の詳細については、次を参照してください。[セキュリティに関する注意事項とトレース用の便利なヒント](https://msdn.microsoft.com/library/ms733053.aspx)です。 メッセージのログ記録を有効にするとセキュリティの向上の詳細については、次を参照してください。[メッセージ ログのセキュリティに関する注意事項](https://msdn.microsoft.com/library/ms730318.aspx)です。 
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)
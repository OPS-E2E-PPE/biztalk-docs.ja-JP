---
title: ベスト プラクティスは、SQL アダプターをセキュリティで保護する |Microsoft Docs
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
ms.openlocfilehash: 1a5bb38e1ffd8c40e56b6e581273b8507159268b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007779"
---
# <a name="best-practices-to-secure-the-sql-adapter"></a>SQL アダプタをセキュリティで保護するベスト プラクティス
使用して、または使用するアプリケーションを開発するときに機密データの保護をより完全に従う必要のあるベスト プラクティス、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]します。  
  
## <a name="security-best-practices-for-the-connection-between-the-sql-adapter-and-the-sql-server-database"></a>SQL アダプタと SQL Server データベース間の接続のセキュリティのベスト プラクティス  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はサポートしていませんし、SQL Server データベース間でセキュリティで保護された通信を支援します。 十分なレベルで、アダプタと SQL Server データベース間で交換されるデータのセキュリティを確保するためのメカニズムを提供する必要があります。  
  
- セキュリティ上の理由から、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI の SQL Server データベースのユーザー名パスワード資格情報を提供することはできません。 別の資格情報を提供する方法は、このトピックの残りの部分を参照してください、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server に接続中に Windows 認証を使用してメタデータを生成し、使用するか、操作を実行することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 Windows 認証を使用する前に、SQL Server Management Studio でのユーザーとして Windows ユーザーを追加する必要があります。 詳細については、次を参照してください。 [SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  
  
  詳細については、次を参照してください。 [SQL Server とアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)します。
  
## <a name="security-best-practices-for-consuming-the-sql-adapter-with-biztalk-server"></a>BizTalk Server と SQL アダプタを使用するためのセキュリティのベスト プラクティス  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI の SQL Server データベースのユーザー名パスワード資格情報を提供することはできません。  
  
- 使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から、SQL Server データベースのユーザー名のパスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
- BizTalk Wcf-custom アダプターを構成するとき、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]から、SQL Server データベースのユーザー名のパスワード資格情報を入力、送信ポートで、**資格情報**のタブ、 **WCF カスタム トランスポートプロパティ** ダイアログ ボックス。  
  
- BizTalk Wcf-custom アダプターを構成するとき、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、受信場所に、SQL Server データベースのユーザー名のパスワード資格情報を入力します、**他**のタブ、 **WCF カスタム トランスポート。プロパティ** ダイアログ ボックス。  
  
- 使用中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータを生成するを構成する送信ポート、受信ポートの構成、または Windows 認証を使用することもできます。 Windows 認証を使用する前に、SQL Server Management Studio でのユーザーとして Windows ユーザーを追加する必要があります。 詳細については、次を参照してください。 [SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  
  
  詳細については、次を参照してください。 [SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。
  
## <a name="security-best-practices-for-consuming-the-sql-adapter-with-programming-solutions"></a>プログラミング ソリューションと SQL アダプタを使用するためのセキュリティのベスト プラクティス  
  
- 接続 URI; で SQL Server データベースのユーザー名パスワードの資格情報を提供する必要があります。ただし、可能であれば、しないでこれを行います。  
  
- 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]から、SQL Server データベースのユーザー名のパスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
- WCF チャネル モデルのプログラミングを使用して、**資格情報**プロパティを SQL Server データベースのユーザー名パスワード資格情報を設定するチャネル ファクトリ。  
  
- WCF サービス モデルのプログラミングを使用して、 **ClientCredentials** SQL Server データベースのユーザー名パスワード資格情報を設定する WCF クライアントのプロパティ。  
  
- 使用するアプリケーションの場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密性の高いデータベースの情報を含む送信メッセージは、これらのメッセージは、適切なデータの提供に適用されるセキュリティ対策のための十分なであることを確認環境内で保護します。  
  
- 使用中に[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].NET アプリケーションから SQL Server に接続を使用することも Windows 認証またはします。 Windows 認証を使用する前に、SQL Server Management Studio でのユーザーとして Windows ユーザーを追加する必要があります。 詳細については、次を参照してください。 [SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  
  
  詳細については、次を参照してください。 [SQL アダプターを使用したプログラミングをセキュリティで保護された](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)します。 
  
## <a name="security-best-practices-for-hosting-the-sql-adapter-in-iis"></a>IIS での SQL アダプタをホストするためのセキュリティのベスト プラクティス  
 ホストしている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で Microsoft インターネット インフォメーション サービス (IIS) web サービス公開操作によって表示される、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Web クライアントにします。 このデータが可能な限り安全であることを確認のための対策を行う必要がありますので、インターネット経由で機密データを交換するには、これらの操作があります。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] HTTP トランスポートの 2 つの標準バインディングを提供します。 **BasicHttpBinding**なしのセキュリティ機構の基本的な HTTP トランスポートを提供します、 **WSHttpBinding**トランス ポート レベルの両方をサポートし、メッセージ レベルのセキュリティ メカニズム。  
  
 使用するか、 **BasicHttpBinding** HTTPS 接続、または使用を介して、 **WSHttpBinding**データを保護するためにします。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれています、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]を WCF サービスの LOB アーティファクトを生成します。 このウィザードは、の使用のみがサポートされます。 **BasicHttpBinding**します。  
  
 お客様の環境を提供する追加のセキュリティ メカニズムを利用するカスタム HTTP バインドを開発することもできます。 詳細については、セキュリティに関する機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx)します。 
  
 ホストする場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Web 開発者、Web サービスとしてから SQL Server データベースに直接渡されるユーザーが入力した文字列を防止する手段を実行する必要があります。 たとえば、Web サイトでは、ユーザーが SELECT ステートメントで WHERE 句の一部となる値を入力できるように、ステートメントにその他のコマンドを追加できないようにするのに、入力文字列をスキャンしたする必要があります。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF の診断トレースとメッセージ ログのセキュリティのベスト プラクティス  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 診断トレースとメッセージ ログをサポートしています。 構成ファイルまたは Windows Management Instrumentation (WMI) を使用して診断トレースとメッセージ ログを構成します。 設定すると、構成オプションに応じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースまたはメッセージ ログがログに機密情報を出力ファイル、場所、可能性のあるにさらされる可能性の観察承認されていないユーザーです。  
  
 これらの機能を有効にすることによって公開される潜在的なセキュリティの脅威を軽減するために、WCF のドキュメントで提供される推奨事項に従ってください。 少なくとも診断トレースとメッセージ ログの次のベスト プラクティスを確認する必要があります。  
  
- 「詳細」または運用環境での「情報」トレースを有効にしないでください。 これは、パフォーマンスが低下する可能性があります。 ただし、「警告」と、運用環境での「エラー」トレースが有効にする必要があります。 トレースを有効にした場合は、データを保護する適切なセキュリティ対策を行う必要があります。 詳細については、WCF ドキュメントを参照してください。  
  
- ログ ファイルと構成ファイルがアクセス制御リスト (Acl) によって保護されていることを確認します。  
  
  クライアント アプリケーション間で交換されるメッセージに具体的には、次の警告を適用し、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 診断トレースと交換されるメッセージのヘッダー (が本文ではない) を記録できます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 メッセージのアクションがメッセージ ヘッダーにあるためで呼び出された操作が表示されます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]クライアント。  
  
- 場合[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージ ログが有効になっていると`logMessagesAtServiceLevel`は`true`、アダプター クライアントの間で交換されるメッセージのメッセージ ヘッダー (ただし、メッセージ本文ではありません)、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ログに記録されます。 メッセージのアクションがメッセージ ヘッダーにあるため、操作で、クライアントが呼び出すことが表示されます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 場合`logEntireMessage`も`true`、メッセージ本文がログに記録されます。 データベースの機密情報を表示このことができます。  
  
  診断トレースを有効にすると、セキュリティを向上させる詳細については、次を参照してください。[セキュリティに関する注意事項とトレース用の役立つヒント](https://msdn.microsoft.com/library/ms733053.aspx)します。 メッセージのログ記録を有効にすると、セキュリティを向上させる詳細については、次を参照してください。[メッセージ ログのセキュリティ関連事項](https://msdn.microsoft.com/library/ms730318.aspx)します。
  
## <a name="see-also"></a>参照  
[SQL アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)
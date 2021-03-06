---
title: ベスト プラクティス、Oracle Database アダプターをセキュリティで保護する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab079e2114eb606ef90e6c40d0857ec8668e1dca
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529622"
---
# <a name="best-practices-to-secure-the-oracle-database-adapter"></a>Oracle データベース アダプターをセキュリティで保護するベスト プラクティス
このセクションより完全に機密データの保護を使用して、使用するアプリケーションを開発したりするときに従うべきベスト プラクティス、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。  
  
## <a name="security-best-practices-for-the-connection-between-the-oracle-database-adapter-and-the-oracle-database"></a>Oracle データベース アダプターと Oracle データベース間の接続のセキュリティのベスト プラクティス  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はサポートしていません、Oracle データベースとの間のセキュリティで保護された通信を支援します。 アダプターと Oracle データベースの間で交換されるデータのセキュリティの適切なレベルを確保するためのメカニズムを提供する必要があります。  
  
- 接続 URI での Oracle データベースのユーザー名パスワード資格情報は提供されません。 資格情報を提供する別の方法について、次のセクションを参照してください、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースへの接続中に Windows 認証を使用してメタデータを生成し、使用するか、操作を実行することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 Windows 認証を使用する前に記載された手順を実行する必要があります[Oracle データベースを使用して Windows 認証に接続する](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)します。  
  
  詳細については、次を参照してください。 [Oracle データベースとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)します。  
  
## <a name="security-best-practices-for-consuming-the-oracle-database-adapter-with-biztalk-server"></a>BizTalk Server と Oracle データベース アダプターを使用するためのセキュリティのベスト プラクティス  
  
- 接続 URI での Oracle データベースのユーザー名パスワード資格情報は提供されません。  
  
- 使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から Oracle データベースのユーザー名のパスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
- BizTalk Wcf-custom アダプターを構成するとき、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]から Oracle データベースのユーザー名のパスワード資格情報を入力、送信ポートで、**資格情報**のタブ、 **WCF カスタム トランスポートの構成**  ダイアログ ボックス。  
  
- BizTalk Wcf-custom アダプターを構成するとき、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 、受信場所に、Oracle データベースからのユーザー名のパスワード資格情報を入力します、**他**のタブ、 **WCF カスタム トランスポートの構成。**  ダイアログ ボックス。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メタデータを生成してから操作を実行する Oracle データベースへの接続中に Windows 認証を使用することもできます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 Windows 認証を使用する前に記載された手順を実行する必要があります[Oracle データベースを使用して Windows 認証に接続する](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)します。  
  
  詳細については、次を参照してください。 [Oracle データベース アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)します。
  
## <a name="security-best-practices-for-consuming-the-oracle-database-adapter-with-programming-solutions"></a>プログラミング ソリューションと Oracle データベース アダプターを使用するためのセキュリティのベスト プラクティス  
  
- 接続 URI; での Oracle データベースのユーザー名パスワードの資格情報を提供する必要があります。ただし、可能であれば、しないでこれを行います。  
  
- 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]から Oracle データベースのユーザー名のパスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
- WCF チャネル モデルのプログラミングを使用して、**資格情報**Oracle データベースのユーザー名パスワード資格情報を設定するチャネル ファクトリのプロパティ。  
  
- WCF サービス モデルのプログラミングを使用して、 **ClientCredentials** Oracle データベースのユーザー名パスワード資格情報を設定する WCF クライアントのプロパティ。  
  
- 使用するアプリケーションの場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密性の高いデータベースの情報を含む送信メッセージは、これらのメッセージは、適切なデータの提供に適用されるセキュリティ対策のための十分なであることを確認環境内で保護します。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メタデータを生成してから操作を実行する Oracle データベースへの接続中に Windows 認証を使用することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 Windows 認証を使用する前に記載された手順を実行する必要があります[Oracle データベースを使用して Windows 認証に接続する](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)します。  
  
  詳細については、「 [Oracle データベース アダプターを使用したプログラミングにセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md)します。  
  
## <a name="security-best-practices-for-hosting-the-oracle-database-adapter-in-iis"></a>IIS での Oracle データベース アダプターのホストのセキュリティのベスト プラクティス  
 ホストしている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で Microsoft インターネット インフォメーション サービス (IIS) web サービス公開操作によって表示される、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Web クライアントにします。 このデータが可能な限り安全であることを確認のための対策を行う必要がありますので、インターネット経由で機密データを交換するには、これらの操作があります。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] HTTP トランスポートの 2 つの標準バインディングを提供します。 **BasicHttpBinding**なしのセキュリティ機構の基本的な HTTP トランスポートを提供します、 **WSHttpBinding**トランス ポート レベルの両方をサポートし、メッセージ レベルのセキュリティ メカニズム。  
  
 使用するか、 **BasicHttpBinding** HTTPS 接続、または使用を介して、 **WSHttpBinding**データを保護するためにします。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれています、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]を WCF サービスの LOB アーティファクトを生成します。 このウィザードは、の使用のみがサポートされます。 **BasicHttpBinding**します。  
  
 お客様の環境を提供する追加のセキュリティ メカニズムを利用するカスタム HTTP バインドを開発することもできます。 詳細については、セキュリティに関する機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx)します。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF の診断トレースとメッセージ ログのセキュリティのベスト プラクティス  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 診断トレースとメッセージ ログをサポートしています。 構成ファイルまたは Windows Management Instrumentation (WMI) を使用して診断トレースとメッセージ ログを構成します。 設定すると、構成オプションに応じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースまたはメッセージ ログがログに機密情報を出力ファイル、場所、可能性のあるにさらされる可能性の観察承認されていないユーザーです。  
  
 これらの機能を有効にすることによって公開される潜在的なセキュリティの脅威を軽減するために、WCF のドキュメントで提供される推奨事項に従ってください。 少なくとも診断トレースとメッセージ ログの次のベスト プラクティスを確認する必要があります。  
  
- 「詳細」または運用環境での「情報」トレースを有効にしないでください。 これは、パフォーマンスが低下する可能性があります。 ただし、「警告」と、運用環境での「エラー」トレースが有効にする必要があります。 トレースを有効にした場合は、データを保護する適切なセキュリティ対策を行う必要があります。 詳細については、WCF ドキュメントを参照してください。  
  
- ログ ファイルと構成ファイルがアクセス制御リスト (Acl) によって保護されていることを確認します。  
  
  クライアント アプリケーション間で交換されるメッセージに具体的には、次の警告を適用し、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 診断トレースと交換されるメッセージのヘッダー (が本文ではない) を記録できます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 メッセージのアクションがメッセージ ヘッダーにあるためで呼び出された操作が表示されます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]クライアント。  
  
- 場合[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージ ログが有効になっていると`logMessagesAtServiceLevel`は`true`、アダプター クライアントの間で交換されるメッセージのメッセージ ヘッダー (ただし、メッセージ本文ではありません)、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ログに記録されます。 メッセージのアクションがメッセージ ヘッダーにあるため、操作で、クライアントが呼び出すことが表示されます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 場合`logEntireMessage`も`true`、メッセージ本文がログに記録されます。 データベースの機密情報を表示このことができます。  
  
  診断トレースを有効にすると、セキュリティを向上させる詳細については、次を参照してください。[セキュリティに関する注意事項とトレース用の役立つヒント](https://msdn.microsoft.com/library/ms733053.aspx)します。 メッセージのログ記録を有効にすると、セキュリティを向上させる詳細については、次を参照してください。[メッセージ ログのセキュリティ関連事項](https://msdn.microsoft.com/library/ms730318.aspx)します。 
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)
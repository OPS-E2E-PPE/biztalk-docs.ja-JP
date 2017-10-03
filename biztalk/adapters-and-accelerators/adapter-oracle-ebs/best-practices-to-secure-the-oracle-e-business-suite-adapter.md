---
title: "ベスト プラクティス、Oracle E-business Suite アダプターをセキュリティで保護する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d492d22-2a1f-4b91-9000-a4d74c6fb2fb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd530d653f1fb5403d1632d94ed688ad7ca8a3b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-to-secure-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターをセキュリティで保護するベスト プラクティス
このセクションより的確に機密データの保護を使用してまたはを使用するアプリケーションを開発するときに従う必要のあるベスト プラクティスを説明、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。  
  
## <a name="security-best-practices-for-the-connection-between-the-oracle-e-business-adapter-and-the-oracle-database"></a>Oracle E-business アダプターと Oracle データベースの間の接続セキュリティのベスト プラクティス  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支援 Oracle E-business Suite との間の通信を保護するためのサポートはありません。 十分なレベルで、アダプターと Oracle データベース間で交換されるデータのセキュリティを確保するためのメカニズムを提供する必要があります。  
  
-   URI の接続で Oracle データベースのユーザー名パスワードの資格情報は提供しません。 資格情報を提示するための別の方法を以下のセクションを参照してください、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メタデータを生成し、使用するか、操作を実行する Oracle E-business Suite に接続中に Windows 認証を使用することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 Windows 認証を使用する前に記載された手順を実行する必要があります[Windows 認証を使用して Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)です。  
  
 詳細については、次を参照してください。 [Oracle E-business Suite とアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-oracle-ebs/security-between-oracle-e-business-suite-and-the-adapter.md)です。  
  
## <a name="security-best-practices-for-consuming-the-oracle-e-business-adapter-with-biztalk-server"></a>BizTalk Server と Oracle E-business アダプターを使用するためのセキュリティのベスト プラクティス  
  
-   For Oracle E-business Suite 接続 URI 内のユーザー名パスワードの資格情報を提供することは避けてください。  
  
-   使用すると、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、for Oracle E-business Suite からユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   BizTalk Wcf-custom アダプターを構成するとき、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]送信ポートから Oracle データベースのユーザー名パスワード資格情報を入力してください、**資格情報**のタブ、 **WCF カスタム トランスポートの構成。**  ダイアログ ボックス。  
  
-   BizTalk Wcf-custom アダプターを構成するとき、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、受信場所に、Oracle データベースからのユーザー名パスワード資格情報を入力してください、**他の**のタブ、 **WCF カスタム トランスポートの構成。**  ダイアログ ボックス。  
  
-   アプリケーションからバインド ファイルをエクスポートした後に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の値を手動で削除する必要があります、 **OraclePassword**バインド ファイルから (クリア テキストで使用可能) のプロパティのバインドと、各ホストでもう一度指定ここでは、エクスポートされたバインドが使用されます。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メタデータを生成し、使用するか、操作を実行する Oracle E-business Suite に接続中に Windows 認証を使用することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 Windows 認証を使用する前に記載された手順を実行する必要があります[Windows 認証を使用して Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)です。  
  
-   使用するアプリケーションの場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密データベースの情報を含む送信メッセージは、これらのメッセージに適用十分なデータを提供するための十分なセキュリティ対策があることを確認してください。環境内での保護。  
  
 詳細については、次を参照してください。 [Oracle E-business Suite アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)です。  
  
## <a name="security-best-practices-for-consuming-the-oracle-e-business-adapter-with-programming-solutions"></a>プログラミング ソリューションと Oracle E-business アダプターを使用するためのセキュリティのベスト プラクティス  
  
-   URI の接続で Oracle データベースのユーザー名パスワードの資格情報を提供することは避けてください。  
  
-   使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]から Oracle データベースのユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   WCF チャネル モデルのプログラミングで使用して、**資格情報**Oracle データベースのユーザー名パスワード資格情報を設定するチャネル ファクトリのプロパティです。  
  
-   WCF サービス モデルのプログラミングで使用して、 **ClientCredentials** Oracle データベースのユーザー名パスワード資格情報を設定する WCF クライアントのプロパティです。  
  
-   使用するアプリケーションの場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密データベースの情報を含む送信メッセージは、これらのメッセージに適用十分なデータを提供するための十分なセキュリティ対策があることを確認してください。環境内での保護。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メタデータを生成し、使用するか、操作を実行する Oracle E-business Suite に接続中に Windows 認証を使用することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 Windows 認証を使用する前に記載された手順を実行する必要があります[Windows 認証を使用して Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)です。  
  
 詳細については、「[アダプターのセキュリティに関する考慮事項](../../core/security-considerations-for-adapters.md)です。  
  
## <a name="security-best-practices-for-hosting-the-oracle-e-business-adapter-in-iis"></a>IIS での Oracle E-business アダプターをホストするためのセキュリティのベスト プラクティス  
 ホストしている、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で Microsoft インターネット インフォメーション サービス (IIS) web サービスは公開操作によって表示される、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Web クライアントにします。 これらの操作は、このデータが可能な限り安全であることを確認のための対策を行う必要がありますので、インターネット経由で機密データを交換する必要があります。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]HTTP トランスポートの 2 つの標準バインディングは、: **BasicHttpBinding**なしのセキュリティ機構の基本的な HTTP トランスポートを提供、 **WSHttpBinding**トランスポート レベルの双方をサポートしているとメッセージ レベルのセキュリティ メカニズム。  
  
 使用するか、 **BasicHttpBinding** over HTTPS 接続またはを使用して、 **WSHttpBinding**データを保護するためにします。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれています、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]を WCF サービスの LOB アーティファクトを生成します。 このウィザードでは、使用のみがサポート**BasicHttpBinding**です。  
  
 お客様の環境を提供する追加のセキュリティ メカニズムを活用するカスタム HTTP バインディングを作成することもできます。 詳細については、セキュリティの機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を提供するで「サービスとクライアントのセキュリティで保護する」を参照してください[http://go.microsoft.com/fwlink/?LinkId=89725](http://go.microsoft.com/fwlink/?LinkId=89725)です。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF の診断トレースとメッセージ ログのセキュリティ ベスト プラクティス  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースとメッセージ ログをサポートしています。 構成ファイルまたは Windows Management Instrumentation (WMI) を使用して診断トレースとメッセージ ログを構成します。 設定すると、構成オプションに応じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースまたはログ記録が機密情報をログを出力メッセージ ファイルをここで、可能性のある公開することを監視する未承認ユーザーがします。  
  
 これらの機能を有効にすることによって公開される可能性のあるセキュリティ上の脅威を軽減するために、WCF ドキュメントで提供される推奨事項に従ってください。 少なくともには、診断トレースとメッセージ ログの次のベスト プラクティスに従う必要があります。  
  
-   "Verbose"または実稼働環境での「情報」のトレースを有効にしないでください。 これは、パフォーマンスが低下する可能性があります。 ただし、「警告」と"error"のトレース、運用環境で有効にする必要があります。 トレースを有効にした場合は、データを保護する適切なセキュリティ対策を行う必要があります。 詳細については、WCF ドキュメントを参照してください。  
  
-   ログ ファイルと構成ファイルがアクセス制御リスト (Acl) によって保護されていることを確認します。  
  
 クライアント アプリケーション間で交換されるメッセージに具体的には、次の警告を適用し、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
-   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレース ログに記録できますで交換されるメッセージのヘッダー (は本文ではない) で、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 メッセージのアクションは、メッセージ ヘッダーにあるため、これで呼び出された操作によってがわかります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]クライアントによってです。  
  
-   場合[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージのログ記録が有効になっていると`logMessagesAtServiceLevel`は`true`、アダプター クライアント間で交換されるメッセージのメッセージ ヘッダー (ただし、メッセージ本文ではない)、および[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ログに記録されます。 メッセージのアクションは、メッセージ ヘッダーにあるため、これで呼び出されるクライアントの操作によってがわかります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 場合`logEntireMessage`も`true`メッセージの本文をログに記録されます。 機密性の高いデータベース情報を明らかにこのことができます。  
  
 診断トレースを有効にするとセキュリティの向上の詳細についてを参照してください「のセキュリティに関する注意事項と便利ですヒントのトレース」 [http://go.microsoft.com/fwlink/?LinkId=89796](http://go.microsoft.com/fwlink/?LinkId=89796)です。 メッセージのログ記録を有効にするとセキュリティの向上の詳細についてを参照してください「のセキュリティに関する注意事項の Message Logging」 [http://go.microsoft.com/fwlink/?LinkId=89797](http://go.microsoft.com/fwlink/?LinkId=89797)です。  
  
## <a name="see-also"></a>参照  
 [Oracle EBS アプリケーションのセキュリティ保護します。](secure-your-oracle-ebs-applications.md)
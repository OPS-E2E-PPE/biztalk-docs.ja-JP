---
title: ベスト プラクティス、Oracle E-business Suite アダプターをセキュリティで保護する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d492d22-2a1f-4b91-9000-a4d74c6fb2fb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53b584ae00a5c4767bec842fd0878546e7842d85
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529578"
---
# <a name="best-practices-to-secure-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターをセキュリティで保護するベスト プラクティス
このセクションより完全に機密データの保護を使用して、使用するアプリケーションを開発したりするときに従うべきベスト プラクティス、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。  
  
## <a name="security-best-practices-for-the-connection-between-the-oracle-e-business-adapter-and-the-oracle-database"></a>Oracle E-business アダプターと Oracle データベース間の接続のセキュリティのベスト プラクティス  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はサポートしていませんし、Oracle E-business Suite のセキュリティで保護された通信を支援します。 アダプターと Oracle データベースの間で交換されるデータのセキュリティの適切なレベルを確保するためのメカニズムを提供する必要があります。  
  
- 接続 URI での Oracle データベースのユーザー名パスワード資格情報は提供されません。 資格情報を提供する別の方法について、次のセクションを参照してください、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続中に Windows 認証を使用してメタデータを生成し、使用するか、操作を実行することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 Windows 認証を使用する前に記載された手順を実行する必要があります[Windows 認証を使用して Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)します。  
  
  詳細については、次を参照してください。 [Oracle E-business Suite とアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-oracle-ebs/security-between-oracle-e-business-suite-and-the-adapter.md)します。  
  
## <a name="security-best-practices-for-consuming-the-oracle-e-business-adapter-with-biztalk-server"></a>BizTalk Server と Oracle E-business アダプターを使用するためのセキュリティのベスト プラクティス  
  
- For Oracle E-business Suite 接続 URI のユーザー名パスワード資格情報を提供することを避ける必要があります。  
  
- 使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から Oracle E-business Suite のユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
- BizTalk Wcf-custom アダプターを構成するとき、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]から Oracle データベースのユーザー名のパスワード資格情報を入力、送信ポートで、**資格情報**のタブ、 **WCF カスタム トランスポートの構成**  ダイアログ ボックス。  
  
- BizTalk Wcf-custom アダプターを構成するとき、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、受信場所に、Oracle データベースからのユーザー名のパスワード資格情報を入力します、**他**のタブ、 **WCF カスタム トランスポートの構成。**  ダイアログ ボックス。  
  
- 内のアプリケーションからバインド ファイルをエクスポートした後に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の値を手動で削除する必要があります、 **OraclePassword**バインド ファイルから (クリア テキストで使用可能な) プロパティをバインドし、各ホストでもう一度指定エクスポートされるバインドが使用されます。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続中に Windows 認証を使用してメタデータを生成し、使用するか、操作を実行することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 Windows 認証を使用する前に記載された手順を実行する必要があります[Windows 認証を使用して Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)します。  
  
- 使用するアプリケーションの場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密性の高いデータベースの情報を含む送信メッセージは、これらのメッセージは、適切なデータの提供に適用されるセキュリティ対策のための十分なであることを確認環境内で保護します。  
  
  詳細については、次を参照してください。 [Oracle E-business Suite アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)します。  
  
## <a name="security-best-practices-for-consuming-the-oracle-e-business-adapter-with-programming-solutions"></a>プログラミング ソリューションと、Oracle E-business アダプターを使用するためのセキュリティのベスト プラクティス  
  
- 接続 URI での Oracle データベースのユーザー名パスワード資格情報を提供することを避ける必要があります。  
  
- 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]から Oracle データベースのユーザー名のパスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
- WCF チャネル モデルのプログラミングを使用して、**資格情報**Oracle データベースのユーザー名パスワード資格情報を設定するチャネル ファクトリのプロパティ。  
  
- WCF サービス モデルのプログラミングを使用して、 **ClientCredentials** Oracle データベースのユーザー名パスワード資格情報を設定する WCF クライアントのプロパティ。  
  
- 使用するアプリケーションの場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密性の高いデータベースの情報を含む送信メッセージは、これらのメッセージは、適切なデータの提供に適用されるセキュリティ対策のための十分なであることを確認環境内で保護します。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続中に Windows 認証を使用してメタデータを生成し、使用するか、操作を実行することもできます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 Windows 認証を使用する前に記載された手順を実行する必要があります[Windows 認証を使用して Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)します。  
  
  詳細については、「[アダプターのセキュリティに関する考慮事項](../../core/security-considerations-for-adapters.md)します。  
  
## <a name="security-best-practices-for-hosting-the-oracle-e-business-adapter-in-iis"></a>IIS での Oracle E-business アダプターをホストするためのセキュリティのベスト プラクティス  
 ホストしている、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で Microsoft インターネット インフォメーション サービス (IIS) web サービス公開操作によって表示される、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Web クライアントにします。 このデータが可能な限り安全であることを確認のための対策を行う必要がありますので、インターネット経由で機密データを交換するには、これらの操作があります。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] HTTP トランスポートの 2 つの標準バインディングを提供します。 **BasicHttpBinding**なしのセキュリティ機構の基本的な HTTP トランスポートを提供します、 **WSHttpBinding**トランス ポート レベルの両方をサポートし、メッセージ レベルのセキュリティ メカニズム。  
  
 使用するか、 **BasicHttpBinding** HTTPS 接続、または使用を介して、 **WSHttpBinding**データを保護するためにします。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれています、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]を WCF サービスの LOB アーティファクトを生成します。 このウィザードは、の使用のみがサポートされます。 **BasicHttpBinding**します。  
  
 お客様の環境を提供する追加のセキュリティ メカニズムを利用するカスタム HTTP バインドを開発することもできます。 詳細については、セキュリティに関する機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますが、ある「サービスとクライアントのセキュリティで保護する」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=89725 ](http://go.microsoft.com/fwlink/?LinkId=89725)。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF の診断トレースとメッセージ ログのセキュリティのベスト プラクティス  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 診断トレースとメッセージ ログをサポートしています。 構成ファイルまたは Windows Management Instrumentation (WMI) を使用して診断トレースとメッセージ ログを構成します。 設定すると、構成オプションに応じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースまたはメッセージ ログがログに機密情報を出力ファイル、場所、可能性のあるにさらされる可能性の観察承認されていないユーザーです。  
  
 これらの機能を有効にすることによって公開される潜在的なセキュリティの脅威を軽減するために、WCF のドキュメントで提供される推奨事項に従ってください。 少なくとも診断トレースとメッセージ ログの次のベスト プラクティスを確認する必要があります。  
  
- 「詳細」または運用環境での「情報」トレースを有効にしないでください。 これは、パフォーマンスが低下する可能性があります。 ただし、「警告」と、運用環境での「エラー」トレースが有効にする必要があります。 トレースを有効にした場合は、データを保護する適切なセキュリティ対策を行う必要があります。 詳細については、WCF ドキュメントを参照してください。  
  
- ログ ファイルと構成ファイルがアクセス制御リスト (Acl) によって保護されていることを確認します。  
  
  クライアント アプリケーション間で交換されるメッセージに具体的には、次の警告を適用し、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 診断トレースと交換されるメッセージのヘッダー (が本文ではない) を記録できます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 メッセージのアクションがメッセージ ヘッダーにあるためで呼び出された操作が表示されます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]クライアント。  
  
- 場合[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージ ログが有効になっていると`logMessagesAtServiceLevel`は`true`、アダプター クライアントの間で交換されるメッセージのメッセージ ヘッダー (ただし、メッセージ本文ではありません)、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ログに記録されます。 メッセージのアクションがメッセージ ヘッダーにあるため、操作で、クライアントが呼び出すことが表示されます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 場合`logEntireMessage`も`true`、メッセージ本文がログに記録されます。 データベースの機密情報を表示このことができます。  
  
  診断トレースを有効にすると、セキュリティを向上させる詳細についてを参照してください"セキュリティの問題と有用なヒントのトレース" [ http://go.microsoft.com/fwlink/?LinkId=89796](http://go.microsoft.com/fwlink/?LinkId=89796)します。 メッセージのログ記録を有効にすると、セキュリティを向上させる詳細についてを参照してください「セキュリティの問題のメッセージのログ」 [ http://go.microsoft.com/fwlink/?LinkId=89797](http://go.microsoft.com/fwlink/?LinkId=89797)します。  
  
## <a name="see-also"></a>参照  
 [Oracle EBS アプリケーションをセキュリティで保護する](secure-your-oracle-ebs-applications.md)
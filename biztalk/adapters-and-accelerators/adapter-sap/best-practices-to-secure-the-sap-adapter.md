---
title: "ベスト プラクティス、SAP アダプターをセキュリティで保護する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security, best practices
ms.assetid: e60014b5-ce2f-4fd4-be2a-921d5cd81267
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34d6c56af06bb6b8dc0831c354d494bb62ad5bfa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-to-secure-the-sap-adapter"></a>SAP アダプターをセキュリティで保護するベスト プラクティス
このセクションより的確に機密データの保護を使用してまたはを使用するアプリケーションを開発するときに従う必要のあるベスト プラクティスを説明、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。  
  
## <a name="security-best-practices-for-the-connection-between-the-sap-adapter-and-the-sap-system"></a>SAP アダプターと、SAP システム間の接続のセキュリティ ベスト プラクティス  
  
-   適切なアダプターと、SAP システムの間で交換されるデータのセキュリティのレベルを確認する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP セキュリティで保護されたネットワーク通信 (SNC) をサポートしています。 SNC を有効にしたり、アダプターと、SAP システムの間のセキュリティで保護された通信のための代替手段を提供することができます。  
  
-   接続 URI 内の SAP システムのユーザー名パスワードの資格情報を提供しません。 資格情報を提示するための別の方法を以下のセクションを参照してください、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   SAP プログラム ID から SAP アイテム (Rfc、Idoc、および tRFCs) を受信する唯一のリスナーにそのプログラム ID へのアクセスがあることを確認してください。 これは、プログラム ID へのアクセス権を持つリスナーは、そのプログラム ID から成果物を受信できるため  
  
-   複数のリスナーを使用している SAP プログラム ID に同時に、SAP が無作為に選択各発信成果物 (RFC、IDOC、または tRFC) に対するリスナーを注意してください。  
  
 詳細については、次を参照してください。 [SAP システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)です。
  
## <a name="security-best-practices-for-consuming-the-sap-adapter-with-biztalk-server"></a>BizTalk Server と SAP アダプターを使用するためのセキュリティのベスト プラクティス  
  
-   接続 URI 内の SAP システムのユーザー名パスワードの資格情報を提供しません。  
  
-   使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から SAP システムのユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   BizTalk Wcf-custom アダプターを構成するとき、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]送信ポートを SAP システムからのユーザー名パスワード資格情報を入力してください、**資格情報**のタブ、 **にWCFカスタムトランスポートを構成します。。**  ダイアログ ボックス。  
  
-   BizTalk Wcf-custom アダプターを構成するとき、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、受信場所に、SAP システムからのユーザー名パスワード資格情報を入力してください、**他の**のタブ、 **にWCFカスタムトランスポートを構成します。。**  ダイアログ ボックス。  
  
 詳細については、次を参照してください。 [SAP アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)です。
  
## <a name="security-best-practices-for-consuming-the-sap-adapter-with-programming-solutions"></a>プログラミング ソリューションで SAP アダプターを使用するためのセキュリティのベスト プラクティス  
  
-   接続 URI; 内の SAP システムのユーザー名パスワードの資格情報を提供する必要があります。ただし、可能であれば、しないでこのです。  
  
-   使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]から SAP システムのユーザー名パスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   WCF チャネル モデルのプログラミングを使用して、**資格情報**SAP システムのユーザー名パスワード資格情報を設定するチャネル ファクトリのプロパティです。  
  
-   WCF サービス モデルのプログラミングを使用して、 **ClientCredentials** SAP システムのユーザー名パスワード資格情報を設定する WCF クライアントのプロパティです。  
  
-   使用するアプリケーションの場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密データベースの情報を含む送信メッセージは、これらのメッセージに適用十分なデータを提供するための十分なセキュリティ対策があることを確認してください。環境内での保護。  
  
 詳細については、次を参照してください。 [SAP アダプターをセキュリティで保護された使用したプログラミング](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)です。  
  
## <a name="security-best-practices-for-hosting-the-sap-adapter-in-iis"></a>IIS での SAP アダプターをホストするためのセキュリティのベスト プラクティス  
  
-   ホストしている、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で Microsoft インターネット インフォメーション サービス (IIS) web サービスは公開操作によって表示される、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Web クライアントにします。 これらの操作は、このデータが可能な限り安全であることを確認のための対策を行う必要がありますので、インターネット経由で機密データを交換する必要があります。  
  
     [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]HTTP トランスポートの 2 つの標準バインディングは、: **BasicHttpBinding**なしのセキュリティ機構の基本的な HTTP トランスポートを提供、 **WSHttpBinding**トランスポート レベルの双方をサポートしているとメッセージ レベルのセキュリティ メカニズム。  
  
     使用するか、 **BasicHttpBinding** over HTTPS 接続またはを使用して、 **WSHttpBinding**データを保護するためにします。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれています、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]を WCF サービスの LOB アーティファクトを生成します。 このウィザードでは、使用のみがサポート**BasicHttpBinding**です。  
  
     お客様の環境を提供する追加のセキュリティ メカニズムを活用するカスタム HTTP バインディングを作成することもできます。 詳細については、セキュリティ機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[セキュリティで保護するサービスとクライアント](https://msdn.microsoft.com/library/ms734736.aspx)です。 
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF の診断トレースとメッセージ ログのセキュリティ ベスト プラクティス  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースとメッセージ ログをサポートしています。 構成ファイルまたは Windows Management Instrumentation (WMI) を使用して診断トレースとメッセージ ログを構成します。 設定すると、構成オプションに応じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースまたはログ記録が機密情報をログを出力メッセージ ファイルをここで、可能性のある公開することを監視する未承認ユーザーがします。  
  
 これらの機能を有効にすることによって公開される可能性のあるセキュリティ上の脅威を軽減するために、WCF ドキュメントで提供される推奨事項に従ってください。 少なくともには、診断トレースとメッセージ ログの次のベスト プラクティスに従う必要があります。  
  
-   "Verbose"または実稼働環境での「情報」のトレースを有効にしないでください。 これは、パフォーマンスが低下する可能性があります。 ただし、「警告」と"error"のトレース、運用環境で有効にする必要があります。 トレースを有効にした場合は、データを保護する適切なセキュリティ対策を行う必要があります。 詳細については、WCF ドキュメントを参照してください。  
  
-   ログ ファイルと構成ファイルがアクセス制御リスト (Acl) によって保護されていることを確認します。  
  
 クライアント アプリケーション間で交換されるメッセージに具体的には、次の警告を適用し、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレース ログに記録できますで交換されるメッセージのヘッダー (は本文ではない) で、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 メッセージのアクションは、メッセージ ヘッダーにあるため、これで呼び出された操作によってがわかります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]クライアントによってです。  
  
-   場合[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージのログ記録が有効になっていると`logMessagesAtServiceLevel`は`true`、アダプター クライアント間で交換されるメッセージのメッセージ ヘッダー (ただし、メッセージ本文ではない)、および[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ログに記録されます。 メッセージのアクションは、メッセージ ヘッダーにあるため、これで呼び出されるクライアントの操作によってがわかります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 場合`logEntireMessage`も`true`メッセージの本文をログに記録されます。 機密性の高いデータベース情報を明らかにこのことができます。  
  
     診断トレースを有効にするとセキュリティの向上の詳細については、次を参照してください。[セキュリティに関する注意事項とトレース用の便利なヒント](https://msdn.microsoft.com/library/ms733053.aspx)です。 メッセージのログ記録を有効にするとセキュリティの向上の詳細については、次を参照してください。[メッセージ ログのセキュリティに関する注意事項](https://msdn.microsoft.com/library/ms730318.aspx)です。  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   
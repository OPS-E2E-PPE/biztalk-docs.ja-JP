---
title: ベスト プラクティス、SAP アダプターをセキュリティで保護する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, best practices
ms.assetid: e60014b5-ce2f-4fd4-be2a-921d5cd81267
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4223012d5f91d1682f165aff48d615c50c708566
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003187"
---
# <a name="best-practices-to-secure-the-sap-adapter"></a>SAP アダプターをセキュリティで保護するベスト プラクティス
このセクションより完全に機密データの保護を使用して、使用するアプリケーションを開発したりするときに従うべきベスト プラクティス、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。  
  
## <a name="security-best-practices-for-the-connection-between-the-sap-adapter-and-the-sap-system"></a>SAP アダプターと SAP システム間の接続のセキュリティのベスト プラクティス  
  
- アダプターと SAP システムの間で交換されるデータのセキュリティの適切なレベルを確認する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP セキュリティで保護されたネットワーク通信 (SNC) をサポートしています。 SNC を有効にしたり、アダプターと SAP システムの間の通信のセキュリティを代替手段を提供できます。  
  
- 接続 URI での SAP システムのユーザー名パスワード資格情報は提供されません。 資格情報を提供する別の方法について、次のセクションを参照してください、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- SAP プログラム ID から SAP アイテム (Rfc、Idoc、および Trfc) を受信する唯一のリスナーがそのプログラム ID にアクセスできるようにします。 これは、プログラム ID にアクセスできるすべてのリスナーは、プログラム ID から成果物を受信できるためです。  
  
- ある場合は、複数のリスナーを使用している SAP プログラム ID に同時に、SAP は無作為に選択各発信成果物 (RFC、IDOC、または tRFC) 用のリスナーを認識します。  
  
  詳細については、[SAP システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)を参照してください。
  
## <a name="security-best-practices-for-consuming-the-sap-adapter-with-biztalk-server"></a>BizTalk Server と SAP アダプターを使用するためのセキュリティのベスト プラクティス  
  
- 接続 URI での SAP システムのユーザー名パスワード資格情報は提供されません。  
  
- 使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から SAP システムのユーザー名のパスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
- BizTalk Wcf-custom アダプターを構成するとき、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]から SAP システムのユーザー名のパスワード資格情報を入力、送信ポートで、**資格情報**のタブ、 **にWCFカスタムトランスポートを構成します。**  ダイアログ ボックス。  
  
- BizTalk Wcf-custom アダプターを構成するとき、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、受信場所での SAP システムのユーザー名のパスワード資格情報を入力します、**他**のタブ、 **にWCFカスタムトランスポートを構成します。**  ダイアログ ボックス。  
  
  詳細については、[SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)を参照してください。
  
## <a name="security-best-practices-for-consuming-the-sap-adapter-with-programming-solutions"></a>プログラミング ソリューションで SAP アダプターを使用するためのセキュリティのベスト プラクティス  
  
- 接続 URI; での SAP システムのユーザー名パスワードの資格情報を提供する必要があります。ただし、可能であれば、しないでこれを行います。  
  
- 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]から SAP システムのユーザー名のパスワード資格情報を入力、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
- WCF チャネル モデルのプログラミングを使用して、**資格情報**SAP システムのユーザー名パスワード資格情報を設定するチャネル ファクトリのプロパティ。  
  
- WCF サービス モデルのプログラミングを使用して、 **ClientCredentials** SAP システムのユーザー名パスワード資格情報を設定する WCF クライアントのプロパティ。  
  
- 使用するアプリケーションの場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を別のサービスまたはクライアント、プロセス境界を越えて機密性の高いデータベースの情報を含む送信メッセージは、これらのメッセージは、適切なデータの提供に適用されるセキュリティ対策のための十分なであることを確認環境内で保護します。  
  
  詳細については、[SAP アダプターを使用したプログラミングをセキュリティで保護された](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)を参照してください。  
  
## <a name="security-best-practices-for-hosting-the-sap-adapter-in-iis"></a>IIS での SAP アダプターをホストするためのセキュリティのベスト プラクティス  
  
- ホストしている、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で Microsoft インターネット インフォメーション サービス (IIS) web サービス公開操作によって表示される、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Web クライアントにします。 このデータが可能な限り安全であることを確認のための対策を行う必要がありますので、インターネット経由で機密データを交換するには、これらの操作があります。  
  
   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] HTTP トランスポートの 2 つの標準バインディングを提供します。 **BasicHttpBinding**なしのセキュリティ機構の基本的な HTTP トランスポートを提供します、 **WSHttpBinding**トランス ポート レベルの両方をサポートし、メッセージ レベルのセキュリティ メカニズム。  
  
   使用するか、 **BasicHttpBinding** HTTPS 接続、または使用を介して、 **WSHttpBinding**データを保護するためにします。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれています、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]を WCF サービスの LOB アーティファクトを生成します。 このウィザードは、の使用のみがサポートされます。 **BasicHttpBinding**します。  
  
   お客様の環境を提供する追加のセキュリティ メカニズムを利用するカスタム HTTP バインドを開発することもできます。 詳細については、セキュリティに関する機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx)します。 
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF の診断トレースとメッセージ ログのセキュリティのベスト プラクティス  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 診断トレースとメッセージ ログをサポートしています。 構成ファイルまたは Windows Management Instrumentation (WMI) を使用して診断トレースとメッセージ ログを構成します。 設定すると、構成オプションに応じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]診断トレースまたはメッセージ ログがログに機密情報を出力ファイル、場所、可能性のあるにさらされる可能性の観察承認されていないユーザーです。  
  
 これらの機能を有効にすることによって公開される潜在的なセキュリティの脅威を軽減するために、WCF のドキュメントで提供される推奨事項に従ってください。 少なくとも診断トレースとメッセージ ログの次のベスト プラクティスを確認する必要があります。  
  
- 「詳細」または運用環境での「情報」トレースを有効にしないでください。 これは、パフォーマンスが低下する可能性があります。 ただし、「警告」と、運用環境での「エラー」トレースが有効にする必要があります。 トレースを有効にした場合は、データを保護する適切なセキュリティ対策を行う必要があります。 詳細については、WCF ドキュメントを参照してください。  
  
- ログ ファイルと構成ファイルがアクセス制御リスト (Acl) によって保護されていることを確認します。  
  
  クライアント アプリケーション間で交換されるメッセージに具体的には、次の警告を適用し、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 診断トレースと交換されるメッセージのヘッダー (が本文ではない) を記録できます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 メッセージのアクションがメッセージ ヘッダーにあるためで呼び出された操作が表示されます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]クライアント。  
  
- 場合[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージ ログが有効になっていると`logMessagesAtServiceLevel`は`true`、アダプター クライアントの間で交換されるメッセージのメッセージ ヘッダー (ただし、メッセージ本文ではありません)、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ログに記録されます。 メッセージのアクションがメッセージ ヘッダーにあるため、操作で、クライアントが呼び出すことが表示されます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 場合`logEntireMessage`も`true`、メッセージ本文がログに記録されます。 データベースの機密情報を表示このことができます。  
  
   診断トレースを有効にすると、セキュリティを向上させる詳細については、[セキュリティに関する注意事項とトレース用の役立つヒント](https://msdn.microsoft.com/library/ms733053.aspx)を参照してください。 メッセージのログ記録を有効にすると、セキュリティを向上させる詳細については、[メッセージ ログのセキュリティ関連事項](https://msdn.microsoft.com/library/ms730318.aspx)を参照してください。  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   
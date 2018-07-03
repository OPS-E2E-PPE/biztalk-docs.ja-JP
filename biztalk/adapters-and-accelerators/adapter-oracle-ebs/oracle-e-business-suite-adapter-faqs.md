---
title: Oracle E-business Suite アダプターに関する Faq |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7fe4e0-ddd5-402f-bbbc-b320850eaf3b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 496c18236c8c6a3fa02971cd17a9263e03167571
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007051"
---
# <a name="oracle-e-business-suite-adapter-faqs"></a>Oracle E-business Suite アダプターに関する Faq
次はいくつかよく寄せられる質問 (Faq) に関連する[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。 参照してください[よく寄せられる質問の BizTalk Adapter Pack](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)します。
  

## <a name="how-can-i-use-the-oracle-e-business-adapter-to-communicate-with-oracle-e-business-suite"></a>Oracle E-business Suite との通信に、Oracle E-business アダプターを使用する方法は?  
 使用することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]か、BizTalk アプリケーションを開発、WCF サービス モデルを使用して、または WCF チャネル モデルを使用して、Oracle E-business Suite と通信します。 詳細については、次を参照してください。[概要の BizTalk Adapter for Oracle E-business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e)します。  
  
## <a name="what-interfaces-are-supported-by-the-oracle-e-business-adapter-for-retrieving-metadata"></a>Oracle E-business アダプターでは、メタデータの取得をどのようなインターフェイスがサポートしますか。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
-   WCF に用意された MetadataExchange します。 WCF は、クライアントが Oracle E-business Suite からメタデータを取得できるようにするにすべての WCF バインドのメタデータ交換エンドポイントに提供します。  
  
-   IMetadataRetrievalContract、WCF LOB Adapter SDK、参照および検索機能を備えたアダプターのメタデータをサポートするによって提供されます。  
  
## <a name="how-does-the-adapter-connect-to-oracle-e-business-suite"></a>アダプターは、Oracle E-business Suite をどのように接続しますか。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle クライアントに Oracle のデータ アクセス コンポーネントを使用します。 [サポートされている LOB システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)クライアント バージョンを一覧表示します。 Oracle E-business Suite に接続するには、アダプター クライアントが、接続文字列を指定する必要があります[接続 Uniform Resource Identifier (URI)](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)します。 内部的には、アダプターは、接続 URI を Oracle E-business Suite で基になるデータベースに接続する接続文字列にマップします。 参照してください[Oracle EBS への接続を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)します。  
  
## <a name="does-the-oracle-e-business-adapter-provide-a-secure-way-of-communicating-with-the-oracle-e-business-suite--are-there-any-best-practices-to-ensure-data-security"></a>Oracle E-business アダプターは、Oracle E-business Suite との通信のセキュリティで保護された方法を提供しますか。  データのセキュリティを確保するときのベスト プラクティスはありますか。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business suite、確立された接続での認証にエンタープライズ シングル サインオン (SSO) をサポートしています。 SSO では、データベースとマスター シークレットを使用して暗号化およびユーザーの資格情報を格納します。 Microsoft Windows アカウントをバックエンド システムへのアクセスに使用される資格情報をセカンダリにマップするサービスも提供します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]も Oracle E-business Suite に接続するユーザー名とパスワードの資格情報を入力する必要があります。 これらの資格情報は、ユーザーを認証され、接続の承認のレベルに使用されます。 Oracle E-business アダプターは、いくつかのメソッドを使用するには、これらの資格情報を指定できますを提供します。 BizTalk ソリューションでの Oracle 資格情報を安全に提供する方法については、次を参照してください。[アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)します。 ソリューションをプログラミングでの Oracle 資格情報を安全に提供する方法については、次を参照してください。 [Oracle EBS アダプターを使用したプログラミングにセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-ebs/secure-programming-with-the-oracle-ebs-adapter.md)します。  
  
 詳細:  
  
- データのセキュリティ、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[、Oracle EBS アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)します。  
  
- ベスト プラクティスでデータのセキュリティを確保する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[セキュリティのベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)します。  
  
## <a name="is-there-a-gui-provided-by-the-oracle-e-business-adapter-to-view-and-perform-operations-on-the-artifacts-in-oracle-e-business-suite"></a>Oracle E-business アダプターによって提供される GUI を表示し、Oracle E-business Suite での成果物に対する操作の実行はありますか。  
 アダプター サービスの使用 BizTalk プロジェクト アドインと、アダプター サービス参照を Visual Studio プラグインの追加、確認し、Oracle E-business Suite で、アーティファクトに対する操作を実行する場所のダイアログ ボックスを提供します。 によって提供される GUI の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[参照、検索、および Oracle EBS 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)します。  
  
## <a name="what-are-binding-properties-in-the-oracle-e-business-adapter-where-can-i-find-information-about-all-the-binding-properties-in-the-oracle-e-business-adapter"></a>Oracle E-business アダプターのプロパティをバインド何でしょうか。 Oracle E-business アダプターのすべてのバインドのプロパティに関する情報はどこで入手できますか。  
 アダプター クライアントのバインドのプロパティを使用できます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を構成して、アダプターの動作を制御します。 すべてのバインドのプロパティに関する情報が表示されるため、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[のバインド プロパティの操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="what-are-inbound-and-outbound-operations-in-the-oracle-e-business-adapter"></a>Oracle E-business アダプターの受信と送信の操作とは  
 受信操作で、LOB システム (Oracle E-business Suite) は、クライアントとアダプターのクライアントは、トランザクションが Oracle E-business Suite から発生する場合、サービス。 たとえば、ポーリングと通知操作です。  
  
 送信操作は、アダプターのクライアントは、クライアントと LOB システム (Oracle E-business Suite) は、トランザクションがアダプター クライアントから送信される場合、サービスになります。 たとえば、Insert、Select、Update、およびインターフェイス テーブル、ストアド プロシージャと関数、操作、および複合操作の操作を削除します。  
  
## <a name="where-can-i-find-information-about-the-oracle-data-types-that-are-supported-in-the-oracle-e-business-adapter"></a>Oracle E-business アダプターでサポートされている Oracle データ型に関する情報はどこで入手できますか。  
 サポートされる Oracle データ型については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle データ型の基本的な](../../adapters-and-accelerators/adapter-oracle-ebs/basic-oracle-data-types2.md)します。  
  
## <a name="what-is-applications-context-how-can-i-set-applications-context-for-various-oracle-artifacts-in-the-oracle-e-business-adapter"></a>アプリケーションのコンテキストとは何ですか。 Oracle E-business アダプターでさまざまな Oracle アーティファクトのアプリケーションのコンテキストを設定する方法はありますか  
 アプリケーションのコンテキストとで設定する方法については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-oracle-e-business-adapter"></a>Oracle E-business アダプターを使用してさまざまな操作を実行するには、(BizTalk Server、WCF サービス モデルまたは WCF チャネル モデル) のどちらのアプローチは使用できますか。  
 使用してさまざまな操作を実行する方法に関する情報を使用できます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[、Oracle EBS アプリケーションを開発](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)します。  
  
## <a name="see-also"></a>参照  
[BizTalk Adapter Pack のよく寄せられる質問](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
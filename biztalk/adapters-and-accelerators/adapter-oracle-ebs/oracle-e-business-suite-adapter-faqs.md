---
title: Oracle E-business Suite アダプター Faq |Microsoft ドキュメント
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
ms.openlocfilehash: 9d576fa5dae04a43daa54f2d99e7f9c14d1341e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218058"
---
# <a name="oracle-e-business-suite-adapter-faqs"></a>Oracle E-business Suite アダプターに関する Faq
次は一部よく寄せられる質問 (Faq) に関連する[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。 参照してください[よく寄せられる質問、BizTalk Adapter Pack の](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)します。
  

## <a name="how-can-i-use-the-oracle-e-business-adapter-to-communicate-with-oracle-e-business-suite"></a>Oracle E-business Suite で通信するために、Oracle E-business アダプタを使用する方法は?  
 使用することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite、BizTalk アプリケーションを開発、WCF サービス モデルを使用して、または WCF チャネル モデルを使用して通信するためにします。 詳細については、次を参照してください。[概要の BizTalk Adapter for Oracle E-business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e)です。  
  
## <a name="what-interfaces-are-supported-by-the-oracle-e-business-adapter-for-retrieving-metadata"></a>Oracle E-business アダプターでは、メタデータの取得をどのようなインターフェイスがサポートしますか。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
-   WCF に用意された MetadataExchange です。 WCF は、クライアントが Oracle E-business Suite からメタデータを取得することができますにすべての WCF バインドをメタデータ交換エンドポイントに提供します。  
  
-   WCF LOB アダプター SDK、参照および検索機能を備えたアダプターのメタデータをサポートするによって提供される IMetadataRetrievalContract です。  
  
## <a name="how-does-the-adapter-connect-to-oracle-e-business-suite"></a>アダプターは、Oracle E-business Suite をどのように接続しますか。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle クライアントに Oracle のデータ アクセス コンポーネントを使用します。 [サポートされている LOB システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)クライアント バージョンを一覧表示します。 Oracle E-business Suite に接続するには、アダプター クライアントが接続文字列を提供する必要があります[接続 (Uniform Resource Identifier)](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。 内部的には、アダプターは、接続 URI を Oracle E-business Suite で基になるデータベースに接続する接続文字列にマップします。 参照してください[Oracle EBS への接続を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)です。  
  
## <a name="does-the-oracle-e-business-adapter-provide-a-secure-way-of-communicating-with-the-oracle-e-business-suite--are-there-any-best-practices-to-ensure-data-security"></a>Oracle E-business アダプターは、Oracle E-business Suite との通信のセキュリティで保護された方法を提供しますか。  データのセキュリティを確保するのベスト プラクティスはありますか。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite では、確立された接続での認証にエンタープライズ シングル サインオン (SSO) をサポートしています。 SSO では、データベースとマスター シークレットを使用して暗号化およびユーザーの資格情報を格納します。 Microsoft Windows アカウントをバックエンド システムへのアクセスに使用される資格情報にマップするサービスも提供します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]も Oracle E-business Suite に接続するユーザー名とパスワードの資格情報を入力する必要があります。 これらの資格情報は、ユーザーを認証でき、したがって、接続の承認レベルが使用されます。 Oracle E-business アダプターでは、いくつかのメソッドを使用するには、これらの資格情報を指定することができますを提供します。 BizTalk ソリューションでの Oracle 資格情報を安全に提供する方法については、次を参照してください。[アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)です。 プログラミング ソリューションでの Oracle 資格情報を安全に提供する方法については、次を参照してください。 [Oracle EBS アダプターを使用したプログラミング セキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-ebs/secure-programming-with-the-oracle-ebs-adapter.md)です。  
  
 詳細:  
  
-   データのセキュリティ、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle EBS アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)です。  
  
-   ベスト プラクティスでデータのセキュリティを確保する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[セキュリティのベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)です。  
  
## <a name="is-there-a-gui-provided-by-the-oracle-e-business-adapter-to-view-and-perform-operations-on-the-artifacts-in-oracle-e-business-suite"></a>Oracle E-business アダプターによって提供される GUI を表示および Oracle E-business Suite でのアイテムに対して操作を実行するのにはありますか。  
 アダプター サービスの使用する BizTalk プロジェクト アドインと、アダプター サービス参照を Visual Studio プラグインの追加は、確認し、Oracle E-business Suite で成果物の操作を実行する場所 ダイアログ ボックスを提供します。 によって提供される GUI の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[参照、検索、および get 操作のメタデータの Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。  
  
## <a name="what-are-binding-properties-in-the-oracle-e-business-adapter-where-can-i-find-information-about-all-the-binding-properties-in-the-oracle-e-business-adapter"></a>新機能は、バインドのプロパティ、Oracle E-business アダプターのですか。 Oracle E-business アダプターのすべてのバインドのプロパティに関する情報を検索する場所は?  
 アダプターのクライアントが使用できるは、バインディングのプロパティに、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を構成し、アダプターの動作を制御します。 すべてのバインドのプロパティに関する情報が表示されるため、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[のバインド プロパティの操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
## <a name="what-are-inbound-and-outbound-operations-in-the-oracle-e-business-adapter"></a>Oracle E-business アダプターの受信と送信操作とは  
 受信操作で (Oracle E-business Suite) の LOB システムは、クライアントと Oracle E-business Suite からトランザクションを送信する場合、サービスのアダプターのクライアントがします。 たとえば、ポーリングと通知操作です。  
  
 送信操作で、アダプター クライアント クライアント、LOB システム (Oracle E-business Suite) が、サービスは、アダプターのクライアントからトランザクションを送信するのになります。 たとえば、Insert、Select、Update、およびインターフェイス テーブル、ストアド プロシージャおよび関数での操作および複合操作に対する操作を削除します。  
  
## <a name="where-can-i-find-information-about-the-oracle-data-types-that-are-supported-in-the-oracle-e-business-adapter"></a>Oracle E-business アダプターでサポートされている Oracle データ型に関する情報を検索する場所は?  
 サポートされる Oracle データ型について、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle データ型の基本](../../adapters-and-accelerators/adapter-oracle-ebs/basic-oracle-data-types2.md)です。  
  
## <a name="what-is-applications-context-how-can-i-set-applications-context-for-various-oracle-artifacts-in-the-oracle-e-business-adapter"></a>アプリケーションのコンテキストとは何ですか。 Oracle E-business アダプターでさまざまな Oracle 成果物のためのアプリケーションのコンテキストを設定する方法は?  
 アプリケーションのコンテキストとで設定する方法については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-oracle-e-business-adapter"></a>Oracle E-business アダプターを使用してさまざまな操作を実行する (BizTalk Server で WCF サービス モデルまたは WCF チャネル モデル) は、どの方法を使用できますか。  
 方法に関する情報を使用してさまざまな操作の実行に使用できます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle EBS アプリケーションの開発](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)です。  
  
## <a name="see-also"></a>参照  
[BizTalk Adapter Pack のよく寄せられる質問](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
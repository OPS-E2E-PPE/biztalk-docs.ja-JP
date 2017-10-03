---
title: "アダプターを使用して Oracle E-business Suite への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80ff31d4-be4c-42d7-a321-8f01b40dd71e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8551c0f09d65d50b87248a6b0dc4030a612fc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-e-business-suite-using-the-adapter"></a>アダプターを使用して Oracle E-business Suite への接続します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ODP.NET 11.1.0.7 を使用して、Oracle E-business Suite に接続します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアント識別子 URI (Uniform Resource)、Oracle E-business Suite に接続する接続と呼ばれる、接続文字列を指定する必要があります。 内部的には、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] URI を基になる、Oracle データベースに接続します。 接続 URI のアダプターのクライアントは、外部システムに接続するための接続パラメーターを指定できます。  

## <a name="connectivity-to-oracle-ebs"></a>Oracle EBS への接続  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントは、次の 2 つの方法 Oracle E-business Suite に接続できるようにします。  
  
-   **Tnsnames.ora を使用して**: アダプターのクライアントによって提供される URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、net サービス名のエントリ tnsnames.ora ファイルからサーバー名、サービス名、およびポート番号などの接続パラメーターを抽出します。 このアプローチを使用するのには、tnsnames.ora ファイルに、Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成しなければなりません。  
  
    > [!IMPORTANT]
    >  Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)操作を実行している場合、複数の 39 文字を含めることはできませんでトランザクション。 したがっての値が指定されていることを確認してください、 **DataSourceName**パラメーターは 39 文字以下のトランザクションで操作を実行する場合。  
  
-   **Tnsnames.ora を使用せず**: アダプターのクライアントによって提供される URI の接続には、サーバー名、サービス名、およびポート番号などの接続パラメーターが含まれています。 この例では、tnsnames.ora ファイル、または実際 tnsnames.ora ファイル自体には、net サービス名は、クライアント コンピューターに存在している必要はありません。 これは、機能は、多数のユーザーが、組織内の Oracle データベースへの接続があり、サーバーの追加/更新が発生しても手動で追加/更新すべてのクライアント コンピューターで tnsnames.ora ファイルで接続の詳細と便利です。  
  
    > [!IMPORTANT]
    >  トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限によるものです。  
  
 Oracle E-business Suite への接続に関する詳細については、次を参照してください。 [Oracle E-business Suite への接続を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)です。  
  
 Oracle E-business Suite への接続を確立するときに、セキュリティのガイドラインに従うことを確認します。 参照してください[Oracle EBS アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)です。
  
## <a name="enter-client-credentials"></a>クライアントの資格情報を入力してください。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、次の 2 か所で Oracle E-business Suite への接続に資格情報を提供することができます。  
  
-   **セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 このダイアログ ボックスを見つけることができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
-   **OracleUserName**と**OraclePassword**バインドのプロパティ、**バインド プロパティ** タブで、**アダプターの構成**ダイアログ ボックス。 このダイアログ ボックスを見つけることができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 この場合、資格情報は、バインド ファイルにプレーン テキストで格納されます。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**資格情報の (Oracle E-business Suite または Oracle データベース) Oracle E-business Suite への接続に使用されるセットを指定することができるようにするプロパティをバインドします。  
  
-   Oracle データベースの資格情報を使って接続するには、指定、 **ClientCredentialType**としてプロパティのバインド**データベース**、、**セキュリティ**タブで、指定しますデータベースの資格情報、**ユーザー名**と**パスワード**テキスト ボックス。  Oracle E-business Suite 資格情報を提供する必要がありますも、Oracle E-business Suite の成果物 (インターフェイス テーブル、ビューのインターフェイス、同時実行プログラム、要求セット、または Oracle E-business Suite PL/SQL Api) のいずれかの操作を実行する場合、**OracleUserName**と**OraclePassword**プロパティをバインドします。  
  
-   Oracle E-business Suite の資格情報を使って接続するには、指定、 **ClientCredentialType**としてプロパティのバインド**EBusiness**での Oracle E-business Suite の資格情報を指定し、 **ユーザー名**と**パスワード**上のテキスト ボックス、**セキュリティ**タブです。Oracle データベースの資格情報を指定する必要がありますも、 **OracleUserName**と**OraclePassword**プロパティをバインドします。  
  
 クライアントの資格情報を指定する方法の詳細については、次を参照してください。 [for Oracle E-business Suite サインイン資格情報を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)です。  
  
## <a name="using-windows-authentication"></a>Windows 認証を使用する  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続中に Windows 認証をサポートします。 Windows 認証では、アダプター クライアントは、Windows ログオン資格情報に基づくユーザーの id を決定することができ、Windows 環境の組み込みのセキュリティを活用できます。 Windows 認証を使用して Oracle E-business Suite に接続する方法の詳細については、次を参照してください。 [Oracle E-business Suite を使用して Windows 認証への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle E-business スーツの BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
---
title: アダプターを使用して Oracle E-business Suite への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80ff31d4-be4c-42d7-a321-8f01b40dd71e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7ef5a7dc47b135cbeeec348c2af2d5054163d33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980699"
---
# <a name="connect-to-oracle-e-business-suite-using-the-adapter"></a>アダプターを使用して Oracle E-business Suite への接続します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ODP.NET 11.1.0.7 を使用して Oracle E-business Suite に接続します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアント接続の Uniform Resource Identifier (URI) を Oracle E-business Suite への接続と呼ばれる接続文字列を指定する必要があります。 内部的には、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] URI を基になる、Oracle データベースに接続します。 接続 URI では、アダプター クライアントは、外部システムに接続する接続パラメーターを指定できます。  

## <a name="connectivity-to-oracle-ebs"></a>Oracle EBS への接続  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが、次の 2 つの方法 Oracle E-business Suite に接続できるようにします。  
  
- **Tnsnames.ora を使用して**: 接続アダプター クライアントによって提供された URI には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、tnsnames.ora ファイルで、net サービス名のエントリから、サーバー名、サービス名、およびポート番号などの接続パラメーターを抽出します。 このアプローチを使用するには、tnsnames.ora ファイルで Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成する必要があります。  
  
  > [!IMPORTANT]
  >  Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)操作を実行している場合は、複数の 39 文字を含めることはできませんトランザクション。 値が指定されているため、必ず、 **DataSourceName**パラメーターは 39 文字未満のトランザクションで操作を実行する場合。  
  
- **Tnsnames.ora を使用せず**: 接続アダプター クライアントによって提供された URI には、サーバー名、サービス名、およびポート番号などの接続パラメーターが含まれています。 この場合は、tnsnames.ora ファイル、または実際の tnsnames.ora ファイル自体には、net サービス名は、クライアント コンピューターに存在する必要はありません。 これは、機能は、お客様の組織での Oracle データベースに接続するユーザーの数が多いがあり、サーバーの追加/更新を手動で追加/更新すべてのクライアント コンピューターで tnsnames.ora ファイルで接続の詳細を発生させない場合に便利です。  
  
  > [!IMPORTANT]
  >  トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限です。  
  
  Oracle E-business Suite への接続に関する詳細については、[、Oracle E-business Suite への接続を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)を参照してください。  
  
  Oracle E-business Suite との接続を確立するときに、セキュリティのガイドラインに従うことを確認します。 参照してください[、Oracle EBS アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)します。
  
## <a name="enter-client-credentials"></a>クライアントの資格情報を入力します。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、次の 2 つの場所での Oracle E-business Suite への接続に資格情報を提供することができます。  
  
- **セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 このダイアログ ボックスを見つけることができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
- **OracleUserName**と**OraclePassword**バインドのプロパティ、**バインド プロパティ** タブで、**アダプターの構成**ダイアログ ボックス。 このダイアログ ボックスを見つけることができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 この場合、資格情報は、バインド ファイルにプレーン テキストで格納されます。  
  
  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**を使用すると、一連の資格情報 (Oracle E-business Suite、または Oracle データベース) Oracle E-business Suite への接続に使用されるプロパティをバインドします。  
  
- Oracle データベースの資格情報を使用して接続するには、指定、 **ClientCredentialType**としてプロパティのバインド**データベース**、し、、**セキュリティ**タブで指定します、データベースの資格情報、**ユーザー名**と**パスワード**テキスト ボックス。  Oracle E-business Suite の資格情報を提供する必要がありますも Oracle E-business Suite の成果物 (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、要求のセット、または Oracle E-business Suite PL/SQL Api) のいずれかの操作を実行する場合、**OracleUserName**と**OraclePassword**プロパティをバインドします。  
  
- Oracle E-business Suite の資格情報を使用して接続するには、指定、 **ClientCredentialType**としてプロパティのバインド**EBusiness**、し、Oracle E-business Suite の資格情報を指定、 **ユーザー名**と**パスワード**上のテキスト ボックス、**セキュリティ**タブ。Oracle データベースの資格情報を指定することも必要があります、 **OracleUserName**と**OraclePassword**プロパティをバインドします。  
  
  クライアントの資格情報を指定する方法については、[、Oracle E-business Suite のサインイン資格情報を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)を参照してください。  
  
## <a name="using-windows-authentication"></a>Windows 認証を使用する  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続中に Windows 認証をサポートしています。 Windows 認証では、アダプター クライアントは Windows ログオン資格情報に基づいて、ユーザーの id を調べるし、Windows 環境の組み込みのセキュリティを活用できます。 Windows 認証を使用して Oracle E-business Suite に接続する方法の詳細については、[Oracle E-business Suite を使用して Windows 認証への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)を参照してください。  
  
## <a name="see-also"></a>参照  
[BizTalk Adapter for Oracle E-business スーツについてください。](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
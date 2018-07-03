---
title: アダプターを使用して Oracle データベースへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection string
- uniform resource identifier
- Oracle database, connecting to
- URI
- connection URI
ms.assetid: 5d5598e5-aba0-4c73-8e97-9156475b93c4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a645ae3a2db79e9e2b5b4e46c758e37dfb0a1a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004323"
---
# <a name="connect-to-oracle-database-using-the-adapter"></a>アダプターを使用して Oracle データベースへの接続します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET 11.1.0.7 を使用して Oracle データベースに接続します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアント接続の Uniform Resource Identifier (URI) を Oracle データベースへの接続と呼ばれる接続文字列を指定する必要があります。 内部的には、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースに接続するデータベース接続文字列に URI をマップします。 接続 URI では、アダプター クライアントは、外部システムに接続する接続パラメーターを指定できます。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]により、2 つの方法を次のように Oracle データベースに接続するクライアントはアダプター。  
  
- **Tnsnames.ora を使用して**: 接続アダプター クライアントによって提供された URI には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、tnsnames.ora ファイルで、net サービス名のエントリから、サーバー名、サービス名、およびポート番号などの接続パラメーターを抽出します。 このアプローチを使用するには、tnsnames.ora ファイルで Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成する必要があります。  
  
  > [!IMPORTANT]
  >  Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [Oracle データベース アダプターの接続 URI の構成](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md)場合は、複数の 39 文字を含めることはできませんをトランザクションでの操作を実行します。 値が指定されているため、必ず、 **DataSourceName**パラメーターは 39 文字未満のトランザクションで操作を実行する場合。  
  
- **Tnsnames.ora を使用せず**: 接続アダプター クライアントによって提供された URI には、サーバー名、サービス名、およびポート番号などの接続パラメーターが含まれています。 この場合は、tnsnames.ora ファイル、または実際の tnsnames.ora ファイル自体には、net サービス名は、クライアント コンピューターに存在する必要はありません。 これは、機能は、お客様の組織での Oracle データベースに接続するユーザーの数が多いがあり、サーバーの追加/更新を手動で追加/更新すべてのクライアント コンピューターで tnsnames.ora ファイルで接続の詳細を発生させない場合に便利です。  
  
  > [!IMPORTANT]
  >  トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限です。  
  
  Oracle データベースへの接続に関する詳細については、次を参照してください。 [Oracle データベースへの接続を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)します。  
  
  Oracle データベースとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。 セキュリティのガイドラインの詳細については、次を参照してください。 [Oracle データベース アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)します。  
  
## <a name="windows-authentication"></a>[Windows 認証]  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースへの接続中に Windows 認証をサポートしています。 Windows 認証では、アダプター クライアントは Windows ログオン資格情報に基づいて、ユーザーの id を調べるし、Windows 環境の組み込みのセキュリティを活用できます。 Windows 認証を使用して Oracle データベースに接続する方法の詳細については、次を参照してください。 [、Oracle データベースを使用して Windows 認証への接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
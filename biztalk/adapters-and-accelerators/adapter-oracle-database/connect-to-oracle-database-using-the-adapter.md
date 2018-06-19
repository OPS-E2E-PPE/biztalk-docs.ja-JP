---
title: アダプターを使用して Oracle データベースへの接続 |Microsoft ドキュメント
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
ms.openlocfilehash: 01b04a615d0b0b8cd83b9ed7516cd096b2c85a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214754"
---
# <a name="connect-to-oracle-database-using-the-adapter"></a>アダプターを使用して Oracle データベースへの接続します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET 11.1.0.7 を使用して Oracle データベースに接続します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアント識別子 URI (Uniform Resource)、Oracle データベースに接続する接続と呼ばれる、接続文字列を指定する必要があります。 内部的には、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースに接続するデータベース接続文字列に URI をマップします。 接続 URI のアダプターのクライアントは、外部システムに接続するための接続パラメーターを指定できます。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]により、2 つの方法を次の Oracle データベースに接続するクライアントはアダプター。  
  
-   **Tnsnames.ora を使用して**: アダプターのクライアントによって提供される URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、net サービス名のエントリ tnsnames.ora ファイルからサーバー名、サービス名、およびポート番号などの接続パラメーターを抽出します。 このアプローチを使用するのには、tnsnames.ora ファイルに、Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成しなければなりません。  
  
    > [!IMPORTANT]
    >  Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [Oracle データベース アダプターの接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md)場合は、複数の 39 文字を含めることはできません、トランザクションで操作を実行します。 したがっての値が指定されていることを確認してください、 **DataSourceName**パラメーターは 39 文字以下のトランザクションで操作を実行する場合。  
  
-   **Tnsnames.ora を使用せず**: アダプターのクライアントによって提供される URI の接続には、サーバー名、サービス名、およびポート番号などの接続パラメーターが含まれています。 この例では、tnsnames.ora ファイル、または実際 tnsnames.ora ファイル自体には、net サービス名は、クライアント コンピューターに存在している必要はありません。 これは、機能は、多数のユーザーが、組織内の Oracle データベースへの接続があり、サーバーの追加/更新が発生しても手動で追加/更新すべてのクライアント コンピューターで tnsnames.ora ファイルで接続の詳細と便利です。  
  
    > [!IMPORTANT]
    >  トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限によるものです。  
  
 Oracle データベースへの接続に関する詳細については、次を参照してください。 [Oracle データベースへの接続を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)です。  
  
 Oracle データベースとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。 セキュリティに関するガイドラインの詳細については、次を参照してください。 [、Oracle データベース アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)です。  
  
## <a name="windows-authentication"></a>[Windows 認証]  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースへの接続中に Windows 認証をサポートします。 Windows 認証では、アダプター クライアントは、Windows ログオン資格情報に基づくユーザーの id を決定することができ、Windows 環境の組み込みのセキュリティを活用できます。 Windows 認証を使用して Oracle データベースに接続する方法の詳細については、次を参照してください。 [Oracle データベースを使用して Windows 認証への接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter 用 Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
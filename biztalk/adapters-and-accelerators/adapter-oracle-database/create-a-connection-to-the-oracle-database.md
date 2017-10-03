---
title: "Oracle データベースへの接続を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapter, connecting to the Oracle Database
ms.assetid: 95f7905a-abad-4841-85c4-62cf0cc1e044
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f9a42994f0cde9df19e3b80e16fcbafbb2d8d5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-oracle-database"></a>Oracle データベースへの接続を作成します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、WCF エンドポイントのアドレスを使用して、Oracle データベースへの通信を可能になります。 WCF では、エンドポイント アドレス、通常表現されますとして、Uniform Resource Identifier ()、サービスのネットワークの場所を識別します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続プロパティが含まれて、URI とは、この場所の表現を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle データベースへの接続を確立するために使用します。  
  
 接続 URI を指定する必要がありますとします。  
  
-   チャネル ファクトリまたはを使用してチャネル リスナーを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルまたはを使用して WCF クライアントまたはサービス ホストを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。  
  
-   物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] 、WCF クライアント クラスまたは WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスを提供します。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースへの接続を確立するための 2 つの方法をサポートしています。  
  
-   **Tnsnames.ora を使用して**です。 この方法では、アダプター クライアントによって提供される URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、サーバー名、サービス名、ポートなしなどに、接続パラメーターを抽出、net サービス名のエントリ、ファイルからなどです。 このアプローチを使用するのには、tnsnames.ora ファイルに、Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成しなければなりません。  
  
    > [!IMPORTANT]
    >  Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)を実行する場合、複数の 39 文字を含めることはできませんトランザクションで操作します。 したがっての値が指定されていることを確認してください、 **DataSourceName**パラメーターは 39 文字以下のトランザクションで操作を実行する場合。  
  
-   **Tnsnames.ora を使用せず**です。 この方法では、アダプターのクライアントは、接続 URI の直接接続パラメーターを指定します。 これは、操作では、tnsnames.ora ファイル、クライアント コンピューター上に存在する net サービス名は必要ありません。 クライアント コンピューターに存在している tnsname.ora ファイルが、この方法でもは必要はありません。  
  
    > [!IMPORTANT]
    >  トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限によるものです。  
  
 このセクションのトピックでは、間の接続を確立する方法を記述、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]と使用することによって Oracle データベース。  
  
-   Oracle クライアントの構成に関する情報。  
  
-   接続のプロパティと、Oracle の接続 URI の構造に関する情報。  
  
-   使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
-   Windows 認証を使用して Oracle データベースへの接続に関する情報。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベース アダプターの Oracle クライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)  
  
-   [Oracle Database 接続 URI を作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)  
  
-   [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)
---
title: Oracle データベースへの接続の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, connecting to the Oracle Database
ms.assetid: 95f7905a-abad-4841-85c4-62cf0cc1e044
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c79af51280879e1cf6c72053a42822cd24fae68e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988459"
---
# <a name="create-a-connection-to-the-oracle-database"></a>Oracle データベースへの接続を作成します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 そのため、WCF エンドポイントのアドレスから Oracle データベースへの通信ができます。 WCF では、エンドポイント アドレスは通常としてする Uniform Resource Identifier (URI)、サービスのネットワークの場所を識別するを表現していました。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続プロパティを格納する、URI として、この場所を表します[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle データベースへの接続を確立するために使用します。  
  
 接続 URI を指定する必要がありますとします。  
  
- チャネル ファクトリまたはを使用してチャネル リスナーを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルまたはを使用して WCF クライアントまたはサービス ホストを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。  
  
- 物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスです。  
  
- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- WCF クライアント クラスまたは WCF サービス モデル ソリューションの WCF サービスのインターフェイスを生成するには、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用します。  
  
  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースへの接続を確立する 2 つの方法をサポートしています。  
  
- **Tnsnames.ora を使用して**します。 この方法では、アダプター クライアントによって提供された URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 サーバー名、サービス名、ポート番号など、アダプターは、接続パラメーターを抽出します。 ファイルの net サービス名のエントリからなど。 このアプローチを使用するには、tnsnames.ora ファイルで Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成する必要があります。  
  
  > [!IMPORTANT]
  >  Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)を実行する場合は、複数の 39 文字を含めることはできませんトランザクションで操作します。 値が指定されているため、必ず、 **DataSourceName**パラメーターは 39 文字未満のトランザクションで操作を実行する場合。  
  
- **Tnsnames.ora を使用せず**します。 この方法では、アダプターのクライアントは、直接接続 URI の接続パラメーターを指定します。 これは、クライアント コンピューターの tnsnames.ora ファイルに存在する net サービス名には必要ありません。 この方法は、クライアント コンピューターに存在している tnsname.ora ファイルをも必要ありません。  
  
  > [!IMPORTANT]
  >  トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限です。  
  
  このセクションのトピックでは、間の接続を確立する方法をについて説明します、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]とを提供することで、Oracle データベース。  
  
- Oracle クライアントの構成に関する情報。  
  
- 接続プロパティおよび Oracle 接続 URI の構造について説明します。  
  
- 使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
- Windows 認証を使用して Oracle データベースへの接続について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベース アダプターの Oracle クライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)  
  
-   [Oracle Database 接続 URI を作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)  
  
-   [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションの開発](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)
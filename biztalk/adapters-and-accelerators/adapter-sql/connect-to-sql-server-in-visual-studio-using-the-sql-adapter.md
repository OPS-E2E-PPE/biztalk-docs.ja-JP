---
title: "SQL アダプターを使用して Visual Studio での SQL Server に接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62fc2c01-6e4d-4b3b-8581-1d57436ef4e9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb5e2d149c9a9533e4bec3c2c1c435bffb3adf26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-sql-adapter"></a>SQL アダプターを使用して Visual Studio での SQL Server に接続します。
このセクションで説明を使用する手順については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
-    **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** で使用できるは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトし、の一部としてインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 使用する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk Server とソリューションの開発に関する詳細については、次を参照してください。 [SQL アダプタを使用する開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)です。  
  
-    **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** で使用できるは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトし、の一部としてインストールされている、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]インストールします。 使用する、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。 使用したソリューションの開発の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL アダプタを使用する開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)です。  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公開される WCF カスタム バインドおよび BizTalk アダプターとして、いずれかを使用できる、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SQL Server に接続する BizTalk プロジェクトからです。  
  
-    **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** は BizTalk 以外のプログラミング プロジェクトで使用できます。 使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルでのソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)です。  
  
 使用する、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、まず、SQL Server に接続する必要があります。 3 つのメソッドは、以下を設定して、接続を構成するダイアログ ボックスを表示します。  
  
-   **接続パラメーター**です。 これらは、SQL Server 名、データベースのインスタンス名、およびデータベース名などの接続 URI の構築に使用されるパラメーターです。  
  
-   **SQL Server のユーザー名パスワード資格情報**です。 これらは、接続が確立されたときに SQL Server の認証に使用されます。 ユーザー名とパスワードを指定する必要があります。  
  
-   **バインドのプロパティ**です。 バインドのプロパティはオプションであり、それらを指定するかどうかによって異なります、主に特定のバインディング プロパティの設定を必要とする操作を対象にするかどうか。 バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
 少なくとも、SQL Server への接続を構成するときにのみ指定する必要がバインドのプロパティおよび接続を確立するために必要な接続パラメーターによって返されるメタデータに影響を与える、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]する操作ターゲット。 ただし、追加のバインドのプロパティと実行時に使用される接続パラメーターの値を指定することがもできます。 これは、ため。  
  
-   [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]バインドのプロパティとの接続を構成し、このファイルをプロジェクトに追加するを指定する接続パラメーターから BizTalk ポートのバインド ファイルを作成します。  
  
-   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとの接続を構成し、このファイルをプロジェクト ディレクトリに追加するを指定する接続プロパティから app.config ファイルを作成します。  
  

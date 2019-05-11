---
title: SQL アダプタを使用して Visual Studio での SQL Server への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62fc2c01-6e4d-4b3b-8581-1d57436ef4e9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78f447d2a30d3082d26ccf04750ae7c9c5580c67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369914"
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-sql-adapter"></a>SQL アダプタを使用して Visual Studio での SQL Server に接続します。
このセクションでは使用する方法について説明、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
- **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトし、の一部としてインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk server ソリューションの開発に関する詳細については、次を参照してください。 [SQL アダプターを使用して開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)します。  
  
- **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** で使用できるは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトし、の一部としてインストールされている、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]インストールします。 使用する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 使用したソリューションの開発の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL アダプターを使用して開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)します。  
  
  > [!NOTE]
  >  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公開される WCF カスタム バインドおよび BizTalk アダプターとして、いずれかを使用できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SQL Server に接続するための BizTalk プロジェクトから。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** は非 BizTalk プログラミング プロジェクトで使用できます。 使用する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルを使用したソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)します。  
  
  使用する、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、まず、SQL Server に接続する必要があります。 3 つのメソッドは、以下を設定して接続を構成するダイアログ ボックスを表示します。  
  
- **接続パラメーター**します。 これらは、SQL Server 名、データベースのインスタンス名、およびデータベース名などの接続 URI の構築に使用されるパラメーターです。  
  
- **SQL Server のユーザー名パスワード資格情報**します。 これらは、接続の確立には SQL Server で、認証に使用されます。 ユーザー名とパスワードを指定する必要があります。  
  
- **バインドのプロパティ**します。 バインドのプロパティはオプションであり、主に特定のバインディング プロパティの設定を必要とする操作を対象にするかどうかに依存したり、指定したかどうか。 バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
  少なくとも、SQL Server への接続を構成するときにのみ指定する必要がバインドのプロパティおよび接続を確立するために必要な接続パラメーターによって返されるメタデータに影響を与える、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]する操作ターゲット。 ただし、追加のバインドのプロパティと実行時に使用される接続パラメーターの値を指定する場合がありますもします。 これは、ためにです。  
  
- [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]バインドのプロパティとの接続を構成し、このファイルをプロジェクトに追加を指定する接続パラメーターから BizTalk ポートのバインド ファイルを作成します。  
  
- [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとの接続を構成し、プロジェクト ディレクトリでこのファイルを追加します。 指定した接続のプロパティから app.config ファイルを作成します。  
  

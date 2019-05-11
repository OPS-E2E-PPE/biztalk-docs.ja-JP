---
title: Visual Studio での Oracle データベースへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 766264c8-bb3f-49e9-b851-1022d1fa5076
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c42af12896f1c8d70634862f0463b0200e561a8a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529452"
---
# <a name="connect-to-oracle-database-in-visual-studio"></a>Visual Studio での Oracle データベースへの接続します。
使用する方法、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

## <a name="connection-options-in-visual-studio"></a>Visual Studio での接続オプション

使用する場合[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]、Oracle データベースへの接続に使用できるいくつかのオプションがあります。 これらのオプションは次のとおりです。 

- **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk server ソリューションの開発に関する詳細については、次を参照してください。 [Oracle データベース アダプターを使用して開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)します。  
  
- **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 使用する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk server ソリューションの開発に関する詳細については、次を参照してください。 [Oracle データベース アダプターを使用して開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)します。  
  
  > [!NOTE]
  >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公開される WCF カスタム バインドおよび BizTalk アダプターとして、いずれかを使用できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SQL Server に接続するための BizTalk プロジェクトから。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** は非 BizTalk プログラミング プロジェクトで使用できます。 使用する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルを使用したソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle データベースの開発アプリケーション](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)します。  
  
  使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、Oracle データベースに初めて接続する必要があります。 3 つのメソッドは、以下を設定して接続を構成するダイアログ ボックスを表示します。  
  
- **接続パラメーター**します。 これらは、接続 URI の構築に使用されるパラメーターです。 データ ソース (Oracle net サービス名) を指定する必要があります。  
  
- **Oracle データベースのユーザー名パスワード資格情報**します。 これらは、接続を確立するには Oracle データベースで、認証に使用されます。 ユーザー名とパスワードを指定する必要があります。  
  
- **バインドのプロパティ**します。 バインドのプロパティは、操作のメタデータの生成中にはデザイン時に、これはオプションです。 バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。  
  
  少なくとも、Oracle データベースへの接続を構成するときにのみ指定する必要がバインドのプロパティおよび接続を確立するために必要な接続パラメーターによって返されるメタデータに影響を与える、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の操作ターゲットにします。 ただし、追加のバインドのプロパティと実行時に使用される接続パラメーターの値を指定する場合がありますもします。 これは、ためにです。  
  
- [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]バインドのプロパティと、接続を構成するときに指定する接続パラメーターから BizTalk ポートのバインド ファイルを作成し、このファイルをプロジェクトに追加します。 後で、このバインド ファイルを使用してでポートを作成することができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。  
  
- [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティと、接続を構成するときに指定する接続のプロパティから app.config ファイルを作成し、プロジェクト ディレクトリにこのファイルを追加します。  
  

  
## <a name="see-also"></a>参照  
[Visual Studio での Oracle データベース操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)
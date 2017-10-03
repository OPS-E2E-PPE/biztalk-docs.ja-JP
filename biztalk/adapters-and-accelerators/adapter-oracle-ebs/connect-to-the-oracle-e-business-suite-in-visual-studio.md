---
title: "Visual Studio での Oracle E-business Suite への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e290ea7e-03f3-49d4-9f18-1e539d727d9c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9221914a9f58c3f739eefd5f07986b0105f77e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-oracle-e-business-suite-in-visual-studio"></a>Visual Studio での Oracle E-business Suite への接続します。
このセクションで説明を使用する方法については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
-    **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** で使用できるは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 使用する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk Server とソリューションの開発に関する詳細については、次を参照してください。 [BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)です。  
  
-    **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** で使用できるは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 使用する、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk Server とソリューションの開発に関する詳細については、次を参照してください。 [BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)です。  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開される WCF カスタム バインドおよび BizTalk アダプターとして、いずれかを使用できる、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Oracle E-business Suite に接続する BizTalk プロジェクトからです。  
  
-    **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** は BizTalk 以外のプログラミング プロジェクトで使用できます。 使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルでのソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用してアプリケーションを開発 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)です。  
  
 使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、まず Oracle E-business Suite に接続する必要があります。 3 つのメソッドは、以下を設定して、接続を構成するダイアログ ボックスを表示します。  
  
-   **接続パラメーター**です。 これらは、接続 URI の構築に使用されるパラメーターです。 データ ソース (Oracle net サービス名) を指定する必要があります。  
  
-   **Oracle E-business Suite のユーザー名パスワード資格情報**です。 これらは、接続が確立されたときに、Oracle E-BUSINESS Suite で認証に使用されます。 ユーザー名とパスワードを指定する必要があります。  
  
    > [!IMPORTANT]
    >  この段階では、Oracle E-business Suite または基になる Oracle データベースの資格情報を指定できます。 接続し、メタデータを生成するには、すべての資格情報を指定できます。 ただし、Oracle E-business Suite の成果物を呼び出す操作を実行中に、呼び出し先の Oracle E-business Suite アプリケーションのアプリケーション コンテキストを設定する必要があるため Oracle E-business Suite 資格情報を指定する必要があります。 アプリケーション コンテキストの設定に関する詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
-   **バインドのプロパティ**です。 バインドのプロパティは、操作のメタデータの生成中に、デザイン時に、オプションです。 バインドのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
 少なくとも、Oracle データベースへの接続を構成するときにのみ指定する必要がバインドのプロパティおよび接続を確立するために必要な接続パラメーターによって返されるメタデータに影響を与える、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の操作ターゲットにします。 ただし、追加のバインドのプロパティと実行時に使用される接続パラメーターの値を指定することがもできます。 これは、ため。  
  
-   [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]バインドのプロパティと、接続を構成するときに指定する接続パラメーターから BizTalk ポートのバインド ファイルを作成し、このファイルをプロジェクトに追加します。 このバインド ファイルを使用して、ポートを作成した後で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。  
  
-   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティと、接続を構成するときに指定する接続のプロパティから app.config ファイルを作成し、プロジェクト ディレクトリにこのファイルを追加します。  
  

-   [アダプター サービス参照のプラグインを使用して Visual Studio での Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-service-reference.md)  
  
## <a name="see-also"></a>参照  
 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)
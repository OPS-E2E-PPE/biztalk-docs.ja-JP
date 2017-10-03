---
title: "Visual Studio での Siebel システムへの接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add Adapter Service Reference Plug-in
- Consume Adapter Service Add-in
- how to, connect to the Siebel System in Visual Studio
ms.assetid: 4a94bce9-fda9-4e00-b26c-08672a80e3be
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f7bacf42f90da21830d24587cc7ae6a6e042bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-siebel-system-in-visual-studio"></a>Visual Studio での Siebel システムへの接続します。
このセクションで説明を使用する手順については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
-    **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** で使用できるは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトし、の一部としてインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 使用する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。 使用したソリューションの開発の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[Siebel アダプターを使用する開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)です。  
  
-    **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** で使用できるは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトし、の一部としてインストールされている、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]インストールします。 使用する、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。 使用したソリューションの開発の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[Siebel アダプターを使用する開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)です。  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公開される WCF カスタム バインドおよび BizTalk アダプターとして、いずれかを使用できる、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Siebel システムへの接続に BizTalk プロジェクトからです。  
  
-    **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** は BizTalk 以外のプログラミング プロジェクトで使用できます。 使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルでのソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発 Siebel アプリケーション](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)です。  
  
 使用する、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、Siebel システムに初めて接続する必要があります。 3 つのメソッドは、以下を設定して、接続を構成するダイアログ ボックスを表示します。  
  
-   **接続パラメーター**です。 これらは、Siebel エンタープライズ サーバーの名前など接続 URI の構築に使用されるパラメーターです。  
  
-   **Siebel システムのユーザー名パスワード資格情報**です。 これらは、接続が確立されたときに、Siebel システムで認証に使用されます。 ユーザー名とパスワードを指定する必要があります。  
  
-   **バインドのプロパティ**です。 バインドのプロパティは省略可能と指定するかどうかによって異なります、主に特定のバインディング プロパティの設定を必要とする操作を対象にするかどうか。  
  
 少なくとも、Siebel システムへの接続を構成するときにのみ指定する必要がバインドのプロパティおよび接続を確立するために必要な接続パラメーターによって返されるメタデータに影響を与える、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]操作します。ターゲットとします。 ただし、追加のバインドのプロパティと実行時に使用される接続パラメーターの値を指定することがもできます。 これは、ため。  
  
-   [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]バインドのプロパティとの接続を構成し、このファイルをプロジェクトに追加するを指定する接続パラメーターから BizTalk ポートのバインド ファイルを作成します。  
  
-   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとの接続を構成し、このファイルをプロジェクト ディレクトリに追加するを指定する接続プロパティから app.config ファイルを作成します。  
  
 
  
## <a name="see-also"></a>参照  
 [Visual Studio での Siebel 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)
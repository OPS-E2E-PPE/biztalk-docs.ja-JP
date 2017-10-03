---
title: "Visual Studio での SAP システムへの接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- Add Adapter Service Reference Visual Studio Plug-in
- Consume Adapter Service BizTalk Project Add-in
ms.assetid: 5fc356b1-05e8-4235-bb04-5ef6192c5291
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20cd25c327f2081fed61e19e1571b91a0e39f556
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-sap-system-in-visual-studio"></a>Visual Studio での SAP システムへの接続します。
このセクションで説明を使用する方法については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
-    **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** は BizTalk Server プロジェクトで使用できます。 使用する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk Server とソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)です。  
  
-    **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** は BizTalk Server プロジェクトで使用できます。 使用する、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk Server とソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)です。  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公開される WCF カスタム バインドおよび BizTalk アダプターとして、いずれかを使用できる、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SAP システムに接続する BizTalk プロジェクトからです。  
  
-    **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** は BizTalk 以外のプログラミング プロジェクトで使用できます。 使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルでのソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)です。  
  
 使用する、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]SAP システムに初めて接続する必要があります。 すべての 3 つのユーザー インターフェイスには、使用する、次の設定で接続を構成するダイアログ ボックスが表示します。  
  
-   **接続パラメーター**です。 これらは、アプリケーション サーバーのホストまたはメッセージ サーバー ホスト、およびクライアント ID などの接続 URI の構築に使用されるパラメーター  
  
-   **SAP システムのユーザー名パスワード資格情報**です。 これらは、接続が確立されたときに、SAP システムで認証に使用されます。 ユーザー名とパスワードを指定する必要があります。  
  
-   **バインドのプロパティ**です。 バインドのプロパティは省略可能と指定するかどうかによって異なります、主に特定のバインディング プロパティの設定を必要とする操作を対象にするかどうか。 たとえば、ReceiveIdoc 操作設定する必要が、 **ReceiveIdocFormat**文字列にプロパティを連結します。 バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
 少なくとも SAP システムへの接続を構成するときにのみ指定する必要がバインドのプロパティおよび接続を確立するために必要な接続パラメーターによって返されるメタデータに影響を与える、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作します。ターゲットとします。 ただし、追加のバインドのプロパティと実行時に使用される接続パラメーターの値を指定することがもできます。 これは、ため。  
  
-   [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]バインドのプロパティとの接続を構成し、このファイルをプロジェクトに追加するを指定する接続パラメーターから BizTalk ポートのバインド ファイルを作成します。  
  
-   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとの接続を構成し、このファイルをプロジェクト ディレクトリに追加するを指定する接続プロパティから app.config ファイルを作成します。  
  

  
## <a name="see-also"></a>参照  
 [Visual Studio での SAP 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)
---
title: "WCF クライアントまたは Oracle データベース ソリューションの成果物のための WCF サービス コントラクトを生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model programming, creating a proxy
- how to, create a proxy
- creating a proxy
- proxy programming, creating a proxy
ms.assetid: 3e832ae9-e253-4476-9f25-8cf0de12f469
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e729adec26aca98df80ecc7917ab0558faa6632e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-database-solution-artifacts"></a>WCF クライアントまたは Oracle データベース ソリューションの成果物のための WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは Oracle データベース アイテムの選択した操作を対象とした WCF サービス コントラクト (インターフェイス) を生成します。 ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラスを生成または WCF サービス コントラクト以外にも使用できます。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスを通じて ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 Svcutil.exe ツールではない参照および検索の機能も用意されていて、Oracle データベースに接続するときに選択したバインドのプロパティに基づく構成ファイルを生成します。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用してクライアント クラスを生成する、プラグイン アダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-generate-a-wcf-client-class"></a>WCF クライアント クラスを生成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)Oracle データベースへの接続を検索および参照するには操作です。 選択した操作のための WCF クライアント クラスを作成することを確認**クライアント (送信操作)**からが選択されている、**選択コントラクト型**(これは、既定値) ドロップダウン リスト。  
  
3.  すべての対象をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 2 つのファイルをプロジェクトに追加します。  
  
-   **OracleDBBindingClient.cs**です。 このファイルには、生成された WCF クライアント クラスとヘルパー コード選択した操作にはが含まれています。  
  
-   **App.config**です。このファイルには、バインディング構成、およびクライアント エンドポイント構成が含まれています。 これらの構成は、バインドとの接続を構成したときに選んだ内容に基づいて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF サービス コントラクトを生成する、プラグイン アダプター サービス参照の追加  
 アダプターは、Oracle データベース アダプター クライアントにメッセージを送信を有効にする受信操作を公開します。 などの操作には、WCF サービス コントラクトを生成する必要があります。 たとえば、アダプターは、Oracle データベースをポーリングする受信の POLLINGSTMT 操作を公開します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で指定されたクエリを実行する、 **PollingStatement**バインディング プロパティ、および結果セットの POLLINGSTMT メッセージの処理を行うアプリケーションに送信します。 このシナリオでは、処理を行うアプリケーションがサービスとして機能し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]クライアントとして機能します。 アダプターから POLLINGSTMT 操作を受信できる WCF サービスを実装する必要があります、そのため、します。 これを行うには、使用する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] POLLINGSTMT 操作用にアダプターによって公開されるサービス コントラクトを表す .NET インターフェイスを生成します。 この .NET インターフェイスは、WCF サービス コントラクトとも呼ばれます。 受信 POLLINGSTMT 操作に使用できる、WCF サービスを作成するには、このインターフェイスを実装します。  
  
 このセクションの内容を使用して WCF サービス コントラクトを生成する方法の情報を提供する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]アダプターによって公開されている受信操作にします。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>受信操作の WCF サービス コントラクトを生成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)Oracle データベースに接続します。 複数のバインドのプロパティとの受信操作の Oracle データベースに接続するときに設定する URI プロパティがあります。 たとえば、受信ポーリング操作 (**POLLINGSTMT**)、指定する必要があります、 **PollingStatement** Oracle データベースへの接続を構成するときに、プロパティをバインドします。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作によって返される結果セットを表すクラスを生成するこのプロパティで指定された SQL SELECT ステートメントを使用します。  
  
3.  Oracle データベースに接続すると、選択**サービス (入力方向の操作)**から、**選択コントラクト型**ドロップダウン リスト。  
  
4.  **カテゴリを選択**ボックスで、ルート ノードをクリックして (**/**)、サービス コントラクトを生成する操作を参照します。 たとえば、ポーリング操作は、次のように選択します。 **POLLINGSTMT**から、**利用可能なカテゴリと操作**ボックスをクリックして**追加**です。  
  
5.  POLLINGSTMT 操作の WCF サービス コントラクトを生成する をクリックして**OK**です。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 3 つのファイルをプロジェクトに追加します。  
  
-   **OracleDBBindingInterface.cs**です。 このファイルには、生成された WCF サービス コントラクト (インターフェイス) と POLLINGSTMT 操作用のヘルパー コード。  
  
-   **OracleDBBindingService.cs**です。 このファイルには、OracleDBBindingInterface.cs で定義されているインターフェイスを実装するクラスが含まれています。 このクラスの POLLINGSTMT メソッドで、ポーリング クエリによって返されるレコードを処理するビジネス ロジックを実装することができます。  
  
-   **App.config**です。このファイルには、バインド構成、エンドポイント動作、およびバインドとの接続の構成時に選んだ内容に基づくサービスのエンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>Svcutil.exe を使用して WCF クライアント クラスまたは WCF サービス コントラクトを生成するには  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスまたは WCF サービスのインターフェイスを生成することができます。 と共に使用する svcutil.exe を構成する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 構成およびで svcutil.exe を使用の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[BizTalk アダプターに、ServiceModel メタデータ ユーティリティ ツールを使用して Oracle データベースの](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)します。  
  
 Svcutil.exe は、出力ファイルには、WCF クライアント クラスまたは WCF サービス コントラクトを生成します。 既定のファイル名は、output.cs です。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)   
 [WCF サービス モデルを使用して SQL での基本的な Insert、Update、Delete、および Select 操作の実行](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model.md)
---
title: "SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fa7d8c0-8ee4-41e7-9394-d22e87e09391
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f961c3648e153847f5ac259c9902da5589b1486d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts"></a>SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスを生成する SQL Server のアイテムを選択した操作を対象としています。 ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスを生成します。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスを通じて ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 また、svcutil.exe ツールではない参照および検索の機能を提供し、SQL Server データベースに接続するときに選択したバインドのプロパティに基づく構成ファイルを生成します。  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF クライアント クラスを生成する、プラグイン アダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)SQL Server に接続しを参照し、操作を検索します。 選択した操作のための WCF クライアント クラスを作成することを確認**クライアント (送信操作)**からが選択されている、**選択コントラクト型**ドロップダウン リスト。 (これは、既定値です。)  
  
3.  すべての対象をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 2 つのファイルをプロジェクトに追加します。  
  
-   **WCF クライアント コード ファイル**です。 このファイルには、生成された WCF クライアント クラスとヘルパー コード選択した操作にはが含まれています。 初めて実行するとき、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、既定の名前には、このファイルを生成、 **SQLAdapterBindingClient.cs**です。 もう一度実行する場合、次のファイルが生成されますが呼び出されます**SQLAdapterBindingClient1.cs**です。  数値のサフィックスが新しいファイルを生成するごとに 1 ずつ増加します。  既定のプレフィックスを変更することもできます**SQLBinding**で別のプレフィックスを入力して、**ファイル名のプレフィックス**のフィールド、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]選択する前に**OK**に。ファイルを生成します。  
  
-   **App.config**です。このファイルには、バインド構成との接続を構成したときに選んだ内容に基づくクライアント エンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF サービス コントラクトを生成する、プラグイン アダプター サービス参照の追加  
 受信などの操作に SQL Server データベースをポーリングまたはデータベースから通知を受け取って、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (ポーリング) の場合、クライアント アプリケーションで指定されたクエリを実行するか、SQL Server (の場合、クエリに登録通知)。 両方のシナリオでは、アダプターは、SQL Server データベースから、使用する受信メッセージを送信します。 このような場合は、処理を行うアプリケーションがサービスとして機能し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]クライアントとして機能します。 アダプターから受信操作を受信できる WCF サービスを実装する必要があります、そのため、します。 これを行うには、使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]の受信操作のアダプターによって公開されるサービス コントラクトを表す .NET インターフェイスを生成します。 この .NET インターフェイスは、WCF サービス コントラクトとも呼ばれます。 受信操作の受信に使用できる、WCF サービスを作成するには、このインターフェイスを実装します。  
  
 使用して WCF サービス コントラクトを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>受信操作の WCF サービス コントラクトを生成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[Visual Studio を使用してアダプター サービス参照プラグインの追加 SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference.md)SQL Server データベースに接続します。  
  
    > [!IMPORTANT]
    >  WCF サービス コントラクトを生成する場合**TypedPolling**受信操作は、する必要がありますを指定する、 **InboundID**接続 URI の一部として、 **PollingStatement**プロパティをバインドします。  
  
3.  SQL Server データベースに接続すると、選択**サービス (入力方向の操作)**から、**選択コントラクト型**ドロップダウン リスト。  
  
4.  **カテゴリを選択**ボックスで、ルート ノードをクリックして (**/**) からの受信操作を選択して、**利用可能なカテゴリと操作**ボックスで、し、をクリックして**追加**です。  
  
5.  受信操作の WCF サービス コントラクトを生成する をクリックして**OK**です。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 3 つのファイルをプロジェクトに追加します。  
  
-   **SqlAdapterBindingInterface.cs**です。 このファイルには、生成された WCF サービス コントラクト (インターフェイス) と、受信操作のヘルパー コード。  
  
-   **SqlAdapterBindingService.cs**です。 このファイルには、SqlAdapterBindingInterface.cs で定義されているインターフェイスを実装するクラスが含まれています。 入力方向の操作によって返されるレコードを処理するビジネス ロジックを実装することができます。  
  
-   **app.config**です。このファイルには、バインド構成、エンドポイント動作、およびバインドとの接続の構成時に選んだ内容に基づくサービスのエンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>Svcutil.exe を使用して、WCF クライアント クラスを生成します。  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスを生成することができます。 と共に使用する svcutil.exe を構成する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
 Svcutil.exe の既定のファイル名の出力ファイルで、WCF クライアント クラスを生成する**output.cs**です。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。 Svcutil.exe の詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)
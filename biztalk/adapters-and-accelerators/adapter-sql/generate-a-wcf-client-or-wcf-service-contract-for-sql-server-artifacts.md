---
title: SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fa7d8c0-8ee4-41e7-9394-d22e87e09391
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0930baa5ec89c500f15a5ae7a88ce36e71785c96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013339"
---
# <a name="generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts"></a>SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスを生成する SQL Server のアイテムを選択した操作を対象としました。 WCF クライアント クラスを生成するのに、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用することもできます。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスから ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 Svcutil.exe ツールを使用できない参照および検索の機能を提供し、SQL Server データベースに接続するときに選択したバインドのプロパティに基づいて構成ファイルを生成します。  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF クライアント クラスの生成、プラグインのアダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)SQL Server に接続しを参照し、操作を検索します。 選択した操作のための WCF クライアント クラスを作成することを確認します**クライアント (送信操作)** からが選択されている、**コントラクト型を選択します**ドロップダウン リスト。 (これは、既定値です。)  
  
3. すべてのターゲット をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をプロジェクトに 2 つのファイルを追加します。  
  
- **WCF クライアントのコード ファイル**します。 このファイルには、生成された WCF クライアント クラスとヘルパーのコード選択した操作にはが含まれています。 初めて実行する、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、既定の名前には、このファイルを生成、 **SQLAdapterBindingClient.cs**します。 もう一度実行する場合は、次のファイルが生成されますが呼び出されます**SQLAdapterBindingClient1.cs**します。  数値のサフィックスを生成する新しいファイルごとに 1 ずつ増加します。  既定のプレフィックスを変更することもできます**SQLBinding**で別のプレフィックスを入力して、**ファイル名のプレフィックス**のフィールド、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]選択する前に**OK**に。ファイルを生成します。  
  
- **App.config**します。このファイルには、バインド構成との接続を構成したときに選択した内容に基づいてクライアント エンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF サービス コントラクトを生成する、プラグインのアダプター サービス参照の追加  
 SQL Server データベースをポーリングまたはデータベースから通知を受信などの受信操作のため、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (ポーリング) の場合、クライアント アプリケーションで指定されたクエリを実行します。 または、(の場合に SQL Server でクエリを登録します。通知の場合)。 両方のシナリオでは、アダプターは、SQL Server データベースから使用する側に受信メッセージを送信します。 このような場合は、コンシューマー側アプリケーションがサービスとして動作し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]クライアントとして機能します。 そのため、アダプターから受信操作を受信できる WCF サービスを実装する必要があります。 これを行うには、使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]アダプターの受信操作によって表示されるサービス コントラクトを表す .NET インターフェイスを生成します。 この .NET インターフェイスは、WCF サービス コントラクトとも呼ばれます。 使用できる受信操作を受信する WCF サービスを作成するには、このインターフェイスを実装します。  
  
 使用して WCF サービス コントラクトを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>受信操作の WCF サービス コントラクトを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [Visual Studio を使用して Add Adapter Service Reference プラグインで SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference.md)SQL Server データベースに接続します。  
  
   > [!IMPORTANT]
   >  WCF サービス コントラクトを生成している場合**TypedPolling**受信の操作を指定する必要がある、 **InboundID**接続 URI の一部として、 **PollingStatement**プロパティをバインドします。  
  
3. SQL Server データベースに接続すると、選択**サービス (受信操作)** から、**コントラクト型を選択します**ドロップダウン リスト。  
  
4. **カテゴリを選択**ボックスに、ルート ノードをクリックします (**/**) からの受信操作を選択して、**利用可能なカテゴリと操作**ボックスで、し、クリックして**追加**します。  
  
5. 受信操作の WCF サービス コントラクトを生成する をクリックして**OK**します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 3 つのファイルをプロジェクトに追加します。  
  
- **SqlAdapterBindingInterface.cs**します。 このファイルには、生成された WCF サービス コントラクト (インターフェイス) と受信操作のヘルパー コード。  
  
- **SqlAdapterBindingService.cs**します。 このファイルには、SqlAdapterBindingInterface.cs で定義されているインターフェイスを実装するクラスが含まれています。 受信操作によって返されるレコードを処理するビジネス ロジックを実装することができます。  
  
- **App.config**します。このファイルには、バインド構成、エンドポイントの動作、およびバインドとの接続を構成したときに選択した内容に基づくサービス エンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>Svcutil.exe を使用して WCF クライアント クラスを生成します。  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスを生成することができます。 Svcutil.exe を使用すればを構成する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
 Svcutil.exe の既定のファイル名を持つ出力ファイルで、WCF クライアント クラスを生成する**output.cs**します。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。 Svcutil.exe の詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)します。
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)
---
title: WCF クライアントまたは Oracle データベース ソリューションの成果物の WCF サービス コントラクトの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model programming, creating a proxy
- how to, create a proxy
- creating a proxy
- proxy programming, creating a proxy
ms.assetid: 3e832ae9-e253-4476-9f25-8cf0de12f469
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1e042fb8a60953996f4651d4a4397f75a264e32
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967507"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-database-solution-artifacts"></a>WCF クライアントまたは Oracle データベース ソリューションの成果物の WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは Oracle データベース アイテムの選択した操作を対象とした WCF サービス コントラクト (インターフェイス) を生成します。 ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラスを生成または WCF サービス コントラクトを使用することもできます。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスから ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 Svcutil.exe ツールを使用できない参照と検索の機能も提供し、Oracle データベースに接続するときに選択したバインドのプロパティに基づいて構成ファイルを生成します。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>クライアント クラスの生成を使用して、プラグインのアダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-generate-a-wcf-client-class"></a>WCF クライアント クラスを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)Oracle データベースへの接続を検索および参照するには操作です。 選択した操作のための WCF クライアント クラスを作成することを確認します**クライアント (送信操作)** からが選択されている、**コントラクト型を選択します**(これは、既定値) のドロップダウン リスト。  
  
3. すべてのターゲット をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をプロジェクトに 2 つのファイルを追加します。  
  
- **OracleDBBindingClient.cs**します。 このファイルには、生成された WCF クライアント クラスとヘルパーのコード選択した操作にはが含まれています。  
  
- **App.config**します。このファイルには、バインド構成とクライアント エンドポイント構成が含まれています。 これらの構成はバインドとの接続を構成したときに選択した内容に基づいて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF サービス コントラクトを生成する、プラグインのアダプター サービス参照の追加  
 アダプターは、Oracle データベース アダプターのクライアントにメッセージを送信するを有効にする受信操作を公開します。 などの操作には、WCF サービス コントラクトを生成する必要があります。 たとえば、アダプターは、Oracle データベースをポーリングする受信の POLLINGSTMT 操作を公開します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で指定されたクエリを実行する、 **PollingStatement**バインド プロパティと、結果セット POLLINGSTMT メッセージで、コンシューマー側アプリケーションに送信します。 このシナリオで、コンシューマー側アプリケーションがサービスとして動作し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]クライアントとして機能します。 したがって、アダプターから POLLINGSTMT 操作を受信できる WCF サービスを実装する必要があります。 これを行うには、使用する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] POLLINGSTMT 操作用のアダプターによって表示されるサービス コントラクトを表す .NET インターフェイスを生成します。 この .NET インターフェイスは、WCF サービス コントラクトとも呼ばれます。 受信 POLLINGSTMT 操作に使用できる WCF サービスを作成するには、このインターフェイスを実装します。  
  
 このセクションでは、使用して WCF サービス コントラクトを生成する方法の情報を提供します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]の受信操作がアダプターによって公開されています。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>受信操作の WCF サービス コントラクトを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)Oracle データベースに接続します。 いくつかのバインドのプロパティとの受信操作の Oracle データベースに接続するときに設定する URI プロパティがあります。 たとえば、ポーリングの受信操作 (**POLLINGSTMT**)、指定する必要があります、 **PollingStatement** Oracle データベースへの接続を構成するときに、プロパティをバインドします。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作によって返される結果セットを表すクラスを生成するこのプロパティで指定した SQL SELECT ステートメントを使用します。  
  
3. Oracle データベースに接続すると、選択**サービス (受信操作)** から、**コントラクト型を選択します**ドロップダウン リスト。  
  
4. **カテゴリを選択**ボックスに、ルート ノードをクリックします (**/**)、サービス コントラクトを生成する操作を参照します。 たとえば、ポーリング操作は、次のように選択します。 **POLLINGSTMT**から、**利用可能なカテゴリと操作**ボックスをクリックして**追加**します。  
  
5. POLLINGSTMT 操作の WCF サービス コントラクトを生成する をクリックして**OK**します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 3 つのファイルをプロジェクトに追加します。  
  
- **OracleDBBindingInterface.cs**します。 このファイルには、生成された WCF サービス コントラクト (インターフェイス) と POLLINGSTMT 操作用のヘルパー コード。  
  
- **OracleDBBindingService.cs**します。 このファイルには、OracleDBBindingInterface.cs で定義されているインターフェイスを実装するクラスが含まれています。 このクラスで POLLINGSTMT メソッドで、ポーリング クエリによって返されるレコードを処理するビジネス ロジックを実装することができます。  
  
- **App.config**します。このファイルには、バインド構成、エンドポイントの動作、およびバインドとの接続を構成したときに選択した内容に基づくサービス エンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>Svcutil.exe を使用して WCF クライアント クラスまたは WCF サービス コントラクトを生成するには  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスまたは WCF サービスのインターフェイスを生成することができます。 Svcutil.exe を使用すればを構成する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 構成と使用を svcutil.exe の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[BizTalk adapter for Oracle Database、ServiceModel メタデータ ユーティリティ ツールを使用して](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)します。  
  
 Svcutil.exe は、出力ファイルで、WCF クライアント クラスまたは WCF サービス コントラクトを生成します。 既定のファイル名は、output.cs です。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベースのアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)   
 [WCF サービス モデルを使用した SQL で基本的な Insert、Update、Delete、および Select 操作を実行します。](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model.md)
---
title: "WCF サービス モデルを使用して Oracle データベース アプリケーションを開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performing operations, by using the WCF service model
- developing applications, by using the WCF service model
- WCF service model, using to develop applications
ms.assetid: 3f2c60b2-4835-492d-8c3c-ed35d3e4c517
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 548ca256d4395aefd67681229e9669ef2afcc2f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-oracle-database-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。
最下位のレベル、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスに対して操作を呼び出すプログラミング モデルを表示します。 WCF チャネル モデルと呼ばれる、このモデルでは、データ型とすると、WCF チャネル アーキテクチャを直接操作できるようにするメソッドを公開します。 WCF チャネル モデルを使うと、直接的な制御を作成する SOAP メッセージの内容および両方方法、アプリケーションを介して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]処理ですただし、チャネル経由で送信する整形式の SOAP メッセージを作成し、検証する、。返される応答メッセージには、詳細で正確なタスクを指定できます。  
  
 このため、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] WCF サービス モデルと呼ばれる別のプログラミング モデルを提供します。 WCF サービス モデルには、プロキシ クラスから発信先サービスに対する操作を呼び出すか、クライアントからの受信操作の使用が含まれます。  
  
-   操作の対象となるサービスの呼び出しに使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを使用して .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、によって公開される操作を呼び出すことができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF クライアント上の .NET メソッドとして。 WCF クライアントの詳細についてを参照してください「WCF クライアントの概要」 [http://go.microsoft.com/fwlink/?LinkId=91458](http://go.microsoft.com/fwlink/?LinkId=91458)です。  
  
-   WCF サービス モデルでは、サービスによって公開されるサービス コントラクトは、インターフェイスによって表されます。 このマネージ コードの表現、サービス コントラクトには、WCF サービス コントラクトが呼び出されます。 WCF サービス コントラクトは、厳密に型指定されたパラメーターを持つメソッドとして、操作をモデル化します。 クライアントから、操作を受信するには、クラスをこのインターフェイスから、WCF サービスを実装します。 このクラスのインスタンスをホストすることができますし、 **System.ServiceModel.ServiceHost**コードで操作を呼び出すクライアントを有効にします。 WCF サービス モデルと POLLINGSTMT 操作を対象とした WCF サービス コントラクトを使用すると、Oracle データベースを使用して、ポーリング操作の結果を受信できる[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 WCF クライアント クラスまたは WCF サービス コントラクトを生成するツールを使用して、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を公開します。 次のツールのいずれかの操作を行うこともできます。  
  
-   ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF に付属しています。  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]に付属する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と統合されて、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]強力な参照および検索機能を備えたアダプターによって公開される操作では、デザイン エクスペリエンスおよび Microsoft Windows の標準のインターフェイスを表します。 WCF クライアントまたは WCF サービス コントラクトを生成する方法の詳細については、次を参照してください。 [Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。  
  
 WCF サービス モデルは、多くの場合のプログラミング ソリューションを開発する最適な選択肢は .NET プログラマになじみの非表示にする SOAP メッセージ交換の基になる複雑なチャネル経由でモデルを表示、ため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 ただし、これには WCF チャネル モデルがより優れた選択肢をする可能性がありますシナリオがあります。 たとえば、WCF サービス モデルのみストリーミングをサポートして ReadLOB 操作します。 これは、シリアル化するためと、メッセージ全体をメモリに読み取るには、SOAP メッセージ内のオブジェクトの XML 表現とそれらを表すサービス モデルで使用される .NET 型をシリアル化解除します。 (ReadLOB 操作の結果は、この規則の例外です)。  
  
 WCF チャネル モデルでは、すべての操作では、XML ノード レベルのストリーミングと ReadLOB と UpdateLOB の操作でデータ レベルのストリーミング サポートを提供します。 大きな結果セットを返すか、LOB テーブル内のフィールドを更新しようとしているクエリを処理する場合、WCF チャネル モデルが方が適切にあります。 詳細については、WCF チャネル モデルを使用して、次を参照してください。 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)です。  
  
 このセクションのトピックでは、情報、プロシージャ、および例を作成してモデルを使用して、WCF サービスを使用してアプリケーションを開発する際に役立ちますが含まれて、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)  
  
-   [メタデータおよび Oracle データベースと、WCF サービスのモデル](../../adapters-and-accelerators/adapter-oracle-database/metadata-and-the-wcf-service-model-with-oracle-database.md)  
  
-   [Oracle データベース ソリューションの成果物のための WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)  
  
-   [Oracle データベースでクライアント バインディングを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)  
  
-   [WCF サービス モデルを使用して基本的な Insert、Update、Delete、および Select 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースでの大規模なデータ型を持つテーブルでの操作を完了します。](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-data-types-in-oracle-db-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して、関数、および Oracle データベースでプロシージャを呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースでの操作を使用して REF CURSOR の実行](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースでの操作を使用してレコードの種類の実行](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースでデータ変更のポーリングに基づいたメッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースの変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-the-wcf-service-model1.md)
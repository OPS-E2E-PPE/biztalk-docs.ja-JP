---
title: WCF サービス モデルを使用して Oracle データベース アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performing operations, by using the WCF service model
- developing applications, by using the WCF service model
- WCF service model, using to develop applications
ms.assetid: 3f2c60b2-4835-492d-8c3c-ed35d3e4c517
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdfb72f4901ce8c4ff10f4ff2e664c10e9f7726c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529212"
---
# <a name="develop-oracle-database-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。
最下位レベルで、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスで操作を呼び出すプログラミング モデルを表示します。 WCF チャネル モデルと呼ばれる、このモデルでは、データ型および WCF チャネル アーキテクチャを直接操作するためのメソッドを公開します。 WCF チャネル モデルを作成する SOAP メッセージの内容と、両方方法、アプリケーションを直接制御とを提供しますおよび[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用。 ただし、チャネル経由で送信する適切な形式で SOAP メッセージを作成および検証します。返される応答メッセージには、詳細かつ面倒なタスクを指定できます。  
  
 このため、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] WCF サービス モデルと呼ばれる別のプログラミング モデルを提供します。 WCF サービス モデルには、発信先サービスに対する操作を呼び出すか、クライアントからの受信操作にプロキシ クラスの使用が含まれます。  
  
- ターゲット サービスで操作を呼び出すために使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを持つ .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、公開操作を呼び出すことができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF クライアントでの .NET メソッドとして。 WCF クライアントの詳細についてを参照してください"WCF Client Overview" [ http://go.microsoft.com/fwlink/?LinkId=91458](http://go.microsoft.com/fwlink/?LinkId=91458)します。  
  
- WCF サービス モデルでは、サービスによって公開されるサービス コントラクトがインターフェイスで表されます。 サービス コントラクトの場合は、このマネージ コード表現は、WCF サービス コントラクトと呼ばれます。 WCF サービス コントラクトは、厳密に型指定されたパラメーターを持つメソッドとして、操作をモデル化します。 クライアントから、操作を受信するには、このインターフェイスから、WCF サービス クラスを実装します。 このクラスのインスタンスをホストすることができますし、 **System.ServiceModel.ServiceHost**コードで操作を呼び出すクライアントを有効にします。 WCF サービス モデルおよび POLLINGSTMT 操作を対象とした WCF サービス コントラクトを使用して Oracle データベースの使用に関するポーリング操作の結果を受信できる[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
  WCF クライアント クラスまたは WCF サービス コントラクトを生成するツールを使用して、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を公開します。 次のツールのいずれかを使用できます。  
  
- ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)、WCF に付属しています。  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]が付属していますが、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]  
  
  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と統合されて、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]強力な参照と検索機能を備えた、アダプターによって公開される操作では、デザイン エクスペリエンスと標準の Microsoft Windows のインターフェイスを表示します。 WCF クライアントまたは WCF サービス コントラクトを生成する方法の詳細については、次を参照してください。 [Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。  
  
  WCF サービス モデルのプログラミングのソリューションの開発に最適な選択肢は、多くの場合、.NET プログラマになじみがあるし、チャネル経由で SOAP メッセージ交換の基になる複雑さが隠蔽されるモデルを表示するため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 ただし、WCF チャネル モデルが適してをする可能性がありますのシナリオがあります。 たとえば、WCF サービス モデルのみをサポート ReadLOB 操作にストリーミングします。 これは、シリアル化するためと、SOAP メッセージ内のオブジェクトの XML 表現とサービス モデルでそれらを表すために使用する .NET 型の間の逆シリアル化には、メッセージ全体をメモリに読み取る必要があります。 (ReadLOB 操作の結果は、この規則の例外です)。  
  
  WCF チャネル モデルでは、XML ノード レベルのすべての操作にストリーミングとデータ レベルのストリーミング、ReadLOB および UpdateLOB 操作でのサポートを提供します。 大きな結果セットを返すか、テーブル内の LOB フィールドを更新しようとしているクエリを扱う場合、WCF チャネル モデルが方が適切にあります。 WCF チャネル モデルの使用に関する詳細については、次を参照してください。 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)します。  
  
  このセクションのトピックでは、情報、手順、および作成しを使用してアプリケーションを開発する WCF サービス モデルを使用するのに役立つ例が含まれて、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベース アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)  
  
-   [メタデータと Oracle Database による WCF サービス モデル](../../adapters-and-accelerators/adapter-oracle-database/metadata-and-the-wcf-service-model-with-oracle-database.md)  
  
-   [Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)  
  
-   [Oracle データベースのクライアントのバインディングを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)  
  
-   [WCF サービス モデルを使用して基本的な Insert、Update、Delete、および Select 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースでの大規模なデータ型を持つテーブルに対する操作を完了します。](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-data-types-in-oracle-db-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して、関数および Oracle データベースでプロシージャを呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースで操作を使用して REF CURSOR を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースで操作を使用してレコードの種類を実行します。](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して Oracle データベースの変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-the-wcf-service-model1.md)
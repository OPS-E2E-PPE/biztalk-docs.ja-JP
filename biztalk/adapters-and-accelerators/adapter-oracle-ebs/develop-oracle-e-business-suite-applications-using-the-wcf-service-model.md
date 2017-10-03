---
title: "WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1cf3430d-12e9-437c-b398-d978faa4da2b
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 103a5f8c84b57693dd8f19d47d2b94d5e26256d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]接続する WCF サービスのモデルと呼ばれるプログラミング モデルを提供、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。 サービス モデルに追加された解決するには、WCF の WCF チャネルのプログラミング モデルの制限の一部。  
  
 WCF サービス モデルでは、使い慣れた .NET パラダイムを使用して、チャネル経由で SOAP メッセージを交換するための複雑さを非表示にします。 サービス モデルは、.NET データ構造体に情報をコピーする前に、SOAP メッセージ全体をメモリに読み取るでこの簡素化を実現します。 時間の長いメッセージをメモリに読み込むことがありますは現実的でない一部のアプリケーションです。 このような場合は、開発者は、WCF チャネル モデルを使用してください。 詳細については、WCF チャネル モデルを使用して、次を参照してください。 [WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)です。  
  
 最下位のレベル、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスに対して操作を呼び出す、WCF チャネル モデルを表示します。 WCF チャネル モデルでは、データ型とすると、WCF チャネル アーキテクチャを直接操作できるようにするメソッドを公開します。 WCF チャネル モデルを使うと、直接的な制御を作成する SOAP メッセージの内容および両方方法、アプリケーションを介して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]それらを使用します。 ただし、チャネル経由で送信する整形式の SOAP メッセージを作成して、返される応答メッセージの検証は、詳細で正確なタスクを指定できます。  
  
 WCF サービス モデルは、発信先サービスに対する操作を呼び出すか、クライアントからの受信操作に、プロキシ クラスを使用します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite をするには、操作を呼び出すことができますを WCF サービスとして公開します。  
  
-   操作の対象となるサービスの呼び出しに使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを使用して .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、によって公開される操作を呼び出すことができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF クライアント上の .NET メソッドとして。 WCF クライアントの詳細については、次を参照してください。 [WCF クライアントの概要](https://msdn.microsoft.com/library/ms735103.aspx)です。
  
 WCF クライアント クラスを生成する、次のツールのいずれかを使用して、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を公開します。  
  
-   **ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)**WCF に付属しています。  
  
-   **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]**に付属している、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]と統合し、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]エクスペリエンスをデザインします。 このツールは、強力な参照および検索、アダプターが公開される操作で機能を提供する標準的な Microsoft Windows のインターフェイスを表示します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [Oracle E-business Suite ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 次のトピックでは、WCF サービス モデルを使用するアプリケーションを開発する方法に関する情報を提供します。  
  
-   [Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [メタデータおよび Oracle E-business Suite では、WCF サービスのモデル](../../adapters-and-accelerators/adapter-oracle-ebs/metadata-and-the-wcf-service-model-with-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite ソリューションの成果物のための WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)  
  
-   [For Oracle E-business Suite クライアント バインディングを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)  
  
-   [Insert、Update、Delete、またはインターフェイスのテーブルと、WCF サービス モデルを使用して、ビューに対する Select 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルの操作を完了します。](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを呼び出す](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite での要求のセットをを呼び出す](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、ExecuteScalar、または ExecuteNonQuery 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite データベースの変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)
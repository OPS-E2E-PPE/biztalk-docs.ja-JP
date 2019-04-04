---
title: WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cf3430d-12e9-437c-b398-d978faa4da2b
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b290ef99349d970179b07ecfce45c72499d88c5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996019"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] 接続するための WCF サービス モデルと呼ばれるプログラミング モデルを提供、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。 サービス モデルに追加された WCF の一部に対処する、WCF チャネルのプログラミング モデルの制限の一部です。  
  
 WCF サービス モデルでは、チャネル経由で SOAP メッセージを交換するための複雑さを隠ぺいするのに使い慣れた .NET パラダイムを使用します。 サービス モデルでは、.NET データ構造体に情報をコピーする前に、SOAP メッセージ全体をメモリに読み取るでこの簡略化を実現します。 時間の長いメッセージをメモリに読み込むことがありますは現実的でない一部のアプリケーション。 このような場合は、開発者は、WCF チャネル モデルを使用してください。 WCF チャネル モデルの使用に関する詳細については、[WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)を参照してください。  
  
 最下位レベルで、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスで操作を呼び出す、WCF チャネル モデルを表示します。 WCF チャネル モデルでは、データ型と、WCF チャネルのアーキテクチャを直接操作するためのメソッドを公開します。 WCF チャネル モデルを作成する SOAP メッセージの内容と、両方方法、アプリケーションを直接制御とを提供します。 および[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]これらを使用できます。 ただし、チャネル経由で送信する適切な形式で SOAP メッセージを作成して、返される応答メッセージの検証は、詳細かつ面倒な作業をすることができます。  
  
 WCF サービス モデルは、発信先サービスに対する操作を呼び出すか、クライアントからの受信操作に、プロキシ クラスを使用します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite をするには、操作を呼び出すことができます、WCF サービスとして公開します。  
  
- ターゲット サービスで操作を呼び出すために使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを持つ .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、公開操作を呼び出すことができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF クライアントでの .NET メソッドとして。 WCF クライアントの詳細については、[WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx)を参照してください。
  
  WCF クライアント クラスを生成する、次のツールのいずれかを使用し、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を公開します。  
  
- **ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)** WCF が付属しています。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** が付属していますが、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]と統合、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]エクスペリエンスを設計します。 このツールは、強力な閲覧と検索機能を備えた、アダプターを公開する操作を提供する標準の Microsoft Windows インターフェイスを表示します。 WCF クライアントを生成する方法の詳細については、[Oracle E-business Suite ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 次のトピックでは、WCF サービス モデルを使用するアプリケーションを開発する方法に関する情報を提供します。  
  
-   [Oracle E-business Suite アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [メタデータと Oracle E-business Suite での WCF サービス モデル](../../adapters-and-accelerators/adapter-oracle-ebs/metadata-and-the-wcf-service-model-with-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)  
  
-   [Oracle E-business suite クライアント バインディングを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)  
  
-   [Insert、Update、Delete、またはインターフェイス テーブルと、WCF サービス モデルを使用してビューに対する Select 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作を完了します。](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを起動します。](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite での要求のセットを呼び出す](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、executescalar、ExecuteNonQuery 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して Oracle E-business Suite データベース変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)
---
title: WCF サービス モデルを使用して SQL アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3ecfd6f-9144-4e41-a4b8-0c768a6ac254
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afeb8d7aac2dd2a29f60c89cf54c86ef2e4519df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983979"
---
# <a name="develop-sql-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL アプリケーションを開発します。
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] WCF チャネル モデルをプログラミングする代わりに、WCF サービス モデルと呼ばれるプログラミング モデルを提供します。  
  
 WCF サービス モデルでは、チャネル経由で SOAP メッセージを交換するための複雑さを隠ぺいするのに使い慣れた .NET パラダイムを使用します。 サービス モデルでは、.NET データ構造体に情報をコピーする前に、SOAP メッセージ全体をメモリに読み取るでこの簡略化を実現します。 時間の長いメッセージをメモリに読み込む、ただしが現実的でない一部のアプリケーション。 このような場合は、開発者は、WCF チャネル モデルを使用してください。 WCF チャネル モデルの使用に関する詳細については、次を参照してください。 [WCF チャネル モデルを使用して SQL の開発アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)します。  
  
 最下位レベルで[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスで操作を呼び出す、WCF チャネル モデルを表示します。 WCF チャネル モデルでは、データ型と、WCF チャネルのアーキテクチャを直接操作するためのメソッドを公開します。 WCF チャネル モデルを作成する SOAP メッセージの内容と、両方方法、アプリケーションを直接制御とを提供します。 および[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]これらを使用できます。 ただし、チャネル経由で送信する適切な形式で SOAP メッセージを作成して、返される応答メッセージの検証は、詳細かつ面倒な作業をすることができます。  
  
 WCF サービス モデルは、発信先サービスに対する操作を呼び出すか、クライアントからの受信操作に、プロキシ クラスを使用します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]いる操作を呼び出すことができますを WCF サービスとしての SQL Server データベースを公開します。  
  
- ターゲット サービスの操作の呼び出しに使用されるプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを持つ .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、公開操作を呼び出すことができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF クライアントでの .NET メソッドとして。 WCF クライアントの詳細については、次を参照してください。 [WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx)します。
  
  WCF クライアント クラスを生成する、次のツールのいずれかを使用し、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を公開します。  
  
- **ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)** WCF が付属しています。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** に付属する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と統合、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]エクスペリエンスを設計します。 このツールは、強力な閲覧と検索機能を備えた、アダプターを公開する操作を提供する標準の Microsoft Windows インターフェイスを表示します。 WCF クライアント アプリケーションを生成する方法の詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。  
  
   このセクションのトピックでは、情報、手順、および作成しを使用してアプリケーションを開発する WCF サービス モデルを使用するのに役立つ例が含まれて、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [メタデータと、SQL アダプターで WCF サービス モデル](../../adapters-and-accelerators/adapter-sql/metadata-and-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [SQL Server アイテムの WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)  
  
-   [SQL アダプタのクライアントのバインディングを構成します。](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)  
  
-   [挿入、更新、削除、またはインターフェイス テーブルと、WCF サービス モデルを使用してビューで操作を選択します。](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して SQL に大規模なデータ型を持つテーブルとビューで操作を実行します。](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す](../../adapters-and-accelerators/adapter-sql/invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して sql ExecuteReader、executescalar、ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)  
  
-   [SQL Server をポーリングする WCF サービス モデルでの SQL アダプタの使用](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SQL のクエリ通知を受信します。](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-from-sql-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)
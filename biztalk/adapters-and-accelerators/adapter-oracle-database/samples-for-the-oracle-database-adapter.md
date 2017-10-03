---
title: "Oracle データベース アダプターのサンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- samples, WCF channel model
- samples, WCF service model
- samples, BizTalk
- samples, migration
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4973c0b4ea54ef3b7692dbe4be19773acf1e6e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="samples-for-the-oracle-database-adapter"></a>Oracle データベース アダプターのサンプル
サンプルを[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]に分類されます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サンプル  
  
-   WCF サービス モデルのサンプル  
  
-   WCF チャネル モデルのサンプル  
  
-   移行のサンプル  
  
 サンプルはいただけます[http://go.microsoft.com/fwlink/p/?LinkID=196854](http://go.microsoft.com/fwlink/p/?LinkID=196854)です。 テーブル、パッケージなどを作成するための SQL スクリプト。 使用されるサンプルも用のサンプルと共に使用できます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 次の一覧には、名前と、サンプルの説明が含まれています、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
## <a name="biztalk-server-samples"></a>BizTalk Server のサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|Func_RecordTypes|レコード型のパラメーターを使用で値を返す関数およびプロシージャを使用する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|Func_RefCursor|関数およびプロシージャを使用して REF CURSOR パラメーターを使用する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|InvokeFunction|使用して Oracle データベース内の関数を呼び出す方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|InvokeOverloadedProc|オーバー ロードされた関数およびプロシージャを使用して Oracle データベースで呼び出す方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|Operate_BFILE|Oracle BFILE 型を使用して Oracle プロシージャで使用する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|Operate_LOB|使用して、LOB データ型を持つテーブルに対して ReadLOB と UpdateLOB の操作を実行する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|PollingQuery|ポーリング クエリを構成しを使用して結果を受信する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|SelectAccTable|Oracle データベースを使用してテーブルに対して select クエリを実行する方法を示しています、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|SqlExec|SQLEXECUTE 操作を使用して Oracle データベースを使用してパラメーター化クエリを実行する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
  
## <a name="wcf-service-model-samples"></a>WCF サービス モデルのサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|OracleBfileTypeSM|Oracle BFILE 型 Oracle のテーブルに対して、パラメーターとしてを Oracle プロシージャに表示される基本的な SQL の操作で使用する方法を示します。|  
|OracleOverloadsSM|オーバー ロードされた関数およびパッケージ内のプロシージャを呼び出す方法を示します。|  
|OraclePollingSM|ポーリング クエリを構成し、結果を受信する方法を示します。|  
|OracleRecordTypesSM|レコード型のパラメーターを使用し、関数およびプロシージャに値を返す方法を示します。|  
|OracleRefCursorsSM|関数およびプロシージャの REF CURSOR パラメーターを使用する方法を示します|  
|OracleTransactedDmlSM|WCF サービス モデルを使用して、トランザクションで Oracle データベースでの操作を実行する方法を示します。|  
  
## <a name="wcf-channel-model-samples"></a>WCF チャネル モデルのサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|OraclePollingCM|ポーリング クエリを構成し、結果を受信する方法を示します。|  
|OracleStreamingDemo|エンド ツー エンドの UpdateLOB とテーブルの Select 操作を使用して LOB データのストリーミングを実行する方法を示します|  
|OracleTransactedDmlCM|WCF チャネル モデルを使用して、トランザクションで Oracle データベースでの操作を実行する方法を示します。|  
  
## <a name="migration-samples"></a>移行のサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|Oracle_Migration|Oracle データベースの BizTalk ODBC アダプターを使用して作成された BizTalk プロジェクトを使用する方法を示します (に付属して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]) と WCF ベースで利用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)](に付属して[!INCLUDE[adapterpack20](../../includes/adapterpack20-md.md)])。|  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)
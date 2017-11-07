---
title: "Oracle データベース アダプター サンプル |Microsoft ドキュメント"
description: "BizTalk Server、WCF サービス モデル、および WCF チャネル モデルで使用できる oracle DB WCF アダプタのサンプル"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bfef9fcfce65d8aede1cd905a53469c565977f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-oracle-database-adapter"></a>Oracle データベース アダプターのサンプル
サンプルを[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]に分類されます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サンプル  
  
-   WCF サービス モデルのサンプル  
  
-   WCF チャネル モデルのサンプル  

  
サンプルはいただけます[BizTalk Adapter Pack 2010: Oracle データベース アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=4675)です。 テーブルと、サンプルで使用されるパッケージを作成するための SQL スクリプトが含まれます。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
サンプルを次に示します。
  
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
  

## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションの開発](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)
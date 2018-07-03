---
title: Oracle データベース アダプターのサンプル |Microsoft Docs
description: BizTalk Server、WCF サービス モデル、および WCF チャネル モデルで使用できる oracle DB の WCF アダプタのサンプル
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ac7a1c2cda4fd66e450d23022787f5e7d0e0324
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006451"
---
# <a name="samples-for-the-oracle-database-adapter"></a>Oracle データベース アダプターのサンプル
サンプルは[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]に分類されます。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] サンプル  
  
- WCF サービス モデルのサンプル  
  
- WCF チャネル モデルのサンプル  

  
サンプルについては、「 [BizTalk Adapter Pack 2010: Oracle データベース アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=4675)します。 テーブルと、サンプルで使用されるパッケージを作成するための SQL スクリプトが含まれます。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
サンプルを次に示します。
  
## <a name="biztalk-server-samples"></a>BizTalk Server のサンプル
  
| サンプルのディレクトリ名 |                                                                                         説明                                                                                         |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   Func_RecordTypes    |      レコード型のパラメーターを使用する関数とプロシージャを使用して値を返す方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。      |
|    Func_RefCursor     |               関数とプロシージャを使用して REF CURSOR パラメーターを使用する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。                |
|    InvokeFunction     |                        使用して Oracle データベース内の関数を呼び出す方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。                        |
| InvokeOverloadedProc  |         オーバー ロードされた関数を使用して Oracle データベースでプロシージャを呼び出す方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。         |
|     Operate_BFILE     |                    使用して Oracle プロシージャで Oracle BFILE 型を使用する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。                     |
|      Operate_LOB      |       使用して LOB データ型を持つテーブルで ReadLOB と UpdateLOB の操作を実行する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。       |
|     PollingQuery      |                 ポーリング クエリを構成しを使用して結果を受信する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。                  |
|    SelectAccTable     |                 Oracle データベースを使用してテーブルに対して select クエリを実行する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。                 |
|        SqlExec        | SQLEXECUTE 操作を使用して Oracle データベースを使用してパラメーター化クエリを実行する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 |
  
## <a name="wcf-service-model-samples"></a>WCF サービス モデルのサンプル  
  
|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|OracleBfileTypeSM|Oracle のテーブルに対して、パラメーターとしてを明らかに Oracle プロシージャの基本的な SQL 操作で Oracle BFILE 型を使用する方法を示します。|  
|OracleOverloadsSM|オーバー ロードされた関数と、パッケージ内のプロシージャを呼び出す方法を示します。|  
|OraclePollingSM|ポーリング クエリを構成し、結果を受信する方法を示します。|  
|OracleRecordTypesSM|レコード型のパラメーターを使用し、関数およびプロシージャで値を返す方法を示します。|  
|OracleRefCursorsSM|関数およびプロシージャの REF CURSOR パラメーターを使用する方法を示します|  
|OracleTransactedDmlSM|WCF サービス モデルを使用して、トランザクションで Oracle データベースで操作を実行する方法を示します。|  
  
## <a name="wcf-channel-model-samples"></a>WCF チャネル モデルのサンプル  
  
|サンプルのディレクトリ名|説明|  
|---------------------------|-----------------|  
|OraclePollingCM|ポーリング クエリを構成し、結果を受信する方法を示します。|  
|OracleStreamingDemo|エンド ツー エンド UpdateLOB とテーブルの Select 操作を使用して LOB データのストリーミングを実行する方法を示します|  
|OracleTransactedDmlCM|WCF チャネル モデルを使用して、トランザクションで Oracle データベースで操作を実行する方法を示します。|  
  

## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションの開発](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)
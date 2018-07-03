---
title: Siebel アダプターの SiebelConnection クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, SiebelConnection
- SiebelConnection, supported properties and methods
- SiebelConnection
ms.assetid: 661d9876-4c14-4748-b05f-cc4fd1c4ebcf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dd9e4bbf08d73c8fa48113aad1ecf12fdf0f237
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001987"
---
# <a name="siebelconnection-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelConnection クラス
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 、基になるにアクセスする[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] `Binding`、`ConnectionFactory`と`Channel`Siebel システムに接続します。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]実装、`DbConnection`クラスには、上記をサポートするためにします。  

 インスタンスを使用して`Microsoft.Data.SiebelClient.SiebelClientFactory`、クライアント プログラムがのインスタンスを取得、 `System.Data.Common.DbConnection` Siebel システムに接続するクラス。  

```  
//In this example, factory is an instance of SiebelClientFactory  
DbConnection connection = factory.CreateConnection();  
```  

 または、次のアプローチを使用して、接続を作成します。  

```  

SiebelConnection connection = new SiebelConnection();  
connection.ConnectionString = connectionString;  
```  

 `SiebelConnection`クラスから継承`DbConnection`します。 名前空間内に存在する`Microsoft.Data.SiebelClient`します。  

## <a name="supported-properties"></a>サポートされているプロパティ  
 `SiebelConnection`クラスは、次をサポート`DbConnection`プロパティ。  


|         名前         |   取得/設定   |                                                                                                      説明                                                                                                       |
|----------------------|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ConnectionString** | Get と Set |                                                                                  接続を開くために使用する文字列を取得または設定します。                                                                                  |
|     **[データベース]**     |     取得     |        接続が開かれる前に、接続文字列で指定されたデータベース名または接続が開かれた後に、現在のデータベースの名前を取得します。 Siebel リポジトリ名があります。         |
|    **DataSource**    |     取得     |                                                                                この接続の Siebel ゲートウェイの名前を取得します。                                                                                |
|  **ServerVersion**   |     取得     | 現在のバージョンで[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、Siebel サーバーの実際のバージョンを表していないハード コーディングされた値を返します。 |
|      **State**       |     取得     |                                               接続の状態を表す文字列を取得します。 これは 3 つの値を含めることができます: オープン、切断、または終了します。                                               |

## <a name="supported-methods"></a>サポートされているメソッド  
 `SiebelConnection`クラスは、次をサポート`DbConnection`メソッド。  

|名前|説明|  
|----------|-----------------|  
|**CreateDbCommand**|この保護されているメソッドは、DbCommand の新しいインスタンスを提供します。|  
|**ChangeDatabase**|このパブリック メソッドは、サポートされていませんし、呼び出された場合、例外がスローされます。|  
|**[ファイル]**|WCF チャネルを作成して、Siebel システムとの接続を開きます。|  
|**Close**|WCF チャネルを閉じることで Siebel システムへの接続を閉じます。|  
|**CreateCommand**|コマンド オブジェクトを作成します。|  

## <a name="see-also"></a>参照  
 [Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)
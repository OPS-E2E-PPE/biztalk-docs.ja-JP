---
title: Siebel アダプターの SiebelCommand クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelCommand
- Data Provider for Siebel, SiebelCommand
- SiebelCommand, supported methods and properties
ms.assetid: 7cba0e47-634b-4878-b480-80fbcbbf5c90
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d268e9a1d5954d703d392070a53c84bd9cee0d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222362"
---
# <a name="siebelcommand-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelCommand クラス
Siebel システムへの接続を確立した後、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] ADO.NET クライアントによって提供されるコマンドのパラメーターと Siebel コマンド文字列を解析し、コマンドは、WCF 要求メッセージにマップします。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]への要求を送信、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]し、応答の XML を取得し、アダプターから本文の内容。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を使用して、 `XMLDataReader` XML 本文からリレーショナル データを取得します。  
  
 インスタンスを使用して`Microsoft.Data.SiebelClient.SiebelClientFactory`、クライアント プログラムがのインスタンスを取得できます、 `System.Data.Common.DbCommand` Siebel コマンドを構築するためにクラスです。  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbCommand command = factory.CreateCommand();  
```  
  
 または、コマンドを作成する、次の方法を使用できます。  
  
```  
//Here connection is an instance of SiebelConnection  
SiebelCommand cmd = (SiebelCommand) connection.CreateCommand();  
cmd.CommandText = "SELECT [Name] as MyName, [City], [Country]  from Account.Account WHERE Name LIKE '3Com*' OPTION 'ViewMode 1'";  
```  
  
 `SiebelCommand`クラスから継承`DbCommand`です。  名前空間内に存在する`Microsoft.Data.SiebelClient`です。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
 **SiebelCommand**クラスは、次をサポート`DbCommand`*保護*プロパティ。  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**DbConnection**|Get および Set|基になるこれを含める必要があります`DbConnection`インスタンスからこの`DbCommand`のインスタンスを取得します。|  
|**DbParameterCollection**|取得|コレクションを取得`DbParameter`オブジェクト。|  
  
 `SiebelCommand`次のサポートも`DbCommand`*パブリック*プロパティ。  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**CommandText**|Get および Set|これには、ADO.NET クライアントを実行することを希望する SQL ステートメントが含まれています。|  
|**CommandType**|Get および Set|サポートされるのは `CommandType.Text` のみです。|  
|**接続**|Get および Set|これは、使用、`DbConnection`メンバー。|  
|**パラメーター**|取得|これは、使用、`DbParameterCollection`メンバー。|  
  
> [!IMPORTANT]
>  `SiebelCommand`クラスは無視されます、 `CommandTimeout`、 `DesignTimeVisible`、および`DbTransaction`プロパティです。  
  
## <a name="supported-methods"></a>サポートされているメソッド  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]次のサポート`DbCommand`*保護*メソッド。  
  
|名前|Description|  
|----------|-----------------|  
|**CreateDbParameter**|新たに作成`DbParameter`インスタンス。|  
|**ExecuteDbDataReader**|これを選択し、EXEC コマンドを実行しを返します、`DbDataReader`です。|  
  
 `SiebelCommand`次のサポートも`DbCommand`*パブリック*メソッド。  
  
|名前|Description|  
|----------|-----------------|  
|**CreateParameter**|新たに作成`DbParameter`を通じてインスタンス`CreateDbParameter().`|  
|**ExecuteReader**|実行`CommandText`に対して、`Connection`し、返します`DbDataReader`を通じて`ExecuteDbDataReader()`です。|  
|**準備します。**|これを解析し、`CommandText`し、SQL コマンドの解析ツリーを構築します。|  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)
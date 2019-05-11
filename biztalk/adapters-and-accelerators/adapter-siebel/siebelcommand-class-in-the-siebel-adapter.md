---
title: Siebel アダプターの SiebelCommand クラス |Microsoft Docs
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
ms.openlocfilehash: e35ecc56dd95fdd413827bc7744c1a02745eaa87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370579"
---
# <a name="siebelcommand-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelCommand クラス
Siebel システムへの接続を確立した後、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コマンド文字列が Siebel と ADO.NET クライアントによって提供されるコマンドのパラメーターを解析し、コマンドを WCF 要求メッセージにマップします。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]する要求を送信し、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]から XML 応答を取得し、アダプターから本文の内容。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を使用して、 `XMLDataReader` XML 本文からリレーショナル データを取得します。  
  
 インスタンスを使用して`Microsoft.Data.SiebelClient.SiebelClientFactory`、クライアント プログラムがのインスタンスを取得、 `System.Data.Common.DbCommand` Siebel コマンドを作成するクラス。  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbCommand command = factory.CreateCommand();  
```  
  
 または、次のアプローチを使用して、コマンドを作成します。  
  
```  
//Here connection is an instance of SiebelConnection  
SiebelCommand cmd = (SiebelCommand) connection.CreateCommand();  
cmd.CommandText = "SELECT [Name] as MyName, [City], [Country]  from Account.Account WHERE Name LIKE '3Com*' OPTION 'ViewMode 1'";  
```  
  
 `SiebelCommand`クラスから継承`DbCommand`します。  名前空間内に存在する`Microsoft.Data.SiebelClient`します。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
 **SiebelCommand**クラスは、次をサポート`DbCommand`*保護*プロパティ。  
  
|名前|Get/Set|説明|  
|----------|--------------|-----------------|  
|**DbConnection**|Get と Set|これは、基になるを含める必要があります`DbConnection`元であるインスタンス`DbCommand`インスタンスを取得します。|  
|**DbParameterCollection**|取得|コレクションを取得`DbParameter`オブジェクト。|  
  
 `SiebelCommand` 次のサポートも`DbCommand`*パブリック*プロパティ。  
  
|名前|Get/Set|説明|  
|----------|--------------|-----------------|  
|**CommandText**|Get と Set|これには、ADO.NET クライアントを実行することを希望する SQL ステートメントが含まれます。|  
|**CommandType**|Get と Set|サポートされるのは `CommandType.Text` のみです。|  
|**Connection**|Get と Set|これを使用して、`DbConnection`メンバー。|  
|**パラメーター**|取得|これを使用して、`DbParameterCollection`メンバー。|  
  
> [!IMPORTANT]
>  `SiebelCommand`クラスは無視されます、 `CommandTimeout`、 `DesignTimeVisible`、および`DbTransaction`プロパティ。  
  
## <a name="supported-methods"></a>サポートされているメソッド  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]は、次をサポート`DbCommand`*保護*メソッド。  
  
|名前|説明|  
|----------|-----------------|  
|**CreateDbParameter**|新たに作成`DbParameter`インスタンス。|  
|**ExecuteDbDataReader**|を選択し、EXEC コマンドを実行し、返しますこれを`DbDataReader`します。|  
  
 `SiebelCommand` 次のサポートも`DbCommand`*パブリック*メソッド。  
  
|名前|説明|  
|----------|-----------------|  
|**CreateParameter**|新たに作成`DbParameter`を通じてインスタンス `CreateDbParameter().`|  
|**ExecuteReader**|実行`CommandText`に対して、`Connection`返します`DbDataReader`を通じて`ExecuteDbDataReader()`。|  
|**準備します。**|これを解析し、`CommandText`し SQL コマンドの解析ツリーをビルドします。|  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)
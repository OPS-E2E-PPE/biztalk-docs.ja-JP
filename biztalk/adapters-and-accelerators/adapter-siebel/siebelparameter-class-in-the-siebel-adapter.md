---
title: Siebel アダプターの SiebelParameter クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelParameter
- Data Provider for Siebel, SiebelParameter
- SiebelParameter, supported properties and methods
ms.assetid: 1dcb72c7-a470-4609-8aba-a5c8ad5f3ac9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4945b7c2dfb72286682b8afa396f882648c88118
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370623"
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelParameter クラス
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供、`DbParameter`特定のコマンドのパラメーターを指定する、ADO.NET クライアントを有効にする実装。 インスタンスを使用して、`System.Data.Common.DbCommand`のクラス、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、クライアント プログラムがのインスタンスを取得、`System.Data.Common.DbParameter`クラス。  

```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  

 または、次のアプローチを使用できます。  

```  

//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  

 `SiebelParameter`クラスから継承`DbParameter`します。  名前空間内に存在する`Microsoft.Data.SiebelClient`します。  

## <a name="supported-properties"></a>サポートされているプロパティ  
 `SiebelParameter`クラスは、次をサポート`DbParameter`*パブリック*プロパティ。  


|       名前        |   Get/Set   |                                                                                                            説明                                                                                                            |
|-------------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    **DbType**     | Get と Set |                                               パラメーターのデータ型。 参照してください[基本的な Siebel データ型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)します。                                               |
|   **[方向]**   | Get と Set | 次の値がサポートされています。<br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput` |
|  **IsNullable**   | Get と Set |                                                                               プロパティはサポートされていません、呼び出された場合、例外がスローされます。                                                                               |
| **ParameterName** | Get と Set |                                  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] ADO.NET クライアント パラメーター名を指定するには、このプロパティをサポートします。                                  |
|     **[値]**     | Get と Set |                                                    [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]文字列としてパラメーター値を表します。                                                    |

###  <a name="BKMK_Datatypes"></a> サポートされるデータ型  
 次の表に、単純な Siebel フィールドの種類を[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]をサポートしています。 カバレッジの詳細を参照してください。[基本的な Siebel データ型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)します。  

|Siebel のフィールドの種類|.NET Type|XML スキーマ型|  
|-----------------------|---------------|---------------------|  
|DTYPE_BOOL|ブール値|xsd:boolean|  
|DTYPE_CURRENCY|10 進数|xsd:decimal|  
|DTYPE_DATE|DateTime|xsd:dateTime|  
|DTYPE_DATETIME|DateTime|xsd:dateTime|  
|DTYPE_ UTCDATETIME|DateTime|xsd:dateTime|  
|DTYPE_ID|String|xsd:string|  
|DTYPE_INTEGER|Integer|xsd:int|  
|DTYPE_NOTE|String|xsd:string|  
|DTYPE_NUMBER|10 進数|xsd:decimal|  
|DTYPE_PHONE|String|xsd:string|  
|DTYPE_TEXT|String|xsd:string|  
|DTYPE_TIME|DateTime|xsd:dateTime|  

## <a name="supported-methods"></a>サポートされているメソッド  
 `SiebelParameter`クラスが内の特殊なメソッドをオーバーライドしていない`DbParameter`します。  

## <a name="see-also"></a>参照  
 [Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)
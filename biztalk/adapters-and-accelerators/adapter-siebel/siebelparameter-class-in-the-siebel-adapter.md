---
title: Siebel アダプターの SiebelParameter クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 27df4b207b23cd04f7d29a2a18ec4ab032836e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222490"
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelParameter クラス
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供、`DbParameter`実装を特定のコマンドのパラメーターを指定する ADO.NET クライアントを有効にします。 インスタンスを使用して、`System.Data.Common.DbCommand`のクラス、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、クライアント プログラムがのインスタンスを取得できます、`System.Data.Common.DbParameter`クラスです。  
  
```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  
  
 また、次のアプローチを使用できます。  
  
```  
  
//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  
  
 `SiebelParameter`クラスから継承`DbParameter`です。  名前空間内に存在する`Microsoft.Data.SiebelClient`です。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
 `SiebelParameter`クラスは、次をサポート`DbParameter`*パブリック*プロパティ。  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**DbType**|Get および Set|パラメーターのデータ型。 参照してください[Siebel の基本的なデータ型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)です。|  
|**方向**|Get および Set|次の値がサポートされています。<br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput`|  
|**IsNullable**|Get および Set|プロパティはサポートされていませんし、呼び出された場合、例外がスローされます。|  
|**パラメーター名**|Get および Set|[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]パラメーター名を指定する ADO.NET クライアントのこのプロパティをサポートします。|  
|**値**|Get および Set|[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]文字列としてのパラメーター値を表します。|  
  
###  <a name="BKMK_Datatypes"></a>サポートされるデータ型  
 次の表は、単純な Siebel フィールドの種類を[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]をサポートしています。 カバレッジの詳細を参照してください。 [Siebel の基本データ型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)です。  
  
|Siebel のフィールドの種類|.NET 型|XML スキーマの型|  
|-----------------------|---------------|---------------------|  
|DTYPE_BOOL|ブール値|xsd:boolean|  
|DTYPE_CURRENCY|Decimal|xsd:decimal|  
|DTYPE_DATE|DateTime|xsd:dateTime|  
|DTYPE_DATETIME|DateTime|xsd:dateTime|  
|DTYPE_ UTCDATETIME のフィールド|DateTime|xsd:dateTime|  
|DTYPE_ID|文字列|xsd:string|  
|DTYPE_INTEGER|Integer|xsd:int|  
|DTYPE_NOTE|文字列|xsd:string|  
|DTYPE_NUMBER|Decimal|xsd:decimal|  
|DTYPE_PHONE|文字列|xsd:string|  
|DTYPE_TEXT|文字列|xsd:string|  
|DTYPE_TIME|DateTime|xsd:dateTime|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
 `SiebelParameter`クラスがで特別なメソッドをオーバーライドしていない`DbParameter`です。  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)
---
title: メッセージのスキーマのレコードの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, message schemas for
- RECORD types, support for
ms.assetid: 637c42f2-eed0-4941-a6cd-7e03d01088b8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aae82fad713fd9a2789e165845958421e1213402
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996923"
---
# <a name="message-schemas-for-record-types"></a>レコードの種類のメッセージ スキーマ
Oracle レコードの種類のいずれかで構成されている PL/SQL データ型が構造化されたより単純型または構造化されたデータベース型。 レコードの種類は、階層データを送受信する PL/SQL ストアド プロシージャおよび関数で主に使用されます。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]次のように、レコードの種類をサポートしています。  
  
- レコードの種類は複合型として表示されます。  
  
- レコードの種類には、入れ子になった (レコードのレコード) を指定できます。  
  
- レコードの種類は、ストアド プロシージャおよび関数では、テーブル %rowtype パラメーターとして宣言できます。  
  
- レコードの種類は PL/SQL パッケージ; 内のレコードの型パラメーターとして宣言することができます。たとえば、`TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`します。  
  
  > [!NOTE]
  >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。  
  
  レコード型のパラメーターを使用すると、ストアド プロシージャまたは関数でその操作の名前空間で修飾されます。 次の XML は、メッセージのレコードの種類の構造を示しています。  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 [REC_PARAM_NAME] は、レコードのパラメーターの名前です。  
  
 [<] は、レコードの種類のフィールドの名前です。  
  
 [OPERATION_NAMESPACE] は、ストアド プロシージャまたはレコードのパラメーターが使用されている関数の名前空間です。  
  
 次の XML は、入れ子になったレコードの種類フィールドを持つレコード型のパラメーターの構造を示しています。  
  
```  
<[REC_PARAM_NAME]>    
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  <[REC_PARAM_NAME2]>  
    <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
    <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME2]>  
    …  
  </[REC_PARAM_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
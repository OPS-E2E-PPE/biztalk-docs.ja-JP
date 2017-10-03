---
title: "メッセージ スキーマのレコードの種類 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RECORD types, message schemas for
- RECORD types, support for
ms.assetid: 637c42f2-eed0-4941-a6cd-7e03d01088b8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9022274041e06ad8ccc3f5243715d44d2b64282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-record-types"></a>レコードの種類のメッセージ スキーマ
Oracle レコードの種類は、いずれかで構成される構造化の PL/SQL データ型またはより単純型または構造化されたデータベースの種類です。 レコードの種類は、階層データを送受信する PL/SQL ストアド プロシージャおよび関数で、主に使用されます。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]次の方法でレコードの種類をサポートしています。  
  
-   レコードの種類は、複合型として表示されます。  
  
-   レコードの種類は、入れ子になった (レコードのレコード) を指定できます。  
  
-   レコードの種類は、ストアド プロシージャおよび関数では、テーブル %rowtype パラメーターとして宣言できます。  
  
-   レコードの種類は PL/SQL パッケージ内のレコードの型パラメーターとして宣言することができます。たとえば、`TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`です。  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。  
  
 レコード型のパラメーターは、ストアド プロシージャまたは関数で使用する場合は、その操作の名前空間で修飾されます。 次の XML では、メッセージのレコードの種類の構造を示しています。  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 [REC_PARAM_NAME] は、レコード パラメーターの名前です。  
  
 [<] は、レコードの種類のフィールドの名前です。  
  
 [OPERATION_NAMESPACE] は、ストアド プロシージャまたはレコード パラメーターが使用されている関数の名前空間です。  
  
 次の XML は、入れ子になったレコードの種類フィールドを持つレコード型パラメーターの構造を示しています。  
  
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
 [メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
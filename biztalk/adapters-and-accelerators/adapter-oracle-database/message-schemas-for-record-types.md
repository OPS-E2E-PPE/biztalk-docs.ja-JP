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
# <a name="message-schemas-for-record-types"></a><span data-ttu-id="633b2-102">レコードの種類のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="633b2-102">Message Schemas for RECORD Types</span></span>
<span data-ttu-id="633b2-103">Oracle レコードの種類は、いずれかで構成される構造化の PL/SQL データ型またはより単純型または構造化されたデータベースの種類です。</span><span class="sxs-lookup"><span data-stu-id="633b2-103">Oracle RECORD types are structured PL/SQL data types that consist of one or more simple or structured database types.</span></span> <span data-ttu-id="633b2-104">レコードの種類は、階層データを送受信する PL/SQL ストアド プロシージャおよび関数で、主に使用されます。</span><span class="sxs-lookup"><span data-stu-id="633b2-104">RECORD types are primarily used in PL/SQL stored procedures and functions to send and receive hierarchical data.</span></span>  
  
 <span data-ttu-id="633b2-105">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]次の方法でレコードの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="633b2-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports RECORD types in the following manner:</span></span>  
  
-   <span data-ttu-id="633b2-106">レコードの種類は、複合型として表示されます。</span><span class="sxs-lookup"><span data-stu-id="633b2-106">RECORD types are surfaced as complex types.</span></span>  
  
-   <span data-ttu-id="633b2-107">レコードの種類は、入れ子になった (レコードのレコード) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="633b2-107">RECORD types can be nested (record in a record).</span></span>  
  
-   <span data-ttu-id="633b2-108">レコードの種類は、ストアド プロシージャおよび関数では、テーブル %rowtype パラメーターとして宣言できます。</span><span class="sxs-lookup"><span data-stu-id="633b2-108">RECORD types can be declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
-   <span data-ttu-id="633b2-109">レコードの種類は PL/SQL パッケージ内のレコードの型パラメーターとして宣言することができます。たとえば、`TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`です。</span><span class="sxs-lookup"><span data-stu-id="633b2-109">RECORD types can be declared as TYPE of RECORD parameters in PL/SQL packages; for example, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="633b2-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="633b2-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
 <span data-ttu-id="633b2-111">レコード型のパラメーターは、ストアド プロシージャまたは関数で使用する場合は、その操作の名前空間で修飾されます。</span><span class="sxs-lookup"><span data-stu-id="633b2-111">When a RECORD type parameter is used in a stored procedure or a function, it is qualified with the namespace of that operation.</span></span> <span data-ttu-id="633b2-112">次の XML では、メッセージのレコードの種類の構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="633b2-112">The following XML shows the structure of a RECORD type in a message:</span></span>  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 <span data-ttu-id="633b2-113">[REC_PARAM_NAME] は、レコード パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="633b2-113">[REC_PARAM_NAME] is the name of the RECORD parameter.</span></span>  
  
 <span data-ttu-id="633b2-114">[<] は、レコードの種類のフィールドの名前です。</span><span class="sxs-lookup"><span data-stu-id="633b2-114">[FIELD_NAME] is the name of a field in the RECORD type.</span></span>  
  
 <span data-ttu-id="633b2-115">[OPERATION_NAMESPACE] は、ストアド プロシージャまたはレコード パラメーターが使用されている関数の名前空間です。</span><span class="sxs-lookup"><span data-stu-id="633b2-115">[OPERATION_NAMESPACE] is the namespace of the stored procedure or function in which the RECORD parameter is being used.</span></span>  
  
 <span data-ttu-id="633b2-116">次の XML は、入れ子になったレコードの種類フィールドを持つレコード型パラメーターの構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="633b2-116">The following XML shows the structure of a RECORD type parameter with a nested RECORD type field:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="633b2-117">参照</span><span class="sxs-lookup"><span data-stu-id="633b2-117">See Also</span></span>  
 [<span data-ttu-id="633b2-118">メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="633b2-118">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
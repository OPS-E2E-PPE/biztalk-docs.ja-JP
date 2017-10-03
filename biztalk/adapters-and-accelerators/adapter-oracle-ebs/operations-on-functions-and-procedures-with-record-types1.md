---
title: "関数名とレコード Types1 プロシージャに対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afc1c84f-2e36-493c-9ea8-4bc2248331db
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43974d1c392a357b9781ff7f6fae5286e282513a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a>関数およびレコードの種類のプロシージャでの操作
Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]複雑な XML 型としてレコードの種類を表示します。 

## <a name="supported-record-types"></a>サポートされているレコードの種類
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]次の種類のレコードの種類をサポートしています。  
  
-   ストアド プロシージャおよび関数では、テーブル %rowtype パラメーターとして宣言されているレコードの種類。  
  
-   PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類。 たとえば、型 rec_type1 は RECORD(name varchar2(100), age number(3));  
  
-   入れ子になったレコードを含むレコードの種類。  
  
-   レコードに表示される型として、OUT、またはプロシージャまたは関数への OUT パラメーターです。  
  
-   関数の戻り値は、レコードの種類。  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
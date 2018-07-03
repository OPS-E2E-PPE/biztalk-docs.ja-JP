---
title: レコード Types1 で関数とプロシージャに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afc1c84f-2e36-493c-9ea8-4bc2248331db
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7d4f392e863dd8966f5c011abfd6e602f2514c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006435"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a>関数とレコードの種類を使用したプロシージャに対する操作
Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの複雑な XML 型としてレコードの種類。 

## <a name="supported-record-types"></a>サポートされているレコードの種類
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]次の種類のレコードの種類をサポートしています。  
  
- ストアド プロシージャおよび関数でテーブル %rowtype パラメーターとして宣言されているレコードの種類。  
  
- PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類。 たとえば、rec_type1 は RECORD(name varchar2(100), age number(3)); を入力します。  
  
- 入れ子になったレコードを含むレコードの種類。  
  
- OUT、IN として表示されるレコードの種類またはプロシージャまたは関数への OUT パラメーター。  
  
- 関数の戻り値であるレコードの種類。  
  
  > [!NOTE]
  >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
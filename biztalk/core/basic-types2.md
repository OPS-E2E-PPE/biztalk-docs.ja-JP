---
title: "基本的な Types2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e5c47d8760e9743ec11a62598581d9d20b3e53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="basic-types"></a>基本型
Microsoft BizTalk Adapter for JD Edwards EnterpriseOne では、JD Edwards EnterpriseOne のビジネス関数にのみアクセスできます。 ビジネス関数メタデータは、ビジネス関数インターフェイスをとおして読み取られ、ビジネス関数の一覧および関連するデータ構造の検索に使用されます。 メタデータは、すべてのビジネス関数メソッドのすべてのケースで厳密に型指定されます。  
  
 すべてのビジネス関数メソッドがある同じ呼び出し規約: 派生は、システムは、3 つのパラメーターとデータ構造体へのポインター。 次の表に、ビジネス関数のデータ型がどのように表されるかを示します。  
  
|JD Edwards EnterpriseOne のデータ型|Description|WDSL 変換|  
|----------------------------------------|-----------------|---------------------|  
|char|文字の文字列。|xsd:string の 1|  
|int|短整数。|xsd:short|  
|long|長整数。|xsd:short|  
|文字列|参照してください[文字列値の処理](../core/handling-string-values2.md)です。|xsd:string|  
|JDEDATE|日付の特殊な実装。|xsd:date|  
|MATH_NUMERIC|浮動小数点数の特殊な実装 (通貨の値を含む)。|32 の xsd:string|  
|Byte|単一の符号なし文字。|xsd:string の 1|  
|JDEUTIME|日付と時刻の両方のコンポーネントが含まれます。<br /><br /> データ型はすべての日付と時刻を格納し、日付と時刻の計算をすべて協定世界時 (UTC) で実行します。|xsd:dateTime|  
  
## <a name="see-also"></a>参照  
 [MATH_NUMERIC 型の使用](../core/using-the-math-numeric-type1.md)   
 [文字列値の処理](../core/handling-string-values2.md)   
 [付録 b: データ型](../core/appendix-b-data-types.md)
---
title: 基本的な Types2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51caed0e57b6b1869fb5e921b5a660293d71840d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530501"
---
# <a name="basic-types"></a>基本的な型
Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne では、JD Edwards EnterpriseOne のビジネス関数にのみアクセスを提供します。 ビジネス関数メタデータは読み取り専用ビジネス関数のインターフェイスを使用してビジネス関数の一覧を検索するために使用し、関連するデータ構造。 メタデータはすべてのビジネス関数メソッドのすべてのケースで厳密に型指定します。  
  
 すべてのビジネス関数メソッドと同じ呼び出し規約がある: システムから派生している 3 つのパラメーターとデータ構造体へのポインター。 次の表では、ビジネス関数のデータ型の表現方法を示します。  
  
|JD Edwards EnterpriseOne のデータ型|説明|WDSL 変換|  
|----------------------------------------|-----------------|---------------------|  
|char|文字の文字列。|xsd:string の 1|  
|ssNoversion|短整数。|xsd:short|  
|long|長整数。|xsd:short|  
|String|参照してください[文字列値を処理する](../core/handling-string-values2.md)します。|xsd:string|  
|JDEDATE|日付の特殊な実装。|xsd:date|  
|MATH_NUMERIC|浮動小数点数、通貨値などの特殊な実装。|32 の xsd:string|  
|バイト|1 つの符号なし文字。|xsd:string の 1|  
|JDEUTIME|日付と時刻の両方のコンポーネントが含まれます。<br /><br /> データ型は、すべての日付を保存/時刻し、世界協定時刻 (UTC) ですべての日付/時刻計算を実行します。|xsd:dateTime|  
  
## <a name="see-also"></a>参照  
 [MATH_NUMERIC 型の使用](../core/using-the-math-numeric-type1.md)   
 [文字列値の処理](../core/handling-string-values2.md)   
 [付録 b:データ型](../core/appendix-b-data-types.md)
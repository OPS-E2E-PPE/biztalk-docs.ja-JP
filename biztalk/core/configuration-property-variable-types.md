---
title: 構成変数の型のプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, properties
- binding files, properties
- binding files, data types
- adapters, data types
ms.assetid: 703219ce-e275-4a07-a2ad-28010d8363e6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ccb07ff8884b4b874bf1da954a5a0ca22b84c2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356462"
---
# <a name="configuration-property-variable-types"></a>構成変数の型のプロパティ
バインド ファイルの TransportTypeData\CustomProps ノードのアダプター構成プロパティは、.NET Framework の VarEnum 列挙で使用できるデータ型に従います。 該当するデータ型を以下の表に示します。  
  
|メンバー名|説明|値|  
|-----------------|-----------------|-----------|  
|VT_EMPTY|値が指定されなかったことを示します。|0|  
|VT_NULL|Null 値を示します。これは、SQL における Null 値に相当します。|1|  
|VT_I2|短整数を示します。|2|  
|VT_I4|長整数を示します。|3|  
|VT_R4|浮動小数点値を示します。|4|  
|VT_R8|double 値を示します。|5|  
|VT_CY|通貨値を示します。|6|  
|VT_DATE|DATE 値を示します。|7|  
|VT_BSTR|BSTR 文字列を示します。|8|  
|VT_DISPATCH|IDispatch ポインターを示します。|9|  
|VT_ERROR|SCODE を示します。|10|  
|VT_BOOL|ブール値を示します。|11|  
|VT_VARIANT|VARIANT far ポインターを示します。|12|  
|VT_UNKNOWN|IUnknown ポインターを示します。|13|  
|VT_DECIMAL|10 進数値を示します。|14|  
|VT_I1|char 値を示します。|16|  
|VT_UI1|バイト値を示します。|17|  
|VT_UI2|符号なしの short を示します。|18|  
|VT_UI4|符号なしの long を示します。|19|  
|VT_I8|64 ビット整数を示します。|20|  
|VT_UI8|64 ビット符号なし整数を示します。|21|  
|VT_CLSID|クラス ID を示します。|72|  
|VT_ARRAY|SAFEARRAY ポインターを示します。|8192|  
|VT_BYREF|値が参照であることを示します。|16384|
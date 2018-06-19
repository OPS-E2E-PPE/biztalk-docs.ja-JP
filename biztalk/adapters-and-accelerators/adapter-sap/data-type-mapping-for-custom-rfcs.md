---
title: データ型マッピング カスタム Rfc の |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom RFCs, data type mapping
ms.assetid: 33539a5a-bdfc-423f-8026-436f69a20c70
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cac254734a35658e3aa635b086f765e8f06494a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217418"
---
# <a name="data-type-mapping-for-custom-rfcs"></a>カスタム Rfc のデータ型マッピング
次の表は、SAP データ型との Z_EXTRACT_DATA_OO RFC .NET データ型にマップする方法に関する情報を提供します。 このカスタム RFC を使って、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
> [!NOTE]
>  によって使用される、Z_EXECUTE_SAP_QUERY の[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]EXECQUERY コマンドを実行するには、すべての SAP データ型が .NET 文字列型に変換されます。  
  
|SAP データ型|.NET データ型|  
|-------------------|--------------------|  
|ACCP|-Int32<br />、場合は文字列、 **disabledatavalidation**オプションは、SELECT ステートメントまたは EXEC ステートメントで設定します。|  
|CHAR|文字列|  
|CLNT|文字列|  
|CUKY|文字列|  
|現在|Decimal、または有効桁数 28 以下<br /><br /> 文字列の場合は、有効桁数 28 桁を超える|  
|DATS|-DateTime<br />、場合は文字列、 **disabledatavalidation**オプションは、SELECT ステートメントまたは EXEC ステートメントで設定します。|  
|DEC|Decimal|  
|FLTP|Double|  
|INT1|Byte|  
|INT2|Int16|  
|INT4|Int32|  
|LANG|文字列|  
|NUMC|、フィールドの場合 Int32、9 の長さ以下<br />、フィールドの場合 Int64、長さ 9 よりも大きい 19 以下<br />文字列、19 より大きい場合<br />、場合は文字列、 **disabledatavalidation**オプションは、SELECT ステートメントまたは EXEC ステートメントで設定します。|  
|PREC|Int16|  
|QUAN|Decimal|  
|RAW|Byte[]|  
|RSTR|Byte[]|  
|SSTR|文字列|  
|STRG|文字列|  
|TIMS|-TimeSpan<br />、場合は文字列、 **disabledatavalidation**オプションは、SELECT ステートメントまたは EXEC ステートメントで設定します。|  
|単位|文字列|  
|LCHR|文字列|  
|LRAW|Byte[]|  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)
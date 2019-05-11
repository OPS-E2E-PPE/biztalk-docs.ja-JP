---
title: カスタム Rfc のデータ型マッピング |Microsoft Docs
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
ms.openlocfilehash: 0d6934847a5c5a9482a9c4f1dc8026c50aec6295
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373551"
---
# <a name="data-type-mapping-for-custom-rfcs"></a>カスタム Rfc のデータ型マッピング
次の表は、SAP のデータ型および Z_EXTRACT_DATA_OO RFC の .NET データ型にマップする方法についての情報を提供します。 このカスタム RFC を使って、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。  
  
> [!NOTE]
>  によって使用されるため、Z_EXECUTE_SAP_QUERY、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] EXECQUERY コマンドを実行するすべての SAP のデータ型は .NET の文字列型に変換されます。  
  
|SAP のデータ型|.NET データ型|  
|-------------------|--------------------|  
|ACCP|-Int32<br />、場合は文字列、 **disabledatavalidation** SELECT または EXEC ステートメントでオプションを設定します。|  
|CHAR|String|  
|CLNT|String|  
|CUKY|String|  
|CURR|場合、28 に等しいかそれよりも有効桁数が 10 進数<br /><br /> 文字列の場合は、有効桁数が 28 より大きい|  
|DATS|-DateTime<br />、場合は文字列、 **disabledatavalidation** SELECT または EXEC ステートメントでオプションを設定します。|  
|12 月|10 進数|  
|FLTP|Double|  
|INT1|バイト|  
|INT2|Int16|  
|INT4|Int32|  
|LANG|String|  
|NUMC|、フィールドの場合 Int32、9 の長さ以下<br />、フィールドの場合 Int64、長さが 9 よりも大きい 19 以下<br />、19 より大きい場合は文字列、<br />、場合は文字列、 **disabledatavalidation** SELECT または EXEC ステートメントでオプションを設定します。|  
|PREC|Int16|  
|QUAN|10 進数|  
|RAW|Byte[]|  
|RSTR|Byte[]|  
|SSTR|String|  
|STRG|String|  
|TIMS|間隔<br />、場合は文字列、 **disabledatavalidation** SELECT または EXEC ステートメントでオプションを設定します。|  
|ユニット|String|  
|LCHR|String|  
|LRAW|Byte[]|  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)
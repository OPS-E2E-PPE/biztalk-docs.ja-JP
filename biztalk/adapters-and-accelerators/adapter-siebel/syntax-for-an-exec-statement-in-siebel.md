---
title: Siebel の EXEC ステートメントの構文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094161f866b12f656dd42e3eddbaba7c56a6ff01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370487"
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a>Siebel の EXEC ステートメントの構文
使用して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、ADO.NET クライアントは、EXEC 操作を実行もできる、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 EXEC ステートメントの構文です。  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 上記の構文で`\<value 1..n\>`無名のパラメーターのセットを表します。 これらは、ハード コーディングされた値です。 通常、パラメーターを表します。  INOUT パラメーターを表すこともできます。 ただし、INOUT パラメーターのハードコード値を使用する場合、パラメーターに関連付けられている出力値を取得できません EXEC ステートメントの実行後。  
  
 `@parameter 1..n`構文は、IN、INOUT、可能性がある名前付きパラメーターのパラメーターまたは OUT パラメーターのセットを表します。 出力パラメーターの後に、**出力**キーワード。  
  
> [!NOTE]
>  **出力**パラメーター OUT および INOUT パラメーターではなくはキーワードを使用する必要がありますはのみです。  
  
 パラメーター値をインラインを指定するには、使用、`@parameter 1..n = <value>`構文。  
  
 すべてのパラメーターは、コンマ区切りにする必要があります。  
  
 EXEC ステートメントの例を次に示します。  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  すべてのパラメーター名 (など`@In`前の例)、Siebel ビジネス サービス メソッドに対応する引数名に一致する必要があります。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for Siebel eBusiness Applications を使用する](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
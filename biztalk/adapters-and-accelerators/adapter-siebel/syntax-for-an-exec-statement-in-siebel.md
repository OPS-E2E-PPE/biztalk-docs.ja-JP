---
title: "Siebel の EXEC ステートメントの構文 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d18481b206b1be7e0062762c1844305fc36e10f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a>Siebel の EXEC ステートメントの構文
使用して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、ADO.NET クライアントも EXEC 操作に対して行える、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 EXEC ステートメントの構文です。  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
\<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 上記の構文で`\<value 1..n>`無名のパラメーターのセットを表します。 これらは、ハード コーディングされた値です。 これらは、通常、パラメーターで表します。  それらを表す場合も INOUT パラメーター。 ただし、INOUT パラメーターのハードコード値を使用する場合そのパラメーターに関連付けられている出力値を取得できません EXEC ステートメントの実行後。  
  
 `@parameter 1..n`構文は、IN、INOUT は、名前付きパラメーターのパラメーターまたは OUT パラメーター セットを表します。 出力パラメーターの後に、**出力**キーワード。  
  
> [!NOTE]
>  **出力**パラメーター OUT および INOUT パラメーターではなくはキーワードを使用する必要がありますはのみです。  
  
 パラメーターの値を行内を指定するには、使用、`@parameter 1..n = <value>`構文です。  
  
 すべてのパラメーターは、コンマで区切られたにする必要があります。  
  
 EXEC ステートメントの例を次に示します。  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  パラメーター名 (など`@In`前の例で)、Siebel ビジネス サービス メソッドに対応する引数の名前に一致する必要があります。  
  
## <a name="see-also"></a>参照  
 [Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
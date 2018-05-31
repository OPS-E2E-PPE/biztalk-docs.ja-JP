---
title: '手順 4: 作成のサンプル XML BeginDoc1 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e494b4b2-4c83-4293-8ae8-acae29018e7f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a48a4ee378560ad2d0360445e3fb732bb46e79f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276730"
---
# <a name="step-4-create-a-sample-xml-begindoc"></a>手順 4: サンプル XML BeginDoc を作成します。
以下のコードを XML ファイルに保存します。 テストで、この例のステップを使用し、コード例で選択されている J.D. Edwards OneWorld オブジェクトの選択 [jde://csales/b4200310] を入力フォルダーと、指定した出力フォルダー (EndDocOut ポートにバインドされているフォルダー) を含んでいるにこれを削除することができます。  
  
> [!NOTE]
>  一部の値は、J.D. Edwards OneWorld サーバーの場合は、たとえば、値 szCMComputerID に設定されています。  
  
```  
<ns0:F4211FSBeginDoc xmlns:ns0="http://schemas.microsoft.com/  
   [JDE://CSALES/B4200310]">  
   <ns0:mnCMJobNumber></ns0:mnCMJobNumber>  
   <ns0:cCMDocAction>A</ns0:cCMDocAction>  
   <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
   <ns0:szCMComputerID>BVISION01</ns0:szCMComputerID>  
   <ns0:cCMUpdateWriteToWF>2</ns0:cCMUpdateWriteToWF>  
   <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
   <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
   <ns0:szOrderType>SO</ns0:szOrderType>  
   <ns0:szBusinessUnit>M30</ns0:szBusinessUnit>  
   <ns0:szOriginalOrderCo></ns0:szOriginalOrderCo>  
   <ns0:szOriginalOrderNo></ns0:szOriginalOrderNo>  
   <ns0:szOriginalOrderType></ns0:szOriginalOrderType>  
   <ns0:mnAddressNumber>1001</ns0:mnAddressNumber>  
   <ns0:jdOrderDate></ns0:jdOrderDate>  
   <ns0:szReference></ns0:szReference>  
   <ns0:cApplyFreightYN>Y</ns0:cApplyFreightYN>  
   <ns0:szCurrencyCode></ns0:szCurrencyCode>  
   <ns0:cWKSourceOfData></ns0:cWKSourceOfData>  
   <ns0:cWKProcMode></ns0:cWKProcMode>  
   <ns0:mnWKSuppressProcess>0</ns0:mnWKSuppressProcess>  
   <ns0:cRetrieveOrderNo>1</ns0:cRetrieveOrderNo>  
   <ns0:nSourceOfOrder>0</ns0:nSourceOfOrder>  
</ns0:F4211FSBeginDoc>  
```  
  
## <a name="see-also"></a>参照  
 [手順 1: スキーマ DLL を参照します。](../core/step-1-reference-the-schema-dll2.md)   
 [手順 2: オーケストレーションを作成します。](../core/step-2-create-the-orchestration1.md)   
 [手順 3: が完了し、プロジェクトを実行](../core/step-3-complete-and-run-the-project2.md)
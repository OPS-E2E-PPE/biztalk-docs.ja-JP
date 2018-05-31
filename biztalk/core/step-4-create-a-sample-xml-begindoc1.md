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
# <a name="step-4-create-a-sample-xml-begindoc"></a><span data-ttu-id="c18d7-102">手順 4: サンプル XML BeginDoc を作成します。</span><span class="sxs-lookup"><span data-stu-id="c18d7-102">Step 4: Create a Sample XML BeginDoc</span></span>
<span data-ttu-id="c18d7-103">以下のコードを XML ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="c18d7-103">Save the following into an XML file.</span></span> <span data-ttu-id="c18d7-104">テストで、この例のステップを使用し、コード例で選択されている J.D.</span><span class="sxs-lookup"><span data-stu-id="c18d7-104">If your test uses the steps in this example, and uses the example's J.D.</span></span> <span data-ttu-id="c18d7-105">Edwards OneWorld オブジェクトの選択 [jde://csales/b4200310] を入力フォルダーと、指定した出力フォルダー (EndDocOut ポートにバインドされているフォルダー) を含んでいるにこれを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c18d7-105">Edwards OneWorld object selection, [JDE://CSALES/B4200310], you can drop this into the Input folder and what it come out the designated Out folder (the folder bound to the EndDocOut port).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c18d7-106">一部の値は、J.D.</span><span class="sxs-lookup"><span data-stu-id="c18d7-106">You will have to modify some of the values to point to your J.D.</span></span> <span data-ttu-id="c18d7-107">Edwards OneWorld サーバーの場合は、たとえば、値 szCMComputerID に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c18d7-107">Edwards OneWorld server, for example, the value set in szCMComputerID.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c18d7-108">参照</span><span class="sxs-lookup"><span data-stu-id="c18d7-108">See Also</span></span>  
 <span data-ttu-id="c18d7-109">[手順 1: スキーマ DLL を参照します。](../core/step-1-reference-the-schema-dll2.md) </span><span class="sxs-lookup"><span data-stu-id="c18d7-109">[Step 1: Reference the Schema DLL](../core/step-1-reference-the-schema-dll2.md) </span></span>  
 <span data-ttu-id="c18d7-110">[手順 2: オーケストレーションを作成します。](../core/step-2-create-the-orchestration1.md) </span><span class="sxs-lookup"><span data-stu-id="c18d7-110">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration1.md) </span></span>  
 [<span data-ttu-id="c18d7-111">手順 3: が完了し、プロジェクトを実行</span><span class="sxs-lookup"><span data-stu-id="c18d7-111">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project2.md)
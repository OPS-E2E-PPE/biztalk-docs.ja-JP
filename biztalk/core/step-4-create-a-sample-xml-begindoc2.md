---
title: 手順 4:サンプルの XML BeginDoc2 の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cdda509-085f-4485-b488-c045d589ee96
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eea7067581391404fbb9c61afc5c340ec26d05e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392526"
---
# <a name="step-4-create-a-sample-xml-begindoc"></a><span data-ttu-id="de7f3-102">手順 4:サンプル XML BeginDoc を作成します。</span><span class="sxs-lookup"><span data-stu-id="de7f3-102">Step 4: Create a Sample XML BeginDoc</span></span>
<span data-ttu-id="de7f3-103">次のコードは、XML ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="de7f3-103">Save the following code into an XML file.</span></span> <span data-ttu-id="de7f3-104">場合は、テスト、この例では、手順を使用し、例の j. d.</span><span class="sxs-lookup"><span data-stu-id="de7f3-104">If your test uses the steps in this example, and uses the example's J.D.</span></span> <span data-ttu-id="de7f3-105">Edwards EnterpriseOne オブジェクトの選択 [jde://csales/b4200310] を入力フォルダーと指定した出力フォルダー (EndDocOut ポートにバインドされているフォルダー) には何にこれをドロップすることができます。</span><span class="sxs-lookup"><span data-stu-id="de7f3-105">Edwards EnterpriseOne object selection, [JDE://CSALES/B4200310], you can drop this into the Input folder and what it come out the designated Out folder (the folder bound to the EndDocOut port).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de7f3-106">J. d. を指す値の一部を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de7f3-106">You will have to modify some of the values to point to your J.D.</span></span> <span data-ttu-id="de7f3-107">Edwards EnterpriseOne サーバー、たとえば、値設定 szCMComputerID にします。</span><span class="sxs-lookup"><span data-stu-id="de7f3-107">Edwards EnterpriseOne server, for example, the value set in szCMComputerID.</span></span>  
  
```  
<ns0:F4211FSBeginDoc xmlns:ns0="http://schemas.microsoft.com/  
      [JDE://CSALES/B4200310]">  
   <ns0:mnCMJobNumber></ns0:mnCMJobNumber>  
   <ns0:cCMDocAction>A</ns0:cCMDocAction>  
   <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
   <ns0:szCMComputerID>BVISION02</ns0:szCMComputerID>  
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
  
## <a name="see-also"></a><span data-ttu-id="de7f3-108">参照</span><span class="sxs-lookup"><span data-stu-id="de7f3-108">See Also</span></span>  
 <span data-ttu-id="de7f3-109">[ステップ 1: スキーマ DLL を参照します。](../core/step-1-reference-the-schema-dll1.md) </span><span class="sxs-lookup"><span data-stu-id="de7f3-109">[Step 1: Reference the Schema DLL](../core/step-1-reference-the-schema-dll1.md) </span></span>  
 <span data-ttu-id="de7f3-110">[手順 2:オーケストレーションを作成します。](../core/step-2-create-the-orchestration2.md) </span><span class="sxs-lookup"><span data-stu-id="de7f3-110">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration2.md) </span></span>  
 [<span data-ttu-id="de7f3-111">ステップ 3:完了して、プロジェクトを実行</span><span class="sxs-lookup"><span data-stu-id="de7f3-111">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project1.md)
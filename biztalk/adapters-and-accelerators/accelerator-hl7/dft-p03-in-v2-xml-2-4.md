---
title: V2 の DFT_P03 します。2.4 XML |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DFT_P03 schema
ms.assetid: 6735685a-2aac-4481-87d1-202b2178aeb5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5e03c35c7ded579a90908c80202ec459fb7cba4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255472"
---
# <a name="dftp03-in-v2xml-24"></a><span data-ttu-id="dfdd1-102">V2 の DFT_P03 します。2.4 XML</span><span class="sxs-lookup"><span data-stu-id="dfdd1-102">DFT_P03 in V2.XML 2.4</span></span>
<span data-ttu-id="dfdd1-103">V2 での DFT_P03 スキーマでは、次のコードを手動で変更する必要があります。Update2XMLSchema ツールの実行後の XML 2.4:</span><span class="sxs-lookup"><span data-stu-id="dfdd1-103">You must manually change the following code in the DFT_P03 schema in V2.XML 2.4 after running the Update2XMLSchema tool:</span></span>  
  
```  
<xsd:element ref="ROL" minOccurs="0" maxOccurs="unbounded" />  
<xsd:element ref="PV1" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="PV2" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="ROL" minOccurs="0" maxOccurs="unbounded" />  
```  
  
 <span data-ttu-id="dfdd1-104">複数回出現によるあいまいさを解決するために、次に、上記のコードを置き換える必要があります、 **ROL**要素の定義。</span><span class="sxs-lookup"><span data-stu-id="dfdd1-104">You must replace the above code with the following, in order to fix the ambiguity caused by multiple occurrences of the **ROL** element definition:</span></span>  
  
```  
<xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
  <xsd:choice minOccurs="0" maxOccurs="1">  
    <xsd:sequence>  
      <xsd:element minOccurs="1" maxOccurs="1" ref="PV1" />  
      <xsd:element minOccurs="0" maxOccurs="1" ref="PV2" />  
      <xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
    </xsd:sequence>  
    <xsd:sequence>  
      <xsd:element minOccurs="1" maxOccurs="1" ref="PV2" />  
      <xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
    </xsd:sequence>  
  </xsd:choice>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfdd1-105">参照</span><span class="sxs-lookup"><span data-stu-id="dfdd1-105">See Also</span></span>  
 <span data-ttu-id="dfdd1-106">[必要な手動の更新プログラム](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) </span><span class="sxs-lookup"><span data-stu-id="dfdd1-106">[Required Manual Updates](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) </span></span>  
 [<span data-ttu-id="dfdd1-107">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="dfdd1-107">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)
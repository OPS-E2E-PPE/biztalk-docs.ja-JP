---
title: V2 の REF_I12 します。2.4 XML |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF_I12 schema
ms.assetid: 95f40b75-a176-4fc6-b9ad-65721d456ea4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2fdd92400754a22e92f5207bdfbc1c0703d3c83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289947"
---
# <a name="refi12-in-v2xml-24"></a>V2 の REF_I12 します。2.4 XML
V2 での REF_I12 スキーマでは、次のコードを手動で変更する必要があります。Update2XMLSchema ツールの実行後の XML 2.4:  
  
```  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
```  
  
 複数回出現によるあいまいさを解決するために、次に、上記のコードを置き換える必要があります、 **REF**要素の定義。  
  
```  
<xsd:element minOccurs="0" maxOccurs="2" ref="REF_I12.PATIENT_VISIT" />  
```  
  
## <a name="see-also"></a>参照  
 [必要な手動の更新プログラム](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)   
 [ユーティリティ](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)
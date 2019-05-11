---
title: 未宣言のカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c5d31c7803eaa8fe0f8afeb6ed7c534f70233db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286420"
---
# <a name="undeclared-customizations"></a>未宣言のカスタマイズ
形式またはデータの性質を定義することがなく、メッセージにデータを追加できます。 未宣言の Z セグメントを使用してこれを行います。 未宣言の Z セグメントは、メッセージの最後の予期しないインスタンスです。 パーサー/XML 検証では、セグメントは検証されません。 任意のスキーマでは定義されません。 Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セグメントをバイナリ ラージ オブジェクト (BLOB) として扱われます。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 3 つの部分のメッセージの 3 番目の部分として宣言されていない経由の Z セグメントのデータを渡します。 3 つの部分は、ヘッダー、本文、および Z の一部とも呼ばれる、宣言されていない Z セグメントです。 文字"Z"、たとえば、"ZPD"カスタム患者の人口統計については、セグメント ID の先頭では、Z の一部を識別します。  
  
## <a name="see-also"></a>参照  
 [宣言済みのカスタマイズ](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)   
 [Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
---
title: "宣言されていないカスタマイズ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f688e4cf6a4bbb55243d9f5f6f60e144bad862
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="undeclared-customizations"></a>宣言されていないカスタマイズ
形式またはデータの特性を定義することがなく、メッセージにデータを追加できます。 宣言されていない Z セグメントを使用してこれを行います。 宣言されていない Z セグメントは、メッセージの最後に予期しないインスタンスです。 パーサー/XML 検証では、セグメントは検証しません。 任意のスキーマで定義されていません。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セグメントをバイナリ ラージ オブジェクト (BLOB) として扱われます。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]3 つの部分のメッセージの 3 番目の部分としてを通じて Z 宣言されていないデータのセグメントを渡します。 3 つの部分は、ヘッダー、本文、および宣言されていない Z セグメント、Z の一部とも呼ばれます。 セグメント ID、文字で始まる"Z"、たとえば、"ZPD"カスタム患者人口統計については、Z の一部を識別します。  
  
## <a name="see-also"></a>参照  
 [宣言のカスタマイズ](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)   
 [Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
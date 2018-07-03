---
title: データの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, messages
- messages, data types
ms.assetid: 7a758289-1629-48a0-843d-6f6773bd5ba6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7b8d75be35be01e9c961d6bd054dcaed6d3aee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984675"
---
# <a name="data-types"></a>データ型
データ型の仕様では、HL7 標準の複雑さをパーティション分割の重要なツール、HL7 フィールドのデータの内容を理解するため重要です。 一部のデータ型は単純なと 1 つだけの要素を含んでいるし、一部は、多くのコンポーネントとサブコンポーネントが含まれます。 たとえば、PID.5 患者名では、バージョン 2.4 で XPN の入力データがあります。 このデータ型には、英語の言語名の一般的な目盛り、たとえば、姓、名、ミドル ネーム、だけでなくサフィックス、プレフィックス、名前型コード、および名前の有効期間 (日) の範囲がサポートされています。  
  
 新しい HL7 のバージョンでは、追加できますがデータ型を削除できません。 新しいコンポーネントまたはサブコンポーネントを追加することで、データ型にコンテンツを追加する場合のみそれらをネストされている構造体の末尾に追加することができます。 場合によっては、HL7 組織は、既存のデータ型と新しいフォームをマージします。 これが元のデータ型内のサブコンポーネントであった以前項目をサポートするために必要につながっています。  
  
 Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 上のすべての HL7 バージョン V2.1 から標準のデータ型をサポートします。  
  
- インターフェイスを開発するときに、適切な場所に、データ型を制限することができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [HL7 のデータ型 ID 2.1](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)
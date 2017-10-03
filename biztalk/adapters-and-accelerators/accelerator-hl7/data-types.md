---
title: "データの種類 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data types, messages
- messages, data types
ms.assetid: 7a758289-1629-48a0-843d-6f6773bd5ba6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8580b4f6c2a3f1a9f461b112bb4125f1a11ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-types"></a>データ型
データ型の仕様では、HL7 標準の複雑さをパーティション分割に関する重要なツール、HL7 フィールドのデータの内容を理解するため重要です。 一部のデータ型は、シンプルで、1 つだけの要素を含んでいるし、一部は、多くのコンポーネントとサブコンポーネントが含まれます。 たとえば、PID.5 患者の名前には、バージョン 2.4 で XPN を入力データがあります。 このデータ型には、英語の言語名では、一般的な目盛り、たとえば、姓、名、ミドル ネーム、だけでなくサフィックス、プレフィックス、名の種類のコードおよび名の有効期間 (日) の範囲がサポートされています。  
  
 新しい HL7 バージョンを追加できますが、データ型を削除できません。 新しいコンポーネントまたはサブコンポーネントを追加することで、データ型にコンテンツを追加する場合のみそれらをネストされている構造体の末尾に追加することができます。 場合によってでは、HL7 組織は、既存のデータ型を新しいものを形成をマージします。 元のデータ型内でこれらのサブコンポーネント以前なった項目をサポートするために必要に生じていました。  
  
 次の関数の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]上のすべての HL7 バージョン V2.1 から標準のデータ型をサポートします。  
  
-   インターフェイスを開発するときに、適切な場所に、データ型を制限することができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [HL7 のデータ型の ID 2.1](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)
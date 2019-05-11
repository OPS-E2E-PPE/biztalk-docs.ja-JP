---
title: ボキャブラリ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, vocabulary
- vocabularies
ms.assetid: c5df05dd-4af8-4e48-8509-e692b04adf3c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b031e30bf1206b80d292458700b45470cb6cc7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285328"
---
# <a name="vocabulary"></a>ボキャブラリ
HL7 バージョン 2 は、コード化された要素のボキャブラリのいくつかのサポートを提供しますが、ほとんどの場合、ローカル システムのコーディングから描画コードを送信する構造を提供します。  
  
 HL7 バージョン 2 では、セグメント テーブルは、すべてのコード化されたフィールドをリンクします。 セグメント テーブルには、フィールドを使用するテーブルの識別子が含まれています。 テーブルの 3 つの種類があります。外部定義とユーザー定義、HL7 が定義されます。 場合によってでは、標準は、ユーザー定義テーブルの値の例を提供します。 HL7 標準がラベルが、これらを扱う必要があります。  
  
 新しいバージョンでは、HL7 定義のテーブルからコードを削除することはできませんが、新しいコードを追加することができます。 ユーザー定義テーブルを変更することができます。  
  
 Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。  
  
-   HL7 が定義されているテーブルのすべてを使用することができます。  
  
-   インポートすることができ、社外での使用が ICD9 LOINC などのコード セットを定義します。  
  
-   ユーザー定義テーブルの値を指定することができます。  
  
-   システムがコードのさまざまなセットをサポートする場合は、相互運用するさまざまなコードのセットを許可するマッピングを設定することができます。 必要に応じて、中間マッピングと共に移動する 1 つのユーザー定義テーブルの複数のインスタンスを定義できます。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
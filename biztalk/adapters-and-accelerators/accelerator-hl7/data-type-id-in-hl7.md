---
title: "HL7 のデータ型の ID |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data types, data type ID
- data types, messages
- messages, data types
ms.assetid: d1412886-ff0b-4333-b01e-1c3ae45240e2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c5778e772d21cb5f9c6759c127c92ebe74b6f5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-id-in-hl7"></a>HL7 のデータ型の ID
HL7 V2.1 場合は、データの種類 ID は、未定義のデータ型のプレース ホルダーです。 その使用例を次に示します。  
  
-   ST フィールドの形式でのデータ型は、SI (シーケンス ID) です。  
  
-   NM フィールドの形式でのデータ型は、複合フィールドです。  
  
 具体的に定義された複合データ型の例を次に示します。  
  
-   チェック ディジットで CK: 複合 ID です。 例:  
  
    ```  
    |128952^6^M11|  
    ```  
  
-   CN: 複合 ID 番号と名前です。 例:  
  
    ```  
    |12372^RIGGINS^JOHN^""^MD|  
    |12372|  
    |^RIGGINS^JOHN^""^MD|  
    ```  
  
-   単位付き CQ: 複合数量。 例:  
  
    ```  
    |123.7^ML|  
    ```  
  
-   CE: コード化された要素。 例:  
  
    ```  
    |54.21^Laparoscopy^I9C^42112^^AS4|  
    ```  
  
 このデータ型はローカライズされ、定義済みのサイト。 さらに、HL7 V2.1 は提供されません、カバレッジ HL7 Access データベースには、このデータ型。 スキーマを生成する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) では、HL7 バージョン 2.2 データ型が有効し、この情報を使用してスキーマを作成します。 スキーマの使用状況、に応じて適切なデータ型を使用するデータ型を CK、CQ、CE、ST に置き換える必要があることを意味 ^ SI というようにします。  
  
## <a name="see-also"></a>参照  
 [データ型](../../adapters-and-accelerators/accelerator-hl7/data-types.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
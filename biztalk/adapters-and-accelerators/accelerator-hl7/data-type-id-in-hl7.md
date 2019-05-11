---
title: HL7 のデータ型 ID |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, data type ID
- data types, messages
- messages, data types
ms.assetid: d1412886-ff0b-4333-b01e-1c3ae45240e2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f90b215857f0d0fea5e1bd899e1101b117b8ecbe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255597"
---
# <a name="data-type-id-in-hl7"></a>HL7 のデータ型の ID
HL7 の V2.1 の場合は、データ型の ID は、未定義のデータ型のプレース ホルダーは。 その使用法の例を次に示します。  
  
- ST フィールドの形式でのデータ型は、SI (シーケンス ID) です。  
  
- NM フィールドの形式でのデータ型は、複合フィールドです。  
  
  具体的には定義された複合データ型の例を次に示します。  
  
- CK:チェック ディジット複合 ID。 例 :  
  
  ```  
  |128952^6^M11|  
  ```  
  
- CN:複合の ID 番号と名前です。 以下に例を示します。  
  
  ```  
  |12372^RIGGINS^JOHN^""^MD|  
  |12372|  
  |^RIGGINS^JOHN^""^MD|  
  ```  
  
- CQ:単位付きの複合数量です。 以下に例を示します。  
  
  ```  
  |123.7^ML|  
  ```  
  
- CE:コード化された要素。 例 :  
  
  ```  
  |54.21^Laparoscopy^I9C^42112^^AS4|  
  ```  
  
  このデータ型はローカライズし、サイト定義します。 さらに、HL7 V2.1 は提供されません、カバレッジの HL7 Access データベースでは、このデータ型。 Microsoft BizTalk Accelerator 用 HL7 スキーマを生成するため ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 V2.2 のデータ型が有効で、この情報を使用して、スキーマをビルドするいると見なします。 スキーマの使用量によって、適切なデータ型を使用する、CK、CQ、CE、ST、データ型を置き換える必要があることを意味 ^ SI、という具合です。  
  
## <a name="see-also"></a>参照  
 [データ型](../../adapters-and-accelerators/accelerator-hl7/data-types.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
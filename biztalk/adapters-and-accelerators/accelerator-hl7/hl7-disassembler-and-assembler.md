---
title: HL7 の逆アセンブラーとアセンブラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, HL7
- disassembler, HL7
ms.assetid: 54e83a04-86c8-482f-bea3-dbbdeb4584d6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d603e74defeac983b1287f16c7f562b706b8c54d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994995"
---
# <a name="hl7-disassembler-and-assembler"></a>HL7 の逆アセンブラーとアセンブラー
HL7 の逆アセンブラーとアセンブラーは、HL7 でエンコードされたメッセージのサポートを提供します。 Microsoft から[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML 形式では、Microsoft BizTalk Accelerator for HL7 のネイティブのメッセージを処理 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 の逆アセンブラーとアセンブラーを使用して、行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HL7 の統合エンジン。  
  
## <a name="hl7-disassembler"></a>HL7 の逆アセンブラー  
 HL7 の逆アセンブラーでは、HL7 でエンコードされたメッセージの受信を処理のための XML セグメントに解析します。 検証メッセージのヘッダーと本文の基本的な検証を実行します。 HL7 メッセージの解析に使用されるスキーマを決定します (を参照してください[、HL7 のスキーマ決定 2.X 逆アセンブラー](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md))、メッセージの送信元パーティの決定および本文の追加の検証を実行します (有効な場合、パーティ)。  
  
## <a name="hl7-assembler"></a>HL7 アセンブラー  
 HL7 アセンブラーは、XML のセグメントを送信 HL7 メッセージにシリアル化します。 HL7 メッセージをシリアル化するために使用するスキーマを決定します (を参照してください[、HL7 のスキーマ決定 2.X アセンブラー](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md))、メッセージの送信先パーティを決定および (パーティの有効な) 場合は、本文の検証を実行します。  
  
 アセンブラーは、次の確認 (ACK) メッセージをシリアル化できます。  
  
- 静的  
  
- 元のモード  
  
- 拡張モード  
  
  HL7 アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。  
  
## <a name="see-also"></a>参照  
 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
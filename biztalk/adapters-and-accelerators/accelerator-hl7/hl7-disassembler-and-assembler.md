---
title: HL7 逆アセンブラおよびアセンブラ |Microsoft ドキュメント
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
ms.openlocfilehash: e81d621656fc678196f7f6fb709b29de87a3aaf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204930"
---
# <a name="hl7-disassembler-and-assembler"></a>HL7 逆アセンブラおよびアセンブラ
HL7 逆アセンブラおよびアセンブラは、HL7 でエンコードされたメッセージのサポートを提供します。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML 形式でネイティブのメッセージを処理[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 逆アセンブラおよびアセンブラを使用して行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HL7 統合エンジンです。  
  
## <a name="hl7-disassembler"></a>HL7 の逆アセンブラー  
 HL7 逆アセンブラーは、処理のための XML セグメントに着信 HL7 でエンコードされたメッセージを解析します。 これは、検証メッセージのヘッダーと本文の基本的な検証を実行します。 HL7 メッセージの解析に使用されるスキーマを決定 (を参照してください[で、HL7 スキーマの決定 2.X 逆アセンブラー](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md))、メッセージの送信元パーティの決定、および本文の追加の検証を実行します (有効な場合、パーティ) です。  
  
## <a name="hl7-assembler"></a>HL7 アセンブラー  
 HL7 アセンブラーは、送信 HL7 メッセージに XML セグメントをシリアル化します。 HL7 メッセージをシリアル化に使用されるスキーマを決定 (を参照してください[で、HL7 スキーマの決定 2.X アセンブラー](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md))、メッセージの送信先パーティの決定、および (有効な場合、パーティの)、本文の検証を実行します。  
  
 アセンブラーは、次の確認 (ACK) メッセージをシリアル化できます。  
  
-   静的  
  
-   元のモード  
  
-   強化されたモード  
  
 HL7 アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。  
  
## <a name="see-also"></a>参照  
 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
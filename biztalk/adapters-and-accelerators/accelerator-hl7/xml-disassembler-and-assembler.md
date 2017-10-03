---
title: "XML 逆アセンブラーまたはアセンブラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4978484f888290377986ee4ae8bf049c14a1b31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xml-disassembler-and-assembler"></a>XML 逆アセンブラーまたはアセンブラー
XML 逆アセンブラーまたはアセンブラーいることを確認[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) だけでなく、HL7 でエンコードされたメッセージをサポートしますも XML メッセージの受信/送信をサポートします。  
  
## <a name="xml-disassembler"></a>XML 逆アセンブラー  
 XML 逆アセンブラーは、受信 XML メッセージを処理するための XML セグメントに解析します。 メッセージを解析する際、逆アセンブラーは、次のタスクを実行します。  
  
-   ハンドルのエスケープ シーケンス  
  
-   必須/オプションのプロパティのチェックを処理します。  
  
-   ハンドル宣言 Z セグメント  
  
 メッセージを解析する際、逆アセンブラーは、次を実行します。  
  
-   構文検証  
  
-   スキーマの検証 (有効な場合)  
  
## <a name="xml-assembler"></a>XML アセンブラー  
 XML アセンブラーは、送信 XML メッセージに XML セグメントをシリアル化します。 XML アセンブラーは、サポートしており、次の受信確認 (ACK) メッセージの作成します。  
  
-   静的  
  
-   元のモード  
  
-   強化されたモード  
  
 XML アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。  
  
## <a name="see-also"></a>参照  
 [BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
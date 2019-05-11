---
title: XML 逆アセンブラーとアセンブラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf8b71b08c35e94f710af12562060d477bf4abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285144"
---
# <a name="xml-disassembler-and-assembler"></a>XML 逆アセンブラーとアセンブラー
XML 逆アセンブラーとアセンブラーことを確認します。 Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) だけでなく、HL7 でエンコードされたメッセージをサポートしますが、受信/送信 XML メッセージをもサポートしています。  
  
## <a name="xml-disassembler"></a>XML 逆アセンブラー  
 XML 逆アセンブラーでは、受信 XML メッセージを処理するための XML セグメントに解析します。 メッセージを解析する際、逆アセンブラーは、次のタスクを実行します。  
  
- ハンドルのエスケープ シーケンス  
  
- 必須/任意のプロパティのチェックを処理します。  
  
- ハンドルの Z セグメントの宣言  
  
  メッセージを解析する際、逆アセンブラーは、次を実行します。  
  
- 構文の検証  
  
- スキーマの検証 (有効な場合)  
  
## <a name="xml-assembler"></a>XML アセンブラー  
 XML アセンブラーは、XML のセグメントを送信 XML メッセージにシリアル化します。 XML アセンブラーは、サポートおよび次の受信確認 (ACK) メッセージを作成します。  
  
- スタティック  
  
- 元のモード  
  
- 拡張モード  
  
  XML アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。  
  
## <a name="see-also"></a>参照  
 [BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
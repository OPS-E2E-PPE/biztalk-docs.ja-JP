---
title: "BTAHL72XML 処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.XML messages, processing
- acknowledgements, 2.XML messages
- 2.XML messages, message modes
- message modes, 2.XML message
- 2.XML messages
- validating, 2.XML messages
- 2.XML messages, acknowledgements
- 2.XML messages, validating
ms.assetid: 2f12cb44-816c-4773-9db0-9cbc3d1b1aee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e86697884c28d71fa9fb91c8b276293f7d36a588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="btahl72xml-processing"></a>BTAHL72XML 処理
次のコンポーネントで[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 2. XML (XML でエンコードされた) メッセージを処理します。  
  
-   パイプラインとコア ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。PipelineCommon.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。PipelineMessageCore.dll  
  
-   アセンブラーおよび逆アセンブラーのライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL72XmlAsm.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL72XmlDAsm.dll  
  
-   送信アダプターを受信確認 (ACK) の検証用のライブラリ双方向の MLLP:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL7ACKHelper.dll  
  
## <a name="xml-message-modes"></a>XML メッセージ モード  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2. XML メッセージを次のメッセージ モードをサポートします。  
  
-   パブリッシャーとサブスクライバー (パブリッシュ サブスクライブ) モード  
  
     パブリッシャーのブロードキャストとして宣言的または要請されていないが、サブスクライバーのパーティに更新します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]および[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]デザイン時の後に、サブスクリプションとパーティを管理することができますので、このモードでは、柔軟性を提供します。  
  
-   要求-応答モード  
  
     Interrogative またはクエリ メッセージ交換を特定のエンティティからの特定の要求の結果、応答メッセージ。  
  
## <a name="xml-validation"></a>XML 検証  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2. の次の検証 XML メッセージを提供します。  
  
-   XML リーダー  
  
-   概略図  
  
     有効にするまたは、パーティがスキーマの検証を無効にするとします。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MSH9.3 メッセージ構造のヘッダー フィールドと MSH12 バージョン ID フィールド (2.3.1、2.4 または 2.5) によって決定される、この処理のために直接、HL7 2. XML スキーマを使用します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]標準の XML 処理機能を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
-   Z セグメント  
  
     [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]宣言されていない Z セグメントで宣言されたセグメントが含まれていないことを検証します。  
  
## <a name="ack-generation"></a>確認の生成  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2. XML メッセージの受信確認 (Ack) の次の種類をサポートします。 HL7 両方エラーの種類と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](代替) エラーの種類が使用されます。  
  
-   HL7 元 Ack  
  
-   HL7 Ack の強化  
  
     コミットがそのまま使用し、アプリケーションの同意  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)
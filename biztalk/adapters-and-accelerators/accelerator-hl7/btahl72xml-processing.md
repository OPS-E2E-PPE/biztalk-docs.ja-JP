---
title: BTAHL72XML 処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76ddf6ebce9cb9e473a348f1abca6a1af49abb02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251443"
---
# <a name="btahl72xml-processing"></a>BTAHL72XML 処理
Microsoft BizTalk Accelerator for HL7 の次のコンポーネント ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 2. XML (XML でエンコードされた) メッセージを処理します。  
  
- パイプラインとコア ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。PipelineCommon.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。PipelineMessageCore.dll  
  
- アセンブラーおよび逆アセンブラー ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL72XmlAsm.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL72XmlDAsm.dll  
  
- 送信アダプターのための双方向の MLLP 受信確認 (ACK) 検証ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL7ACKHelper.dll  
  
## <a name="xml-message-modes"></a>XML メッセージ モード  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2. XML メッセージの次のメッセージ モードをサポートしています。  
  
- パブリッシャーとサブスクライバー (パブリッシュ-サブスクライブ) モード  
  
   パブリッシャーにブロードキャストする宣言型または要請されていないが、サブスクライバーのパーティを更新します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]デザイン時後のサブスクリプションとパーティを管理できるため、このモードでは、柔軟性を提供します。  
  
- 要求-応答モード  
  
   Interrogative またはクエリ メッセージ交換を特定のエンティティから特定の要求の結果、応答メッセージ。  
  
## <a name="xml-validation"></a>XML 検証  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2. の次の検証 XML メッセージを提供します。  
  
- XML リーダー  
  
- 概略図  
  
   有効にするまたはで、パーティがスキーマの検証を無効にします。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH9.3 メッセージ構造のヘッダー フィールドと MSH12 バージョン ID フィールド (2.3.1 や 2.4、2.5) によって決定される、この処理には直接、HL7 2. XML スキーマを使用します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 標準の XML 処理機能を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
- Z セグメント  
  
   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 未宣言の Z セグメントで宣言されたセグメントが含まれていないことを検証します。  
  
## <a name="ack-generation"></a>確認の生成  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2. XML メッセージの受信確認 (Ack) の次の種類をサポートしています。 HL7 両方エラーの種類と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](代替) エラーの種類が使用されます。  
  
-   HL7 の元の確認  
  
-   HL7 の Ack を強化します。  
  
     コミットがそのまま使用し、アプリケーションの同意  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)
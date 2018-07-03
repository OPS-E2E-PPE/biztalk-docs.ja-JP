---
title: HL7 2.X アセンブラーのスキーマの決定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, assembler
- MSH5
- assembler, schemas
ms.assetid: 464c006e-4fae-4e2a-99ea-157301c0179e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 962f9576032ec8b42542111502c2b6d6698f98d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983651"
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a>HL7 2.X アセンブラーのスキーマ決定
シリアライザーにメッセージをフローするときでは、Microsoft BizTalk Accelerator for HL7 のシリアライザー ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) MSH5 を使用して (送信先パーティ) のメッセージに対して実行する操作を決定するメッセージ。 このような操作は次のとおりです。  
  
- 本文のセグメントの XML の検証を実行するかどうか  
  
- 本文のセグメントのカスタム データ型を検証するかどうか  
  
- 末尾の本体に区切り記号を許可するかどうか  
  
- シリアライザーを使用するスキーマ ターゲットの名前空間  
  
- シリアライザーがヘッダーにマップする必要があるかどうか  
  
  スキーマを決定するには、シリアライザーは、次を行います。  
  
- ターゲットの名前空間の設定 (**TargetNS**) 送信先のパーティ用に構成された名前空間と同じ値を  
  
- 抽出**Rootnode**から、 **BTS します。MessageType**プロパティの昇格  
  
  **Doctype**なります**TargetNS「#」+ Rootnode**します。  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)
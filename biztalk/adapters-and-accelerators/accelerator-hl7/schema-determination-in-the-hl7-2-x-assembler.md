---
title: HL7 2.X アセンブラーでスキーマの決定 |Microsoft ドキュメント
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
ms.openlocfilehash: 50a430750846ae2567f063f9aa77221bad9c97e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206098"
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a>HL7 2.X アセンブラーでスキーマの決定
メッセージが、このシリアライザーで、シリアライザーに送信されるときに[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) MSH5 を使用して (送信先パーティ)、メッセージ上で実行される操作を決定するメッセージのです。 このような操作は次のとおりです。  
  
-   本文のセグメントの XML 検証を実行するかどうか  
  
-   本文のセグメントのカスタム データ型を検証するかどうか  
  
-   末尾の本体に区切り記号を許可するかどうか  
  
-   シリアライザーを使用するスキーマ ターゲットの名前空間  
  
-   かどうか、シリアライザーは、ヘッダーにマップする必要があります。  
  
 スキーマを決定するには、シリアライザーは次のとおり  
  
-   ターゲットの名前空間の設定 (**TargetNS**) 送信先パーティに対して構成されている名前空間と同じ値を  
  
-   抽出**Rootnode**から、 **BTS です。MessageType**昇格されたプロパティ  
  
 **Doctype**なります**TargetNS「#」+ Rootnode**です。  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)
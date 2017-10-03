---
title: "受信確認 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c519ec4649ee1fbcfbc51edb7e3e8fe6ba6b5871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments"></a>受信確認
パーティ レベルを使用して、HL7 の受信確認を構成する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 構成エクスプ ローラー。 受信確認が受信場所 (MLLP アダプター可能性があります) と、HL7 を通じて HL7 メッセージを送信するパーティに適用 2.X 受信パイプラインです。 メッセージの解析と検証の完了時に[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の検証プロセスの結果 (成功またはエラー) が含まれる受信確認メッセージを作成できます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 つの方法のいずれかで受信確認メッセージを返すことができます。 元の送信元パーティには、双方向で元のメッセージが送信された場合の受信ポートの構成、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]その元のポートの場所から受信確認メッセージが返されます。 元の送信ポートが一方向で元のメッセージを送信し、ポート、表示される[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ ボックス データベースに受信確認メッセージを送信し、サブスクリプションのモデルを使用してルーティングします。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 受信メッセージは、HL7 メッセージ (MSH 3.1) の送信側のアプリケーションのフィールド内の値に基づいて自動的に処理するためには、関係者の関連付けを実行します。  
  
## <a name="see-also"></a>参照  
 [メッセージ フロー](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)
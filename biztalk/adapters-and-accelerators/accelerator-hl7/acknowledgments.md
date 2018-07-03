---
title: 受信確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46dedd4f2173fd4a3ad36c272963334b4ce66a20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969787"
---
# <a name="acknowledgments"></a>受信確認
HL7 の Microsoft BizTalk Accelerator を使用してパーティ レベルで HL7 受信確認を構成する ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 構成エクスプ ローラー。 受信確認が受信場所 (MLLP アダプターでは可能性があります) および、HL7 HL7 メッセージを送信しているパーティに適用 2.X 受信パイプライン。 メッセージの解析と検証が完了すると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の検証プロセスの結果 (成功またはエラー) が含まれる受信確認メッセージを作成できます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2 つの方法のいずれかで受信確認メッセージを返すことができます。 元の送信元パーティには、双方向で元のメッセージが送信された場合の受信ポートの構成、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]その元のポートの場所でメッセージを受信確認を返します。 元の送信ポートが一方向で元のメッセージを送信し、ポート、表示される[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ ボックス データベースに受信確認メッセージを送信し、サブスクリプション モデルを使用して、ルーティングします。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 受信メッセージを (MSH 3.1) HL7 メッセージの送信元アプリケーションのフィールド内の値に基づいて自動的に処理するためには、関係者の関連付けを実行します。  
  
## <a name="see-also"></a>参照  
 [メッセージ フロー](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)
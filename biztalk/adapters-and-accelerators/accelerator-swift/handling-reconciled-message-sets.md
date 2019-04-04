---
title: 調整のメッセージ セットの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d3a06955e0072348098ddd7f191bf4862fb119a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986091"
---
# <a name="handling-reconciled-message-sets"></a>調整されたメッセージ セットの処理
SAA にへの応答が返されるときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ ボックスで、応答を記録し、応答や、元のメッセージに対する応答に一致します。 この情報を使用してカスタム アプリケーションの動作を実装することができます。 これを行うには、調整/応答メッセージのセットに対する顧客固有の反応を実装するカスタム ハンドラーを開発します。 次のカスタム ハンドラーを作成できます。  

- SWIFT によってからのメッセージが正常に受信しないようにを示します、MTS21_FIN_ACKNAK 負では受信確認メッセージの FRR が相関関係するメッセージを処理[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 これは、メッセージを修正し、SAA と SWIFT ネットワークのメッセージが正常に表示されることができれば、その後の修復に再び送信修理会社を有効にできます。 このソリューションの詳細については、[FRR NAK ハンドラー サンプル](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)を参照してください。  

- セット内のメッセージの関係を示す一意のファイル名を持つファイル フォルダーに、オーケストレーションによって公開されたメッセージ応答セットを削除します。 これらのメッセージにビジネス ロジックを実行できます。  

- タイムアウト メッセージを処理します。  

- メッセージ送信の結果を記録し、実際のメッセージを破棄します。

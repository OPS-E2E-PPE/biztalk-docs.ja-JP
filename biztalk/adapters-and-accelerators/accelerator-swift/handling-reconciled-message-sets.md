---
title: "照合済みのメッセージ セットの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc9f35f9381f82df90acb92e9536bbd967901a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handling-reconciled-message-sets"></a>処理は、メッセージの設定を調整
SAA にへの応答が返されるときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ ボックスで、応答を記録し、応答または応答を元のメッセージに一致します。 この情報を使用してカスタム アプリケーションの動作を実装することができます。 これを行うには、調整/応答メッセージのセットに対する顧客固有の反応を実装するカスタムのハンドラーを開発します。 次のカスタム ハンドラーを作成できます。  
  
-   SWIFT 受信しなかったことが正常にからメッセージを示す MTS21_FIN_ACKNAK 負の値確認のメッセージで FRR が関連付けられたメッセージを処理[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 これは、メッセージを修正して再 SAA および SWIFT ネットワークで修復後にメッセージが正常に表示されることが望まれます送信修理会社を有効にできます。 このソリューションの詳細については、次を参照してください。 [FRR NAK ハンドラー サンプル](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)です。  
  
-   セット内のメッセージの関係を示す一意のファイル名を持つファイルのフォルダーに、オーケストレーションによって公開されたメッセージ応答セットを削除します。 これらのメッセージでビジネス ロジックを実行できます。  
  
-   タイムアウトになったメッセージを処理します。  
  
-   メッセージ送信の結果を記録し、実際のメッセージを破棄します。
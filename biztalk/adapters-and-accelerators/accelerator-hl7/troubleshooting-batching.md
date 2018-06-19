---
title: バッチ処理のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, troubleshooting
- troubleshooting, batching
ms.assetid: f47e1a16-47fd-4bd8-8dad-fcdba31a833e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94c8413a8022529e6ace56c50d5e6d75267a72e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206306"
---
# <a name="troubleshooting-batching"></a>バッチ処理のトラブルシューティング
関連する問題に対処[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ処理します。  
  
## <a name="error-activating-batch"></a>アクティブ化のバッチのエラー  
  
### <a name="symptom"></a>現象  
 バッチをアクティブにできません。 一般的なネットワーク エラーが表示されます。  
  
**考えられる原因**:[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]再起動されましたが、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーでした。  
  
**解像度**: 再起動[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="messages-are-not-batched-when-the-target-namespace-is-not-the-default"></a>ターゲットの名前空間が既定ではない場合は、メッセージをバッチ処理されません。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージのバッチを処理はありません。  
  
**考えられる原因**: 送信元と送信先のパーティは、同じスキーマの名前空間ではありません。  
  
**解像度**: 検証が必要な場合、送信元と送信先のパーティが同じスキーマの名前空間を使用する必要があります。 送信元と移行先のパーティが同じスキーマの名前空間を使用していることを確認します。  
  
## <a name="see-also"></a>参照  
 [HL7 のトラブルシューティングと既知の問題](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)
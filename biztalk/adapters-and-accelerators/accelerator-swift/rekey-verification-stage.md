---
title: 検証ステージを鍵更新 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- rekey verification
- stages, rekey verification
ms.assetid: 8a2880b6-bb25-4af5-9f51-d0b090ca38c8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9fe163a8351b0edc904f81d77a7ea341de13df6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214202"
---
# <a name="rekey-verification-stage"></a>検証ステージを鍵更新します。
検証のトレイにステージが発生したワークフローでは、メッセージの修復、メッセージの修復および New Submission とメッセージの正確なコピーで、元のメッセージのコピーが保持される鍵更新の確認が送信されるときに検証を鍵更新します。 キーの再検証[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Message Repair and New Submission 手動再登録の指定したフィールドをクリアします。  
  
 この概念は」で詳しく、[サーバー ランタイム セキュリティ](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)トピックです。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー鍵更新の検証段階に参加している必要があります手動で再入力をクリアされたフィールドにを通じて、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ([作成] または修復段階) から元のメッセージが正確に一致する値を形成します。 検証は、有効な証明書を持つメッセージに署名し、メッセージを送信します。  
  
 Rekeyed フィールドの値では、元のメッセージ フィールドを正確に一致しない場合、は、ワークフロー内のステージをリセット Message Repair and New Submission し、メッセージを修理会社の受信トレイに送信します。 また、フィールドを再生成した検証の署名を検証します。 検証ツールが検証されない場合は、検証の受信トレイに、メッセージを送信します。
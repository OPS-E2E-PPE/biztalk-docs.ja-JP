---
title: キー更新の検証ステージ |Microsoft Docs
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
ms.openlocfilehash: 18f0d6acc7621ac50ef257c481d8ce7486ad74bf
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529988"
---
# <a name="rekey-verification-stage"></a>検証ステージの再入力します。
ステージがメッセージ修復のワークフローで発生したメッセージの修復と新しい送信メッセージの正確なコピーして、元のメッセージのコピーが保持されるキーを再入力の検証がの検証ツールの受信トレイに送信されるときに検証の再入力します。 キー更新の検証、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission の手動の再指定フィールドをクリアします。  
  
 この概念は」で詳しく、 [Server ランタイム セキュリティ](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)トピック。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー鍵更新の検証段階に参加している必要があります手動で再入力をクリアされたフィールドにを通じて、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ([作成] または修復段階) から元のメッセージが正確に一致する値を形成します。 検証ツールは、有効な証明書を持つメッセージに署名し、メッセージを送信します。  
  
 Rekeyed フィールドの値では、元のメッセージ フィールドを正確に一致しない場合、は、ワークフロー内のステージをリセット Message Repair and New Submission し、メッセージを修理会社の受信トレイに送信します。 また、フィールドを変更した検証の署名を検証します。 検証ツールが検証されない場合は、検証の受信トレイに、メッセージを送信します。
---
title: "メッセージの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, messages
- messages, validating
ms.assetid: 720ab16a-7ab4-4741-9951-9ab10a2c4c24
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 940b6aa811cbee845b287c09a66c4b9753313ee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-validation"></a>メッセージの検証
2.X が受信および送信パイプライン、メッセージの検証は HL7 で受信および送信の HL7 メッセージに対して発生します。 MSH (ヘッダー) セグメントのみまたはメッセージの本文全体の検証を構成することができます。 さらに、スキーマの一意のローカライズ バージョンに対して検証することができます。 ために、一意の名前空間の値を定義して (パーティ レベルでは、HL7 メッセージング構成と、メッセージを定義する実際のスキーマのターゲット名前空間プロパティの両方でこの名前空間の値を使用します。 実行時に、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) メッセージの解析と検証の適切なスキーマを選択する名前空間とスキーマのルート参照プロパティの組み合わせを使用します。  
  
 パーサーとシリアライザーは、メッセージに関連付けられているパーティの設定に基づく検証を実行します。 バッチ処理、受信確認、およびメッセージ ヘッダーの上書きを含むその他のパーティの設定は、パーサーは、シリアライザーが検証を実行する方法に影響します。  
  
> [!NOTE]
>  シリアライザーは一連の手順については、(該当する場合) を含む MSH マップでヘッダーの上書きを実行して、XML 検証を実行します。 メッセージが本文の検証に合格した場合でもヘッダーの override キーワードと検証の処理がどちらも有効になり、ヘッダーのオーバーライド処理は、ヘッダー フィールドに不適切な値を入力すると場合に、メッセージで、検証は失敗します。  
  
## <a name="see-also"></a>参照  
 [MSH 上書き](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)
---
title: メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, messages
- messages, validating
ms.assetid: 720ab16a-7ab4-4741-9951-9ab10a2c4c24
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b4c94b7a7122572724060b2a45447699e15c1a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970195"
---
# <a name="message-validation"></a>メッセージの検証
2.X の受信および送信パイプラインは、HL7 で受信および送信の HL7 メッセージのメッセージの検証が発生します。 MSH (ヘッダー) セグメントのまたはメッセージ本文全体の検証を構成することができます。 さらに、一意のローカライズされたバージョンのスキーマに対して検証することができます。 これを実現するには、一意の名前空間値を定義して、(パーティ レベル) では、HL7 メッセージング構成と、メッセージを定義する実際のスキーマのターゲット名前空間のプロパティの両方でこの名前空間の値を使用してします。 実行時に、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) メッセージの解析と検証のための適切なスキーマを選択する名前空間とスキーマのルート参照プロパティの組み合わせを使用します。  
  
 パーサーとシリアライザーは、メッセージに関連付けられているパーティの設定に基づく検証を実行します。 バッチ処理、受信確認、およびメッセージ ヘッダーの上書きを含む、他のパーティ設定では、パーサーまたはシリアライザーの検証を実行する方法に影響します。  
  
> [!NOTE]
>  シリアライザーは、一連の (存在する場合) を含む手順を実行します。 MSH マップでヘッダーの上書きを実行すると、XML の検証を実行します。 ヘッダーの上書きと検証プロセスは、両方を有効にし、ヘッダーの上書きプロセス ヘッダー フィールドに誤った値を入力する場合、メッセージは、検証メッセージが本文の検証に合格した場合でも失敗します。  
  
## <a name="see-also"></a>参照  
 
  [MSH のオーバーライド](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)
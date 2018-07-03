---
title: SWIFT トレーラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT Trailer schema
- schemas, SWIFT
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: b6d64584-0514-4c87-98c0-33755efc4695
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1457c05b37c3f5b1dfcc5887c1a3f6ce27fcb0d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004843"
---
# <a name="swift-trailers"></a>SWIFT トレーラー
各 SWIFT のメッセージには、メッセージ交換とセキュリティ要件に必要な 1 つまたは複数のトレーラーがいます。 システム トレーラー、該当する場合、ユーザーのトレーラーに従います。 内で中かっこのペアをさらに区切られた subblock トレーラー ブロック内で各トレーラが表示されます。 各 subblock 後にコロン、トレーラーの型を表す 3 文字から始まります。  
  
 SWIFT トレーラー スキーマ (SWIFT Trailer.xsd) には、次の形式が含まれています。  
  
- テキスト ブロックの終了区切り記号  
  
- ユーザー トレーラー (ユーザーおよびシステム情報)  
  
- システム トレーラー  
  
  テキスト ブロックの終了区切り記号は、「-}」です。 トレーラーのブロックが始まる"{5:"です。 トレーラーのブロックの内容には、ユーザー情報 (チェックサム、メッセージの認証、独自の認証およびなど) とシステム情報 (遅延メッセージ、メッセージの参照、使用可能な重複するメッセージ、およびなど) の両方が含まれます。 SWIFT によって追加されたトレーラーで区切られた、3 番目のブロックを提供も"{s:"です。 *SWIFT ユーザー向けハンドブック*、「FIN サービスの説明」のトピックで詳しく 5 ブロックの内容について説明します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] %s のブロックの内容を検証できません。  
  
  実際、FIN インターフェイスまたは SWIFT ネットワークは、トレーラーを追加します。 メッセージにトレーラーが含まれている場合と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ トレーラーを実行します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] メッセージにトレーラーが含まれていない場合、エラーは発生しないとき[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを受信します。 として、ヘッダー付きのブロックをはじめ、トレーラーのエントリはすべてオプションで[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。  
  
  このセクションには、次のトピックが含まれています。  
  
- [ユーザー トレーラー](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
- [システム トレーラー](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)
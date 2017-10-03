---
title: "SWIFT トレーラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SWIFT Trailer schema
- schemas, SWIFT
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: b6d64584-0514-4c87-98c0-33755efc4695
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc3155ac21f55e7c61483b9287429f9b722f6a84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-trailers"></a>SWIFT は、トレーラー
各 SWIFT メッセージは、メッセージ交換とセキュリティ要件に必要な 1 つまたは複数のトレーラーがします。 システム トレーラー、該当する場合、ユーザーのトレーラーに従います。 各トレーラーをトレーラ ブロック内では、中かっこのペアをこれ以上で区切られたサブブロック内が表示されます。 各サブブロック後にコロンをトレーラ型を表す 3 文字から始まります。  
  
 SWIFT トレーラー スキーマ (SWIFT Trailer.xsd) には、次の形式が含まれています。  
  
-   テキスト ブロックの終了区切り記号  
  
-   ユーザーのトレーラー (ユーザーおよびシステム情報)  
  
-   システムのトレーラー  
  
 テキスト ブロックの終了区切り記号は、「-」} です。 トレーラー ブロックが始まる"{5:"です。 トレーラーのブロックの内容には、ユーザー情報 (チェックサム、メッセージの認証、独自の認証およびなど) とシステム情報 (遅延メッセージ、メッセージの参照を使用可能な重複するメッセージ、およびなど) の両方が含まれます。 SWIFT によって追加されたトレーラーで区切られた 3 番目のブロックを提供も"{s:"です。 *SWIFT ユーザー マニュアル*、「FIN サービスの説明」のトピックで詳しく 5 ブロックの内容について説明します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]%s のブロックの内容を検証できません。  
  
 実際、FIN インターフェイスまたは SWIFT ネットワークは、トレーラーを追加します。 メッセージにトレーラーが含まれている場合と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]はメッセージを受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージにトレーラーを実行します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージにトレーラーが含まれていない場合、エラーを生成しない場合に[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを受信します。 として、ヘッダー付き自体のブロックを含む、トレーラーのエントリはすべてオプションで[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [ユーザーのトレーラー](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
-   [システムのトレーラー](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)
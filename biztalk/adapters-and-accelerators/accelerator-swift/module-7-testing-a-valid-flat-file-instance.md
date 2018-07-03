---
title: 'モジュール 7: 有効なフラット ファイル インスタンスのテスト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, flat file instance
- tutorial, testing flat file instance
- flat files, testing
ms.assetid: ba8a5d81-41b0-4da7-8c2e-02cf29953af7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2344e537fe2b66720e0df9296e22145d1c23bfa6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972251"
---
# <a name="module-7-testing-a-valid-flat-file-instance"></a>モジュール 7: 有効なフラット ファイル インスタンスをテストします。
このモジュールでは、有効なサンプル フラット ファイルをファイルの受信ポートの前の演習で作成された MT103 を送信します。 このタスクは、前の演習で作成した受信パイプラインをテストします。 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]前のレッスンでは、選択した送信ポートの出力フォルダーに XML 形式で出力を書き込みます[レッスン 2: XML の送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)します。  
  
 ファイルを開始する受信アダプターの受信フォルダーに SWIFT のフラット形式のファイルをコピーします。 この操作の結果で[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]有効な SWIFT XML ファイルを送信フォルダーにルーティングします。  
  
 このタスクでは、無効な MT103 メッセージも送信します。 エラーを解決するのにには、イベントを使用します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [レッスン 1: サンプル フラット ファイルを送信する](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)  
  
-   [レッスン 2: 無効な MT103 メッセージを送信する](../../adapters-and-accelerators/accelerator-swift/lesson-2-submitting-an-mt103-message-that-is-not-valid.md)  
  
-   [レッスン 3: XML インスタンスをテストする](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)
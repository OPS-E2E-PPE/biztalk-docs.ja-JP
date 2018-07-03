---
title: 'レッスン 3: XML インスタンスのテスト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, XML instances
- XML instances
ms.assetid: 19d7dd18-17dc-4355-a4f1-5c5e6750faf3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5660ab4e67545b1b98785aedeaeea6e123b6d008
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971899"
---
# <a name="lesson-3-testing-an-xml-instance"></a>レッスン 3: XML インスタンスをテストします。
このレッスンでは、XML 形式でファイルにメッセージの受信ポートの前のレッスンで作成した有効な MT103 を送信します。 このアクションは、前のモジュールで作成した送信パイプラインをテストします。 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]前のモジュールで、送信ポート用に選択した出力フォルダーにフラット ファイルとして出力を書き込みます。  
  
 ファイルを開始する受信アダプターの受信フォルダーに SWIFT XML 形式のファイルをコピーします。 この操作の結果、システムが有効な SWIFT フラット ファイルを送信フォルダーにコピーします。  
  
### <a name="to-test-an-xml-instance"></a>XML インスタンスをテストするには  
  
1. Windows エクスプ ローラーで開く\<*ドライブ*\>: \Labs\Outbound します。 このフォルダーにこのフォルダー内に送信した {GUID} .xml ファイルが含まれていることを確認[レッスン 1: サンプル フラット ファイルを送信する](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)このモジュールの。  
  
2. XML ファイルをコピーして貼り付けます\<*ドライブ*\>: \Labs\Inbound\XMLFile します。 このファイルを貼り付けることに注意してください。  
  
3. 移動\<*ドライブ*\>: \Labs\Outbound します。 このフォルダーに、{GUID} .txt という名前のファイルが変更された日付列でこのファイルの時刻が、ファイルに貼り付けた時間に対応していることを確認\<*ドライブ*\>: \Labs\Inbound\XMLFile します。  
  
4. メモ帳で開きで MT103_Sample.txt \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial します。  
  
5. メモ帳の別のインスタンスで開く {GUID} .txt で\<*ドライブ*\>: \Labs\Inbound\XMLFile します。  
  
6. メモ帳で 2 つのファイルに同じコンテンツが含まれていることを確認します。  
  
   進みます[モジュール 8: 無効なメッセージの修復](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d)します。
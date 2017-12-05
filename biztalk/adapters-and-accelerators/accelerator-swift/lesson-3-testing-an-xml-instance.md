---
title: "レッスン 3: XML インスタンスのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, XML instances
- XML instances
ms.assetid: 19d7dd18-17dc-4355-a4f1-5c5e6750faf3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 948ea484b5cc3138a73a67b384705ed73d9478b2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-3-testing-an-xml-instance"></a>レッスン 3: XML インスタンスのテスト
このレッスンでは、ファイルに XML 形式でメッセージの受信前のレッスンで作成されたポートの有効な MT103 を送信します。 この操作は、前のモジュールで作成した送信パイプラインをテストします。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]前のモジュールで、送信ポート用に選択した出力フォルダーにフラット ファイルとして出力を書き込みます。  
  
 ファイルを開始する受信アダプターの受信フォルダーに SWIFT XML 形式のファイルをコピーしています。 発信フォルダーに SWIFT 有効なフラット ファイルをコピーする、システムでこの操作の結果します。  
  
### <a name="to-test-an-xml-instance"></a>XML インスタンスをテストするには  
  
1.  Windows エクスプ ローラーで開く\<*ドライブ*\>: \Labs\Outbound です。 このフォルダーにこのフォルダーに送信した {GUID} .xml ファイルが含まれていることを確認[レッスン 1: サンプル フラット ファイルを送信する](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)このモジュールのです。  
  
2.  XML ファイルをコピーして貼り付けます\<*ドライブ*\>: \Labs\Inbound\XMLFile です。 このファイルを貼り付けることに注意してください。  
  
3.  移動\<*ドライブ*\>: \Labs\Outbound です。 このフォルダーに {GUID} .txt という名前のファイルがあることと、更新日時 列でこのファイルの時刻が、ファイルに貼り付けたとなる時間に対応していることを確認\<*ドライブ*\>: \Labs\Inbound\XMLFile です。  
  
4.  メモ帳で開きますで MT103_Sample.txt \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial です。  
  
5.  メモ帳の別のインスタンスで開くで {GUID} .txt \<*ドライブ*\>: \Labs\Inbound\XMLFile です。  
  
6.  メモ帳で次の 2 つのファイルに同じコンテンツが含まれていることを確認します。  
  
 進みます[第 8 章: 無効なメッセージの修復](http://msdn.microsoft.com/en-us/fb531b22-ac7a-4620-b395-87aebf56077d)です。
---
title: "レッスン 2: 無効な MT103 メッセージを送信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, invalid messages
- submitting, invalid messages
- submitting, MT103 messages
- MT103 messages
- messages, MT103 messages
ms.assetid: 4b070ae1-c400-421a-b2f6-b7b1f22c0e41
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d064c06aec2698da1be3824ec709dac1702f8e40
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a>レッスン 2: 無効な MT103 メッセージを送信します。
このレッスンでは無効な MT103 メッセージを送信して、システム ツールを使用して、結果として得られるエラーをトラブルシューティングします。  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a>無効な MT103 メッセージを送信するには  
  
1.  MT103_Invalid_Sample.txt ファイルのコピーから\<*ドライブ:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial に\<*ドライブ*\>: \Labs\Inbound\FlatFile フォルダーです。 フォルダーにファイルをドロップすることに注意してください。  
  
2.  開いている\<*ドライブ:*\>\Labs\Outbound MT103_Invalid_Sample.txt に対応する XML ファイルがフォルダー内にないことを確認します。 (有効な MT103_Sample.txt メッセージに対応する XML ファイルはまだそのフォルダーにします。)  
  
3.  メモ帳で、開くファイル MT103_Invalid_Sample.txt で\<*ドライブ:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial です。  
  
4.  開始**BizTalk Server 管理**です。  
  
5.  BizTalk Server 管理コンソールで、展開**イベント ビューアー (ローカル)**、クリックして**アプリケーション**です。  
  
6.  ソースを持つ BizTalk accelerator 用 SWIFT およびに無効なメッセージが削除されるときに対応する時間のエラー エントリを探して、 \<*ドライブ*\>: \Labs\Inbound\FlatFile フォルダーです。 そのエラー エントリをダブルクリックします。  
  
7.  エラーのイベントのプロパティ ダイアログ ボックスでことを確認して、説明ペインに、失敗したメッセージをメッセージ ボックス データベースに発行されていること、SWIFT 逆アセンブラー **A4SWIFT_Failed**として**True**です。 イベントのプロパティ ダイアログ ボックスを閉じます。  
  
8.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**の順に展開および**BizTalk グループ**です。 **ビュー**  メニューをクリックして**グループ ハブ ページ**です。  
  
9. **グループの概要** ウィンドウで、**中断サービス インスタンスのグループ化** ウィンドウで、をクリックして**アプリケーション別にグループ化**です。  
  
10. **、選択したクエリ結果のプレビュー**  ウィンドウで、エントリをダブルクリック**MT103_FlatFile_ReceivePort**です。  
  
11. [サービスの詳細] ダイアログ ボックス、**メッセージ**タブです。サービス名のエントリをダブルクリックして**MT103_FlatFile_ReceivePort**です。  
  
12. メッセージの詳細] ダイアログ ボックスで、[**本文**左側のウィンドウでします。  
  
13. メッセージの詳細 ダイアログ ボックスの body ペインに表示されるメッセージは、メモ帳で開いた MT103_Invalid_Sample.txt に対応していることを確認します。  
  
 進みます[レッスン 3: XML インスタンスをテスト](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)です。
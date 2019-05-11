---
title: レッスン 2:無効な MT103 メッセージを送信する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, invalid messages
- submitting, invalid messages
- submitting, MT103 messages
- MT103 messages
- messages, MT103 messages
ms.assetid: 4b070ae1-c400-421a-b2f6-b7b1f22c0e41
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b686b0ba84d5069f739f129495ee14c7654645d8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530332"
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a>レッスン 2:無効な MT103 メッセージを送信します。
このレッスンでは、無効な MT103 メッセージを送信して、システム ツールを使用して、結果として得られるエラーのトラブルシューティングを行うします。  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a>無効な MT103 メッセージを送信するには  
  
1. MT103_Invalid_Sample.txt ファイルのコピーから\<*ドライブ:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial に\<*ドライブ*\>: \Labs\Inbound\FlatFile フォルダー。 フォルダーにファイルを削除することに注意してください。  
  
2. 開いている\<*ドライブ:*\>\Labs\Outbound MT103_Invalid_Sample.txt に対応する XML ファイルは、フォルダー内にないことを確認します。 (有効な MT103_Sample.txt メッセージに対応する XML ファイルはまだそのフォルダーにします。)  
  
3. メモ帳で開くファイル MT103_Invalid_Sample.txt で\<*ドライブ:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial します。  
  
4. 開始**BizTalk Server 管理**します。  
  
5. BizTalk Server 管理コンソールで [**イベント ビューアー (ローカル)**、] をクリックし、**アプリケーション**します。  
  
6. SWIFT およびに無効なメッセージが削除されるときに対応する時間の BizTalk アクセラレータのソースのあるエラー エントリを探して、 \<*ドライブ*\>: \Labs\Inbound\FlatFile フォルダー。 そのエラー エントリをダブルクリックします。  
  
7. エラーのイベントのプロパティ ダイアログ ボックスでことを確認して、説明ペインに、メッセージ ボックスに、失敗したメッセージが発行されていること、SWIFT 逆アセンブラー **A4SWIFT_Failed**として**True**します。 イベントのプロパティ ダイアログ ボックスを閉じます。  
  
8. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、順に展開**BizTalk グループ**します。 **ビュー**  メニューのをクリックして**グループ ハブ ページ**します。  
  
9. **グループの概要** ウィンドウで、**グループ化された中断サービス インスタンス**ウィンドウで、をクリックして**アプリケーションによるグループ化**します。  
  
10. **選択されたクエリ結果のプレビュー**ペインのエントリをダブルクリック**MT103_FlatFile_ReceivePort**します。  
  
11. サービスの詳細 ダイアログ ボックスで、クリックして、**メッセージ**タブ。サービス名のエントリをダブルクリックして**MT103_FlatFile_ReceivePort**します。  
  
12. メッセージの詳細] ダイアログ ボックスで、[**本文**左側のウィンドウでします。  
  
13. メッセージの詳細 ダイアログ ボックスの body ペインに表示されるメッセージは、メモ帳で開いた MT103_Invalid_Sample.txt に対応していることを確認します。  
  
    続行する[レッスン 3。XML インスタンスをテスト](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)します。
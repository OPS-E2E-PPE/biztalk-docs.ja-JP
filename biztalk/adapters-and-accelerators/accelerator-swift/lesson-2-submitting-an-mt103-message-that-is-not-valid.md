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
ms.openlocfilehash: 1968549cb2417a180ee69dff82f233c43a40318c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="3b1b4-102">レッスン 2: 無効な MT103 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-102">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>
<span data-ttu-id="3b1b4-103">このレッスンでは無効な MT103 メッセージを送信して、システム ツールを使用して、結果として得られるエラーをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-103">In this lesson, you submit an MT103 message that is not valid and then you troubleshoot the resulting error using your System Tools.</span></span>  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="3b1b4-104">無効な MT103 メッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="3b1b4-104">To submit an MT103 message that is not valid</span></span>  
  
1.  <span data-ttu-id="3b1b4-105">MT103_Invalid_Sample.txt ファイルのコピーから\<*ドライブ:*> \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial に\<*ドライブ*>: \Labs\Inbound\フラット ファイルのフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-105">Copy the file MT103_Invalid_Sample.txt from \<*drive:*>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial to \<*drive*>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="3b1b4-106">フォルダーにファイルをドロップすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-106">Note the time that you drop the file into the folder.</span></span>  
  
2.  <span data-ttu-id="3b1b4-107">開いている\<*ドライブ:*> \Labs\Outbound MT103_Invalid_Sample.txt に対応する XML ファイルがフォルダー内にないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-107">Open \<*drive:*>\Labs\Outbound to verify that no XML file corresponding to MT103_Invalid_Sample.txt is in the folder.</span></span> <span data-ttu-id="3b1b4-108">(有効な MT103_Sample.txt メッセージに対応する XML ファイルはまだそのフォルダーにします。)</span><span class="sxs-lookup"><span data-stu-id="3b1b4-108">(The XML file corresponding to the valid MT103_Sample.txt message should still be in that folder.)</span></span>  
  
3.  <span data-ttu-id="3b1b4-109">メモ帳で、開くファイル MT103_Invalid_Sample.txt で\<*ドライブ:*> \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-109">In Notepad, open the file MT103_Invalid_Sample.txt in \<*drive:*>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
4.  <span data-ttu-id="3b1b4-110">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-110">Start **BizTalk Server Administration**.</span></span>  
  
5.  <span data-ttu-id="3b1b4-111">BizTalk Server 管理コンソールで、展開**イベント ビューアー (ローカル)**、クリックして**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-111">In the BizTalk Server Administration Console, expand **Event Viewer (Local)**, and then click **Application**.</span></span>  
  
6.  <span data-ttu-id="3b1b4-112">ソースを持つ BizTalk accelerator 用 SWIFT およびに無効なメッセージが削除されるときに対応する時間のエラー エントリを探して、 \<*ドライブ*>: \Labs\Inbound\FlatFile フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-112">Look for an error entry that has a source of BizTalk Accelerator for SWIFT and a time that corresponds to when you dropped the invalid message into the \<*drive*>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="3b1b4-113">そのエラー エントリをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-113">Double-click that error entry.</span></span>  
  
7.  <span data-ttu-id="3b1b4-114">エラーのイベントのプロパティ ダイアログ ボックスでことを確認して、説明ペインに、失敗したメッセージをメッセージ ボックス データベースに発行されていること、SWIFT 逆アセンブラー **A4SWIFT_Failed**として**True**です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-114">In the Event Properties dialog box for the error, verify in the Description pane that the failed message was published to the MessageBox and that the SWIFT Disassembler marked **A4SWIFT_Failed** as **True**.</span></span> <span data-ttu-id="3b1b4-115">イベントのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-115">Close the Event Properties dialog box.</span></span>  
  
8.  <span data-ttu-id="3b1b4-116">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**の順に展開および**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-116">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, and then expand **BizTalk Group**.</span></span> <span data-ttu-id="3b1b4-117">**ビュー**  メニューをクリックして**グループ ハブ ページ**です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-117">In the **View** menu, click **Group Hub Page**.</span></span>  
  
9. <span data-ttu-id="3b1b4-118">**グループの概要** ウィンドウで、**中断サービス インスタンスのグループ化** ウィンドウで、をクリックして**アプリケーション別にグループ化**です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-118">In the **Group Overview** pane, in the **Grouped Suspended Service Instances** pane, click **Grouped by Application**.</span></span>  
  
10. <span data-ttu-id="3b1b4-119">**、選択したクエリ結果のプレビュー**  ウィンドウで、エントリをダブルクリック**MT103_FlatFile_ReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-119">In the **Preview for the selected query result** pane, double-click the entry for **MT103_FlatFile_ReceivePort**.</span></span>  
  
11. <span data-ttu-id="3b1b4-120">[サービスの詳細] ダイアログ ボックス、**メッセージ**タブです。サービス名のエントリをダブルクリックして**MT103_FlatFile_ReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-120">In the Service Details dialog box, click the **Messages** tab. Double-click the entry for which the Service Name is **MT103_FlatFile_ReceivePort**.</span></span>  
  
12. <span data-ttu-id="3b1b4-121">メッセージの詳細] ダイアログ ボックスで、[**本文**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-121">In the Message Details dialog box, click **Body** in the left pane.</span></span>  
  
13. <span data-ttu-id="3b1b4-122">メッセージの詳細 ダイアログ ボックスの body ペインに表示されるメッセージは、メモ帳で開いた MT103_Invalid_Sample.txt に対応していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-122">Verify that the message displayed in the body pane of the Message Details dialog box corresponds to MT103_Invalid_Sample.txt that you opened in Notepad.</span></span>  
  
 <span data-ttu-id="3b1b4-123">進みます[レッスン 3: XML インスタンスをテスト](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)です。</span><span class="sxs-lookup"><span data-stu-id="3b1b4-123">Proceed to [Lesson 3: Testing an XML Instance](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md).</span></span>
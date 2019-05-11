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
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="ea5ed-102">レッスン 2:無効な MT103 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-102">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>
<span data-ttu-id="ea5ed-103">このレッスンでは、無効な MT103 メッセージを送信して、システム ツールを使用して、結果として得られるエラーのトラブルシューティングを行うします。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-103">In this lesson, you submit an MT103 message that is not valid and then you troubleshoot the resulting error using your System Tools.</span></span>  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a><span data-ttu-id="ea5ed-104">無効な MT103 メッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="ea5ed-104">To submit an MT103 message that is not valid</span></span>  
  
1. <span data-ttu-id="ea5ed-105">MT103_Invalid_Sample.txt ファイルのコピーから\<*ドライブ:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial に\<*ドライブ*\>: \Labs\Inbound\FlatFile フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-105">Copy the file MT103_Invalid_Sample.txt from \<*drive:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial to \<*drive*\>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="ea5ed-106">フォルダーにファイルを削除することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-106">Note the time that you drop the file into the folder.</span></span>  
  
2. <span data-ttu-id="ea5ed-107">開いている\<*ドライブ:*\>\Labs\Outbound MT103_Invalid_Sample.txt に対応する XML ファイルは、フォルダー内にないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-107">Open \<*drive:*\>\Labs\Outbound to verify that no XML file corresponding to MT103_Invalid_Sample.txt is in the folder.</span></span> <span data-ttu-id="ea5ed-108">(有効な MT103_Sample.txt メッセージに対応する XML ファイルはまだそのフォルダーにします。)</span><span class="sxs-lookup"><span data-stu-id="ea5ed-108">(The XML file corresponding to the valid MT103_Sample.txt message should still be in that folder.)</span></span>  
  
3. <span data-ttu-id="ea5ed-109">メモ帳で開くファイル MT103_Invalid_Sample.txt で\<*ドライブ:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-109">In Notepad, open the file MT103_Invalid_Sample.txt in \<*drive:*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
4. <span data-ttu-id="ea5ed-110">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-110">Start **BizTalk Server Administration**.</span></span>  
  
5. <span data-ttu-id="ea5ed-111">BizTalk Server 管理コンソールで [**イベント ビューアー (ローカル)**、] をクリックし、**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-111">In the BizTalk Server Administration Console, expand **Event Viewer (Local)**, and then click **Application**.</span></span>  
  
6. <span data-ttu-id="ea5ed-112">SWIFT およびに無効なメッセージが削除されるときに対応する時間の BizTalk アクセラレータのソースのあるエラー エントリを探して、 \<*ドライブ*\>: \Labs\Inbound\FlatFile フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-112">Look for an error entry that has a source of BizTalk Accelerator for SWIFT and a time that corresponds to when you dropped the invalid message into the \<*drive*\>:\Labs\Inbound\FlatFile folder.</span></span> <span data-ttu-id="ea5ed-113">そのエラー エントリをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-113">Double-click that error entry.</span></span>  
  
7. <span data-ttu-id="ea5ed-114">エラーのイベントのプロパティ ダイアログ ボックスでことを確認して、説明ペインに、メッセージ ボックスに、失敗したメッセージが発行されていること、SWIFT 逆アセンブラー **A4SWIFT_Failed**として**True**します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-114">In the Event Properties dialog box for the error, verify in the Description pane that the failed message was published to the MessageBox and that the SWIFT Disassembler marked **A4SWIFT_Failed** as **True**.</span></span> <span data-ttu-id="ea5ed-115">イベントのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-115">Close the Event Properties dialog box.</span></span>  
  
8. <span data-ttu-id="ea5ed-116">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、順に展開**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-116">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, and then expand **BizTalk Group**.</span></span> <span data-ttu-id="ea5ed-117">**ビュー**  メニューのをクリックして**グループ ハブ ページ**します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-117">In the **View** menu, click **Group Hub Page**.</span></span>  
  
9. <span data-ttu-id="ea5ed-118">**グループの概要** ウィンドウで、**グループ化された中断サービス インスタンス**ウィンドウで、をクリックして**アプリケーションによるグループ化**します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-118">In the **Group Overview** pane, in the **Grouped Suspended Service Instances** pane, click **Grouped by Application**.</span></span>  
  
10. <span data-ttu-id="ea5ed-119">**選択されたクエリ結果のプレビュー**ペインのエントリをダブルクリック**MT103_FlatFile_ReceivePort**します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-119">In the **Preview for the selected query result** pane, double-click the entry for **MT103_FlatFile_ReceivePort**.</span></span>  
  
11. <span data-ttu-id="ea5ed-120">サービスの詳細 ダイアログ ボックスで、クリックして、**メッセージ**タブ。サービス名のエントリをダブルクリックして**MT103_FlatFile_ReceivePort**します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-120">In the Service Details dialog box, click the **Messages** tab. Double-click the entry for which the Service Name is **MT103_FlatFile_ReceivePort**.</span></span>  
  
12. <span data-ttu-id="ea5ed-121">メッセージの詳細] ダイアログ ボックスで、[**本文**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-121">In the Message Details dialog box, click **Body** in the left pane.</span></span>  
  
13. <span data-ttu-id="ea5ed-122">メッセージの詳細 ダイアログ ボックスの body ペインに表示されるメッセージは、メモ帳で開いた MT103_Invalid_Sample.txt に対応していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-122">Verify that the message displayed in the body pane of the Message Details dialog box corresponds to MT103_Invalid_Sample.txt that you opened in Notepad.</span></span>  
  
    <span data-ttu-id="ea5ed-123">続行する[レッスン 3。XML インスタンスをテスト](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="ea5ed-123">Proceed to [Lesson 3: Testing an XML Instance](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md).</span></span>
---
title: "第 7 章: テストの有効なフラット ファイル インスタンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, flat file instance
- tutorial, testing flat file instance
- flat files, testing
ms.assetid: ba8a5d81-41b0-4da7-8c2e-02cf29953af7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 572df71fe479bc26e6b803cdbb95ff7a409c394a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="module-7-testing-a-valid-flat-file-instance"></a><span data-ttu-id="bc257-102">第 7 章: テストの有効なフラット ファイル インスタンス</span><span class="sxs-lookup"><span data-stu-id="bc257-102">Module 7: Testing a Valid Flat File Instance</span></span>
<span data-ttu-id="bc257-103">このモジュールでは、有効なサンプル フラット ファイルをファイル受信ポートの前の実習で作成した MT103 を送信します。</span><span class="sxs-lookup"><span data-stu-id="bc257-103">In this module, you submit a valid sample MT103 flat file to the file receive ports created in the previous labs.</span></span> <span data-ttu-id="bc257-104">このタスクは、前の実習で作成した受信パイプラインをテストします。</span><span class="sxs-lookup"><span data-stu-id="bc257-104">This task tests the receive pipelines you created in previous labs.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="bc257-105">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]前のレッスンで選択した送信ポートの出力フォルダーに XML 形式で出力を書き込みます[レッスン 2: XML 送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc257-105">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] writes the output in XML format to the output folder in the send port you selected in the previous lesson, [Lesson 2: Adding an XML Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span></span>  
  
 <span data-ttu-id="bc257-106">ファイルを開始する受信アダプターの受信フォルダーに SWIFT のフラット形式のファイルをコピーしています。</span><span class="sxs-lookup"><span data-stu-id="bc257-106">You initiate the file receive adapter by copying a SWIFT flat-formatted file to the inbound folder.</span></span> <span data-ttu-id="bc257-107">この操作の結果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]発信フォルダーに有効な SWIFT XML ファイルをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="bc257-107">This action results in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] routing a valid SWIFT XML file to the outbound folder.</span></span>  
  
 <span data-ttu-id="bc257-108">このタスクもが無効です MT103 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bc257-108">In this task, you also submit an MT103 message that is not valid.</span></span> <span data-ttu-id="bc257-109">エラーを解決するのにには、イベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc257-109">You use the Event to resolve the error.</span></span>  
  
 <span data-ttu-id="bc257-110">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc257-110">This section contains:</span></span>  
  
-   [<span data-ttu-id="bc257-111">レッスン 1: サンプル フラット ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="bc257-111">Lesson 1: Submitting a Sample Flat File</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)  
  
-   [<span data-ttu-id="bc257-112">レッスン 2: 無効な MT103 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bc257-112">Lesson 2: Submitting an MT103 Message That Is Not Valid</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-submitting-an-mt103-message-that-is-not-valid.md)  
  
-   [<span data-ttu-id="bc257-113">レッスン 3: XML インスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="bc257-113">Lesson 3: Testing an XML Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)
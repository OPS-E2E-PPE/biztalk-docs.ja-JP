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
ms.openlocfilehash: 5ae33f29d37e7d36dd09aa33439ce62d34391e21
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530316"
---
# <a name="lesson-3-testing-an-xml-instance"></a><span data-ttu-id="1ea29-102">レッスン 3: XML インスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="1ea29-102">Lesson 3: Testing an XML Instance</span></span>
<span data-ttu-id="1ea29-103">このレッスンでは、XML 形式でファイルにメッセージの受信ポートの前のレッスンで作成した有効な MT103 を送信します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-103">In this lesson, you submit a valid MT103 message in XML format to the file receive ports created in the previous lessons.</span></span> <span data-ttu-id="1ea29-104">このアクションは、前のモジュールで作成した送信パイプラインをテストします。</span><span class="sxs-lookup"><span data-stu-id="1ea29-104">This action tests the send pipelines that you created in previous modules.</span></span> <span data-ttu-id="1ea29-105">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]前のモジュールで、送信ポート用に選択した出力フォルダーにフラット ファイルとして出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1ea29-105">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] writes the output as a flat file to the output folder that you selected for the send port in the previous module.</span></span>  
  
 <span data-ttu-id="1ea29-106">ファイルを開始する受信アダプターの受信フォルダーに SWIFT XML 形式のファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1ea29-106">You initiate the file receive adapter by copying a SWIFT XML-formatted file to the inbound folder.</span></span> <span data-ttu-id="1ea29-107">この操作の結果、システムが有効な SWIFT フラット ファイルを送信フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1ea29-107">This action results in the system copying a valid SWIFT flat file to the outbound folder.</span></span>  
  
### <a name="to-test-an-xml-instance"></a><span data-ttu-id="1ea29-108">XML インスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="1ea29-108">To test an XML Instance</span></span>  
  
1. <span data-ttu-id="1ea29-109">Windows エクスプ ローラーで開く\<*ドライブ*\>: \Labs\Outbound します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-109">In Windows Explorer, open \<*drive*\>:\Labs\Outbound.</span></span> <span data-ttu-id="1ea29-110">このフォルダーにこのフォルダー内に送信した {GUID} .xml ファイルが含まれていることを確認[レッスン 1。サンプル フラット ファイルを送信する](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)このモジュールの。</span><span class="sxs-lookup"><span data-stu-id="1ea29-110">Verify that this folder contains the {GUID}.xml file that you sent to this folder in [Lesson 1: Submitting a Sample Flat File](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md) of this module.</span></span>  
  
2. <span data-ttu-id="1ea29-111">XML ファイルをコピーして貼り付けます\<*ドライブ*\>: \Labs\Inbound\XMLFile します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-111">Copy the XML file, and paste it into \<*drive*\>:\Labs\Inbound\XMLFile.</span></span> <span data-ttu-id="1ea29-112">このファイルを貼り付けることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1ea29-112">Note the time that you pasted this file.</span></span>  
  
3. <span data-ttu-id="1ea29-113">移動\<*ドライブ*\>: \Labs\Outbound します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-113">Move to \<*drive*\>:\Labs\Outbound.</span></span> <span data-ttu-id="1ea29-114">このフォルダーに、{GUID} .txt という名前のファイルが変更された日付列でこのファイルの時刻が、ファイルに貼り付けた時間に対応していることを確認\<*ドライブ*\>: \Labs\Inbound\XMLFile します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-114">Verify that there is a file called {GUID}.txt in this folder, and that the time in the Date Modified column for this file corresponds to the time that you pasted the file into \<*drive*\>:\Labs\Inbound\XMLFile.</span></span>  
  
4. <span data-ttu-id="1ea29-115">メモ帳で開きで MT103_Sample.txt \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-115">In Notepad, open MT103_Sample.txt in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial.</span></span>  
  
5. <span data-ttu-id="1ea29-116">メモ帳の別のインスタンスで開く {GUID} .txt で\<*ドライブ*\>: \Labs\Inbound\XMLFile します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-116">In another instance of Notepad, open {GUID}.txt in \<*drive*\>:\Labs\Inbound\XMLFile.</span></span>  
  
6. <span data-ttu-id="1ea29-117">メモ帳で 2 つのファイルに同じコンテンツが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-117">Verify that the two files in Notepad contain the same content.</span></span>  
  
   <span data-ttu-id="1ea29-118">続行する[モジュール 8。無効なメッセージの修復](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d)します。</span><span class="sxs-lookup"><span data-stu-id="1ea29-118">Proceed to [Module 8: Repairing an Invalid Message](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d).</span></span>
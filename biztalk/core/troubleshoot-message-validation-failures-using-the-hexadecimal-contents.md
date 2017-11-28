---
title: "保留メッセージの 16 進数の内容を表示することによってメッセージの検証エラーのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f7dc0f24a85f206831e3706bd03f2206aaa2c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a><span data-ttu-id="bd360-102">保留メッセージの 16 進数コンテンツの確認によるメッセージ検証エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bd360-102">Troubleshooting Message Validation Failures by Viewing the Hexadecimal Contents of Suspended Messages</span></span>
<span data-ttu-id="bd360-103">メッセージが検証エラーにより保留された場合は、メッセージ部分を 16 進表現にして確認すると検証エラーの原因の特定に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="bd360-103">If a message is suspended due to validation failures, it may be helpful to view the hexadecimal representation of the message parts to determine the cause of the validation failure.</span></span> <span data-ttu-id="bd360-104">このトピックでは、保留メッセージのメッセージ部分を 16 進表現で表示する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd360-104">This topic lists steps that can be followed to view the hexadecimal representation of the parts of a suspended message.</span></span>  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a><span data-ttu-id="bd360-105">[メッセージの詳細] ダイアログ ボックスを使用したメッセージ部分の表示</span><span class="sxs-lookup"><span data-stu-id="bd360-105">Use the Message Details dialog box to view message parts</span></span>  
 <span data-ttu-id="bd360-106">メッセージ部分を 16 進表現で表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd360-106">Follow these steps to view the hexadecimal representation of message parts:</span></span>  
  
1.  <span data-ttu-id="bd360-107">使用して、**クエリ** タブで、BizTalk 管理コンソールを 1 つまたは複数の保留メッセージを含む結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="bd360-107">Use the **Query** tab in the BizTalk Administration Console to return a result set with one or more suspended messages.</span></span> <span data-ttu-id="bd360-108">参照してください[メッセージの検索方法](../core/how-to-search-for-messages.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="bd360-108">See [How to Search for Messages](../core/how-to-search-for-messages.md) for more information.</span></span>  
  
2.  <span data-ttu-id="bd360-109">表示を調査する保留中のメッセージをダブルクリックして、**メッセージの詳細**メッセージのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bd360-109">Double-click the suspended message that you want to investigate to display the **Message Details** dialog box for the message.</span></span>  
  
3.  <span data-ttu-id="bd360-110">左側のウィンドウでメッセージ部分をクリックして、**メッセージの詳細**ダイアログ ボックスに、メッセージ部を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd360-110">Click a message part in the left hand pane of the **Message Details** dialog box to display the message part.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd360-111">メッセージには、メッセージ部分を持たないものと 1 つまたは複数のメッセージ部分を持つものがあります。</span><span class="sxs-lookup"><span data-stu-id="bd360-111">Messages may have 0, 1 or many message parts.</span></span> <span data-ttu-id="bd360-112">"本文" と呼ばれるメッセージ部分を 1 つだけ持つメッセージがほとんどです。</span><span class="sxs-lookup"><span data-stu-id="bd360-112">Most often messages have single message part that is called "body".</span></span>  
  
4.  <span data-ttu-id="bd360-113">クリックして、**バイナリ** タブの右側のペインで、**メッセージの詳細**ダイアログ ボックスに、メッセージ部分を 16 進表現を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd360-113">Click the **Binary** tab in the right hand pane of the **Message Details** dialog box to display the hexadecimal representation of the message part.</span></span>  
  
5.  <span data-ttu-id="bd360-114">メッセージ部分の文字を 16 進表現で表示して、次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="bd360-114">Check the hexadecimal representation of characters in message parts for the following:</span></span>  
  
    -   <span data-ttu-id="bd360-115">バイト オーダー マークの欠落または無効なバイト オーダー マーク。</span><span class="sxs-lookup"><span data-stu-id="bd360-115">Missing or invalid byte order mark.</span></span> <span data-ttu-id="bd360-116">詳細については、バイト順マークを参照してください[http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380)です。</span><span class="sxs-lookup"><span data-stu-id="bd360-116">For more information about byte order marks see [http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380).</span></span>  
  
    -   <span data-ttu-id="bd360-117">UNIX と Windows での改行のエンコード方法の違い。</span><span class="sxs-lookup"><span data-stu-id="bd360-117">Differences between the encoding of linebreaks in Unix and Windows.</span></span> <span data-ttu-id="bd360-118">Unix では、改行を 16 進のラインフィード (0A) のみで表しますが、Windows では、16 進の復帰 (0D) とラインフィード (0A) の 2 つで表します。</span><span class="sxs-lookup"><span data-stu-id="bd360-118">Unix uses hex linefeed (0A) to indicate a line break where Windows uses both hex carriage return (0D) and linefeed (0A) to indicate a line break.</span></span>  
  
    -   <span data-ttu-id="bd360-119">メッセージ部分の無効な制御文字。</span><span class="sxs-lookup"><span data-stu-id="bd360-119">Invalid control character(s) in message parts.</span></span> <span data-ttu-id="bd360-120">メッセージ部分の制御文字は、テキスト ビューでは表示されませんがバイナリ ビューでは表示できます。</span><span class="sxs-lookup"><span data-stu-id="bd360-120">Control characters in message parts that do not show up in the text view may be visible in the binary view.</span></span>  
  
    -   <span data-ttu-id="bd360-121">メッセージ部分の途中の無効な Null 文字によるメッセージの切り捨て。</span><span class="sxs-lookup"><span data-stu-id="bd360-121">Invalid nul character(s) in the middle of a message part can cause the message part to be truncated.</span></span> <span data-ttu-id="bd360-122">Null 文字は 16 進では 00 で表されます。</span><span class="sxs-lookup"><span data-stu-id="bd360-122">The nul character is represented as hex (00).</span></span>  
  
    -   <span data-ttu-id="bd360-123">位置指定フラット ファイル内の無効な文字オフセット。</span><span class="sxs-lookup"><span data-stu-id="bd360-123">Invalid character offset in positional flat files.</span></span> <span data-ttu-id="bd360-124">メッセージ部分を 16 進表現で表示すると、位置指定フラット ファイルのデータのオフセットを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bd360-124">Display the hexadecimal representation of a message part to view the offset of data in a positional flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd360-125">参照</span><span class="sxs-lookup"><span data-stu-id="bd360-125">See Also</span></span>  
 [<span data-ttu-id="bd360-126">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="bd360-126">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)
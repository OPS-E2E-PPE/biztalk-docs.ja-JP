---
title: 保留メッセージの 16 進数の内容を表示することによってメッセージ検証エラーのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 562caf377691e8bfcea5d05bba307e28859d7999
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243122"
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a><span data-ttu-id="adadd-102">保留メッセージの 16 進数の内容を表示することによってメッセージ検証エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="adadd-102">Troubleshooting Message Validation Failures by Viewing the Hexadecimal Contents of Suspended Messages</span></span>
<span data-ttu-id="adadd-103">検証エラーによりメッセージが中断の場合は、メッセージ部分の検証エラーの原因を特定する 16 進数形式で表示すると役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="adadd-103">If a message is suspended due to validation failures, it may be helpful to view the hexadecimal representation of the message parts to determine the cause of the validation failure.</span></span> <span data-ttu-id="adadd-104">このトピックでは、中断されたメッセージの部分の 16 進数形式で表示する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="adadd-104">This topic lists steps that can be followed to view the hexadecimal representation of the parts of a suspended message.</span></span>  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a><span data-ttu-id="adadd-105">メッセージの詳細 ダイアログ ボックスを使用してメッセージ部分の表示</span><span class="sxs-lookup"><span data-stu-id="adadd-105">Use the Message Details dialog box to view message parts</span></span>  
 <span data-ttu-id="adadd-106">メッセージ部分の 16 進数形式で表示する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="adadd-106">Follow these steps to view the hexadecimal representation of message parts:</span></span>  
  
1.  <span data-ttu-id="adadd-107">使用して、**クエリ** タブで、BizTalk 管理コンソールを 1 つまたは複数の保留メッセージを含む結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="adadd-107">Use the **Query** tab in the BizTalk Administration Console to return a result set with one or more suspended messages.</span></span> <span data-ttu-id="adadd-108">参照してください[メッセージを検索する方法](../core/how-to-search-for-messages.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="adadd-108">See [How to Search for Messages](../core/how-to-search-for-messages.md) for more information.</span></span>  
  
2.  <span data-ttu-id="adadd-109">表示する調査する保留中のメッセージをダブルクリックして、**メッセージの詳細**メッセージのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="adadd-109">Double-click the suspended message that you want to investigate to display the **Message Details** dialog box for the message.</span></span>  
  
3.  <span data-ttu-id="adadd-110">左側のウィンドウでメッセージ部分をクリックして、**メッセージの詳細**ダイアログ ボックスに、メッセージ部分を表示します。</span><span class="sxs-lookup"><span data-stu-id="adadd-110">Click a message part in the left hand pane of the **Message Details** dialog box to display the message part.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="adadd-111">メッセージには、0、1 つまたは複数のメッセージ部分があります。</span><span class="sxs-lookup"><span data-stu-id="adadd-111">Messages may have 0, 1 or many message parts.</span></span> <span data-ttu-id="adadd-112">メッセージがほとんどでは、"body"に呼び出される単一のメッセージ部分があります。</span><span class="sxs-lookup"><span data-stu-id="adadd-112">Most often messages have single message part that is called "body".</span></span>  
  
4.  <span data-ttu-id="adadd-113">をクリックして、**バイナリ** タブの右側のウィンドウで、**メッセージの詳細**ダイアログ ボックスにメッセージ部分の 16 進数表現を表示します。</span><span class="sxs-lookup"><span data-stu-id="adadd-113">Click the **Binary** tab in the right hand pane of the **Message Details** dialog box to display the hexadecimal representation of the message part.</span></span>  
  
5.  <span data-ttu-id="adadd-114">次のメッセージ部分の文字の 16 進数表現を確認します。</span><span class="sxs-lookup"><span data-stu-id="adadd-114">Check the hexadecimal representation of characters in message parts for the following:</span></span>  
  
    -   <span data-ttu-id="adadd-115">存在しないか無効のバイト オーダー マークします。</span><span class="sxs-lookup"><span data-stu-id="adadd-115">Missing or invalid byte order mark.</span></span> <span data-ttu-id="adadd-116">詳細については、バイト順はマークを参照してください[ http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380)します。</span><span class="sxs-lookup"><span data-stu-id="adadd-116">For more information about byte order marks see [http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380).</span></span>  
  
    -   <span data-ttu-id="adadd-117">Unix と Windows での改行のエンコードの間の相違点。</span><span class="sxs-lookup"><span data-stu-id="adadd-117">Differences between the encoding of linebreaks in Unix and Windows.</span></span> <span data-ttu-id="adadd-118">Unix は、行の区切りを示すために、Windows が 16 進キャリッジ リターン (0 D) とラインフィード (0 a) の両方を使用するという改行を 16 進のラインフィード (0 a) を使用します。</span><span class="sxs-lookup"><span data-stu-id="adadd-118">Unix uses hex linefeed (0A) to indicate a line break where Windows uses both hex carriage return (0D) and linefeed (0A) to indicate a line break.</span></span>  
  
    -   <span data-ttu-id="adadd-119">メッセージ部分の無効な制御文字。</span><span class="sxs-lookup"><span data-stu-id="adadd-119">Invalid control character(s) in message parts.</span></span> <span data-ttu-id="adadd-120">テキスト ビューで表示しないメッセージ部分の制御文字をバイナリのビューに表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="adadd-120">Control characters in message parts that do not show up in the text view may be visible in the binary view.</span></span>  
  
    -   <span data-ttu-id="adadd-121">メッセージ部分の途中で無効な nul 文字には、メッセージ部分が切り捨てられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="adadd-121">Invalid nul character(s) in the middle of a message part can cause the message part to be truncated.</span></span> <span data-ttu-id="adadd-122">Nul 文字は 16 進数 (00) として表されます。</span><span class="sxs-lookup"><span data-stu-id="adadd-122">The nul character is represented as hex (00).</span></span>  
  
    -   <span data-ttu-id="adadd-123">無効な文字が位置指定フラット ファイル内のオフセットします。</span><span class="sxs-lookup"><span data-stu-id="adadd-123">Invalid character offset in positional flat files.</span></span> <span data-ttu-id="adadd-124">位置指定フラット ファイルのデータのオフセットを表示するメッセージ部分の 16 進数表現を表示します。</span><span class="sxs-lookup"><span data-stu-id="adadd-124">Display the hexadecimal representation of a message part to view the offset of data in a positional flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adadd-125">参照</span><span class="sxs-lookup"><span data-stu-id="adadd-125">See Also</span></span>  
 [<span data-ttu-id="adadd-126">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="adadd-126">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)
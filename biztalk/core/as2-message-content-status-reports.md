---
title: AS2 メッセージ コンテンツのステータス レポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6244aa59-a80d-450b-ab95-9a5e14c0c40e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2dadb3231136255dcf532e5054c1a6228880f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230490"
---
# <a name="as2-message-content-status-reports"></a><span data-ttu-id="74009-102">AS2 メッセージ コンテンツの状態レポート</span><span class="sxs-lookup"><span data-stu-id="74009-102">AS2 Message Content Status Reports</span></span>

## <a name="overview"></a><span data-ttu-id="74009-103">概要</span><span class="sxs-lookup"><span data-stu-id="74009-103">Overview</span></span>
<span data-ttu-id="74009-104">これらの状態レポートには、AS2 メッセージまたは MDN のコンテキスト プロパティ、ヘッダー、およびペイロードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74009-104">These status reports display the context properties, headers and payload of an AS2 message or an MDN.</span></span> <span data-ttu-id="74009-105">AS2 メッセージ コンテンツの状態レポートには、次の 3 つがあります。</span><span class="sxs-lookup"><span data-stu-id="74009-105">There are three AS2 message content status reports:</span></span>  
  
-   <span data-ttu-id="74009-106">メッセージのワイヤ形式のレポート</span><span class="sxs-lookup"><span data-stu-id="74009-106">Message Wire Format report</span></span>  
  
-   <span data-ttu-id="74009-107">メッセージのデコードされた形式のレポート</span><span class="sxs-lookup"><span data-stu-id="74009-107">Message Decoded Format report</span></span>  
  
-   <span data-ttu-id="74009-108">MDN メッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="74009-108">Mdn Message report</span></span>  
  
 <span data-ttu-id="74009-109">AS2/MDN の状態レポート内で AS2 メッセージを右クリックし、をクリックしてこれらのレポートのいずれかを表示する**ビュー メッセージのワイヤ形式**、**ビュー メッセージのデコードされた形式**、または**ビュー Mdnメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="74009-109">You display one of these reports by right-clicking an AS2 message within the AS2/MDN status report, and then clicking **View Message Wire Format**, **View Message Decoded Format**, or **View Mdn Message**.</span></span> <span data-ttu-id="74009-110">MDN コマンドを実行すると、AS2 メッセージに関連付けられている MDN が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74009-110">The MDN command will display the MDN that is correlated to the AS2 message.</span></span>  
  
 <span data-ttu-id="74009-111">各レポートを使用できるのは、関連するパーティの [AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページまたは [パーティ - AS2 メッセージの受信者] ページで、対応するプロパティ (否認不可データベースへのメッセージの保管を表す) をオンにした場合のみです。</span><span class="sxs-lookup"><span data-stu-id="74009-111">Each of these reports is available only if you have selected the corresponding "Store messages in non-repudiation database" properties in the Party as AS2 Message Sender page or Party as AS2 Message Receiver page of the AS2 Properties dialog box for the related party.</span></span> <span data-ttu-id="74009-112">コマンドを実行すると、AS2 メッセージまたは MDN は、ワイヤ形式またはデコードされた形式で BizTalkDTADb データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="74009-112">The commands store AS2 messages or MDNs in wire format or decoded format in the BizTalkDTADb database.</span></span>  
  
 <span data-ttu-id="74009-113">このレポートを使用して、**メッセージの詳細プロパティ ダイアログ ボックス**(UI の詳細を参照してください[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) ページに分けられる情報を含むメッセージ データを表示します。</span><span class="sxs-lookup"><span data-stu-id="74009-113">This report uses the **Message Details Properties Dialog Box** (see the UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) to display message data, with information separated into pages:</span></span>  
  
|<span data-ttu-id="74009-114">ページ</span><span class="sxs-lookup"><span data-stu-id="74009-114">Page</span></span>|<span data-ttu-id="74009-115">表示されるデータ</span><span class="sxs-lookup"><span data-stu-id="74009-115">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="74009-116">**全般**</span><span class="sxs-lookup"><span data-stu-id="74009-116">**General**</span></span>|<span data-ttu-id="74009-117">メッセージの概要</span><span class="sxs-lookup"><span data-stu-id="74009-117">Overview information about the message</span></span>|  
|<span data-ttu-id="74009-118">**コンテキスト**</span><span class="sxs-lookup"><span data-stu-id="74009-118">**Context**</span></span>|<span data-ttu-id="74009-119">このメッセージに関連するコンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="74009-119">Context properties associated with this message</span></span>|  
|<span data-ttu-id="74009-120">**メッセージ部分**</span><span class="sxs-lookup"><span data-stu-id="74009-120">**Message Parts**</span></span>|<span data-ttu-id="74009-121">このメッセージ内に含まれる個別のドキュメント ペイロード。</span><span class="sxs-lookup"><span data-stu-id="74009-121">Individual document payload contained within this message.</span></span> <span data-ttu-id="74009-122">各ドキュメントはテキストまたはバイナリとして表示できます。</span><span class="sxs-lookup"><span data-stu-id="74009-122">Each document can be viewed as either text or binary:</span></span><br /><br /> <span data-ttu-id="74009-123">テキスト形式のビューは、EDI テキスト ファイルなど、人間が判読できる形式で、AS2 メッセージまたは MDN のコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="74009-123">-   Text Format view shows the contents of the AS2 message or MDN in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="74009-124">このビューでは、AS2 ヘッダー、EDI トレーラー、および EDI ペイロードが表示されます。各セグメントは別々の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="74009-124">This view shows the AS2 headers, EDI trailers, and EDI payload, with each segment on a separate line.</span></span><br /><span data-ttu-id="74009-125">-バイナリ形式のビューは、区切りなしテキスト形式と、AS2 メッセージまたは MDN 内の各 ASCII 文字の 16 進数表記の表で、AS2 メッセージまたは MDN のコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="74009-125">-   Binary Format view shows the contents of the AS2 message or MDN in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the AS2 message or MDN.</span></span>|
---
title: AS2 メッセージのコンテンツの状態レポート |Microsoft Docs
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
ms.openlocfilehash: 89504de79279a42d14061606a31985bed0563635
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358916"
---
# <a name="as2-message-content-status-reports"></a><span data-ttu-id="9708d-102">AS2 メッセージ コンテンツのステータス レポート</span><span class="sxs-lookup"><span data-stu-id="9708d-102">AS2 Message Content Status Reports</span></span>

## <a name="overview"></a><span data-ttu-id="9708d-103">概要</span><span class="sxs-lookup"><span data-stu-id="9708d-103">Overview</span></span>
<span data-ttu-id="9708d-104">これらの状態レポートでは、AS2 メッセージまたは MDN のヘッダーとペイロード、コンテキスト プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="9708d-104">These status reports display the context properties, headers and payload of an AS2 message or an MDN.</span></span> <span data-ttu-id="9708d-105">これには次の 3 つの AS2 メッセージ コンテンツのステータスのレポートがあります。</span><span class="sxs-lookup"><span data-stu-id="9708d-105">There are three AS2 message content status reports:</span></span>  
  
- <span data-ttu-id="9708d-106">メッセージのワイヤ形式のレポート</span><span class="sxs-lookup"><span data-stu-id="9708d-106">Message Wire Format report</span></span>  
  
- <span data-ttu-id="9708d-107">メッセージのデコードされた形式のレポート</span><span class="sxs-lookup"><span data-stu-id="9708d-107">Message Decoded Format report</span></span>  
  
- <span data-ttu-id="9708d-108">Mdn メッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="9708d-108">Mdn Message report</span></span>  
  
  <span data-ttu-id="9708d-109">AS2/MDN の状態レポート内で AS2 メッセージを右クリックし、をクリックしてこれらのレポートのいずれかを表示する**ビュー メッセージのワイヤ形式**、**ビュー メッセージのデコードされた形式**、または**ビュー Mdnメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="9708d-109">You display one of these reports by right-clicking an AS2 message within the AS2/MDN status report, and then clicking **View Message Wire Format**, **View Message Decoded Format**, or **View Mdn Message**.</span></span> <span data-ttu-id="9708d-110">MDN コマンドにより、相関関係に MDN が AS2 メッセージに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9708d-110">The MDN command will display the MDN that is correlated to the AS2 message.</span></span>  
  
  <span data-ttu-id="9708d-111">これらのレポートの各機能は、選択した、対応する「否認不可データベースにストア メッセージ」プロパティ [パーティ-AS2 メッセージの送信者] ページまたは [パーティ AS2 のプロパティ] ダイアログ ボックスの [AS2 メッセージの受信者] ページとして、関連するパーティの場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9708d-111">Each of these reports is available only if you have selected the corresponding "Store messages in non-repudiation database" properties in the Party as AS2 Message Sender page or Party as AS2 Message Receiver page of the AS2 Properties dialog box for the related party.</span></span> <span data-ttu-id="9708d-112">コマンドは、ワイヤ形式またはデコードされた形式で BizTalkDTADb データベースで AS2 メッセージまたは Mdn を格納します。</span><span class="sxs-lookup"><span data-stu-id="9708d-112">The commands store AS2 messages or MDNs in wire format or decoded format in the BizTalkDTADb database.</span></span>  
  
  <span data-ttu-id="9708d-113">このレポートを使用して、**メッセージの詳細プロパティ ダイアログ ボックス**(UI の詳細を参照してください。 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) ページに分割の情報メッセージのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="9708d-113">This report uses the **Message Details Properties Dialog Box** (see the UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) to display message data, with information separated into pages:</span></span>  
  
|<span data-ttu-id="9708d-114">ページ</span><span class="sxs-lookup"><span data-stu-id="9708d-114">Page</span></span>|<span data-ttu-id="9708d-115">表示されるデータ</span><span class="sxs-lookup"><span data-stu-id="9708d-115">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="9708d-116">**全般**</span><span class="sxs-lookup"><span data-stu-id="9708d-116">**General**</span></span>|<span data-ttu-id="9708d-117">概要については、メッセージ</span><span class="sxs-lookup"><span data-stu-id="9708d-117">Overview information about the message</span></span>|  
|<span data-ttu-id="9708d-118">**コンテキスト**</span><span class="sxs-lookup"><span data-stu-id="9708d-118">**Context**</span></span>|<span data-ttu-id="9708d-119">このメッセージに関連付けられたコンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="9708d-119">Context properties associated with this message</span></span>|  
|<span data-ttu-id="9708d-120">**メッセージ部分**</span><span class="sxs-lookup"><span data-stu-id="9708d-120">**Message Parts**</span></span>|<span data-ttu-id="9708d-121">このメッセージ内に含まれる個々 のドキュメント ペイロード。</span><span class="sxs-lookup"><span data-stu-id="9708d-121">Individual document payload contained within this message.</span></span> <span data-ttu-id="9708d-122">各ドキュメントは、テキストまたはバイナリのいずれかとして表示できます。</span><span class="sxs-lookup"><span data-stu-id="9708d-122">Each document can be viewed as either text or binary:</span></span><br /><br /> <span data-ttu-id="9708d-123">テキスト形式のビューは、EDI テキスト ファイルなど、人間が判読できる形式で AS2 メッセージまたは MDN の内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="9708d-123">-   Text Format view shows the contents of the AS2 message or MDN in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="9708d-124">AS2 ヘッダー、EDI トレーラー、および個別の行には、各セグメントの EDI ペイロードを表示します。</span><span class="sxs-lookup"><span data-stu-id="9708d-124">This view shows the AS2 headers, EDI trailers, and EDI payload, with each segment on a separate line.</span></span><br /><span data-ttu-id="9708d-125">-バイナリ形式のビューは、区切りなしテキスト形式と、AS2 メッセージまたは MDN の場合は、各 ASCII 文字の 16 進数表記の表に、AS2 メッセージまたは MDN の内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="9708d-125">-   Binary Format view shows the contents of the AS2 message or MDN in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the AS2 message or MDN.</span></span>|
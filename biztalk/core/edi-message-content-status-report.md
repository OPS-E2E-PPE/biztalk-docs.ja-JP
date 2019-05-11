---
title: EDI メッセージ コンテンツのステータスのレポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29acab25-354d-42f0-b6e3-37ebca47addb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cdda1a3188809d9209d8acb2badc4c035724706
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350427"
---
# <a name="edi-message-content-status-report"></a><span data-ttu-id="53bdc-102">EDI メッセージ コンテンツのステータス レポート</span><span class="sxs-lookup"><span data-stu-id="53bdc-102">EDI Message Content Status Report</span></span>

## <a name="overview"></a><span data-ttu-id="53bdc-103">概要</span><span class="sxs-lookup"><span data-stu-id="53bdc-103">Overview</span></span>
<span data-ttu-id="53bdc-104">この状態レポートには、ヘッダーとトランザクション セットのペイロードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53bdc-104">This status report displays the headers and payload of a transaction set.</span></span> <span data-ttu-id="53bdc-105">このレポートを表示するには、トランザクション セットの詳細ステータス レポート内のトランザクション セットを右クリックし、をクリックして**トランザクション セット**します。</span><span class="sxs-lookup"><span data-stu-id="53bdc-105">You display this report by right-clicking a transaction set within the Transaction Set Details status report, and then clicking **View Transaction Set Content**.</span></span>  
  
 <span data-ttu-id="53bdc-106">このレポートは、選択した場合にのみ使用可能な**レポート用にトランザクション セット/ペイロードを格納**関連するパーティの EDI のプロパティ ダイアログ ボックスの 全般 ページのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="53bdc-106">This report is available only if you have selected the **Store transaction set/payload for reporting** property in the General Page of the EDI Properties dialog box for the related party.</span></span>  
  
 <span data-ttu-id="53bdc-107">このレポートは、コンテンツの 2 つのビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="53bdc-107">This report provides two views of the content:</span></span>  
  
-   <span data-ttu-id="53bdc-108">トランザクションの内容を表示するテキスト形式のビューは、EDI テキスト ファイルなど、人間が判読できる形式で設定します。</span><span class="sxs-lookup"><span data-stu-id="53bdc-108">A Text Format view that shows the contents of the transaction set in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="53bdc-109">このビューには、ペイロード、および個別の行には、各セグメントの SE トレーラのトランザクション セット、ST ヘッダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53bdc-109">This view shows the ST header, the transaction set payload, and the SE trailer, with each segment on a separate line.</span></span>  
  
-   <span data-ttu-id="53bdc-110">トランザクションの内容を表示するバイナリ形式のビューは、区切りなしテキスト形式と、トランザクション セット内の各 ASCII 文字の 16 進数表記の表に設定します。</span><span class="sxs-lookup"><span data-stu-id="53bdc-110">A Binary Format view that shows the contents of the transaction set in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the transaction set.</span></span>  
  

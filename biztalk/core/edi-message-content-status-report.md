---
title: "EDI メッセージ コンテンツのステータス レポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29acab25-354d-42f0-b6e3-37ebca47addb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62dbb260bb23e3ed5de7e8d416158a0e142c6c32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-content-status-report"></a><span data-ttu-id="132f5-102">EDI メッセージ コンテンツのステータス レポート</span><span class="sxs-lookup"><span data-stu-id="132f5-102">EDI Message Content Status Report</span></span>

## <a name="overview"></a><span data-ttu-id="132f5-103">概要</span><span class="sxs-lookup"><span data-stu-id="132f5-103">Overview</span></span>
<span data-ttu-id="132f5-104">この状態レポートには、トランザクション セットのヘッダーとペイロードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="132f5-104">This status report displays the headers and payload of a transaction set.</span></span> <span data-ttu-id="132f5-105">トランザクション セットの詳細ステータス レポート内のトランザクション セットを右クリックし、をクリックしてこのレポートを表示する**トランザクション セットのコンテンツ**です。</span><span class="sxs-lookup"><span data-stu-id="132f5-105">You display this report by right-clicking a transaction set within the Transaction Set Details status report, and then clicking **View Transaction Set Content**.</span></span>  
  
 <span data-ttu-id="132f5-106">このレポートは、選択した場合にのみ使用可能な**レポート用にトランザクション セット/ペイロードを格納**関連するパーティの EDI のプロパティ ダイアログ ボックスの 全般 ページのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="132f5-106">This report is available only if you have selected the **Store transaction set/payload for reporting** property in the General Page of the EDI Properties dialog box for the related party.</span></span>  
  
 <span data-ttu-id="132f5-107">このレポートには、次の 2 つのコンテンツ ビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="132f5-107">This report provides two views of the content:</span></span>  
  
-   <span data-ttu-id="132f5-108">トランザクション セットの内容を人間が判読できる形式 (EDI テキスト ファイルなど) で表示する、テキスト形式のビュー。</span><span class="sxs-lookup"><span data-stu-id="132f5-108">A Text Format view that shows the contents of the transaction set in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="132f5-109">このビューでは、ST ヘッダー、トランザクション セットのペイロード、および SE トレーラが表示されます。各セグメントは別々の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="132f5-109">This view shows the ST header, the transaction set payload, and the SE trailer, with each segment on a separate line.</span></span>  
  
-   <span data-ttu-id="132f5-110">区切りなしテキスト形式のトランザクション セットの内容と、トランザクション セットに含まれる各 ASCII 文字の 16 進数表記の表を表示する、バイナリ形式のビュー。</span><span class="sxs-lookup"><span data-stu-id="132f5-110">A Binary Format view that shows the contents of the transaction set in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the transaction set.</span></span>  
  

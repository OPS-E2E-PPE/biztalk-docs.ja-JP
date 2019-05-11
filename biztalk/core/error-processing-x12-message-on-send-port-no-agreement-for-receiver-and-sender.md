---
title: X12 の処理でエラーが発生しました。 送信ポートでメッセージ。契約受信者および送信者 id 修飾子のペアと名前のパーティは存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdf445e8-51a3-44fb-aa71-e0b0ab9c428f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33f187c2804032b881305652f76cd9e45cc081e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388511"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a><span data-ttu-id="beebb-102">X12 の処理でエラーが発生しました。 送信ポートでメッセージ。契約受信者および送信者 id 修飾子のペアと名前のパーティは存在しません</span><span class="sxs-lookup"><span data-stu-id="beebb-102">A failure occurred in processing X12 message on send port: No agreement for receiver and sender identifier-qualifier pairs and no party with name</span></span>
## <a name="details"></a><span data-ttu-id="beebb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="beebb-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="beebb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="beebb-104">Product Name</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="beebb-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="beebb-105">Product Version</span></span> |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="beebb-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="beebb-106">Event ID</span></span>     |                                                                                              -                                                                                               |
|  <span data-ttu-id="beebb-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="beebb-107">Event Source</span></span>   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="beebb-108">EDI</span><span class="sxs-lookup"><span data-stu-id="beebb-108">EDI</span></span>                                                    |
|    <span data-ttu-id="beebb-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="beebb-109">Component</span></span>    |                                                                                          <span data-ttu-id="beebb-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="beebb-110">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="beebb-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="beebb-111">Symbolic Name</span></span>  |                                                                                              -                                                                                               |
|  <span data-ttu-id="beebb-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="beebb-112">Message Text</span></span>   | <span data-ttu-id="beebb-113">X12 の処理でエラーが発生しました。 送信ポートでメッセージ{0}します。</span><span class="sxs-lookup"><span data-stu-id="beebb-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="beebb-114">受信者および送信者の識別子と修飾子の組み合わせのアグリーメントが存在しない{1}、 {2}、 {3}、{4}します。</span><span class="sxs-lookup"><span data-stu-id="beebb-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> <span data-ttu-id="beebb-115">名前のパーティが存在しない{5}します。</span><span class="sxs-lookup"><span data-stu-id="beebb-115">No Party exists with name {5}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="beebb-116">説明</span><span class="sxs-lookup"><span data-stu-id="beebb-116">Explanation</span></span>  
 <span data-ttu-id="beebb-117">このエラー/警告/情報イベントは、BizTalk Server が EDIFACT インターチェンジに BizTalk Server が一致するようにできなかったためには、送信者の修飾子と識別子のプロパティを昇格のパーティを解決できなかったし、受信者の修飾子を昇格することを示します、。パーティの対応する値の識別子プロパティ。</span><span class="sxs-lookup"><span data-stu-id="beebb-117">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="beebb-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="beebb-118">User Action</span></span>  
 <span data-ttu-id="beebb-119">このエラーを解決するには、一致するよう送信者の修飾子と識別子 (ISA5 および ISA6) および受信者の修飾子と識別子 (ISA7 と ISA8) が、EDI のプロパティ ダイアログ ボックスのパーティの ISA セグメントの定義 ページで定義されている、対応する昇格インターチェンジのコンテキスト内のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="beebb-119">To resolve this error, ensure that the sender qualifier and identifier (ISA5 and ISA6) and receiver qualifier and identifier (ISA7 and ISA8) defined in the party's ISA Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>
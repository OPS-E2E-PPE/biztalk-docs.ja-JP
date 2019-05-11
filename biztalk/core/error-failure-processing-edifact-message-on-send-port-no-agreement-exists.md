---
title: 送信ポートで Edifact メッセージの処理中にエラーが発生しました。契約受信者および送信者 id 修飾子のペアと名前のパーティは存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11880c7c-6032-449b-b251-27fc2b2f0d72
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd3df9a2635864f0dcc884426816f1674c9284c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389302"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a><span data-ttu-id="b71d0-102">送信ポートで Edifact メッセージの処理中にエラーが発生しました。契約受信者および送信者 id 修飾子のペアと名前のパーティは存在しません</span><span class="sxs-lookup"><span data-stu-id="b71d0-102">A failure occurred in processing Edifact message on send port: No agreement for receiver and sender identifier-qualifier pairs and no party with name</span></span>
## <a name="details"></a><span data-ttu-id="b71d0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b71d0-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b71d0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b71d0-104">Product Name</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| <span data-ttu-id="b71d0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b71d0-105">Product Version</span></span> |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    <span data-ttu-id="b71d0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b71d0-106">Event ID</span></span>     |                                                                                                -                                                                                                 |
|  <span data-ttu-id="b71d0-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b71d0-107">Event Source</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b71d0-108">EDI</span><span class="sxs-lookup"><span data-stu-id="b71d0-108">EDI</span></span>                                                      |
|    <span data-ttu-id="b71d0-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b71d0-109">Component</span></span>    |                                                                                            <span data-ttu-id="b71d0-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b71d0-110">EDI Engine</span></span>                                                                                            |
|  <span data-ttu-id="b71d0-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b71d0-111">Symbolic Name</span></span>  |                                                                                                -                                                                                                 |
|  <span data-ttu-id="b71d0-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b71d0-112">Message Text</span></span>   | <span data-ttu-id="b71d0-113">送信ポートで Edifact メッセージの処理中にエラーが発生しました{0}します。</span><span class="sxs-lookup"><span data-stu-id="b71d0-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="b71d0-114">受信者および送信者の識別子と修飾子の組み合わせのアグリーメントが存在しない{1}、 {2}、 {3}、{4}します。</span><span class="sxs-lookup"><span data-stu-id="b71d0-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> <span data-ttu-id="b71d0-115">名前のパーティが存在しない{5}します。</span><span class="sxs-lookup"><span data-stu-id="b71d0-115">No Party exists with name {5}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b71d0-116">説明</span><span class="sxs-lookup"><span data-stu-id="b71d0-116">Explanation</span></span>  
 <span data-ttu-id="b71d0-117">このエラー/警告/情報イベントは、BizTalk Server が EDIFACT インターチェンジのパーティを照合できなかったため、昇格の送信者の修飾子と識別子のプロパティを解決することができませんでしたと受信者の修飾子と識別子を昇格することを示します。プロパティでは、パーティの対応する値。</span><span class="sxs-lookup"><span data-stu-id="b71d0-117">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because it was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b71d0-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b71d0-118">User Action</span></span>  
 <span data-ttu-id="b71d0-119">このエラーを解決するには、一致するよう送信者の修飾子と識別子 (UNB2.1 と UNB2.2) および受信者の修飾子と識別子 (UNB3.1 と UNB3.2) が、EDI のプロパティ ダイアログ ボックスのパーティの UNB セグメントの定義 ページで定義されている、対応します。インターチェンジのコンテキストで昇格させたプロパティです。</span><span class="sxs-lookup"><span data-stu-id="b71d0-119">To resolve this error, ensure that the sender qualifier and identifier (UNB2.1 and UNB2.2) and receiver qualifier and identifier (UNB3.1 and UNB3.2) defined in the party's UNB Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>
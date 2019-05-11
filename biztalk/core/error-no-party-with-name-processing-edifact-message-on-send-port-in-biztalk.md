---
title: 送信ポートで Edifact メッセージの処理中にエラーが発生しました。名前のパーティは存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98884d7e3a2ab36faddb831ca2550120c345f1b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347186"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a><span data-ttu-id="ddcf8-102">送信ポートで Edifact メッセージの処理中にエラーが発生しました。名前のパーティは存在しません</span><span class="sxs-lookup"><span data-stu-id="ddcf8-102">A failure occurred in processing Edifact message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="ddcf8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ddcf8-103">Details</span></span>  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ddcf8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ddcf8-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| <span data-ttu-id="ddcf8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ddcf8-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    <span data-ttu-id="ddcf8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ddcf8-106">Event ID</span></span>     |                                                 -                                                 |
|  <span data-ttu-id="ddcf8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ddcf8-107">Event Source</span></span>   |                                        <span data-ttu-id="ddcf8-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="ddcf8-108">BizTalk Server EDI</span></span>                                         |
|    <span data-ttu-id="ddcf8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ddcf8-109">Component</span></span>    |                                            <span data-ttu-id="ddcf8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ddcf8-110">EDI Engine</span></span>                                             |
|  <span data-ttu-id="ddcf8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ddcf8-111">Symbolic Name</span></span>  |                                                 -                                                 |
|  <span data-ttu-id="ddcf8-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ddcf8-112">Message Text</span></span>   | <span data-ttu-id="ddcf8-113">送信ポートで Edifact メッセージの処理中にエラーが発生しました{0}します。</span><span class="sxs-lookup"><span data-stu-id="ddcf8-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="ddcf8-114">名前のパーティが存在しない{1}します。</span><span class="sxs-lookup"><span data-stu-id="ddcf8-114">No Party exists with name {1}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ddcf8-115">説明</span><span class="sxs-lookup"><span data-stu-id="ddcf8-115">Explanation</span></span>  
 <span data-ttu-id="ddcf8-116">このエラー/警告/情報イベントは、BizTalk Server が BizTalk Server がパーティに関連付けられている送信ポートと、インターチェンジをサブスクライブした送信ポートを一致するようにできなかったため、EDIFACT インターチェンジのパーティを解決するのにはできなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ddcf8-116">This Error/Warning/Information event indicates that BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="ddcf8-117">これは、DestinationPartyName プロパティも、送信者の修飾子および識別子と受信者の修飾子と識別子のプロパティが昇格される、そのため、送信側パーティの解決に使用できるもないかどうかに発生します。</span><span class="sxs-lookup"><span data-stu-id="ddcf8-117">This occurs if neither the DestinationPartyName property nor the sender qualifier and identifier and receiver qualifier and identifier properties are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddcf8-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ddcf8-118">User Action</span></span>  
 <span data-ttu-id="ddcf8-119">このエラーを解決するのには、インターチェンジをサブスクライブした送信ポートがパーティに関連付けられている送信ポートと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ddcf8-119">To resolve this error, ensure that the send port that subscribed to the interchange matches the send port associated with a party.</span></span>
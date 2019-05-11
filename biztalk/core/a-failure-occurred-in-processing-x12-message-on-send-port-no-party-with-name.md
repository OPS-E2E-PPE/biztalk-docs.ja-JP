---
title: X12 の処理でエラーが発生しました。 送信ポートでメッセージ。名前のパーティは存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af059a04-3b7c-48e2-a3bf-48ad62deb139
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efebb75a8d7b4989382f7c4855aab9b981c38c2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362436"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a><span data-ttu-id="a6b1d-102">X12 の処理でエラーが発生しました。 送信ポートでメッセージ。名前のパーティは存在しません</span><span class="sxs-lookup"><span data-stu-id="a6b1d-102">A failure occurred in processing X12 message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="a6b1d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a6b1d-103">Details</span></span>  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a6b1d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a6b1d-104">Product Name</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="a6b1d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a6b1d-105">Product Version</span></span> |                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    <span data-ttu-id="a6b1d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a6b1d-106">Event ID</span></span>     |                                               -                                               |
|  <span data-ttu-id="a6b1d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a6b1d-107">Event Source</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a6b1d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a6b1d-108">EDI</span></span>     |
|    <span data-ttu-id="a6b1d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a6b1d-109">Component</span></span>    |                                          <span data-ttu-id="a6b1d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="a6b1d-110">EDI Engine</span></span>                                           |
|  <span data-ttu-id="a6b1d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a6b1d-111">Symbolic Name</span></span>  |                                               -                                               |
|  <span data-ttu-id="a6b1d-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a6b1d-112">Message Text</span></span>   | <span data-ttu-id="a6b1d-113">X12 の処理でエラーが発生しました。 送信ポートでメッセージ{0}します。</span><span class="sxs-lookup"><span data-stu-id="a6b1d-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="a6b1d-114">名前のパーティが存在しない{1}します。</span><span class="sxs-lookup"><span data-stu-id="a6b1d-114">No Party exists with name {1}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a6b1d-115">説明</span><span class="sxs-lookup"><span data-stu-id="a6b1d-115">Explanation</span></span>  
 <span data-ttu-id="a6b1d-116">このエラー/警告/情報イベントは、BizTalk Server で x12 の場合、パーティを解決できなかったことを示しますインターチェンジの BizTalk Server がパーティに関連付けられている送信ポートと、インターチェンジをサブスクライブした送信ポートを一致するようにできなかったためです。</span><span class="sxs-lookup"><span data-stu-id="a6b1d-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the X12 interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="a6b1d-117">これは、DestinationPartyName プロパティも、送信者の修飾子、送信者の識別子、受信者の修飾子、および受信者の識別子のプロパティが昇格される、そのため、送信側パーティの解決に使用できるもないかどうかに発生します。</span><span class="sxs-lookup"><span data-stu-id="a6b1d-117">This occurs if neither the DestinationPartyName property, nor the sender qualifier, sender identifier, receiver qualifier, and receiver identifier properties, are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6b1d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a6b1d-118">User Action</span></span>  
 <span data-ttu-id="a6b1d-119">このエラーを解決するのには、インターチェンジをサブスクライブした送信ポートがパーティに関連付けられている送信ポートと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6b1d-119">To resolve this error, ensure the send port that subscribed to the interchange matches the send port associated with a party.</span></span>
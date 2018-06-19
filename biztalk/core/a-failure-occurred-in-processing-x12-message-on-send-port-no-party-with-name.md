---
title: 'X12 の処理中にエラーが発生した送信ポートでメッセージ: いいえパーティ名 |Microsoft ドキュメント'
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
ms.openlocfilehash: f0e620797d45fb0b3d2ef929865a4b8bb98d2d90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225354"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a><span data-ttu-id="be924-102">X12 の処理中にエラーが発生した送信ポートでメッセージ: いいえパーティ名</span><span class="sxs-lookup"><span data-stu-id="be924-102">A failure occurred in processing X12 message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="be924-103">詳細</span><span class="sxs-lookup"><span data-stu-id="be924-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be924-104">製品名</span><span class="sxs-lookup"><span data-stu-id="be924-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="be924-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="be924-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="be924-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="be924-106">Event ID</span></span>|-|  
|<span data-ttu-id="be924-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="be924-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="be924-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="be924-108"> EDI</span></span>|  
|<span data-ttu-id="be924-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be924-109">Component</span></span>|<span data-ttu-id="be924-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="be924-110">EDI Engine</span></span>|  
|<span data-ttu-id="be924-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="be924-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="be924-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="be924-112">Message Text</span></span>|<span data-ttu-id="be924-113">送信ポート {0} で X12 メッセージの処理中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="be924-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="be924-114">名前 {1} のパーティが存在しません。</span><span class="sxs-lookup"><span data-stu-id="be924-114">No Party exists with name {1}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be924-115">説明</span><span class="sxs-lookup"><span data-stu-id="be924-115">Explanation</span></span>  
 <span data-ttu-id="be924-116">このエラー/警告/情報イベントは、パーティに関連付けられている送信ポートと、インターチェンジをサブスクライブした送信ポートが一致しなかったため、BizTalk Server が X12 インターチェンジのパーティを解決できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="be924-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the X12 interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="be924-117">このイベントが発生するのは、DestinationPartyName プロパティと、送信者の修飾子、送信者の識別子、受信者の修飾子、および受信者の識別子の各プロパティが昇格されないため、送信側パーティの解決にそれらのプロパティを利用できない場合です。</span><span class="sxs-lookup"><span data-stu-id="be924-117">This occurs if neither the DestinationPartyName property, nor the sender qualifier, sender identifier, receiver qualifier, and receiver identifier properties, are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be924-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="be924-118">User Action</span></span>  
 <span data-ttu-id="be924-119">このエラーを解決するには、インターチェンジをサブクライブした送信ポートが、パーティに関連付けられている送信ポートに一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="be924-119">To resolve this error, ensure the send port that subscribed to the interchange matches the send port associated with a party.</span></span>
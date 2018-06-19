---
title: '送信ポートで Edifact メッセージの処理中にエラーが発生しました: 名前のないパーティ |Microsoft ドキュメント'
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
ms.openlocfilehash: 6becad3fefaa8167c9cf1af051731aa08be0d80a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005155"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a><span data-ttu-id="8fc06-102">送信ポートで Edifact メッセージの処理中にエラーが発生しました: 名前のないパーティ</span><span class="sxs-lookup"><span data-stu-id="8fc06-102">A failure occurred in processing Edifact message on send port: No Party with name</span></span>
## <a name="details"></a><span data-ttu-id="8fc06-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8fc06-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8fc06-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8fc06-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8fc06-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8fc06-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8fc06-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8fc06-106">Event ID</span></span>|-|  
|<span data-ttu-id="8fc06-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8fc06-107">Event Source</span></span>|<span data-ttu-id="8fc06-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="8fc06-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="8fc06-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8fc06-109">Component</span></span>|<span data-ttu-id="8fc06-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8fc06-110">EDI Engine</span></span>|  
|<span data-ttu-id="8fc06-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8fc06-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="8fc06-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8fc06-112">Message Text</span></span>|<span data-ttu-id="8fc06-113">送信ポート {0} で Edifact メッセージの処理中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8fc06-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="8fc06-114">名前 {1} のパーティが存在しません。</span><span class="sxs-lookup"><span data-stu-id="8fc06-114">No Party exists with name {1}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8fc06-115">説明</span><span class="sxs-lookup"><span data-stu-id="8fc06-115">Explanation</span></span>  
 <span data-ttu-id="8fc06-116">このエラー/警告/情報イベントは、パーティに関連付けられている送信ポートと、インターチェンジをサブスクライブした送信ポートが一致しなかったため、BizTalk Server が EDIFACT インターチェンジのパーティを解決できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8fc06-116">This Error/Warning/Information event indicates that BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match the send port that subscribed to the interchange with the send port associated with a party.</span></span> <span data-ttu-id="8fc06-117">このイベントが発生するのは、DestinationPartyName プロパティと、送信者の修飾子と識別子のプロパティおよび受信者の修飾子と識別子のプロパティのどちらも昇格されないため、送信側パーティの解決にそれらのプロパティを利用できない場合です。</span><span class="sxs-lookup"><span data-stu-id="8fc06-117">This occurs if neither the DestinationPartyName property nor the sender qualifier and identifier and receiver qualifier and identifier properties are promoted, so are unavailable for send-side party resolution.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8fc06-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8fc06-118">User Action</span></span>  
 <span data-ttu-id="8fc06-119">このエラーを解決するのには、インターチェンジをサブスクライブした送信ポートがパーティに関連付けられている送信ポートと一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8fc06-119">To resolve this error, ensure that the send port that subscribed to the interchange matches the send port associated with a party.</span></span>
---
title: パーティに関連付けられている送信ポートがあるために、バッチ メッセージをシリアル化することはできません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d697ff9c-a6d1-4a3c-9ec3-4cd496f7eec2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b20d10a2c7b584eccc7d1fb57e5132a4ac0d608
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241482"
---
# <a name="batch-message-cannot-be-serialized-as-there-is-no-party-associated-with-send-port"></a><span data-ttu-id="60396-102">送信ポートに関連付けられたパーティが存在しないため、バッチ メッセージをシリアル化できません</span><span class="sxs-lookup"><span data-stu-id="60396-102">Batch message cannot be serialized as there is no party associated with send port</span></span>
## <a name="details"></a><span data-ttu-id="60396-103">詳細</span><span class="sxs-lookup"><span data-stu-id="60396-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60396-104">製品名</span><span class="sxs-lookup"><span data-stu-id="60396-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="60396-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="60396-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="60396-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="60396-106">Event ID</span></span>|-|  
|<span data-ttu-id="60396-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="60396-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="60396-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="60396-108"> EDI</span></span>|  
|<span data-ttu-id="60396-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="60396-109">Component</span></span>|<span data-ttu-id="60396-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="60396-110">Batching Engine</span></span>|  
|<span data-ttu-id="60396-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="60396-111">Symbolic Name</span></span>|<span data-ttu-id="60396-112">BatchMessageSerializationFailureDueToMissingParty</span><span class="sxs-lookup"><span data-stu-id="60396-112">BatchMessageSerializationFailureDueToMissingParty</span></span>|  
|<span data-ttu-id="60396-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="60396-113">Message Text</span></span>|<span data-ttu-id="60396-114">送信ポート {0} に関連付けられたパーティが存在しないため、バッチ メッセージをシリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="60396-114">Batch message can not be serialized as there is no party associated with send port {0}.</span></span> <span data-ttu-id="60396-115">パーティがポートに関連付けられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="60396-115">Make sure that a party is associated with the port</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60396-116">説明</span><span class="sxs-lookup"><span data-stu-id="60396-116">Explanation</span></span>  
 <span data-ttu-id="60396-117">このエラー/警告/情報イベントは、メッセージの送信先となるパーティを特定できなかったため、送信パイプラインが、保存されたインターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="60396-117">This Error/Warning/Information event indicates that the send pipeline could not process a preserved interchange because it could not determine the party that the message should be sent to.</span></span> <span data-ttu-id="60396-118">パーティを特定できなかったのは、DestinationPartyName コンテキスト プロパティが設定されていなかったためです。</span><span class="sxs-lookup"><span data-stu-id="60396-118">It could not determine the party because the DestinationPartyName context property was not set.</span></span> <span data-ttu-id="60396-119">その結果、送信パイプラインはエンベロープの設定を特定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="60396-119">As a result, the send pipeline could not determine the envelope settings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60396-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="60396-120">User Action</span></span>  
 <span data-ttu-id="60396-121">このエラーを解決するには、パススルー送信パイプライン経由でメッセージを渡し、メッセージの DestinationPartyName コンテキスト プロパティを決定します。</span><span class="sxs-lookup"><span data-stu-id="60396-121">To resolve this error, pass the message through a passthrough send pipeline, and then determine the DestinationPartyName context property for the message.</span></span> <span data-ttu-id="60396-122">そのパーティが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="60396-122">Verify that the party exists.</span></span> <span data-ttu-id="60396-123">存在しない場合は、パーティを作成し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="60396-123">If not, create the party, and then resend the message.</span></span>
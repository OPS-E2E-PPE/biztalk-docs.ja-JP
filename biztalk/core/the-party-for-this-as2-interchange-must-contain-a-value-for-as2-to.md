---
title: "この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-に |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 029eae5d-4c13-402d-90c5-8e9ef3814a1f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4adda90c2ae0e5dfa659e3bd36dcadfc58f815ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a><span data-ttu-id="77046-102">この AS2 インターチェンジのパーティには、AS2-To の値が含まれている必要があります</span><span class="sxs-lookup"><span data-stu-id="77046-102">The party for this AS2 interchange must contain a value for AS2-To</span></span>
## <a name="details"></a><span data-ttu-id="77046-103">詳細</span><span class="sxs-lookup"><span data-stu-id="77046-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77046-104">製品名</span><span class="sxs-lookup"><span data-stu-id="77046-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="77046-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="77046-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="77046-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77046-106">Event ID</span></span>|-|  
|<span data-ttu-id="77046-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="77046-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="77046-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="77046-108"> EDI</span></span>|  
|<span data-ttu-id="77046-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77046-109">Component</span></span>|<span data-ttu-id="77046-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="77046-110">AS2 Engine</span></span>|  
|<span data-ttu-id="77046-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="77046-111">Symbolic Name</span></span>|<span data-ttu-id="77046-112">InvalidAgreementAS2ToName</span><span class="sxs-lookup"><span data-stu-id="77046-112">InvalidAgreementAS2ToName</span></span>|  
|<span data-ttu-id="77046-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="77046-113">Message Text</span></span>|<span data-ttu-id="77046-114">この AS2 インターチェンジのパーティには、AS2-To の値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="77046-114">The party for this AS2 interchange must contain a value for AS2-To.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77046-115">説明</span><span class="sxs-lookup"><span data-stu-id="77046-115">Explanation</span></span>  
 <span data-ttu-id="77046-116">このエラー/警告/情報イベントは、メッセージの受信者として解決されるパーティの AS2-To プロパティが設定されていなかったため、送信パイプラインで送信 AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="77046-116">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing AS2 message because the AS2-To property was not set for the resolved party as message receiver.</span></span> <span data-ttu-id="77046-117">これは、送信 AS2 メッセージのパーティが、パーティに関連付けられた送信ポートとメッセージをサブスクライブした送信ポートの照合によって解決されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="77046-117">This indicates that the party for the outgoing AS2 message was resolved by matching the send port associated with the party with the send port that subscribed to the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77046-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="77046-118">User Action</span></span>  
 <span data-ttu-id="77046-119">このエラーを解決するには、次のように操作を行います。</span><span class="sxs-lookup"><span data-stu-id="77046-119">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="77046-120">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="77046-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="77046-121">[パーティ] ノードに移動し、メッセージに関して解決されるパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="77046-121">Move to the Parties node, and open the AS2 Properties dialog box for the party resolved for the message.</span></span>  
  
3.  <span data-ttu-id="77046-122">[パーティ - AS2 メッセージの受信者] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="77046-122">Click the Party as AS2 Message Receiver node.</span></span>  
  
4.  <span data-ttu-id="77046-123">AS2-To プロパティの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="77046-123">Enter a value for the AS2-To property.</span></span>
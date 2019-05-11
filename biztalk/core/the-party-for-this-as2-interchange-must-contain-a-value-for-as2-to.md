---
title: この AS2 インターチェンジのパーティが AS2 の値を含める必要がありますを |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029eae5d-4c13-402d-90c5-8e9ef3814a1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccabce0ce60f018f6d55d64a26c1f9540ed88fa2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394104"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a><span data-ttu-id="19176-102">この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-を</span><span class="sxs-lookup"><span data-stu-id="19176-102">The party for this AS2 interchange must contain a value for AS2-To</span></span>
## <a name="details"></a><span data-ttu-id="19176-103">詳細</span><span class="sxs-lookup"><span data-stu-id="19176-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="19176-104">製品名</span><span class="sxs-lookup"><span data-stu-id="19176-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="19176-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="19176-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="19176-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="19176-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="19176-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="19176-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="19176-108">EDI</span><span class="sxs-lookup"><span data-stu-id="19176-108">EDI</span></span> |
|    <span data-ttu-id="19176-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="19176-109">Component</span></span>    |                                       <span data-ttu-id="19176-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="19176-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="19176-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="19176-111">Symbolic Name</span></span>  |                               <span data-ttu-id="19176-112">InvalidAgreementAS2ToName</span><span class="sxs-lookup"><span data-stu-id="19176-112">InvalidAgreementAS2ToName</span></span>                                |
|  <span data-ttu-id="19176-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="19176-113">Message Text</span></span>   |          <span data-ttu-id="19176-114">この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-にします。</span><span class="sxs-lookup"><span data-stu-id="19176-114">The party for this AS2 interchange must contain a value for AS2-To.</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="19176-115">説明</span><span class="sxs-lookup"><span data-stu-id="19176-115">Explanation</span></span>  
 <span data-ttu-id="19176-116">このエラー/警告/情報イベントは、エントリのため、送信パイプラインが送信 AS2 メッセージが処理しないことを示します、AS2 のプロパティにはメッセージの受信者として解決されるパーティは設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="19176-116">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing AS2 message because the AS2-To property was not set for the resolved party as message receiver.</span></span> <span data-ttu-id="19176-117">これは、送信 AS2 メッセージのパーティがメッセージにサブスクライブする送信ポートとパーティに関連付けられている送信ポートを照合することによって解決されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="19176-117">This indicates that the party for the outgoing AS2 message was resolved by matching the send port associated with the party with the send port that subscribed to the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19176-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="19176-118">User Action</span></span>  
 <span data-ttu-id="19176-119">このエラーを解決するには、次のように操作を行います。</span><span class="sxs-lookup"><span data-stu-id="19176-119">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="19176-120">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="19176-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="19176-121">パーティ ノードに移動し、メッセージに対して解決されるパーティの AS2 のプロパティ ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="19176-121">Move to the Parties node, and open the AS2 Properties dialog box for the party resolved for the message.</span></span>  
  
3.  <span data-ttu-id="19176-122">AS2 メッセージの受信者 ノードには、パーティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19176-122">Click the Party as AS2 Message Receiver node.</span></span>  
  
4.  <span data-ttu-id="19176-123">AS2 の値を入力、プロパティにします。</span><span class="sxs-lookup"><span data-stu-id="19176-123">Enter a value for the AS2-To property.</span></span>
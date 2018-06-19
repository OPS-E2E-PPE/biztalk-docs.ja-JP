---
title: この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-から |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d338759-5646-4dc2-8319-a42aaa8c3d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b52f153cce06eac014d98fa1908978694fc67706
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278778"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-from"></a><span data-ttu-id="aa933-102">この AS2 インターチェンジのパーティには、AS2-From の値が含まれている必要があります</span><span class="sxs-lookup"><span data-stu-id="aa933-102">The party for this AS2 interchange must contain a value for AS2-From</span></span>
## <a name="details"></a><span data-ttu-id="aa933-103">詳細</span><span class="sxs-lookup"><span data-stu-id="aa933-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa933-104">製品名</span><span class="sxs-lookup"><span data-stu-id="aa933-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="aa933-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="aa933-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="aa933-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aa933-106">Event ID</span></span>|-|  
|<span data-ttu-id="aa933-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="aa933-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="aa933-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="aa933-108"> EDI</span></span>|  
|<span data-ttu-id="aa933-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aa933-109">Component</span></span>|<span data-ttu-id="aa933-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="aa933-110">AS2 Engine</span></span>|  
|<span data-ttu-id="aa933-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="aa933-111">Symbolic Name</span></span>|<span data-ttu-id="aa933-112">InvalidAgreementAS2FromName</span><span class="sxs-lookup"><span data-stu-id="aa933-112">InvalidAgreementAS2FromName</span></span>|  
|<span data-ttu-id="aa933-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="aa933-113">Message Text</span></span>|<span data-ttu-id="aa933-114">この AS2 インターチェンジのパーティには、AS2-From の値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa933-114">The party for this AS2 interchange must contain a value for AS2-From.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa933-115">説明</span><span class="sxs-lookup"><span data-stu-id="aa933-115">Explanation</span></span>  
 <span data-ttu-id="aa933-116">このエラー/警告/情報イベントは、メッセージの受信者として解決されるパーティの AS2-From プロパティが設定されていなかったため、送信パイプラインで AS2 メッセージを送信できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="aa933-116">This Error/Warning/Information event indicates that the send pipeline could not send the AS2 message because the AS2-From property was not set for the resolved party as message receiver.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa933-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="aa933-117">User Action</span></span>  
 <span data-ttu-id="aa933-118">このエラーを解決するには、BizTalk Server 管理コンソールを開き、[パーティ] ノードに移動して、メッセージに対して解決されるパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[パーティ - AS2 メッセージの受信者] ノードをクリックし、AS2-From プロパティの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa933-118">To resolve this error, open the BizTalk Server Administration Console, move to the Parties node, open the AS2 Properties dialog box for the party resolved for the message, click the Party as AS2 Message Receiver node, and then enter a value for the AS2-From property.</span></span>
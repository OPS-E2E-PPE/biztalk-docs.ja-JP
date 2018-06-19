---
title: このインスタンスがパートナーの [Batching Service] ウィンドウの範囲外 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e420d75-11fd-4221-9d97-814ca6e48c81
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e93e7e769a8f0e30b3753af690a69c5e6eaa9786
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278666"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a><span data-ttu-id="2cc4a-102">このインスタンスはパートナーの [Batching Service] ウィンドウ内にありません</span><span class="sxs-lookup"><span data-stu-id="2cc4a-102">This instance is outside the Batching Service window for the partner</span></span>
## <a name="details"></a><span data-ttu-id="2cc4a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2cc4a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2cc4a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2cc4a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2cc4a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2cc4a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2cc4a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2cc4a-106">Event ID</span></span>|-|  
|<span data-ttu-id="2cc4a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2cc4a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2cc4a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="2cc4a-108"> EDI</span></span>|  
|<span data-ttu-id="2cc4a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2cc4a-109">Component</span></span>|<span data-ttu-id="2cc4a-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="2cc4a-110">Batching Engine</span></span>|  
|<span data-ttu-id="2cc4a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2cc4a-111">Symbolic Name</span></span>|<span data-ttu-id="2cc4a-112">OutsideBatchingServiceWindow</span><span class="sxs-lookup"><span data-stu-id="2cc4a-112">OutsideBatchingServiceWindow</span></span>|  
|<span data-ttu-id="2cc4a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2cc4a-113">Message Text</span></span>|<span data-ttu-id="2cc4a-114">このインスタンスはパートナーの [Batching Service] ウィンドウ内にありません</span><span class="sxs-lookup"><span data-stu-id="2cc4a-114">This instance is outside the Batching Service window for the partner</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2cc4a-115">説明</span><span class="sxs-lookup"><span data-stu-id="2cc4a-115">Explanation</span></span>  
 <span data-ttu-id="2cc4a-116">このエラー/警告/情報イベントは、バッチ処理オーケストレーションのインスタンスがパーティのアクティベーションの範囲外であったため、インスタンスを開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="2cc4a-116">This Error/Warning/Information event indicates that an instance of the batching orchestration could not be started because the instance fell outside the activation range for the party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2cc4a-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2cc4a-117">User Action</span></span>  
 <span data-ttu-id="2cc4a-118">このエラーを解決するには、パーティの [EDI のプロパティ] の [インターチェンジのバッチ作成用の設定] ページを開き、オーケストレーション インスタンスがアクティベーションの範囲内にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2cc4a-118">To resolve this error, open the Interchange Batch Creations Settings page of the EDI Properties for the party, and make sure that the orchestration instance is within the activation range.</span></span> <span data-ttu-id="2cc4a-119">以外の場合、開始時刻 プロパティを変更し、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="2cc4a-119">If not, change the Start time property and then click **Start**.</span></span>
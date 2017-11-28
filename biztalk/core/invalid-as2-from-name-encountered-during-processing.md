---
title: "無効な AS2 の処理中に発生した名前から |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba658119-9171-4851-835c-72c188275b73
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 819d059f0d59f59164ab80eeb4501e5cd52ce7b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-from-name-encountered-during-processing"></a><span data-ttu-id="14aa9-102">処理中に無効な AS2-From 名を検出しました</span><span class="sxs-lookup"><span data-stu-id="14aa9-102">Invalid AS2-From name encountered during processing</span></span>
## <a name="details"></a><span data-ttu-id="14aa9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="14aa9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14aa9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="14aa9-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="14aa9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="14aa9-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="14aa9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="14aa9-106">Event ID</span></span>|-|  
|<span data-ttu-id="14aa9-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="14aa9-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14aa9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="14aa9-108"> EDI</span></span>|  
|<span data-ttu-id="14aa9-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="14aa9-109">Component</span></span>|<span data-ttu-id="14aa9-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="14aa9-110">AS2 Engine</span></span>|  
|<span data-ttu-id="14aa9-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="14aa9-111">Symbolic Name</span></span>|<span data-ttu-id="14aa9-112">InvalidAS2FromNameEncounteredError</span><span class="sxs-lookup"><span data-stu-id="14aa9-112">InvalidAS2FromNameEncounteredError</span></span>|  
|<span data-ttu-id="14aa9-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="14aa9-113">Message Text</span></span>|<span data-ttu-id="14aa9-114">処理中に無効な AS2-From 名を検出しました。</span><span class="sxs-lookup"><span data-stu-id="14aa9-114">Invalid AS2-From name encountered during processing.</span></span>  <span data-ttu-id="14aa9-115">値: {0}</span><span class="sxs-lookup"><span data-stu-id="14aa9-115">Value: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14aa9-116">説明</span><span class="sxs-lookup"><span data-stu-id="14aa9-116">Explanation</span></span>  
 <span data-ttu-id="14aa9-117">このエラー/警告/情報イベントは、AS2-From ヘッダーの値が、AS2 RFC 4130 の仕様に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="14aa9-117">This Error/Warning/Information event indicates that either the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the value of the AS2-From header did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14aa9-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="14aa9-118">User Action</span></span>  
 <span data-ttu-id="14aa9-119">このエラーを解決するには、受信メッセージまたは送信メッセージの AS2-From ヘッダーが AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="14aa9-119">To resolve this error, make sure that the AS2-From header in the incoming or outgoing message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>
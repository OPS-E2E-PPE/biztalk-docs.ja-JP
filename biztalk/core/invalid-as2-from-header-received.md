---
title: "無効な AS2 のヘッダーを受信しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d773e09-8526-4533-9066-8e743e65a688
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f20a74e60a6365c0c16e139e8b2caca1bc33646
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-from-header-received"></a><span data-ttu-id="9a7b3-102">無効な AS2-From ヘッダーを受信しました</span><span class="sxs-lookup"><span data-stu-id="9a7b3-102">Invalid AS2-From header received</span></span>
## <a name="details"></a><span data-ttu-id="9a7b3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9a7b3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a7b3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9a7b3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9a7b3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9a7b3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9a7b3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9a7b3-106">Event ID</span></span>|-|  
|<span data-ttu-id="9a7b3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9a7b3-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9a7b3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9a7b3-108"> EDI</span></span>|  
|<span data-ttu-id="9a7b3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9a7b3-109">Component</span></span>|<span data-ttu-id="9a7b3-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9a7b3-110">AS2 Engine</span></span>|  
|<span data-ttu-id="9a7b3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9a7b3-111">Symbolic Name</span></span>|<span data-ttu-id="9a7b3-112">InvalidAS2FromNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="9a7b3-112">InvalidAS2FromNameHeaderReceivedError</span></span>|  
|<span data-ttu-id="9a7b3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9a7b3-113">Message Text</span></span>|<span data-ttu-id="9a7b3-114">無効な AS2-From ヘッダーを受信しました。</span><span class="sxs-lookup"><span data-stu-id="9a7b3-114">Invalid AS2-From header received.</span></span>  <span data-ttu-id="9a7b3-115">値: {0}</span><span class="sxs-lookup"><span data-stu-id="9a7b3-115">Value: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9a7b3-116">説明</span><span class="sxs-lookup"><span data-stu-id="9a7b3-116">Explanation</span></span>  
 <span data-ttu-id="9a7b3-117">このエラー/警告/情報イベントは、メッセージの AS2-From ヘッダーの値が AS2 RFC 4130 の仕様に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9a7b3-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-From header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a7b3-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9a7b3-118">User Action</span></span>  
 <span data-ttu-id="9a7b3-119">このエラーを解決するには、メッセージの AS2-From ヘッダーの値が AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="9a7b3-119">To resolve this error, make sure that the value in the AS2-From header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>
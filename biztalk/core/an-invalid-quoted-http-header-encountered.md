---
title: "無効な HTTP ヘッダーが検出されました引用符で囲まれた |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb530ee6-ec6a-4791-ae99-b9db426c0896
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e154e3bacf34025edd837516a15dca6f2caa174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="an-invalid-quoted-http-header-encountered"></a><span data-ttu-id="3bf10-102">引用符で囲まれた無効な HTTP ヘッダーが検出されました</span><span class="sxs-lookup"><span data-stu-id="3bf10-102">An invalid quoted HTTP header encountered</span></span>
## <a name="details"></a><span data-ttu-id="3bf10-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3bf10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3bf10-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3bf10-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3bf10-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3bf10-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3bf10-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3bf10-106">Event ID</span></span>|-|  
|<span data-ttu-id="3bf10-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3bf10-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3bf10-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3bf10-108"> EDI</span></span>|  
|<span data-ttu-id="3bf10-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3bf10-109">Component</span></span>|<span data-ttu-id="3bf10-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="3bf10-110">AS2 Engine</span></span>|  
|<span data-ttu-id="3bf10-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3bf10-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="3bf10-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3bf10-112">Message Text</span></span>|<span data-ttu-id="3bf10-113">引用符で囲まれた無効な HTTP ヘッダーが検出されました。</span><span class="sxs-lookup"><span data-stu-id="3bf10-113">An invalid quoted HTTP header encountered.</span></span>  <span data-ttu-id="3bf10-114">詳細については次のようにしますヘッダー名:"{0}"ヘッダーの値:"{1}"。</span><span class="sxs-lookup"><span data-stu-id="3bf10-114">Details are as follows:  Header Name: "{0}"  Header Value: "{1}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3bf10-115">説明</span><span class="sxs-lookup"><span data-stu-id="3bf10-115">Explanation</span></span>  
 <span data-ttu-id="3bf10-116">このエラー/警告/情報イベントは、メッセージの AS2-From または AS2-To HTTP ヘッダーの名前が正しく引用符で囲まれていなかったため、AS2 受信パイプラインまたは AS2 送信パイプラインで AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3bf10-116">This Error/Warning/Information event indicates that the AS2 receive pipeline or the AS2 send pipeline could not process the AS2 message because the name of the AS2-From or AS2-To HTTP header in the message was not quoted correctly.</span></span> <span data-ttu-id="3bf10-117">ヘッダー名は、名前内でスペース、バックスラッシュ、または二重引用符に対応するために、引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="3bf10-117">The header name is quoted in order to accommodate a space, backslash, or double quotes within the name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3bf10-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3bf10-118">User Action</span></span>  
 <span data-ttu-id="3bf10-119">このエラーを解決するには、RFC 4130「MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」のセクション 6.2「AS2 System Identifiers」に記載されているルールに従って、AS2 メッセージのヘッダー名を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="3bf10-119">To resolve this error, quote the header name in the AS2 message in accordance with the rules stated in section 6.2, "AS2 System Identifiers", in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)".</span></span>
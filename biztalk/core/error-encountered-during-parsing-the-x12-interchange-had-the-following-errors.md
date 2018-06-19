---
title: 解析中にエラーが発生しました。 X12 インターチェンジ次のエラーが発生しました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c1085d4-75ef-4f63-84c9-287a4a61274a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94b9907667a7f99c1ecf8c2dc326fe32e134abf3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240130"
---
# <a name="error-encountered-during-parsing-the-x12-interchange-had-the-following-errors"></a><span data-ttu-id="52a63-103">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="52a63-103">Error encountered during parsing.</span></span> <span data-ttu-id="52a63-104">X12 インターチェンジに次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="52a63-104">The X12 interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="52a63-105">詳細</span><span class="sxs-lookup"><span data-stu-id="52a63-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52a63-106">製品名</span><span class="sxs-lookup"><span data-stu-id="52a63-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="52a63-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="52a63-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="52a63-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="52a63-108">Event ID</span></span>|-|  
|<span data-ttu-id="52a63-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="52a63-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="52a63-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="52a63-110"> EDI</span></span>|  
|<span data-ttu-id="52a63-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="52a63-111">Component</span></span>|<span data-ttu-id="52a63-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="52a63-112">EDI Engine</span></span>|  
|<span data-ttu-id="52a63-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="52a63-113">Symbolic Name</span></span>|<span data-ttu-id="52a63-114">X12InterchangeReceiveError</span><span class="sxs-lookup"><span data-stu-id="52a63-114">X12InterchangeReceiveError</span></span>|  
|<span data-ttu-id="52a63-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="52a63-115">Message Text</span></span>|<span data-ttu-id="52a63-116">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="52a63-116">Error encountered during parsing.</span></span> <span data-ttu-id="52a63-117">X12 インターチェンジの送信者 id '{1}'、受信者 id '{2}' に '{0}'、id を次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="52a63-117">The X12 interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="52a63-118">説明</span><span class="sxs-lookup"><span data-stu-id="52a63-118">Explanation</span></span>  
 <span data-ttu-id="52a63-119">このエラー/警告/情報イベントは、示されたエラーがインターチェンジにあるため、受信 X12 インターチェンジを解析しているときに EDI 受信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="52a63-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="52a63-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="52a63-120">User Action</span></span>  
 <span data-ttu-id="52a63-121">このエラーを解決するには、エラー メッセージの情報を使用してインターチェンジのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="52a63-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>
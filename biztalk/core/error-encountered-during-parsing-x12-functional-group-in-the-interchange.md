---
title: "解析中にエラーが発生しました。 X12 機能グループ、インターチェンジで次のエラーが発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2229c83-89bd-491f-9504-4afbf0084297
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e519e8f89f00574ad2b51c1f9884889077c902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-x12-functional-group-in-the-interchange-had-the-following-errors"></a><span data-ttu-id="8b745-103">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8b745-103">Error encountered during parsing.</span></span> <span data-ttu-id="8b745-104">インターチェンジ内の X12 機能グループに次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="8b745-104">The X12 functional group in the interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="8b745-105">詳細</span><span class="sxs-lookup"><span data-stu-id="8b745-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b745-106">製品名</span><span class="sxs-lookup"><span data-stu-id="8b745-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8b745-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8b745-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8b745-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8b745-108">Event ID</span></span>|-|  
|<span data-ttu-id="8b745-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8b745-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8b745-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="8b745-110"> EDI</span></span>|  
|<span data-ttu-id="8b745-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8b745-111">Component</span></span>|<span data-ttu-id="8b745-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8b745-112">EDI Engine</span></span>|  
|<span data-ttu-id="8b745-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8b745-113">Symbolic Name</span></span>|<span data-ttu-id="8b745-114">X12FunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="8b745-114">X12FunctionalGroupReceiveError</span></span>|  
|<span data-ttu-id="8b745-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8b745-115">Message Text</span></span>|<span data-ttu-id="8b745-116">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8b745-116">Error encountered during parsing.</span></span> <span data-ttu-id="8b745-117">受信者 id '{0}'、id '{1}' を持つインターチェンジの送信者 id '{2}' の X12 機能グループ id '{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8b745-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8b745-118">説明</span><span class="sxs-lookup"><span data-stu-id="8b745-118">Explanation</span></span>  
 <span data-ttu-id="8b745-119">このエラー/警告/情報イベントは、識別された機能グループで、示されたエラーが発生したため、受信 X12 インターチェンジを解析しているときに EDI 受信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="8b745-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8b745-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8b745-120">User Action</span></span>  
 <span data-ttu-id="8b745-121">このエラーを解決するには、エラー メッセージの情報を使用してグループのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8b745-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>
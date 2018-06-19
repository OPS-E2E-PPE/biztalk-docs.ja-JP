---
title: シリアル化中にエラーが発生しました。 X12 機能グループが、次のエラーがありました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c6b74d713f0d182a07cc6a509cd7d06fc34b82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290058"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a><span data-ttu-id="722e0-103">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="722e0-103">Error encountered during serialization.</span></span> <span data-ttu-id="722e0-104">X12 機能グループに次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="722e0-104">The X12 functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="722e0-105">詳細</span><span class="sxs-lookup"><span data-stu-id="722e0-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="722e0-106">製品名</span><span class="sxs-lookup"><span data-stu-id="722e0-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="722e0-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="722e0-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="722e0-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="722e0-108">Event ID</span></span>|-|  
|<span data-ttu-id="722e0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="722e0-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="722e0-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="722e0-110"> EDI</span></span>|  
|<span data-ttu-id="722e0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="722e0-111">Component</span></span>|<span data-ttu-id="722e0-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="722e0-112">EDI Engine</span></span>|  
|<span data-ttu-id="722e0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="722e0-113">Symbolic Name</span></span>|<span data-ttu-id="722e0-114">X12FunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="722e0-114">X12FunctionalGroupSendError</span></span>|  
|<span data-ttu-id="722e0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="722e0-115">Message Text</span></span>|<span data-ttu-id="722e0-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="722e0-116">Error encountered during serialization.</span></span> <span data-ttu-id="722e0-117">受信者 id '{0}'、id '{1}' を持つインターチェンジの送信者 id '{2}' の X12 機能グループ id '{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="722e0-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="722e0-118">説明</span><span class="sxs-lookup"><span data-stu-id="722e0-118">Explanation</span></span>  
 <span data-ttu-id="722e0-119">このエラー/警告/情報イベントは、識別された機能グループに、示されたエラーがあったため、X12 の送信インターチェンジのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="722e0-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="722e0-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="722e0-120">User Action</span></span>  
 <span data-ttu-id="722e0-121">このエラーを解決するには、エラー メッセージの情報を使用して機能グループのエラーを特定し、製品のヘルプで問題解決の方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="722e0-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the product help.</span></span>
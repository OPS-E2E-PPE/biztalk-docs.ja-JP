---
title: シリアル化中にエラーが発生しました。 Edifact 機能グループ次のエラーが発生しました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed81bc79-d99c-4305-805f-ab38eae91ea0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a8166e5a66038d4cbda3a6fcb9597c7827d1eeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239850"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a><span data-ttu-id="992d3-103">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="992d3-103">Error encountered during serialization.</span></span> <span data-ttu-id="992d3-104">EDIFACT 機能グループに次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="992d3-104">The Edifact functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="992d3-105">詳細</span><span class="sxs-lookup"><span data-stu-id="992d3-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="992d3-106">製品名</span><span class="sxs-lookup"><span data-stu-id="992d3-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="992d3-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="992d3-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="992d3-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="992d3-108">Event ID</span></span>|-|  
|<span data-ttu-id="992d3-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="992d3-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="992d3-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="992d3-110"> EDI</span></span>|  
|<span data-ttu-id="992d3-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="992d3-111">Component</span></span>|<span data-ttu-id="992d3-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="992d3-112">EDI Engine</span></span>|  
|<span data-ttu-id="992d3-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="992d3-113">Symbolic Name</span></span>|<span data-ttu-id="992d3-114">EfactFunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="992d3-114">EfactFunctionalGroupSendError</span></span>|  
|<span data-ttu-id="992d3-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="992d3-115">Message Text</span></span>|<span data-ttu-id="992d3-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="992d3-116">Error encountered during serialization.</span></span> <span data-ttu-id="992d3-117">Edifact 機能グループ id '{0}'、id '{1}' を持つインターチェンジの送信者 id '{2}' に受信者 id '{3}' では、次のエラーがありました。</span><span class="sxs-lookup"><span data-stu-id="992d3-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="992d3-118">説明</span><span class="sxs-lookup"><span data-stu-id="992d3-118">Explanation</span></span>  
 <span data-ttu-id="992d3-119">このエラー/警告/情報イベントは、示されたエラーがグループで発生したため、送信 EDIFACT インターチェンジ内の機能グループのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="992d3-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing a functional group within an outgoing EDIFACT interchange because of the stated errors with the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="992d3-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="992d3-120">User Action</span></span>  
 <span data-ttu-id="992d3-121">このエラーを解決するには、エラー メッセージの情報を使用して機能グループのエラーを特定し、ドキュメントで問題解決の方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="992d3-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the documentation.</span></span>
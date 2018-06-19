---
title: 解析中にエラーが発生しました。 Edifact トランザクション セット (グループなしの) インターチェンジに含まれるが次のエラーで中断されています |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc5633917c708f457f11fc824997fa7eb6d4c59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240234"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="ba00f-103">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ba00f-103">Error encountered during parsing.</span></span> <span data-ttu-id="ba00f-104">インターチェンジに含まれる EDIFACT トランザクション セット (グループ以外) が、次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="ba00f-104">The Edifact transaction set contained in interchange (without group) is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="ba00f-105">詳細</span><span class="sxs-lookup"><span data-stu-id="ba00f-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ba00f-106">製品名</span><span class="sxs-lookup"><span data-stu-id="ba00f-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ba00f-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ba00f-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ba00f-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ba00f-108">Event ID</span></span>|-|  
|<span data-ttu-id="ba00f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ba00f-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ba00f-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="ba00f-110"> EDI</span></span>|  
|<span data-ttu-id="ba00f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ba00f-111">Component</span></span>|<span data-ttu-id="ba00f-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ba00f-112">EDI Engine</span></span>|  
|<span data-ttu-id="ba00f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ba00f-113">Symbolic Name</span></span>|<span data-ttu-id="ba00f-114">EfactTransactionSetReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="ba00f-114">EfactTransactionSetReceiveErrorWithoutGroup</span></span>|  
|<span data-ttu-id="ba00f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ba00f-115">Message Text</span></span>|<span data-ttu-id="ba00f-116">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ba00f-116">Error encountered during parsing.</span></span> <span data-ttu-id="ba00f-117">Edifact トランザクション セット id '{0}' id '{1}'、送信者 id '{2}' を持つ (グループなしの) インターチェンジに含まれている受信者 id '{3}' で中断されていますが次のエラー。</span><span class="sxs-lookup"><span data-stu-id="ba00f-117">The Edifact transaction set with id '{0}' contained in interchange (without group) with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ba00f-118">説明</span><span class="sxs-lookup"><span data-stu-id="ba00f-118">Explanation</span></span>  
 <span data-ttu-id="ba00f-119">このエラー/警告/情報イベントは、インターチェンジで識別されたトランザクション セットで、示されたエラーが発生したため、受信 EDIFACT インターチェンジ (グループ以外) の解析時に EDI 受信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="ba00f-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange without a group because of the stated errors with the identified transaction set in the interchange.</span></span> <span data-ttu-id="ba00f-120">このトランザクション セットは、インターチェンジ内のグループには含まれないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ba00f-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ba00f-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ba00f-121">User Action</span></span>  
 <span data-ttu-id="ba00f-122">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ba00f-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>
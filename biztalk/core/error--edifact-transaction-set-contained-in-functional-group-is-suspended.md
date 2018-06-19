---
title: 解析中にエラーが発生しました。 Edifact トランザクション セットの機能グループに含まれているが次のエラーで中断されています |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a7220-d35a-4047-8996-7d44c7d2b823
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70428ae8f430ea5ccb9ff13e068716cb35555f69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239946"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="b077d-103">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b077d-103">Error encountered during parsing.</span></span> <span data-ttu-id="b077d-104">機能グループに含まれる EDIFACT トランザクション セットが次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="b077d-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="b077d-105">詳細</span><span class="sxs-lookup"><span data-stu-id="b077d-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b077d-106">製品名</span><span class="sxs-lookup"><span data-stu-id="b077d-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b077d-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b077d-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b077d-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b077d-108">Event ID</span></span>|-|  
|<span data-ttu-id="b077d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b077d-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b077d-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="b077d-110"> EDI</span></span>|  
|<span data-ttu-id="b077d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b077d-111">Component</span></span>|<span data-ttu-id="b077d-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b077d-112">EDI Engine</span></span>|  
|<span data-ttu-id="b077d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b077d-113">Symbolic Name</span></span>|<span data-ttu-id="b077d-114">EfactTransactionSetReceiveError</span><span class="sxs-lookup"><span data-stu-id="b077d-114">EfactTransactionSetReceiveError</span></span>|  
|<span data-ttu-id="b077d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b077d-115">Message Text</span></span>|<span data-ttu-id="b077d-116">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b077d-116">Error encountered during parsing.</span></span> <span data-ttu-id="b077d-117">Edifact トランザクション セット id '{0}' id '{1}' の機能グループに含まれている次のエラーで送信者 id '{3}' と ' {2}'、id を持つインターチェンジの受信者 id '{4}' が中断されています。</span><span class="sxs-lookup"><span data-stu-id="b077d-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b077d-118">説明</span><span class="sxs-lookup"><span data-stu-id="b077d-118">Explanation</span></span>  
 <span data-ttu-id="b077d-119">このエラー/警告/情報イベントは、識別されたトランザクション セットで、示されたエラーが発生したため、EDI 受信パイプラインでグループの受信 EDIFACT インターチェンジを解析できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b077d-119">This Error/Warning/Information event indicates that the EDI receive pipeline could not parse an incoming EDIFACT interchange with a group because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b077d-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b077d-120">User Action</span></span>  
 <span data-ttu-id="b077d-121">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、ドキュメントで問題解決の方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="b077d-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the documentation.</span></span>
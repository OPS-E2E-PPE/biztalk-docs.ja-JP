---
title: "解析中にエラーが発生しました。 トランザクション機能グループに含まれているセットは、次のエラーで中断されていますが、X12 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51c6fa8e-d81c-4ccb-93b4-852ab184c4e9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa837fb86b34cfdd696874dd02ba26635bf7356
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="c3e81-103">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c3e81-103">Error encountered during parsing.</span></span> <span data-ttu-id="c3e81-104">機能グループに含まれる X12 トランザクション セットが次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="c3e81-104">The X12 transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="c3e81-105">詳細</span><span class="sxs-lookup"><span data-stu-id="c3e81-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3e81-106">製品名</span><span class="sxs-lookup"><span data-stu-id="c3e81-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c3e81-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c3e81-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c3e81-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c3e81-108">Event ID</span></span>|-|  
|<span data-ttu-id="c3e81-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c3e81-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c3e81-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="c3e81-110"> EDI</span></span>|  
|<span data-ttu-id="c3e81-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c3e81-111">Component</span></span>|<span data-ttu-id="c3e81-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c3e81-112">EDI Engine</span></span>|  
|<span data-ttu-id="c3e81-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c3e81-113">Symbolic Name</span></span>|<span data-ttu-id="c3e81-114">X12TransactionSetReceiveError</span><span class="sxs-lookup"><span data-stu-id="c3e81-114">X12TransactionSetReceiveError</span></span>|  
|<span data-ttu-id="c3e81-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c3e81-115">Message Text</span></span>|<span data-ttu-id="c3e81-116">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c3e81-116">Error encountered during parsing.</span></span> <span data-ttu-id="c3e81-117">含まれるトランザクション セット id '{0}' の X12 機能グループ id '{1}'、id '{2}' のインターチェンジの送信者 id '{3}'、受信者 id '{4}' でが次のエラーで中断されています。</span><span class="sxs-lookup"><span data-stu-id="c3e81-117">The X12 transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c3e81-118">説明</span><span class="sxs-lookup"><span data-stu-id="c3e81-118">Explanation</span></span>  
 <span data-ttu-id="c3e81-119">このエラー/警告/情報イベントは、識別されたトランザクション セットに、示されたエラーがあったため、受信 X12 インターチェンジの解析中に EDI 受信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c3e81-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c3e81-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c3e81-120">User Action</span></span>  
 <span data-ttu-id="c3e81-121">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c3e81-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>
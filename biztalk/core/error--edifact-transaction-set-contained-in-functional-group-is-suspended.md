---
title: 解析中に発生したエラーです。 機能グループに含まれる設定の Edifact トランザクションは、次のエラーで中断されています |Microsoft Docs
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
ms.openlocfilehash: 19f6332f1f1f7f97c9dd69f34ae221e120770958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389038"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="14e08-103">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="14e08-103">Error encountered during parsing.</span></span> <span data-ttu-id="14e08-104">機能グループに含まれる Edifact トランザクション セットは、次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="14e08-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="14e08-105">詳細</span><span class="sxs-lookup"><span data-stu-id="14e08-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="14e08-106">製品名</span><span class="sxs-lookup"><span data-stu-id="14e08-106">Product Name</span></span>   |                                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                            |
| <span data-ttu-id="14e08-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="14e08-107">Product Version</span></span> |                                                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                        |
|    <span data-ttu-id="14e08-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="14e08-108">Event ID</span></span>     |                                                                                                                    -                                                                                                                     |
|  <span data-ttu-id="14e08-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="14e08-109">Event Source</span></span>   |                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="14e08-110">EDI</span><span class="sxs-lookup"><span data-stu-id="14e08-110">EDI</span></span>                                                                          |
|    <span data-ttu-id="14e08-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="14e08-111">Component</span></span>    |                                                                                                                <span data-ttu-id="14e08-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="14e08-112">EDI Engine</span></span>                                                                                                                |
|  <span data-ttu-id="14e08-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="14e08-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="14e08-114">EfactTransactionSetReceiveError</span><span class="sxs-lookup"><span data-stu-id="14e08-114">EfactTransactionSetReceiveError</span></span>                                                                                                      |
|  <span data-ttu-id="14e08-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="14e08-115">Message Text</span></span>   | <span data-ttu-id="14e08-116">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="14e08-116">Error encountered during parsing.</span></span> <span data-ttu-id="14e08-117">Edifact トランザクション セット id を持つ '{0}'機能グループ id に含まれている'{1}'、id を持つインターチェンジ内'{2}'、送信者 id '{3}'、受信者 id'{4}' 次のエラーで中断されています。</span><span class="sxs-lookup"><span data-stu-id="14e08-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="14e08-118">説明</span><span class="sxs-lookup"><span data-stu-id="14e08-118">Explanation</span></span>  
 <span data-ttu-id="14e08-119">このエラー/警告/情報イベントを示します、EDI 受信パイプラインは、識別されたトランザクション セット、示されたエラーのため、グループで受信 EDIFACT インターチェンジを解析できませんでした。</span><span class="sxs-lookup"><span data-stu-id="14e08-119">This Error/Warning/Information event indicates that the EDI receive pipeline could not parse an incoming EDIFACT interchange with a group because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14e08-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="14e08-120">User Action</span></span>  
 <span data-ttu-id="14e08-121">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、ドキュメントで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="14e08-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the documentation.</span></span>
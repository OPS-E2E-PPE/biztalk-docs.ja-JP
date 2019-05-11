---
title: 解析中に発生したエラーです。 Edifact トランザクション セット (グループ) なしのインターチェンジに含まれるは、次のエラーで中断されています |Microsoft Docs
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
ms.openlocfilehash: 3fe401b82d9492590d332dcbdb7d6d59bfaf3c91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348898"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="50103-103">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="50103-103">Error encountered during parsing.</span></span> <span data-ttu-id="50103-104">Edifact トランザクション セット (グループ) なしのインターチェンジに含まれるは、次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="50103-104">The Edifact transaction set contained in interchange (without group) is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="50103-105">詳細</span><span class="sxs-lookup"><span data-stu-id="50103-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="50103-106">製品名</span><span class="sxs-lookup"><span data-stu-id="50103-106">Product Name</span></span>   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| <span data-ttu-id="50103-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="50103-107">Product Version</span></span> |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    <span data-ttu-id="50103-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="50103-108">Event ID</span></span>     |                                                                                                           -                                                                                                           |
|  <span data-ttu-id="50103-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="50103-109">Event Source</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="50103-110">EDI</span><span class="sxs-lookup"><span data-stu-id="50103-110">EDI</span></span>                                                                 |
|    <span data-ttu-id="50103-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="50103-111">Component</span></span>    |                                                                                                      <span data-ttu-id="50103-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="50103-112">EDI Engine</span></span>                                                                                                       |
|  <span data-ttu-id="50103-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="50103-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="50103-114">EfactTransactionSetReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="50103-114">EfactTransactionSetReceiveErrorWithoutGroup</span></span>                                                                                      |
|  <span data-ttu-id="50103-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="50103-115">Message Text</span></span>   | <span data-ttu-id="50103-116">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="50103-116">Error encountered during parsing.</span></span> <span data-ttu-id="50103-117">Edifact トランザクション セット id を持つ '{0}'id (グループ) なしのインターチェンジに含まれる'{1}'、送信者 id'{2}'、受信者 id '{3}' 次のエラーで中断されています。</span><span class="sxs-lookup"><span data-stu-id="50103-117">The Edifact transaction set with id '{0}' contained in interchange (without group) with id '{1}', with sender id '{2}', receiver id '{3}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="50103-118">説明</span><span class="sxs-lookup"><span data-stu-id="50103-118">Explanation</span></span>  
 <span data-ttu-id="50103-119">このエラー/警告/情報イベントを示します、EDI 受信パイプラインでは、識別されたトランザクション、示されたエラーのため、グループなし受信 EDIFACT インターチェンジの解析、インターチェンジの設定時にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="50103-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange without a group because of the stated errors with the identified transaction set in the interchange.</span></span> <span data-ttu-id="50103-120">トランザクション セットがインターチェンジ内のグループでないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="50103-120">Note that the transaction set is not in a group in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="50103-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="50103-121">User Action</span></span>  
 <span data-ttu-id="50103-122">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="50103-122">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>
---
title: 解析中にエラーが発生しました。 Edifact インターチェンジ、グループが含まれていませんでしたが、次のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6b324fd-f365-41b9-81aa-b6c5c5d3f673
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c3ef771093a376349ee6656709f90d2ca7ece7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015314"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="106b6-103">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="106b6-103">Error encountered during parsing.</span></span> <span data-ttu-id="106b6-104">グループを含まない EDIFACT インターチェンジに、次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="106b6-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="106b6-105">詳細</span><span class="sxs-lookup"><span data-stu-id="106b6-105">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="106b6-106">製品名</span><span class="sxs-lookup"><span data-stu-id="106b6-106">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="106b6-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="106b6-107">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="106b6-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="106b6-108">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="106b6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="106b6-109">Event Source</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="106b6-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="106b6-110"> EDI</span></span>                                                 |
|    <span data-ttu-id="106b6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="106b6-111">Component</span></span>    |                                                                                      <span data-ttu-id="106b6-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="106b6-112">EDI Engine</span></span>                                                                                       |
|  <span data-ttu-id="106b6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="106b6-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="106b6-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="106b6-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span></span>                                                                      |
|  <span data-ttu-id="106b6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="106b6-115">Message Text</span></span>   | <span data-ttu-id="106b6-116">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="106b6-116">Error encountered during parsing.</span></span> <span data-ttu-id="106b6-117">Edifact インターチェンジのインターチェンジ id を持つ、グループを含まない '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="106b6-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="106b6-118">説明</span><span class="sxs-lookup"><span data-stu-id="106b6-118">Explanation</span></span>  
 <span data-ttu-id="106b6-119">このエラー/警告/情報イベントは、示されたエラーのため、グループを含まない受信 EDIFACT インターチェンジの解析中に、EDI 受信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="106b6-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange that did not contain a group because of the stated errors.</span></span> <span data-ttu-id="106b6-120">EDIFACT インターチェンジでは、グループは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="106b6-120">Note that groups are optional in EDIFACT interchanges.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="106b6-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="106b6-121">User Action</span></span>  
 <span data-ttu-id="106b6-122">このエラーを解決するには、エラー メッセージの情報を使用してエラーを特定し、製品のヘルプで問題解決の方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="106b6-122">To resolve this error, use the information in the error message to identify the error and then determine the problem resolution in the product help.</span></span>
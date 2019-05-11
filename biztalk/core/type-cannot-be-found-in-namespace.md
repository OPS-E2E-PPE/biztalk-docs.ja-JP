---
title: 名前空間で型が見つからない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70011a83e5264344a5ef4f30c4525529aa403dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393771"
---
# <a name="type-cannot-be-found-in-namespace"></a><span data-ttu-id="b4599-102">種類が名前空間に見つかりません</span><span class="sxs-lookup"><span data-stu-id="b4599-102">Type cannot be found in namespace</span></span>
## <a name="details"></a><span data-ttu-id="b4599-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b4599-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="b4599-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b4599-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="b4599-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b4599-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="b4599-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b4599-106">Event ID</span></span>     |                                         <span data-ttu-id="b4599-107">0</span><span class="sxs-lookup"><span data-stu-id="b4599-107">0</span></span>                                          |
|  <span data-ttu-id="b4599-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b4599-108">Event Source</span></span>   |                                         <span data-ttu-id="b4599-109">0</span><span class="sxs-lookup"><span data-stu-id="b4599-109">0</span></span>                                          |
|    <span data-ttu-id="b4599-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b4599-110">Component</span></span>    |                                         <span data-ttu-id="b4599-111">0</span><span class="sxs-lookup"><span data-stu-id="b4599-111">0</span></span>                                          |
|  <span data-ttu-id="b4599-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b4599-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="b4599-113">0</span><span class="sxs-lookup"><span data-stu-id="b4599-113">0</span></span>                                          |
|  <span data-ttu-id="b4599-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b4599-114">Message Text</span></span>   |                <span data-ttu-id="b4599-115">エラー:型"{0}「名前空間で見つかったことはできません」{1}"</span><span class="sxs-lookup"><span data-stu-id="b4599-115">Error: Type "{0}" cannot be found in namespace "{1}"</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="b4599-116">説明</span><span class="sxs-lookup"><span data-stu-id="b4599-116">Explanation</span></span>  
 <span data-ttu-id="b4599-117">このエラーは、作成される成果物が型指定された名前空間で見つからないを参照していることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4599-117">This error indicates artifacts that are created are referencing types which cannot be found in the namespace specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b4599-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b4599-118">User Action</span></span>  
 <span data-ttu-id="b4599-119">型が見つからないことが含まれている参照を追加し、(使用しようとしている WCF サービスを所有) 場合は、ウィザードを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="b4599-119">Add a reference that contain the type that is not found, and run the wizard again (if you own the WCF service that you are trying to consume).</span></span> <span data-ttu-id="b4599-120">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="b4599-120">Otherwise, contact the service provider.</span></span>
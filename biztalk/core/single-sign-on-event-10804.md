---
title: シングル サインオン:イベント 10804 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a93cce2d1ad17248c1ad007f07c0a885b1a8fa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399521"
---
# <a name="single-sign-on-event-10804"></a><span data-ttu-id="f3cb4-102">シングル サインオン:イベント 10804</span><span class="sxs-lookup"><span data-stu-id="f3cb4-102">Single Sign-On: Event 10804</span></span>
## <a name="details"></a><span data-ttu-id="f3cb4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f3cb4-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="f3cb4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f3cb4-104">Product Name</span></span>   |                 <span data-ttu-id="f3cb4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f3cb4-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="f3cb4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f3cb4-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="f3cb4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f3cb4-107">Event ID</span></span>     |                           <span data-ttu-id="f3cb4-108">10804</span><span class="sxs-lookup"><span data-stu-id="f3cb4-108">10804</span></span>                            |
|  <span data-ttu-id="f3cb4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f3cb4-109">Event Source</span></span>   |                           <span data-ttu-id="f3cb4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f3cb4-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="f3cb4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f3cb4-111">Component</span></span>    |                            <span data-ttu-id="f3cb4-112">なし</span><span class="sxs-lookup"><span data-stu-id="f3cb4-112">N/A</span></span>                             |
|  <span data-ttu-id="f3cb4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f3cb4-113">Symbolic Name</span></span>  |                <span data-ttu-id="f3cb4-114">ENTSSO_E_INCORRECT_COMPUTER</span><span class="sxs-lookup"><span data-stu-id="f3cb4-114">ENTSSO_E_INCORRECT_COMPUTER</span></span>                 |
|  <span data-ttu-id="f3cb4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f3cb4-115">Message Text</span></span>   |     <span data-ttu-id="f3cb4-116">このアダプターはこのコンピューターに構成されていません。</span><span class="sxs-lookup"><span data-stu-id="f3cb4-116">This adapter is not configured for this computer.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="f3cb4-117">説明</span><span class="sxs-lookup"><span data-stu-id="f3cb4-117">Explanation</span></span>  
 <span data-ttu-id="f3cb4-118">各アダプターを構成するには、長い名前で識別される特定のコンピューター上で実行します。</span><span class="sxs-lookup"><span data-stu-id="f3cb4-118">Each adapter is configured to run on a specific computer, which is identified by its long name.</span></span> <span data-ttu-id="f3cb4-119">名前が正しくないか、別のコンピューターでアダプターを実行しようとしています。</span><span class="sxs-lookup"><span data-stu-id="f3cb4-119">Either the name is incorrect, or you are trying to run the adapter on a different computer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3cb4-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f3cb4-120">User Action</span></span>  
 <span data-ttu-id="f3cb4-121">適切なコンピューターの適切な名前を確認するには、このアダプターの構成を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3cb4-121">See the configuration for this adapter to determine the proper name of the appropriate computer.</span></span>
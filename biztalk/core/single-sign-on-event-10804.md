---
title: 'シングル サインオン: イベント 10804 |Microsoft Docs'
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
ms.openlocfilehash: 3a262448f4d07a01f726f111ca5ddd01901e9e7d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017014"
---
# <a name="single-sign-on-event-10804"></a><span data-ttu-id="6cdc2-102">シングル サインオン: イベント 10804</span><span class="sxs-lookup"><span data-stu-id="6cdc2-102">Single Sign-On: Event 10804</span></span>
## <a name="details"></a><span data-ttu-id="6cdc2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6cdc2-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="6cdc2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6cdc2-104">Product Name</span></span>   |                 <span data-ttu-id="6cdc2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6cdc2-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="6cdc2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6cdc2-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="6cdc2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6cdc2-107">Event ID</span></span>     |                           <span data-ttu-id="6cdc2-108">10804</span><span class="sxs-lookup"><span data-stu-id="6cdc2-108">10804</span></span>                            |
|  <span data-ttu-id="6cdc2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6cdc2-109">Event Source</span></span>   |                           <span data-ttu-id="6cdc2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6cdc2-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="6cdc2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6cdc2-111">Component</span></span>    |                            <span data-ttu-id="6cdc2-112">なし</span><span class="sxs-lookup"><span data-stu-id="6cdc2-112">N/A</span></span>                             |
|  <span data-ttu-id="6cdc2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6cdc2-113">Symbolic Name</span></span>  |                <span data-ttu-id="6cdc2-114">ENTSSO_E_INCORRECT_COMPUTER</span><span class="sxs-lookup"><span data-stu-id="6cdc2-114">ENTSSO_E_INCORRECT_COMPUTER</span></span>                 |
|  <span data-ttu-id="6cdc2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6cdc2-115">Message Text</span></span>   |     <span data-ttu-id="6cdc2-116">このアダプターはこのコンピューター用に構成されていません。</span><span class="sxs-lookup"><span data-stu-id="6cdc2-116">This adapter is not configured for this computer.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="6cdc2-117">説明</span><span class="sxs-lookup"><span data-stu-id="6cdc2-117">Explanation</span></span>  
 <span data-ttu-id="6cdc2-118">各アダプターは特定のコンピューターで実行されるように構成され、コンピューターの長い名前によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="6cdc2-118">Each adapter is configured to run on a specific computer, which is identified by its long name.</span></span> <span data-ttu-id="6cdc2-119">この名前が正しくないか、別のコンピューター上のアダプターを実行しようとしています。</span><span class="sxs-lookup"><span data-stu-id="6cdc2-119">Either the name is incorrect, or you are trying to run the adapter on a different computer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6cdc2-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6cdc2-120">User Action</span></span>  
 <span data-ttu-id="6cdc2-121">このアダプターの構成を確認して、適切なコンピューターの正しい名前を特定します。</span><span class="sxs-lookup"><span data-stu-id="6cdc2-121">See the configuration for this adapter to determine the proper name of the appropriate computer.</span></span>
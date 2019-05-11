---
title: シングル サインオン:イベント 10814 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d61d17eb-4cc7-48ac-942d-e7b94fee5931
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 215ab39f98f8f516917640d7ff21960b401f7419
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396135"
---
# <a name="single-sign-on-event-10814"></a><span data-ttu-id="c48de-102">シングル サインオン:イベント 10814</span><span class="sxs-lookup"><span data-stu-id="c48de-102">Single Sign-On: Event 10814</span></span>
## <a name="details"></a><span data-ttu-id="c48de-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c48de-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="c48de-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c48de-104">Product Name</span></span>   |                 <span data-ttu-id="c48de-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c48de-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="c48de-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c48de-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="c48de-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c48de-107">Event ID</span></span>     |                           <span data-ttu-id="c48de-108">10814</span><span class="sxs-lookup"><span data-stu-id="c48de-108">10814</span></span>                            |
|  <span data-ttu-id="c48de-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c48de-109">Event Source</span></span>   |                           <span data-ttu-id="c48de-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c48de-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="c48de-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c48de-111">Component</span></span>    |                            <span data-ttu-id="c48de-112">なし</span><span class="sxs-lookup"><span data-stu-id="c48de-112">N/A</span></span>                             |
|  <span data-ttu-id="c48de-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c48de-113">Symbolic Name</span></span>  |               <span data-ttu-id="c48de-114">ENTSSO_E_REENCRYPT_IN_PROGRESS</span><span class="sxs-lookup"><span data-stu-id="c48de-114">ENTSSO_E_REENCRYPT_IN_PROGRESS</span></span>               |
|  <span data-ttu-id="c48de-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c48de-115">Message Text</span></span>   |         <span data-ttu-id="c48de-116">SSO データベースを再暗号化は、実行中です。</span><span class="sxs-lookup"><span data-stu-id="c48de-116">SSO database re-encryption is in progress.</span></span>         |
  
## <a name="explanation"></a><span data-ttu-id="c48de-117">説明</span><span class="sxs-lookup"><span data-stu-id="c48de-117">Explanation</span></span>  
 <span data-ttu-id="c48de-118">SSO データベースが再暗号化されている間に、この操作を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="c48de-118">This action cannot be performed while the SSO database is being re-encrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c48de-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c48de-119">User Action</span></span>  
 <span data-ttu-id="c48de-120">後でもう一度操作を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="c48de-120">Try the action again later.</span></span>
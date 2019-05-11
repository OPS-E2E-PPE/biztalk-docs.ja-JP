---
title: シングル サインオン:イベント 10753 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca0c0066e1643ec6cc84f19eaf1ca5ece9822e69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307789"
---
# <a name="single-sign-on-event-10753"></a><span data-ttu-id="5cb7e-102">シングル サインオン:イベント 10753</span><span class="sxs-lookup"><span data-stu-id="5cb7e-102">Single Sign-On: Event 10753</span></span>
## <a name="details"></a><span data-ttu-id="5cb7e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5cb7e-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="5cb7e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5cb7e-104">Product Name</span></span>   |                 <span data-ttu-id="5cb7e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5cb7e-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="5cb7e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5cb7e-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="5cb7e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5cb7e-107">Event ID</span></span>     |                           <span data-ttu-id="5cb7e-108">10753</span><span class="sxs-lookup"><span data-stu-id="5cb7e-108">10753</span></span>                            |
|  <span data-ttu-id="5cb7e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5cb7e-109">Event Source</span></span>   |                           <span data-ttu-id="5cb7e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5cb7e-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="5cb7e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5cb7e-111">Component</span></span>    |                            <span data-ttu-id="5cb7e-112">なし</span><span class="sxs-lookup"><span data-stu-id="5cb7e-112">N/A</span></span>                             |
|  <span data-ttu-id="5cb7e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5cb7e-113">Symbolic Name</span></span>  |                  <span data-ttu-id="5cb7e-114">ENTSSO_E_MAPPING_EXISTS</span><span class="sxs-lookup"><span data-stu-id="5cb7e-114">ENTSSO_E_MAPPING_EXISTS</span></span>                   |
|  <span data-ttu-id="5cb7e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5cb7e-115">Message Text</span></span>   |                <span data-ttu-id="5cb7e-116">マッピングは既に存在します。</span><span class="sxs-lookup"><span data-stu-id="5cb7e-116">The mapping already exists.</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="5cb7e-117">説明</span><span class="sxs-lookup"><span data-stu-id="5cb7e-117">Explanation</span></span>  
 <span data-ttu-id="5cb7e-118">このマッピングが既に存在するには既に使用されている Windows アカウントまたは外部のアカウント。</span><span class="sxs-lookup"><span data-stu-id="5cb7e-118">This mapping already exists, either on the Windows account already in use or the external account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5cb7e-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5cb7e-119">User Action</span></span>  
 <span data-ttu-id="5cb7e-120">既存のマッピングおよび作成しようとしているマッピングを確認します。</span><span class="sxs-lookup"><span data-stu-id="5cb7e-120">Check the existing mappings and the mapping you are trying to create.</span></span> <span data-ttu-id="5cb7e-121">既にマッピングが存在する場合は、それを使用し、新しいを削除します。</span><span class="sxs-lookup"><span data-stu-id="5cb7e-121">If the mapping you want already exists, use it and delete your new one.</span></span> <span data-ttu-id="5cb7e-122">そうでない場合は、新しいを削除し、再作成します。</span><span class="sxs-lookup"><span data-stu-id="5cb7e-122">If not, delete your new one and recreate it.</span></span>
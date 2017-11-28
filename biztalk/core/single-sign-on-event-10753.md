---
title: "シングル サインオン: イベント 10753 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc43f8ffba195b7a0156a9004d140f1e3c585db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10753"></a><span data-ttu-id="5dc7a-102">シングル サインオン: イベント 10753</span><span class="sxs-lookup"><span data-stu-id="5dc7a-102">Single Sign-On: Event 10753</span></span>
## <a name="details"></a><span data-ttu-id="5dc7a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5dc7a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5dc7a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5dc7a-104">Product Name</span></span>|<span data-ttu-id="5dc7a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5dc7a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5dc7a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5dc7a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5dc7a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5dc7a-107">Event ID</span></span>|<span data-ttu-id="5dc7a-108">10753</span><span class="sxs-lookup"><span data-stu-id="5dc7a-108">10753</span></span>|  
|<span data-ttu-id="5dc7a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5dc7a-109">Event Source</span></span>|<span data-ttu-id="5dc7a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5dc7a-110">ENTSSO</span></span>|  
|<span data-ttu-id="5dc7a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5dc7a-111">Component</span></span>|<span data-ttu-id="5dc7a-112">なし</span><span class="sxs-lookup"><span data-stu-id="5dc7a-112">N/A</span></span>|  
|<span data-ttu-id="5dc7a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5dc7a-113">Symbolic Name</span></span>|<span data-ttu-id="5dc7a-114">ENTSSO_E_MAPPING_EXISTS</span><span class="sxs-lookup"><span data-stu-id="5dc7a-114">ENTSSO_E_MAPPING_EXISTS</span></span>|  
|<span data-ttu-id="5dc7a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5dc7a-115">Message Text</span></span>|<span data-ttu-id="5dc7a-116">マッピングは既に存在します。</span><span class="sxs-lookup"><span data-stu-id="5dc7a-116">The mapping already exists.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5dc7a-117">説明</span><span class="sxs-lookup"><span data-stu-id="5dc7a-117">Explanation</span></span>  
 <span data-ttu-id="5dc7a-118">このマッピングは、使用中の Windows アカウントまたは外部アカウントに既に存在しています。</span><span class="sxs-lookup"><span data-stu-id="5dc7a-118">This mapping already exists, either on the Windows account already in use or the external account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5dc7a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5dc7a-119">User Action</span></span>  
 <span data-ttu-id="5dc7a-120">既存のマッピングおよび作成しようとしているマッピングを確認します。</span><span class="sxs-lookup"><span data-stu-id="5dc7a-120">Check the existing mappings and the mapping you are trying to create.</span></span> <span data-ttu-id="5dc7a-121">必要なマッピングが既に存在している場合は、そのマッピングを使用し、新しいマッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="5dc7a-121">If the mapping you want already exists, use it and delete your new one.</span></span> <span data-ttu-id="5dc7a-122">マッピングが存在しない場合は、新しいマッピングを削除して作成し直します。</span><span class="sxs-lookup"><span data-stu-id="5dc7a-122">If not, delete your new one and recreate it.</span></span>
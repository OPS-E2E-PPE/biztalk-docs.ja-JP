---
title: 'シングル サインオン: イベント 10849 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdfb1cea-e445-4318-9891-b6b70a266ca9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3ef1e5454c80f5aba963426c04950c33a2f773a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276938"
---
# <a name="single-sign-on-event-10849"></a><span data-ttu-id="39def-102">シングル サインオン: イベント 10849</span><span class="sxs-lookup"><span data-stu-id="39def-102">Single Sign-On: Event 10849</span></span>
## <a name="details"></a><span data-ttu-id="39def-103">詳細</span><span class="sxs-lookup"><span data-stu-id="39def-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39def-104">製品名</span><span class="sxs-lookup"><span data-stu-id="39def-104">Product Name</span></span>|<span data-ttu-id="39def-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="39def-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="39def-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="39def-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="39def-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="39def-107">Event ID</span></span>|<span data-ttu-id="39def-108">10849</span><span class="sxs-lookup"><span data-stu-id="39def-108">10849</span></span>|  
|<span data-ttu-id="39def-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="39def-109">Event Source</span></span>|<span data-ttu-id="39def-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="39def-110">ENTSSO</span></span>|  
|<span data-ttu-id="39def-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="39def-111">Component</span></span>|<span data-ttu-id="39def-112">なし</span><span class="sxs-lookup"><span data-stu-id="39def-112">N/A</span></span>|  
|<span data-ttu-id="39def-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="39def-113">Symbolic Name</span></span>|<span data-ttu-id="39def-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="39def-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE</span></span>|  
|<span data-ttu-id="39def-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="39def-115">Message Text</span></span>|<span data-ttu-id="39def-116">‘直接パスワード同期’ フラグを指定してアプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="39def-116">An application cannot be created with the ‘direct password sync’ flag specified.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="39def-117">説明</span><span class="sxs-lookup"><span data-stu-id="39def-117">Explanation</span></span>  
 <span data-ttu-id="39def-118">‘直接パスワード同期’ フラグを指定してアプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="39def-118">An application cannot be created with the ‘direct password sync’ flag specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="39def-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="39def-119">User Action</span></span>  
 <span data-ttu-id="39def-120">直接パスワード同期フラグを設定しないでアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="39def-120">Create the application without the direct password sync flag.</span></span> <span data-ttu-id="39def-121">その後、フィールドを追加および作成し、アプリケーションを有効にして、直接パスワード同期フラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="39def-121">Then add and create the fields, enable the application, and specify the direct password sync flag.</span></span>
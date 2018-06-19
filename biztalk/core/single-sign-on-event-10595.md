---
title: 'シングル サインオン: イベント 10595 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1517478c-7217-4e34-a5cb-ff7deea367ed
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9139eb7479b0a048e2fab197863b42c47f87992a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271266"
---
# <a name="single-sign-on-event-10595"></a><span data-ttu-id="1d0ca-102">シングル サインオン: イベント 10595</span><span class="sxs-lookup"><span data-stu-id="1d0ca-102">Single Sign-On: Event 10595</span></span>
## <a name="details"></a><span data-ttu-id="1d0ca-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1d0ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d0ca-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1d0ca-104">Product Name</span></span>|<span data-ttu-id="1d0ca-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1d0ca-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1d0ca-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1d0ca-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1d0ca-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1d0ca-107">Event ID</span></span>|<span data-ttu-id="1d0ca-108">10595</span><span class="sxs-lookup"><span data-stu-id="1d0ca-108">10595</span></span>|  
|<span data-ttu-id="1d0ca-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1d0ca-109">Event Source</span></span>|<span data-ttu-id="1d0ca-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1d0ca-110">ENTSSO</span></span>|  
|<span data-ttu-id="1d0ca-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1d0ca-111">Component</span></span>|<span data-ttu-id="1d0ca-112">なし</span><span class="sxs-lookup"><span data-stu-id="1d0ca-112">N/A</span></span>|  
|<span data-ttu-id="1d0ca-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1d0ca-113">Symbolic Name</span></span>|<span data-ttu-id="1d0ca-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span><span class="sxs-lookup"><span data-stu-id="1d0ca-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span></span>|  
|<span data-ttu-id="1d0ca-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1d0ca-115">Message Text</span></span>|<span data-ttu-id="1d0ca-116">このアプリケーションのフィールドが入力されていないので、アプリケーションを有効にすることができません。%r</span><span class="sxs-lookup"><span data-stu-id="1d0ca-116">The application cannot be enabled because the fields are incomplete for this application.%r</span></span><br /><br /> <span data-ttu-id="1d0ca-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1d0ca-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="1d0ca-118">定義したフィールドの数: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1d0ca-118">Number of Fields Defined: %2%r</span></span><br /><br /> <span data-ttu-id="1d0ca-119">作成されたフィールドの数: %3</span><span class="sxs-lookup"><span data-stu-id="1d0ca-119">Number of Fields Created: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1d0ca-120">説明</span><span class="sxs-lookup"><span data-stu-id="1d0ca-120">Explanation</span></span>  
 <span data-ttu-id="1d0ca-121">API レベルでアプリケーションを作成するときに、アプリケーションで定義するフィールド (UserID、Password) を指定しました。</span><span class="sxs-lookup"><span data-stu-id="1d0ca-121">When creating an application at the API level, you specified the number of fields (i.e. UserID, Password) the application would define.</span></span> <span data-ttu-id="1d0ca-122">定義した各フィールドは、作成することも必要です。</span><span class="sxs-lookup"><span data-stu-id="1d0ca-122">Each field that has been defined must also be created.</span></span> <span data-ttu-id="1d0ca-123">この警告メッセージは、アプリケーション名、定義されているフィールド数、および作成されたフィールド数の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="1d0ca-123">This warning message lists the application name, number of fields defined, and number of fields created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d0ca-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1d0ca-124">User Action</span></span>  
 <span data-ttu-id="1d0ca-125">定義済みだが作成されていないフィールドを特定し、前の手順に戻ってフィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d0ca-125">Determine which fields were defined but not created, and then go back and create them.</span></span>
---
title: 'シングル サインオン: イベント 10740 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928760bebef1119207ee6a3021cd39c22ceacad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270658"
---
# <a name="single-sign-on-event-10740"></a><span data-ttu-id="bd5dd-102">シングル サインオン: イベント 10740</span><span class="sxs-lookup"><span data-stu-id="bd5dd-102">Single Sign-On: Event 10740</span></span>
## <a name="details"></a><span data-ttu-id="bd5dd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bd5dd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd5dd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bd5dd-104">Product Name</span></span>|<span data-ttu-id="bd5dd-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bd5dd-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="bd5dd-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bd5dd-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="bd5dd-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bd5dd-107">Event ID</span></span>|<span data-ttu-id="bd5dd-108">10740</span><span class="sxs-lookup"><span data-stu-id="bd5dd-108">10740</span></span>|  
|<span data-ttu-id="bd5dd-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bd5dd-109">Event Source</span></span>|<span data-ttu-id="bd5dd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bd5dd-110">ENTSSO</span></span>|  
|<span data-ttu-id="bd5dd-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bd5dd-111">Component</span></span>|<span data-ttu-id="bd5dd-112">N\A</span><span class="sxs-lookup"><span data-stu-id="bd5dd-112">N\A</span></span>|  
|<span data-ttu-id="bd5dd-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bd5dd-113">Symbolic Name</span></span>|<span data-ttu-id="bd5dd-114">SSO_WARN_INVALID_WINDOWS_USER</span><span class="sxs-lookup"><span data-stu-id="bd5dd-114">SSO_WARN_INVALID_WINDOWS_USER</span></span>|  
|<span data-ttu-id="bd5dd-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bd5dd-115">Message Text</span></span>|<span data-ttu-id="bd5dd-116">Windows アカウントがアプリケーションの更新について有効ではありません。%r</span><span class="sxs-lookup"><span data-stu-id="bd5dd-116">The Windows Account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="bd5dd-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bd5dd-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="bd5dd-118">Windows アカウント: %2 %r</span><span class="sxs-lookup"><span data-stu-id="bd5dd-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="bd5dd-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="bd5dd-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd5dd-120">説明</span><span class="sxs-lookup"><span data-stu-id="bd5dd-120">Explanation</span></span>  
 <span data-ttu-id="bd5dd-121">この警告イベントは、(イベント メッセージに示されている) Windows アカウントがアプリケーションの更新について有効ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="bd5dd-121">This Warning event indicates that the Windows Account (specified in the event message) is not valid for application update.</span></span> <span data-ttu-id="bd5dd-122">これは、ホスト グループ アプリケーションの Windows アカウントを変更したときに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd5dd-122">This can occur when changing the Windows account for a Host Group application.</span></span> <span data-ttu-id="bd5dd-123">ホスト グループ アプリケーションは、外部システムから Windows システムへのシングル サインオンに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd5dd-123">Host Group applications are used for single sign-on from external systems to Windows systems.</span></span> <span data-ttu-id="bd5dd-124">ホスト グループ アプリケーションは、外部ユーザーのセットを 1 つの Windows アカウントにマッピングすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd5dd-124">They can map a set of external users to a single Windows account.</span></span> <span data-ttu-id="bd5dd-125">ホスト グループ アプリケーションがマッピングされる Windows アカウントは、アプリケーションのアプリケーション ユーザー フィールドで定義されます。</span><span class="sxs-lookup"><span data-stu-id="bd5dd-125">The Windows account they are mapped to is defined in the Application Users field of the application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd5dd-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bd5dd-126">User Action</span></span>  
 <span data-ttu-id="bd5dd-127">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="bd5dd-127">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="bd5dd-128">使用している Windows アカウントが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd5dd-128">Check that the Windows account your are using is valid.</span></span>  
  
-   <span data-ttu-id="bd5dd-129">正しい Windows アカウントのプロパティを使用して Windows アカウントを再作成します。</span><span class="sxs-lookup"><span data-stu-id="bd5dd-129">Recreate the Windows account with the correct Windows account properties.</span></span>  
  
 <span data-ttu-id="bd5dd-130">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd5dd-130">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="bd5dd-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="bd5dd-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
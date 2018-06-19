---
title: 'シングル サインオン: イベント 10850 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e9bef6d104b8da3c41d295005a7a274a1d2610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278034"
---
# <a name="single-sign-on-event-10850"></a><span data-ttu-id="81b22-102">シングル サインオン: イベント 10850</span><span class="sxs-lookup"><span data-stu-id="81b22-102">Single Sign-On: Event 10850</span></span>
## <a name="details"></a><span data-ttu-id="81b22-103">詳細</span><span class="sxs-lookup"><span data-stu-id="81b22-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81b22-104">製品名</span><span class="sxs-lookup"><span data-stu-id="81b22-104">Product Name</span></span>|<span data-ttu-id="81b22-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="81b22-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="81b22-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="81b22-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="81b22-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="81b22-107">Event ID</span></span>|<span data-ttu-id="81b22-108">10850</span><span class="sxs-lookup"><span data-stu-id="81b22-108">10850</span></span>|  
|<span data-ttu-id="81b22-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="81b22-109">Event Source</span></span>|<span data-ttu-id="81b22-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="81b22-110">ENTSSO</span></span>|  
|<span data-ttu-id="81b22-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="81b22-111">Component</span></span>|<span data-ttu-id="81b22-112">なし</span><span class="sxs-lookup"><span data-stu-id="81b22-112">N/A</span></span>|  
|<span data-ttu-id="81b22-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="81b22-113">Symbolic Name</span></span>|<span data-ttu-id="81b22-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="81b22-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span></span>|  
|<span data-ttu-id="81b22-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="81b22-115">Message Text</span></span>|<span data-ttu-id="81b22-116">'enabled' フラグを指定してアプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="81b22-116">An application cannot be created with the 'enabled' flag specified.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81b22-117">説明</span><span class="sxs-lookup"><span data-stu-id="81b22-117">Explanation</span></span>  
 <span data-ttu-id="81b22-118">アプリケーションを有効にするには、アプリケーションを作成し、アプリケーションの各フィールド (UserID および Password) にフィールド情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81b22-118">Before enabling an application, it is necessary to both create the application and enter the field information for each of its fields (i.e. UserID and Password).</span></span> <span data-ttu-id="81b22-119">"enabled" フィールドを設定済みの状態でアプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="81b22-119">It is not possible to create an application with the “enabled” field already set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81b22-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="81b22-120">User Action</span></span>  
 <span data-ttu-id="81b22-121">アプリケーション作成 API または関連アプリケーションの新規作成ウィザードを使用して、もう一度アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="81b22-121">Create the application again (using either the Create Application API or the Create New Affiliate Application Wizard).</span></span> <span data-ttu-id="81b22-122">アプリケーションが完成し、フィールドに情報を入力してから、アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="81b22-122">When the application is complete and the fields populated, enable the application.</span></span>
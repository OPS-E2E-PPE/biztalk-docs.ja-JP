---
title: 'シングル サインオン: イベント 10705 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81456bdd-dfd8-4483-aa76-5ec72350cc70
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41db0b3aeba4e3c71da3193af807f881bb4ae586
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271074"
---
# <a name="single-sign-on-event-10705"></a><span data-ttu-id="a263f-102">シングル サインオン: イベント 10705</span><span class="sxs-lookup"><span data-stu-id="a263f-102">Single Sign-On: Event 10705</span></span>
## <a name="details"></a><span data-ttu-id="a263f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a263f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a263f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a263f-104">Product Name</span></span>|<span data-ttu-id="a263f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a263f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a263f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a263f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a263f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a263f-107">Event ID</span></span>|<span data-ttu-id="a263f-108">10705</span><span class="sxs-lookup"><span data-stu-id="a263f-108">10705</span></span>|  
|<span data-ttu-id="a263f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a263f-109">Event Source</span></span>|<span data-ttu-id="a263f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a263f-110">ENTSSO</span></span>|  
|<span data-ttu-id="a263f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a263f-111">Component</span></span>|<span data-ttu-id="a263f-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a263f-112">N\A</span></span>|  
|<span data-ttu-id="a263f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a263f-113">Symbolic Name</span></span>|<span data-ttu-id="a263f-114">SSO_WARN_PS_NOT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="a263f-114">SSO_WARN_PS_NOT_ADAPTER</span></span>|  
|<span data-ttu-id="a263f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a263f-115">Message Text</span></span>|<span data-ttu-id="a263f-116">指定されたアダプターはアダプター アプリケーションではありません。</span><span class="sxs-lookup"><span data-stu-id="a263f-116">The specified adapter is not an adapter application.</span></span> <span data-ttu-id="a263f-117">アプリケーションの種類を確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="a263f-117">Check the application type.%r</span></span><br /><br /> <span data-ttu-id="a263f-118">アダプタ: %1</span><span class="sxs-lookup"><span data-stu-id="a263f-118">Adapter: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a263f-119">説明</span><span class="sxs-lookup"><span data-stu-id="a263f-119">Explanation</span></span>  
 <span data-ttu-id="a263f-120">この警告イベントは、指定されたアダプターがアダプター アプリケーションではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="a263f-120">This Warning event indicates that the specified adapter is not an adapter application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a263f-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a263f-121">User Action</span></span>  
 <span data-ttu-id="a263f-122">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="a263f-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="a263f-123">SSO 管理 MMC スナップインを使用して、指定したアダプターを右クリックし、[プロパティ] をクリックしてアプリケーションの種類を特定するか、コマンド ライン ツール ssops -list および ssops -display を使用してアプリケーションの種類を特定します。</span><span class="sxs-lookup"><span data-stu-id="a263f-123">Use the SSO Admin MMC Snap-In, right click the specified adapter, and then click Properties to determine the application type or use the command line tool  ssops -list and ssops -display to determine the application type.</span></span>  
  
-   <span data-ttu-id="a263f-124">SSO 管理 MMC スナップインまたは ssops -addapp を使用して、アダプター アプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="a263f-124">Use the SSO Admin MMC Snap-In or ssops -addapp to set the adapter application.</span></span>  
  
 <span data-ttu-id="a263f-125">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a263f-125">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="a263f-126">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="a263f-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
---
title: "シングル サインオン: イベント 10746 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc2bc096211d8a90089b3b5fdd31b4dbb82f2b14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10746"></a><span data-ttu-id="d48c2-102">シングル サインオン: イベント 10746</span><span class="sxs-lookup"><span data-stu-id="d48c2-102">Single Sign-On: Event 10746</span></span>
## <a name="details"></a><span data-ttu-id="d48c2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d48c2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d48c2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d48c2-104">Product Name</span></span>|<span data-ttu-id="d48c2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d48c2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d48c2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d48c2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d48c2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d48c2-107">Event ID</span></span>|<span data-ttu-id="d48c2-108">10746</span><span class="sxs-lookup"><span data-stu-id="d48c2-108">10746</span></span>|  
|<span data-ttu-id="d48c2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d48c2-109">Event Source</span></span>|<span data-ttu-id="d48c2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d48c2-110">ENTSSO</span></span>|  
|<span data-ttu-id="d48c2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d48c2-111">Component</span></span>|<span data-ttu-id="d48c2-112">N\A</span><span class="sxs-lookup"><span data-stu-id="d48c2-112">N\A</span></span>|  
|<span data-ttu-id="d48c2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d48c2-113">Symbolic Name</span></span>|<span data-ttu-id="d48c2-114">SSO_WARN_PASSWORD_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="d48c2-114">SSO_WARN_PASSWORD_EXPIRED</span></span>|  
|<span data-ttu-id="d48c2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d48c2-115">Message Text</span></span>|<span data-ttu-id="d48c2-116">外部アカウントのパスワードの有効期限が切れています。%r</span><span class="sxs-lookup"><span data-stu-id="d48c2-116">The password for the external account has expired.%r</span></span><br /><br /> <span data-ttu-id="d48c2-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d48c2-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d48c2-118">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d48c2-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="d48c2-119">外部アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="d48c2-119">External Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d48c2-120">説明</span><span class="sxs-lookup"><span data-stu-id="d48c2-120">Explanation</span></span>  
 <span data-ttu-id="d48c2-121">この警告イベントは、外部アカウントのパスワードの有効期限が切れていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d48c2-121">This Warning event indicates that the password for the external account has expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d48c2-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d48c2-122">User Action</span></span>  
 <span data-ttu-id="d48c2-123">この警告を解決するには、関連付けられているエラーのシステムとアプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="d48c2-123">To resolve this warning, check the system and application event logs for associated errors.</span></span>    

## <a name="more-info"></a><span data-ttu-id="d48c2-124">詳細</span><span class="sxs-lookup"><span data-stu-id="d48c2-124">More info</span></span>
<span data-ttu-id="d48c2-125">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48c2-125">For more information, see the following resources:</span></span>  
  
-   <span data-ttu-id="d48c2-126">**パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="d48c2-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
  
-   [<span data-ttu-id="d48c2-127">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="d48c2-127">Password Synchronization</span></span>](../core/password-synchronization2.md)
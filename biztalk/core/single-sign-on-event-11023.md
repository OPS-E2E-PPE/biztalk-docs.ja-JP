---
title: 'シングル サインオン: イベント 11023 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd65ac5cab5b49f43e0c3649cf205f7f6dc2ceaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277426"
---
# <a name="single-sign-on-event-11023"></a><span data-ttu-id="47596-102">シングル サインオン: イベント 11023</span><span class="sxs-lookup"><span data-stu-id="47596-102">Single Sign-On: Event 11023</span></span>
## <a name="details"></a><span data-ttu-id="47596-103">詳細</span><span class="sxs-lookup"><span data-stu-id="47596-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47596-104">製品名</span><span class="sxs-lookup"><span data-stu-id="47596-104">Product Name</span></span>|<span data-ttu-id="47596-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="47596-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="47596-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="47596-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="47596-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="47596-107">Event ID</span></span>|<span data-ttu-id="47596-108">11023</span><span class="sxs-lookup"><span data-stu-id="47596-108">11023</span></span>|  
|<span data-ttu-id="47596-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="47596-109">Event Source</span></span>|<span data-ttu-id="47596-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="47596-110">ENTSSO</span></span>|  
|<span data-ttu-id="47596-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="47596-111">Component</span></span>|<span data-ttu-id="47596-112">なし</span><span class="sxs-lookup"><span data-stu-id="47596-112">N/A</span></span>|  
|<span data-ttu-id="47596-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="47596-113">Symbolic Name</span></span>|<span data-ttu-id="47596-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="47596-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span></span>|  
|<span data-ttu-id="47596-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="47596-115">Message Text</span></span>|<span data-ttu-id="47596-116">アカウントのロックアウトを防ぐために、SSO データベースの無効な Windows パスワードを削除しました。%r</span><span class="sxs-lookup"><span data-stu-id="47596-116">An invalid Windows password in the SSO database was deleted to prevent account lockout.%r</span></span><br /><br /> <span data-ttu-id="47596-117">SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。%r</span><span class="sxs-lookup"><span data-stu-id="47596-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="47596-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="47596-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="47596-119">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="47596-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="47596-120">Windows アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="47596-120">Windows Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47596-121">説明</span><span class="sxs-lookup"><span data-stu-id="47596-121">Explanation</span></span>  
 <span data-ttu-id="47596-122">無効な Windows パスワードを削除しました。</span><span class="sxs-lookup"><span data-stu-id="47596-122">An invalid Windows password has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47596-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="47596-123">User Action</span></span>  
 <span data-ttu-id="47596-124">SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="47596-124">Use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="47596-125">詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)です。</span><span class="sxs-lookup"><span data-stu-id="47596-125">For more information, see [Using SSO](../core/using-sso.md).</span></span>
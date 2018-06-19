---
title: 'シングル サインオン: イベント 10603 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139d1eb5-af88-4216-9604-c052f3db13c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738d2939f4178fdfaa115b8dfcc2273935c37b85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270394"
---
# <a name="single-sign-on-event-10603"></a><span data-ttu-id="79c46-102">シングル サインオン: イベント 10603</span><span class="sxs-lookup"><span data-stu-id="79c46-102">Single Sign-On: Event 10603</span></span>
## <a name="details"></a><span data-ttu-id="79c46-103">詳細</span><span class="sxs-lookup"><span data-stu-id="79c46-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79c46-104">製品名</span><span class="sxs-lookup"><span data-stu-id="79c46-104">Product Name</span></span>|<span data-ttu-id="79c46-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="79c46-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="79c46-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="79c46-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="79c46-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="79c46-107">Event ID</span></span>|<span data-ttu-id="79c46-108">10603</span><span class="sxs-lookup"><span data-stu-id="79c46-108">10603</span></span>|  
|<span data-ttu-id="79c46-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="79c46-109">Event Source</span></span>|<span data-ttu-id="79c46-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="79c46-110">ENTSSO</span></span>|  
|<span data-ttu-id="79c46-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="79c46-111">Component</span></span>|<span data-ttu-id="79c46-112">なし</span><span class="sxs-lookup"><span data-stu-id="79c46-112">N/A</span></span>|  
|<span data-ttu-id="79c46-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="79c46-113">Symbolic Name</span></span>|<span data-ttu-id="79c46-114">SSO_WARN_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="79c46-114">SSO_WARN_DB_ACCESS</span></span>|  
|<span data-ttu-id="79c46-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="79c46-115">Message Text</span></span>|<span data-ttu-id="79c46-116">SSO データベースにアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="79c46-116">Could not access the SSO database.</span></span> <span data-ttu-id="79c46-117">この状況が継続すると、SSO サービスはオフラインになります。%r</span><span class="sxs-lookup"><span data-stu-id="79c46-117">If this condition persists, the SSO service will go offline.%r</span></span><br /><br /> <span data-ttu-id="79c46-118">%1.%r</span><span class="sxs-lookup"><span data-stu-id="79c46-118">%1.%r</span></span><br /><br /> <span data-ttu-id="79c46-119">SQL エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="79c46-119">SQL Error code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="79c46-120">説明</span><span class="sxs-lookup"><span data-stu-id="79c46-120">Explanation</span></span>  
 <span data-ttu-id="79c46-121">SSO データベースを利用できません。</span><span class="sxs-lookup"><span data-stu-id="79c46-121">The SSO database is unavailable.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79c46-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="79c46-122">User Action</span></span>  
 <span data-ttu-id="79c46-123">警告に含まれる SQL エラー コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="79c46-123">Check the SQL error code contained in the warning.</span></span> <span data-ttu-id="79c46-124">これによってガイダンスが示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="79c46-124">This may offer some guidance.</span></span> <span data-ttu-id="79c46-125">ガイダンスが示されない場合は、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="79c46-125">If not, contact Microsoft Product Support Services.</span></span>
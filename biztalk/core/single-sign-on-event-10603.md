---
title: 'シングル サインオン: イベント 10603 |Microsoft Docs'
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
ms.openlocfilehash: 5416ae8a2dcfdf5a3da6d8c1d00eb5a556fc3599
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970067"
---
# <a name="single-sign-on-event-10603"></a><span data-ttu-id="ccf4f-102">シングル サインオン: イベント 10603</span><span class="sxs-lookup"><span data-stu-id="ccf4f-102">Single Sign-On: Event 10603</span></span>
## <a name="details"></a><span data-ttu-id="ccf4f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ccf4f-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ccf4f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ccf4f-104">Product Name</span></span>   |                                                             <span data-ttu-id="ccf4f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ccf4f-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="ccf4f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ccf4f-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="ccf4f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ccf4f-107">Event ID</span></span>     |                                                                       <span data-ttu-id="ccf4f-108">10603</span><span class="sxs-lookup"><span data-stu-id="ccf4f-108">10603</span></span>                                                                        |
|  <span data-ttu-id="ccf4f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ccf4f-109">Event Source</span></span>   |                                                                       <span data-ttu-id="ccf4f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ccf4f-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="ccf4f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ccf4f-111">Component</span></span>    |                                                                        <span data-ttu-id="ccf4f-112">なし</span><span class="sxs-lookup"><span data-stu-id="ccf4f-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="ccf4f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ccf4f-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="ccf4f-114">SSO_WARN_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="ccf4f-114">SSO_WARN_DB_ACCESS</span></span>                                                                 |
|  <span data-ttu-id="ccf4f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ccf4f-115">Message Text</span></span>   | <span data-ttu-id="ccf4f-116">SSO データベースにアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-116">Could not access the SSO database.</span></span> <span data-ttu-id="ccf4f-117">この状況が継続すると、SSO サービスはオフラインになります。%r</span><span class="sxs-lookup"><span data-stu-id="ccf4f-117">If this condition persists, the SSO service will go offline.%r</span></span><br /><br /> <span data-ttu-id="ccf4f-118">%1.%r</span><span class="sxs-lookup"><span data-stu-id="ccf4f-118">%1.%r</span></span><br /><br /> <span data-ttu-id="ccf4f-119">SQL エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="ccf4f-119">SQL Error code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ccf4f-120">説明</span><span class="sxs-lookup"><span data-stu-id="ccf4f-120">Explanation</span></span>  
 <span data-ttu-id="ccf4f-121">SSO データベースを利用できません。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-121">The SSO database is unavailable.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ccf4f-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ccf4f-122">User Action</span></span>  
 <span data-ttu-id="ccf4f-123">警告に含まれる SQL エラー コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-123">Check the SQL error code contained in the warning.</span></span> <span data-ttu-id="ccf4f-124">これによってガイダンスが示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-124">This may offer some guidance.</span></span> <span data-ttu-id="ccf4f-125">ガイダンスが示されない場合は、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-125">If not, contact Microsoft Product Support Services.</span></span>
---
title: シングル サインオン:イベント 10603 |Microsoft Docs
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
ms.openlocfilehash: c57b75ba39be2b49606b351573f50c677077aa48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397780"
---
# <a name="single-sign-on-event-10603"></a><span data-ttu-id="64593-102">シングル サインオン:イベント 10603</span><span class="sxs-lookup"><span data-stu-id="64593-102">Single Sign-On: Event 10603</span></span>
## <a name="details"></a><span data-ttu-id="64593-103">詳細</span><span class="sxs-lookup"><span data-stu-id="64593-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="64593-104">製品名</span><span class="sxs-lookup"><span data-stu-id="64593-104">Product Name</span></span>   |                                                             <span data-ttu-id="64593-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="64593-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="64593-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="64593-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="64593-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="64593-107">Event ID</span></span>     |                                                                       <span data-ttu-id="64593-108">10603</span><span class="sxs-lookup"><span data-stu-id="64593-108">10603</span></span>                                                                        |
|  <span data-ttu-id="64593-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="64593-109">Event Source</span></span>   |                                                                       <span data-ttu-id="64593-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="64593-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="64593-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="64593-111">Component</span></span>    |                                                                        <span data-ttu-id="64593-112">なし</span><span class="sxs-lookup"><span data-stu-id="64593-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="64593-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="64593-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="64593-114">SSO_WARN_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="64593-114">SSO_WARN_DB_ACCESS</span></span>                                                                 |
|  <span data-ttu-id="64593-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="64593-115">Message Text</span></span>   | <span data-ttu-id="64593-116">SSO データベースにアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="64593-116">Could not access the SSO database.</span></span> <span data-ttu-id="64593-117">この条件が解決しない場合、SSO サービスになる offline.%r</span><span class="sxs-lookup"><span data-stu-id="64593-117">If this condition persists, the SSO service will go offline.%r</span></span><br /><br /> <span data-ttu-id="64593-118">%1.%r</span><span class="sxs-lookup"><span data-stu-id="64593-118">%1.%r</span></span><br /><br /> <span data-ttu-id="64593-119">SQL エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="64593-119">SQL Error code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="64593-120">説明</span><span class="sxs-lookup"><span data-stu-id="64593-120">Explanation</span></span>  
 <span data-ttu-id="64593-121">SSO データベースは使用できません。</span><span class="sxs-lookup"><span data-stu-id="64593-121">The SSO database is unavailable.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64593-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="64593-122">User Action</span></span>  
 <span data-ttu-id="64593-123">警告に含まれる SQL エラー コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="64593-123">Check the SQL error code contained in the warning.</span></span> <span data-ttu-id="64593-124">いくつかのガイダンスが提供することができます。</span><span class="sxs-lookup"><span data-stu-id="64593-124">This may offer some guidance.</span></span> <span data-ttu-id="64593-125">それ以外の場合は、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="64593-125">If not, contact Microsoft Product Support Services.</span></span>
---
title: "シングル サインオン: イベント 10856 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10c06a86-e402-4adc-abbe-5ded923d626a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6be0f098929e0419378de9eaebdf0ca00f5eb421
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10856"></a><span data-ttu-id="3794d-102">シングル サインオン: イベント 10856</span><span class="sxs-lookup"><span data-stu-id="3794d-102">Single Sign-On: Event 10856</span></span>
## <a name="details"></a><span data-ttu-id="3794d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3794d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3794d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3794d-104">Product Name</span></span>|<span data-ttu-id="3794d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3794d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3794d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3794d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3794d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3794d-107">Event ID</span></span>|<span data-ttu-id="3794d-108">10856</span><span class="sxs-lookup"><span data-stu-id="3794d-108">10856</span></span>|  
|<span data-ttu-id="3794d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3794d-109">Event Source</span></span>|<span data-ttu-id="3794d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3794d-110">ENTSSO</span></span>|  
|<span data-ttu-id="3794d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3794d-111">Component</span></span>|<span data-ttu-id="3794d-112">なし</span><span class="sxs-lookup"><span data-stu-id="3794d-112">N/A</span></span>|  
|<span data-ttu-id="3794d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3794d-113">Symbolic Name</span></span>|<span data-ttu-id="3794d-114">ENTSSO_E_MAPPING_CREATE_RESTRICTED</span><span class="sxs-lookup"><span data-stu-id="3794d-114">ENTSSO_E_MAPPING_CREATE_RESTRICTED</span></span>|  
|<span data-ttu-id="3794d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3794d-115">Message Text</span></span>|<span data-ttu-id="3794d-116">アプリケーション ユーザーは、このアプリケーションのマッピングを作成できません。</span><span class="sxs-lookup"><span data-stu-id="3794d-116">Application Users cannot create mappings for this application.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3794d-117">説明</span><span class="sxs-lookup"><span data-stu-id="3794d-117">Explanation</span></span>  
 <span data-ttu-id="3794d-118">このアプリケーションは、Application Users グループのメンバーにマッピングの作成を許可するように構成されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="3794d-118">This application was configured in such a way that members of the Application Users group are not permitted to create mappings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3794d-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3794d-119">User Action</span></span>  
 <span data-ttu-id="3794d-120">十分な特権を持つユーザーにこのようなマッピングの作成を依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3794d-120">You should ask a person with sufficient privileges to create these mappings.</span></span>
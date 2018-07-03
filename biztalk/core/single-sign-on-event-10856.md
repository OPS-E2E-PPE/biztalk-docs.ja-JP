---
title: 'シングル サインオン: イベント 10856 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10c06a86-e402-4adc-abbe-5ded923d626a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 707160ddfededefd5f0ef47e77df08844b38abcf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989347"
---
# <a name="single-sign-on-event-10856"></a><span data-ttu-id="55494-102">シングル サインオン: イベント 10856</span><span class="sxs-lookup"><span data-stu-id="55494-102">Single Sign-On: Event 10856</span></span>
## <a name="details"></a><span data-ttu-id="55494-103">詳細</span><span class="sxs-lookup"><span data-stu-id="55494-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="55494-104">製品名</span><span class="sxs-lookup"><span data-stu-id="55494-104">Product Name</span></span>   |                   <span data-ttu-id="55494-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="55494-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="55494-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="55494-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="55494-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="55494-107">Event ID</span></span>     |                             <span data-ttu-id="55494-108">10856</span><span class="sxs-lookup"><span data-stu-id="55494-108">10856</span></span>                              |
|  <span data-ttu-id="55494-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="55494-109">Event Source</span></span>   |                             <span data-ttu-id="55494-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="55494-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="55494-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="55494-111">Component</span></span>    |                              <span data-ttu-id="55494-112">なし</span><span class="sxs-lookup"><span data-stu-id="55494-112">N/A</span></span>                               |
|  <span data-ttu-id="55494-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="55494-113">Symbolic Name</span></span>  |               <span data-ttu-id="55494-114">ENTSSO_E_MAPPING_CREATE_RESTRICTED</span><span class="sxs-lookup"><span data-stu-id="55494-114">ENTSSO_E_MAPPING_CREATE_RESTRICTED</span></span>               |
|  <span data-ttu-id="55494-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="55494-115">Message Text</span></span>   | <span data-ttu-id="55494-116">アプリケーションのユーザーには、このアプリケーションのマッピングを作成できません。</span><span class="sxs-lookup"><span data-stu-id="55494-116">Application Users cannot create mappings for this application.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="55494-117">説明</span><span class="sxs-lookup"><span data-stu-id="55494-117">Explanation</span></span>  
 <span data-ttu-id="55494-118">このアプリケーションは、Application Users グループのメンバーにマッピングの作成を許可するように構成されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="55494-118">This application was configured in such a way that members of the Application Users group are not permitted to create mappings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55494-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="55494-119">User Action</span></span>  
 <span data-ttu-id="55494-120">十分な特権を持つユーザーにこのようなマッピングの作成を依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55494-120">You should ask a person with sufficient privileges to create these mappings.</span></span>
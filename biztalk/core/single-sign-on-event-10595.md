---
title: シングル サインオン:イベント 10595 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1517478c-7217-4e34-a5cb-ff7deea367ed
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6aecfef61ece56075c4eb0c47ba7852380d4c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397849"
---
# <a name="single-sign-on-event-10595"></a><span data-ttu-id="16e9e-102">シングル サインオン:イベント 10595</span><span class="sxs-lookup"><span data-stu-id="16e9e-102">Single Sign-On: Event 10595</span></span>
## <a name="details"></a><span data-ttu-id="16e9e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="16e9e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="16e9e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="16e9e-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="16e9e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="16e9e-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="16e9e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="16e9e-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="16e9e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="16e9e-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="16e9e-108">10595</span><span class="sxs-lookup"><span data-stu-id="16e9e-108">10595</span></span>                                                                                                        |
|  <span data-ttu-id="16e9e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="16e9e-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="16e9e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="16e9e-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="16e9e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="16e9e-111">Component</span></span>    |                                                                                                        <span data-ttu-id="16e9e-112">なし</span><span class="sxs-lookup"><span data-stu-id="16e9e-112">N/A</span></span>                                                                                                         |
|  <span data-ttu-id="16e9e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="16e9e-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="16e9e-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span><span class="sxs-lookup"><span data-stu-id="16e9e-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span></span>                                                                                           |
|  <span data-ttu-id="16e9e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="16e9e-115">Message Text</span></span>   | <span data-ttu-id="16e9e-116">フィールドがこの application.%r 不完全なため、アプリケーションを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="16e9e-116">The application cannot be enabled because the fields are incomplete for this application.%r</span></span><br /><br /> <span data-ttu-id="16e9e-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="16e9e-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="16e9e-118">定義したフィールドの数: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="16e9e-118">Number of Fields Defined: %2%r</span></span><br /><br /> <span data-ttu-id="16e9e-119">作成されたフィールドの数: %3</span><span class="sxs-lookup"><span data-stu-id="16e9e-119">Number of Fields Created: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="16e9e-120">説明</span><span class="sxs-lookup"><span data-stu-id="16e9e-120">Explanation</span></span>  
 <span data-ttu-id="16e9e-121">レベル API でアプリケーションを作成、するときに、アプリケーションでは定義フィールド (UserID、Password) の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="16e9e-121">When creating an application at the API level, you specified the number of fields (i.e. UserID, Password) the application would define.</span></span> <span data-ttu-id="16e9e-122">定義されている各フィールドを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e9e-122">Each field that has been defined must also be created.</span></span> <span data-ttu-id="16e9e-123">この警告メッセージは、アプリケーション名、定義されている場合、フィールドの数と作成されたフィールドの数を示します。</span><span class="sxs-lookup"><span data-stu-id="16e9e-123">This warning message lists the application name, number of fields defined, and number of fields created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16e9e-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="16e9e-124">User Action</span></span>  
 <span data-ttu-id="16e9e-125">定義済みだが作成されていないフィールドを決定し、戻ってそれらを作成します。</span><span class="sxs-lookup"><span data-stu-id="16e9e-125">Determine which fields were defined but not created, and then go back and create them.</span></span>
---
title: 'シングル サインオン: イベント 10595 |Microsoft Docs'
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
ms.openlocfilehash: 0cbc952197971f4e0db0586bc4f1d2d6c37aba44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995227"
---
# <a name="single-sign-on-event-10595"></a><span data-ttu-id="1d2b4-102">シングル サインオン: イベント 10595</span><span class="sxs-lookup"><span data-stu-id="1d2b4-102">Single Sign-On: Event 10595</span></span>
## <a name="details"></a><span data-ttu-id="1d2b4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1d2b4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1d2b4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1d2b4-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="1d2b4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1d2b4-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="1d2b4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1d2b4-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="1d2b4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1d2b4-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="1d2b4-108">10595</span><span class="sxs-lookup"><span data-stu-id="1d2b4-108">10595</span></span>                                                                                                        |
|  <span data-ttu-id="1d2b4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1d2b4-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="1d2b4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1d2b4-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="1d2b4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1d2b4-111">Component</span></span>    |                                                                                                        <span data-ttu-id="1d2b4-112">なし</span><span class="sxs-lookup"><span data-stu-id="1d2b4-112">N/A</span></span>                                                                                                         |
|  <span data-ttu-id="1d2b4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1d2b4-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="1d2b4-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span><span class="sxs-lookup"><span data-stu-id="1d2b4-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span></span>                                                                                           |
|  <span data-ttu-id="1d2b4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1d2b4-115">Message Text</span></span>   | <span data-ttu-id="1d2b4-116">このアプリケーションのフィールドが入力されていないので、アプリケーションを有効にすることができません。%r</span><span class="sxs-lookup"><span data-stu-id="1d2b4-116">The application cannot be enabled because the fields are incomplete for this application.%r</span></span><br /><br /> <span data-ttu-id="1d2b4-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1d2b4-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="1d2b4-118">定義したフィールドの数: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="1d2b4-118">Number of Fields Defined: %2%r</span></span><br /><br /> <span data-ttu-id="1d2b4-119">作成されたフィールドの数: %3</span><span class="sxs-lookup"><span data-stu-id="1d2b4-119">Number of Fields Created: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1d2b4-120">説明</span><span class="sxs-lookup"><span data-stu-id="1d2b4-120">Explanation</span></span>  
 <span data-ttu-id="1d2b4-121">API レベルでアプリケーションを作成するときに、アプリケーションで定義するフィールド (UserID、Password) を指定しました。</span><span class="sxs-lookup"><span data-stu-id="1d2b4-121">When creating an application at the API level, you specified the number of fields (i.e. UserID, Password) the application would define.</span></span> <span data-ttu-id="1d2b4-122">定義した各フィールドは、作成することも必要です。</span><span class="sxs-lookup"><span data-stu-id="1d2b4-122">Each field that has been defined must also be created.</span></span> <span data-ttu-id="1d2b4-123">この警告メッセージは、アプリケーション名、定義されているフィールド数、および作成されたフィールド数の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="1d2b4-123">This warning message lists the application name, number of fields defined, and number of fields created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d2b4-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1d2b4-124">User Action</span></span>  
 <span data-ttu-id="1d2b4-125">定義済みだが作成されていないフィールドを特定し、前の手順に戻ってフィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d2b4-125">Determine which fields were defined but not created, and then go back and create them.</span></span>
---
title: シングル サインオン:イベント 10818 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa489e88a3742dfb7acbd1995a6f996bdc58142c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295915"
---
# <a name="single-sign-on-event-10818"></a><span data-ttu-id="1a431-102">シングル サインオン:イベント 10818</span><span class="sxs-lookup"><span data-stu-id="1a431-102">Single Sign-On: Event 10818</span></span>
## <a name="details"></a><span data-ttu-id="1a431-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1a431-103">Details</span></span>  
  
|                 |                                                                                 |
|-----------------|---------------------------------------------------------------------------------|
|  <span data-ttu-id="1a431-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1a431-104">Product Name</span></span>   |                            <span data-ttu-id="1a431-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1a431-105">Enterprise Single Sign-On</span></span>                            |
| <span data-ttu-id="1a431-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1a431-106">Product Version</span></span> |           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="1a431-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1a431-107">Event ID</span></span>     |                                      <span data-ttu-id="1a431-108">10818</span><span class="sxs-lookup"><span data-stu-id="1a431-108">10818</span></span>                                      |
|  <span data-ttu-id="1a431-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1a431-109">Event Source</span></span>   |                                     <span data-ttu-id="1a431-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1a431-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="1a431-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a431-111">Component</span></span>    |                                       <span data-ttu-id="1a431-112">なし</span><span class="sxs-lookup"><span data-stu-id="1a431-112">N/A</span></span>                                       |
|  <span data-ttu-id="1a431-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1a431-113">Symbolic Name</span></span>  |                         <span data-ttu-id="1a431-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span><span class="sxs-lookup"><span data-stu-id="1a431-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span></span>                          |
|  <span data-ttu-id="1a431-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1a431-115">Message Text</span></span>   | <span data-ttu-id="1a431-116">アプリケーションに 2 つのフィールドが必要または同期の 1 つのみのフィールドをマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a431-116">The application must have two fields or only one field must be marked for sync.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1a431-117">説明</span><span class="sxs-lookup"><span data-stu-id="1a431-117">Explanation</span></span>  
 <span data-ttu-id="1a431-118">複数の 2 つのフィールドがある場合、1 つだけ必要があります指定はパスワードの同期です。</span><span class="sxs-lookup"><span data-stu-id="1a431-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a431-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1a431-119">User Action</span></span>  
 <span data-ttu-id="1a431-120">このような状況を解決するには、するには、アプリケーションを削除し、再作成するため、これらのガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="1a431-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>
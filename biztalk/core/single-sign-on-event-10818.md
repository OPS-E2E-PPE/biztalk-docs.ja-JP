---
title: 'シングル サインオン: イベント 10818 |Microsoft Docs'
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
ms.openlocfilehash: 328e4286ed024923ab66e147e806ef5db5065b77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972435"
---
# <a name="single-sign-on-event-10818"></a><span data-ttu-id="db21a-102">シングル サインオン: イベント 10818</span><span class="sxs-lookup"><span data-stu-id="db21a-102">Single Sign-On: Event 10818</span></span>
## <a name="details"></a><span data-ttu-id="db21a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="db21a-103">Details</span></span>  
  
|                 |                                                                                 |
|-----------------|---------------------------------------------------------------------------------|
|  <span data-ttu-id="db21a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="db21a-104">Product Name</span></span>   |                            <span data-ttu-id="db21a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="db21a-105">Enterprise Single Sign-On</span></span>                            |
| <span data-ttu-id="db21a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="db21a-106">Product Version</span></span> |           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="db21a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="db21a-107">Event ID</span></span>     |                                      <span data-ttu-id="db21a-108">10818</span><span class="sxs-lookup"><span data-stu-id="db21a-108">10818</span></span>                                      |
|  <span data-ttu-id="db21a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="db21a-109">Event Source</span></span>   |                                     <span data-ttu-id="db21a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="db21a-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="db21a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="db21a-111">Component</span></span>    |                                       <span data-ttu-id="db21a-112">なし</span><span class="sxs-lookup"><span data-stu-id="db21a-112">N/A</span></span>                                       |
|  <span data-ttu-id="db21a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="db21a-113">Symbolic Name</span></span>  |                         <span data-ttu-id="db21a-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span><span class="sxs-lookup"><span data-stu-id="db21a-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span></span>                          |
|  <span data-ttu-id="db21a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="db21a-115">Message Text</span></span>   | <span data-ttu-id="db21a-116">アプリケーションのフィールドは 2 つであるか、または 1 つのフィールドだけが同期の対象としてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db21a-116">The application must have two fields or only one field must be marked for sync.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="db21a-117">説明</span><span class="sxs-lookup"><span data-stu-id="db21a-117">Explanation</span></span>  
 <span data-ttu-id="db21a-118">フィールドが 2 つ以上ある場合、パスワードの同期を設定できるのは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="db21a-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="db21a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="db21a-119">User Action</span></span>  
 <span data-ttu-id="db21a-120">この状況を解決するために、アプリケーションをいったん削除し、これらのガイドラインに沿って再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db21a-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>
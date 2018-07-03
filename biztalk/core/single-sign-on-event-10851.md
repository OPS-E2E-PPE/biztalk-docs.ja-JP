---
title: 'シングル サインオン: イベント 10851 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15121c1d7829f04bd9c106ed71da391d401ae564
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987235"
---
# <a name="single-sign-on-event-10851"></a><span data-ttu-id="acc36-102">シングル サインオン: イベント 10851</span><span class="sxs-lookup"><span data-stu-id="acc36-102">Single Sign-On: Event 10851</span></span>
## <a name="details"></a><span data-ttu-id="acc36-103">詳細</span><span class="sxs-lookup"><span data-stu-id="acc36-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="acc36-104">製品名</span><span class="sxs-lookup"><span data-stu-id="acc36-104">Product Name</span></span>   |                                             <span data-ttu-id="acc36-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="acc36-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="acc36-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="acc36-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="acc36-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="acc36-107">Event ID</span></span>     |                                                       <span data-ttu-id="acc36-108">10851</span><span class="sxs-lookup"><span data-stu-id="acc36-108">10851</span></span>                                                       |
|  <span data-ttu-id="acc36-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="acc36-109">Event Source</span></span>   |                                                      <span data-ttu-id="acc36-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="acc36-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="acc36-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="acc36-111">Component</span></span>    |                                                        <span data-ttu-id="acc36-112">なし</span><span class="sxs-lookup"><span data-stu-id="acc36-112">N/A</span></span>                                                        |
|  <span data-ttu-id="acc36-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="acc36-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="acc36-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span><span class="sxs-lookup"><span data-stu-id="acc36-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span></span>                                      |
|  <span data-ttu-id="acc36-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="acc36-115">Message Text</span></span>   | <span data-ttu-id="acc36-116">'直接パスワード同期' フラグが設定されているので、アプリケーションをパスワード同期アダプターに割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="acc36-116">The application cannot be assigned to a password sync adapter because it has the 'direct password sync' flag set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="acc36-117">説明</span><span class="sxs-lookup"><span data-stu-id="acc36-117">Explanation</span></span>  
 <span data-ttu-id="acc36-118">アプリケーションでは、直接パスワード同期とパスワード同期アダプターの両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="acc36-118">An application cannot use both direct password sync and a password sync adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="acc36-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="acc36-119">User Action</span></span>  
 <span data-ttu-id="acc36-120">アプリケーションを見直して、直接パスワード同期が必要であるかどうかを決定します。必要である場合は、このフラグを設定したままにして、アプリケーションをパスワード同期アダプターに割り当てないようにします。</span><span class="sxs-lookup"><span data-stu-id="acc36-120">Review your application and decide whether or not it should have direct password sync. If it should, leave the flag set as it is and do not attempt to assign the application to a password sync adapter.</span></span> <span data-ttu-id="acc36-121">必要ではない場合は、このフラグをオフにし、必要に応じてアプリケーションをパスワード同期アダプターに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="acc36-121">If it should not, then turn the flag off and assign the application to a password sync adapter as appropriate.</span></span>
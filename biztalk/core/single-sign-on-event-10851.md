---
title: シングル サインオン:イベント 10851 |Microsoft Docs
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
ms.openlocfilehash: 172eae8de676cb581dd07b823ab362bf1a2401b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306631"
---
# <a name="single-sign-on-event-10851"></a><span data-ttu-id="b222a-102">シングル サインオン:イベント 10851</span><span class="sxs-lookup"><span data-stu-id="b222a-102">Single Sign-On: Event 10851</span></span>
## <a name="details"></a><span data-ttu-id="b222a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b222a-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b222a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b222a-104">Product Name</span></span>   |                                             <span data-ttu-id="b222a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b222a-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="b222a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b222a-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="b222a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b222a-107">Event ID</span></span>     |                                                       <span data-ttu-id="b222a-108">10851</span><span class="sxs-lookup"><span data-stu-id="b222a-108">10851</span></span>                                                       |
|  <span data-ttu-id="b222a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b222a-109">Event Source</span></span>   |                                                      <span data-ttu-id="b222a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b222a-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="b222a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b222a-111">Component</span></span>    |                                                        <span data-ttu-id="b222a-112">なし</span><span class="sxs-lookup"><span data-stu-id="b222a-112">N/A</span></span>                                                        |
|  <span data-ttu-id="b222a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b222a-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="b222a-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span><span class="sxs-lookup"><span data-stu-id="b222a-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span></span>                                      |
|  <span data-ttu-id="b222a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b222a-115">Message Text</span></span>   | <span data-ttu-id="b222a-116">アプリケーションは、'direct password sync' フラグが設定があるため、パスワード同期アダプターに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="b222a-116">The application cannot be assigned to a password sync adapter because it has the 'direct password sync' flag set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b222a-117">説明</span><span class="sxs-lookup"><span data-stu-id="b222a-117">Explanation</span></span>  
 <span data-ttu-id="b222a-118">アプリケーションには、直接パスワード同期とパスワード同期アダプターの両方を使用できません。</span><span class="sxs-lookup"><span data-stu-id="b222a-118">An application cannot use both direct password sync and a password sync adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b222a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b222a-119">User Action</span></span>  
 <span data-ttu-id="b222a-120">アプリケーションを確認し、直接パスワード同期が必要かどうかを決定します。フラグが設定のままにする必要があります、その場合は、アプリケーションをパスワード同期アダプターに割り当てるには試行されません。</span><span class="sxs-lookup"><span data-stu-id="b222a-120">Review your application and decide whether or not it should have direct password sync. If it should, leave the flag set as it is and do not attempt to assign the application to a password sync adapter.</span></span> <span data-ttu-id="b222a-121">不要な場合は、フラグをオフにし、必要に応じてパスワード同期アダプターにアプリケーションを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b222a-121">If it should not, then turn the flag off and assign the application to a password sync adapter as appropriate.</span></span>
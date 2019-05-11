---
title: シングル サインオン:イベント 10710 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469dc407-be7a-45a1-bcf5-2ba7060a19e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62c43785a276ce33412b509af7a034697caab9f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397253"
---
# <a name="single-sign-on-event-10710"></a><span data-ttu-id="01a73-102">シングル サインオン:イベント 10710</span><span class="sxs-lookup"><span data-stu-id="01a73-102">Single Sign-On: Event 10710</span></span>
## <a name="details"></a><span data-ttu-id="01a73-103">詳細</span><span class="sxs-lookup"><span data-stu-id="01a73-103">Details</span></span>  

|                 |                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="01a73-104">製品名</span><span class="sxs-lookup"><span data-stu-id="01a73-104">Product Name</span></span>   |                                                                          <span data-ttu-id="01a73-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="01a73-105">Enterprise Single Sign-On</span></span>                                                                          |
| <span data-ttu-id="01a73-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="01a73-106">Product Version</span></span> |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                          |
|    <span data-ttu-id="01a73-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="01a73-107">Event ID</span></span>     |                                                                                    <span data-ttu-id="01a73-108">10710</span><span class="sxs-lookup"><span data-stu-id="01a73-108">10710</span></span>                                                                                    |
|  <span data-ttu-id="01a73-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="01a73-109">Event Source</span></span>   |                                                                                   <span data-ttu-id="01a73-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="01a73-110">ENTSSO</span></span>                                                                                    |
|    <span data-ttu-id="01a73-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="01a73-111">Component</span></span>    |                                                                                     <span data-ttu-id="01a73-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="01a73-112">N\A</span></span>                                                                                     |
|  <span data-ttu-id="01a73-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="01a73-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="01a73-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span><span class="sxs-lookup"><span data-stu-id="01a73-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span></span>                                                                        |
|  <span data-ttu-id="01a73-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="01a73-115">Message Text</span></span>   | <span data-ttu-id="01a73-116">Windows パスワードの変更は抑制されました (重複および discarded).%r として検出します。</span><span class="sxs-lookup"><span data-stu-id="01a73-116">A Windows password change was damped (detected as a duplicate and discarded).%r</span></span><br /><br /> <span data-ttu-id="01a73-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="01a73-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="01a73-118">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="01a73-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="01a73-119">クライアント ユーザー: %3</span><span class="sxs-lookup"><span data-stu-id="01a73-119">Client User: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="01a73-120">説明</span><span class="sxs-lookup"><span data-stu-id="01a73-120">Explanation</span></span>  
 <span data-ttu-id="01a73-121">この情報イベントは、重複として検出されたために、Windows パスワードの変更が破棄されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="01a73-121">This Information event indicates that a Windows password change was discarded because it was detected as a duplicate.</span></span>  

## <a name="user-action"></a><span data-ttu-id="01a73-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="01a73-122">User Action</span></span>  

- <span data-ttu-id="01a73-123">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="01a73-123">No user action is necessary.</span></span>  

  <span data-ttu-id="01a73-124">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01a73-124">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="01a73-125">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="01a73-125">Password Synchronization</span></span>](../core/password-synchronization2.md)

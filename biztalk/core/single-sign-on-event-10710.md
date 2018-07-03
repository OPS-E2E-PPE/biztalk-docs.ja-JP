---
title: 'シングル サインオン: イベント 10710 |Microsoft Docs'
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
ms.openlocfilehash: 888468da03c01f654bd550ce210b02c4a03ad40b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989923"
---
# <a name="single-sign-on-event-10710"></a><span data-ttu-id="7a5eb-102">シングル サインオン: イベント 10710</span><span class="sxs-lookup"><span data-stu-id="7a5eb-102">Single Sign-On: Event 10710</span></span>
## <a name="details"></a><span data-ttu-id="7a5eb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7a5eb-103">Details</span></span>  

|                 |                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7a5eb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7a5eb-104">Product Name</span></span>   |                                                                          <span data-ttu-id="7a5eb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7a5eb-105">Enterprise Single Sign-On</span></span>                                                                          |
| <span data-ttu-id="7a5eb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7a5eb-106">Product Version</span></span> |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                          |
|    <span data-ttu-id="7a5eb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7a5eb-107">Event ID</span></span>     |                                                                                    <span data-ttu-id="7a5eb-108">10710</span><span class="sxs-lookup"><span data-stu-id="7a5eb-108">10710</span></span>                                                                                    |
|  <span data-ttu-id="7a5eb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7a5eb-109">Event Source</span></span>   |                                                                                   <span data-ttu-id="7a5eb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7a5eb-110">ENTSSO</span></span>                                                                                    |
|    <span data-ttu-id="7a5eb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7a5eb-111">Component</span></span>    |                                                                                     <span data-ttu-id="7a5eb-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7a5eb-112">N\A</span></span>                                                                                     |
|  <span data-ttu-id="7a5eb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7a5eb-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="7a5eb-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span><span class="sxs-lookup"><span data-stu-id="7a5eb-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span></span>                                                                        |
|  <span data-ttu-id="7a5eb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7a5eb-115">Message Text</span></span>   | <span data-ttu-id="7a5eb-116">Windows パスワードの変更は抑制されました (重複として検出され、破棄されました)。%r</span><span class="sxs-lookup"><span data-stu-id="7a5eb-116">A Windows password change was damped (detected as a duplicate and discarded).%r</span></span><br /><br /> <span data-ttu-id="7a5eb-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7a5eb-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="7a5eb-118">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="7a5eb-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="7a5eb-119">クライアント ユーザー: %3</span><span class="sxs-lookup"><span data-stu-id="7a5eb-119">Client User: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="7a5eb-120">説明</span><span class="sxs-lookup"><span data-stu-id="7a5eb-120">Explanation</span></span>  
 <span data-ttu-id="7a5eb-121">この情報イベントは、Windows パスワードの変更が重複として検出されたため、破棄されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="7a5eb-121">This Information event indicates that a Windows password change was discarded because it was detected as a duplicate.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7a5eb-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7a5eb-122">User Action</span></span>  

- <span data-ttu-id="7a5eb-123">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7a5eb-123">No user action is necessary.</span></span>  

  <span data-ttu-id="7a5eb-124">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a5eb-124">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="7a5eb-125">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="7a5eb-125">Password Synchronization</span></span>](../core/password-synchronization2.md)

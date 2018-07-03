---
title: 'シングル サインオン: イベント 10739 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1039c832-80ff-4cc2-97b4-2671672b6b12
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a08c0b5194b3c6cb2a75966a33d7215fd0b7b499
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969451"
---
# <a name="single-sign-on-event-10739"></a><span data-ttu-id="90afe-102">シングル サインオン: イベント 10739</span><span class="sxs-lookup"><span data-stu-id="90afe-102">Single Sign-On: Event 10739</span></span>
## <a name="details"></a><span data-ttu-id="90afe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="90afe-103">Details</span></span>  

|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="90afe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="90afe-104">Product Name</span></span>   |                                                                               <span data-ttu-id="90afe-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="90afe-105">Enterprise Single Sign-On</span></span>                                                                               |
| <span data-ttu-id="90afe-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="90afe-106">Product Version</span></span> |                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                               |
|    <span data-ttu-id="90afe-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="90afe-107">Event ID</span></span>     |                                                                                         <span data-ttu-id="90afe-108">10739</span><span class="sxs-lookup"><span data-stu-id="90afe-108">10739</span></span>                                                                                         |
|  <span data-ttu-id="90afe-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="90afe-109">Event Source</span></span>   |                                                                                        <span data-ttu-id="90afe-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="90afe-110">ENTSSO</span></span>                                                                                         |
|    <span data-ttu-id="90afe-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="90afe-111">Component</span></span>    |                                                                                          <span data-ttu-id="90afe-112">N\A</span><span class="sxs-lookup"><span data-stu-id="90afe-112">N\A</span></span>                                                                                          |
|  <span data-ttu-id="90afe-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="90afe-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="90afe-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="90afe-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span></span>                                                                        |
|  <span data-ttu-id="90afe-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="90afe-115">Message Text</span></span>   | <span data-ttu-id="90afe-116">SSO データベースの Windows パスワードを更新できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="90afe-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="90afe-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="90afe-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="90afe-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="90afe-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="90afe-119">Windows アカウント: %3\\% 4 %r</span><span class="sxs-lookup"><span data-stu-id="90afe-119">Windows Account: %3\\%4%r</span></span><br /><br /> <span data-ttu-id="90afe-120">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="90afe-120">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="90afe-121">説明</span><span class="sxs-lookup"><span data-stu-id="90afe-121">Explanation</span></span>  
 <span data-ttu-id="90afe-122">この警告イベントは、SSO によって、SSO データベース内の Windows パスワードを更新できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="90afe-122">This Warning event indicates that SSO failed to update the Windows password in the SSO database.</span></span> <span data-ttu-id="90afe-123">警告メッセージには、失敗の考えられるさまざまな原因が示されています。場合によっては、この警告で構成の問題が示されることがあります。また、パスワードの変更中にマッピングが削除された可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="90afe-123">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="90afe-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="90afe-124">User Action</span></span>  
 <span data-ttu-id="90afe-125">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="90afe-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="90afe-126">パスワードの変更を再試行します。</span><span class="sxs-lookup"><span data-stu-id="90afe-126">Retry the password change.</span></span>  

- <span data-ttu-id="90afe-127">再試行も失敗する場合、UI またはコマンド ライン ツールを使用して手動でパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="90afe-127">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  

  <span data-ttu-id="90afe-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90afe-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="90afe-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="90afe-129">Password Synchronization</span></span>](../core/password-synchronization2.md)

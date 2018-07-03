---
title: 'シングル サインオン: イベント 10737 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2102930b-8b1f-4d48-a14d-e8884dc7f9aa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd21b244e86c14aaf0f3af7418f1ca2ed8fbf067
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987683"
---
# <a name="single-sign-on-event-10737"></a><span data-ttu-id="32be8-102">シングル サインオン: イベント 10737</span><span class="sxs-lookup"><span data-stu-id="32be8-102">Single Sign-On: Event 10737</span></span>
## <a name="details"></a><span data-ttu-id="32be8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="32be8-103">Details</span></span>  

|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="32be8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="32be8-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="32be8-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="32be8-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="32be8-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="32be8-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="32be8-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="32be8-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="32be8-108">10737</span><span class="sxs-lookup"><span data-stu-id="32be8-108">10737</span></span>                                                                                                          |
|  <span data-ttu-id="32be8-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="32be8-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="32be8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="32be8-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="32be8-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="32be8-111">Component</span></span>    |                                                                                                          <span data-ttu-id="32be8-112">N\A</span><span class="sxs-lookup"><span data-stu-id="32be8-112">N\A</span></span>                                                                                                           |
|  <span data-ttu-id="32be8-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="32be8-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="32be8-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="32be8-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span></span>                                                                                            |
|  <span data-ttu-id="32be8-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="32be8-115">Message Text</span></span>   | <span data-ttu-id="32be8-116">SSO データベース内で外部パスワードを更新できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="32be8-116">Failed to update the external password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="32be8-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="32be8-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="32be8-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="32be8-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="32be8-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="32be8-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="32be8-120">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="32be8-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="32be8-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="32be8-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="32be8-122">説明</span><span class="sxs-lookup"><span data-stu-id="32be8-122">Explanation</span></span>  
 <span data-ttu-id="32be8-123">この警告イベントは、SSO によって、SSO データベース内の外部パスワードを更新できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="32be8-123">This Warning event indicates that SSO failed to update the external password in the SSO database.</span></span> <span data-ttu-id="32be8-124">警告メッセージには、失敗の考えられるさまざまな原因が示されています。場合によっては、この警告で構成の問題が示されることがあります。また、パスワードの変更中にマッピングが削除された可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="32be8-124">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="32be8-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="32be8-125">User Action</span></span>  
 <span data-ttu-id="32be8-126">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="32be8-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="32be8-127">パスワードの変更を再試行します。</span><span class="sxs-lookup"><span data-stu-id="32be8-127">Retry the password change.</span></span>  

- <span data-ttu-id="32be8-128">再試行も失敗する場合、UI またはコマンド ライン ツールを使用して手動でパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="32be8-128">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  

  <span data-ttu-id="32be8-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32be8-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="32be8-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="32be8-130">Password Synchronization</span></span>](../core/password-synchronization2.md)

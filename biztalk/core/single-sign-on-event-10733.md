---
title: 'シングル サインオン: イベント 10733 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd392f2a00d3010039501b99f731f1d9c350cdda
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023488"
---
# <a name="single-sign-on-event-10733"></a><span data-ttu-id="a1727-102">シングル サインオン: イベント 10733</span><span class="sxs-lookup"><span data-stu-id="a1727-102">Single Sign-On: Event 10733</span></span>
## <a name="details"></a><span data-ttu-id="a1727-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a1727-103">Details</span></span>  

|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a1727-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a1727-104">Product Name</span></span>   |                                                                  <span data-ttu-id="a1727-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a1727-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="a1727-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a1727-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    <span data-ttu-id="a1727-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a1727-107">Event ID</span></span>     |                                                                            <span data-ttu-id="a1727-108">10733</span><span class="sxs-lookup"><span data-stu-id="a1727-108">10733</span></span>                                                                            |
|  <span data-ttu-id="a1727-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a1727-109">Event Source</span></span>   |                                                                           <span data-ttu-id="a1727-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a1727-110">ENTSSO</span></span>                                                                            |
|    <span data-ttu-id="a1727-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a1727-111">Component</span></span>    |                                                                             <span data-ttu-id="a1727-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a1727-112">N\A</span></span>                                                                             |
|  <span data-ttu-id="a1727-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a1727-113">Symbolic Name</span></span>  |                                                              <span data-ttu-id="a1727-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="a1727-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span></span>                                                               |
|  <span data-ttu-id="a1727-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a1727-115">Message Text</span></span>   | <span data-ttu-id="a1727-116">SSO データベースの Windows パスワードを更新できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="a1727-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="a1727-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a1727-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a1727-118">Windows アカウント: %2\\% 3 %r</span><span class="sxs-lookup"><span data-stu-id="a1727-118">Windows Account: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="a1727-119">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="a1727-119">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="a1727-120">説明</span><span class="sxs-lookup"><span data-stu-id="a1727-120">Explanation</span></span>  
 <span data-ttu-id="a1727-121">この警告イベントは、パスワード同期によって、SSO データベース内の指定された Windows アカウント パスワードを更新できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a1727-121">This Warning event indicates that Password Sync failed to update the specified Windows account password in the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a1727-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a1727-122">User Action</span></span>  
 <span data-ttu-id="a1727-123">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="a1727-123">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="a1727-124">関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1727-124">Check the system and application event logs for associated errors.</span></span>  

- <span data-ttu-id="a1727-125">指定したアカウントのパスワードが有効な Windows パスワードであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1727-125">Verify the password for the specified account is a valid Windows password.</span></span>  

  <span data-ttu-id="a1727-126">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1727-126">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="a1727-127">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="a1727-127">Password Synchronization</span></span>](../core/password-synchronization2.md)

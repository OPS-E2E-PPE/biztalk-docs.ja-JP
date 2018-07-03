---
title: 'シングル サインオン: イベント 10807 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 882c01c6-70db-4986-9f4b-f08335424250
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e23aefbb950160f29b6145e64bfaa1784dc3f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985411"
---
# <a name="single-sign-on-event-10807"></a><span data-ttu-id="d4b70-102">シングル サインオン: イベント 10807</span><span class="sxs-lookup"><span data-stu-id="d4b70-102">Single Sign-On: Event 10807</span></span>
## <a name="details"></a><span data-ttu-id="d4b70-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d4b70-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="d4b70-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d4b70-104">Product Name</span></span>   |                 <span data-ttu-id="d4b70-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d4b70-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="d4b70-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d4b70-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="d4b70-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d4b70-107">Event ID</span></span>     |                           <span data-ttu-id="d4b70-108">10807</span><span class="sxs-lookup"><span data-stu-id="d4b70-108">10807</span></span>                            |
|  <span data-ttu-id="d4b70-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d4b70-109">Event Source</span></span>   |                           <span data-ttu-id="d4b70-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d4b70-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="d4b70-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d4b70-111">Component</span></span>    |                            <span data-ttu-id="d4b70-112">なし</span><span class="sxs-lookup"><span data-stu-id="d4b70-112">N/A</span></span>                             |
|  <span data-ttu-id="d4b70-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d4b70-113">Symbolic Name</span></span>  |        <span data-ttu-id="d4b70-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="d4b70-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span></span>         |
|  <span data-ttu-id="d4b70-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d4b70-115">Message Text</span></span>   |            <span data-ttu-id="d4b70-116">未確認の通知が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="d4b70-116">Too many unconfirmed notifications.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="d4b70-117">説明</span><span class="sxs-lookup"><span data-stu-id="d4b70-117">Explanation</span></span>  
 <span data-ttu-id="d4b70-118">パスワード変更通知が送信されるたびに、確認メッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="d4b70-118">Each time a password change notification is sent, a confirmation message is received.</span></span> <span data-ttu-id="d4b70-119">この場合、確認されていない通知の制限値を超えています。</span><span class="sxs-lookup"><span data-stu-id="d4b70-119">In this case, the limit for notifications without confirmation has been exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4b70-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d4b70-120">User Action</span></span>  
 <span data-ttu-id="d4b70-121">パスワード同期アダプターを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4b70-121">Check the password sync adapter.</span></span>
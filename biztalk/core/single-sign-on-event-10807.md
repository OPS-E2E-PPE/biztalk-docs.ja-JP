---
title: シングル サインオン:イベント 10807 |Microsoft Docs
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
ms.openlocfilehash: 774769a952436729e3a32c5aeaf9d3d8eb98243c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267527"
---
# <a name="single-sign-on-event-10807"></a><span data-ttu-id="03599-102">シングル サインオン:イベント 10807</span><span class="sxs-lookup"><span data-stu-id="03599-102">Single Sign-On: Event 10807</span></span>
## <a name="details"></a><span data-ttu-id="03599-103">詳細</span><span class="sxs-lookup"><span data-stu-id="03599-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="03599-104">製品名</span><span class="sxs-lookup"><span data-stu-id="03599-104">Product Name</span></span>   |                 <span data-ttu-id="03599-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="03599-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="03599-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="03599-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="03599-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="03599-107">Event ID</span></span>     |                           <span data-ttu-id="03599-108">10807</span><span class="sxs-lookup"><span data-stu-id="03599-108">10807</span></span>                            |
|  <span data-ttu-id="03599-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="03599-109">Event Source</span></span>   |                           <span data-ttu-id="03599-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="03599-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="03599-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="03599-111">Component</span></span>    |                            <span data-ttu-id="03599-112">なし</span><span class="sxs-lookup"><span data-stu-id="03599-112">N/A</span></span>                             |
|  <span data-ttu-id="03599-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="03599-113">Symbolic Name</span></span>  |        <span data-ttu-id="03599-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="03599-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span></span>         |
|  <span data-ttu-id="03599-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="03599-115">Message Text</span></span>   |            <span data-ttu-id="03599-116">未確認の通知が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="03599-116">Too many unconfirmed notifications.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="03599-117">説明</span><span class="sxs-lookup"><span data-stu-id="03599-117">Explanation</span></span>  
 <span data-ttu-id="03599-118">たびに、パスワード変更通知が送信される、確認メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="03599-118">Each time a password change notification is sent, a confirmation message is received.</span></span> <span data-ttu-id="03599-119">この場合、確認なしの通知の制限を超過しました。</span><span class="sxs-lookup"><span data-stu-id="03599-119">In this case, the limit for notifications without confirmation has been exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="03599-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="03599-120">User Action</span></span>  
 <span data-ttu-id="03599-121">パスワード同期アダプターを確認します。</span><span class="sxs-lookup"><span data-stu-id="03599-121">Check the password sync adapter.</span></span>
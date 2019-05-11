---
title: シングル サインオン:イベント 10848 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccec085ec74ab06a57232c0fa81afd6e9bfadd32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306696"
---
# <a name="single-sign-on-event-10848"></a><span data-ttu-id="3d175-102">シングル サインオン:イベント 10848</span><span class="sxs-lookup"><span data-stu-id="3d175-102">Single Sign-On: Event 10848</span></span>
## <a name="details"></a><span data-ttu-id="3d175-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3d175-103">Details</span></span>  
  
|                 |                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3d175-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3d175-104">Product Name</span></span>   |                                 <span data-ttu-id="3d175-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3d175-105">Enterprise Single Sign-On</span></span>                                  |
| <span data-ttu-id="3d175-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3d175-106">Product Version</span></span> |                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    <span data-ttu-id="3d175-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3d175-107">Event ID</span></span>     |                                           <span data-ttu-id="3d175-108">10848</span><span class="sxs-lookup"><span data-stu-id="3d175-108">10848</span></span>                                            |
|  <span data-ttu-id="3d175-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3d175-109">Event Source</span></span>   |                                           <span data-ttu-id="3d175-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3d175-110">ENTSSO</span></span>                                           |
|    <span data-ttu-id="3d175-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3d175-111">Component</span></span>    |                                            <span data-ttu-id="3d175-112">なし</span><span class="sxs-lookup"><span data-stu-id="3d175-112">N/A</span></span>                                             |
|  <span data-ttu-id="3d175-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3d175-113">Symbolic Name</span></span>  |                         <span data-ttu-id="3d175-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="3d175-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span></span>                         |
|  <span data-ttu-id="3d175-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3d175-115">Message Text</span></span>   | <span data-ttu-id="3d175-116">直接パスワード同期は、そのフィールドがあいまいなため、このアプリケーションは許可されません。</span><span class="sxs-lookup"><span data-stu-id="3d175-116">Direct password sync is not allowed for this application because its fields are ambiguous.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3d175-117">説明</span><span class="sxs-lookup"><span data-stu-id="3d175-117">Explanation</span></span>  
 <span data-ttu-id="3d175-118">複数の 2 つのフィールドがある場合、1 つだけ必要があります指定はパスワードの同期です。</span><span class="sxs-lookup"><span data-stu-id="3d175-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3d175-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3d175-119">User Action</span></span>  
 <span data-ttu-id="3d175-120">このような状況を解決するには、するには、アプリケーションを削除し、再作成するため、これらのガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="3d175-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>
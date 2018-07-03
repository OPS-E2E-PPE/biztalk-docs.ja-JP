---
title: 'シングル サインオン: イベント 10785 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4f4a2ad-a378-4806-ba16-d2872c4773f1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96194f9ab4a057301e9c0a20d4c222f730e70bfb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991515"
---
# <a name="single-sign-on-event-10785"></a><span data-ttu-id="229b3-102">シングル サインオン: イベント 10785</span><span class="sxs-lookup"><span data-stu-id="229b3-102">Single Sign-On: Event 10785</span></span>
## <a name="details"></a><span data-ttu-id="229b3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="229b3-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="229b3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="229b3-104">Product Name</span></span>   |                   <span data-ttu-id="229b3-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="229b3-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="229b3-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="229b3-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="229b3-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="229b3-107">Event ID</span></span>     |                             <span data-ttu-id="229b3-108">10785</span><span class="sxs-lookup"><span data-stu-id="229b3-108">10785</span></span>                              |
|  <span data-ttu-id="229b3-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="229b3-109">Event Source</span></span>   |                             <span data-ttu-id="229b3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="229b3-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="229b3-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="229b3-111">Component</span></span>    |                              <span data-ttu-id="229b3-112">なし</span><span class="sxs-lookup"><span data-stu-id="229b3-112">N/A</span></span>                               |
|  <span data-ttu-id="229b3-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="229b3-113">Symbolic Name</span></span>  |                       <span data-ttu-id="229b3-114">ENTSSO_E_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="229b3-114">ENTSSO_E_DB_ACCESS</span></span>                       |
|  <span data-ttu-id="229b3-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="229b3-115">Message Text</span></span>   | <span data-ttu-id="229b3-116">SSO データベースへのアクセスを試みているときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="229b3-116">An error occurred while attempting to access the SSO database.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="229b3-117">説明</span><span class="sxs-lookup"><span data-stu-id="229b3-117">Explanation</span></span>  
 <span data-ttu-id="229b3-118">ENTSSO データベースがオフラインの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="229b3-118">The ENTSSO database may be offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="229b3-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="229b3-119">User Action</span></span>  
 <span data-ttu-id="229b3-120">システム管理者に ENTSSO サーバーのイベント ログの確認を依頼します。</span><span class="sxs-lookup"><span data-stu-id="229b3-120">Have your system administrator check the Event Log on the ENTSSO server.</span></span>
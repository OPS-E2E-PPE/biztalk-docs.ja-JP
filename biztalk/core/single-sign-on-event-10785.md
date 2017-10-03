---
title: "シングル サインオン: イベント 10785 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4f4a2ad-a378-4806-ba16-d2872c4773f1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 331c79298532db45770640dbea0ca8be0c8ab00b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10785"></a><span data-ttu-id="37944-102">シングル サインオン: イベント 10785</span><span class="sxs-lookup"><span data-stu-id="37944-102">Single Sign-On: Event 10785</span></span>
## <a name="details"></a><span data-ttu-id="37944-103">詳細</span><span class="sxs-lookup"><span data-stu-id="37944-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37944-104">製品名</span><span class="sxs-lookup"><span data-stu-id="37944-104">Product Name</span></span>|<span data-ttu-id="37944-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="37944-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="37944-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="37944-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="37944-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="37944-107">Event ID</span></span>|<span data-ttu-id="37944-108">10785</span><span class="sxs-lookup"><span data-stu-id="37944-108">10785</span></span>|  
|<span data-ttu-id="37944-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="37944-109">Event Source</span></span>|<span data-ttu-id="37944-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="37944-110">ENTSSO</span></span>|  
|<span data-ttu-id="37944-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="37944-111">Component</span></span>|<span data-ttu-id="37944-112">なし</span><span class="sxs-lookup"><span data-stu-id="37944-112">N/A</span></span>|  
|<span data-ttu-id="37944-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="37944-113">Symbolic Name</span></span>|<span data-ttu-id="37944-114">ENTSSO_E_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="37944-114">ENTSSO_E_DB_ACCESS</span></span>|  
|<span data-ttu-id="37944-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="37944-115">Message Text</span></span>|<span data-ttu-id="37944-116">SSO データベースへのアクセスを試みているときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="37944-116">An error occurred while attempting to access the SSO database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="37944-117">説明</span><span class="sxs-lookup"><span data-stu-id="37944-117">Explanation</span></span>  
 <span data-ttu-id="37944-118">ENTSSO データベースがオフラインの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37944-118">The ENTSSO database may be offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="37944-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="37944-119">User Action</span></span>  
 <span data-ttu-id="37944-120">システム管理者に ENTSSO サーバーのイベント ログの確認を依頼します。</span><span class="sxs-lookup"><span data-stu-id="37944-120">Have your system administrator check the Event Log on the ENTSSO server.</span></span>
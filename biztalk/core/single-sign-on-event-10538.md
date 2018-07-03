---
title: 'シングル サインオン: イベント 10538 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4b7fba63d26fde664e14470eb95b41a1580ae7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975779"
---
# <a name="single-sign-on-event-10538"></a><span data-ttu-id="fb015-102">シングル サインオン: イベント 10538</span><span class="sxs-lookup"><span data-stu-id="fb015-102">Single Sign-On: Event 10538</span></span>
## <a name="details"></a><span data-ttu-id="fb015-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fb015-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="fb015-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fb015-104">Product Name</span></span>   |                         <span data-ttu-id="fb015-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fb015-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="fb015-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fb015-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="fb015-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fb015-107">Event ID</span></span>     |                                   <span data-ttu-id="fb015-108">10538</span><span class="sxs-lookup"><span data-stu-id="fb015-108">10538</span></span>                                   |
|  <span data-ttu-id="fb015-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fb015-109">Event Source</span></span>   |                                  <span data-ttu-id="fb015-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fb015-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="fb015-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fb015-111">Component</span></span>    |                                    <span data-ttu-id="fb015-112">CO</span><span class="sxs-lookup"><span data-stu-id="fb015-112">CO</span></span>                                     |
|  <span data-ttu-id="fb015-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fb015-113">Symbolic Name</span></span>  |                           <span data-ttu-id="fb015-114">SSO_WARN_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="fb015-114">SSO_WARN_APP_DISABLED</span></span>                           |
|  <span data-ttu-id="fb015-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fb015-115">Message Text</span></span>   | <span data-ttu-id="fb015-116">このアプリケーションは現在無効になっています。%r</span><span class="sxs-lookup"><span data-stu-id="fb015-116">The application is currently disabled.%r</span></span><br /><br /> <span data-ttu-id="fb015-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="fb015-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="fb015-118">説明</span><span class="sxs-lookup"><span data-stu-id="fb015-118">Explanation</span></span>  
 <span data-ttu-id="fb015-119">この警告イベントは、アプリケーション管理者が SSO 関連アプリケーションを無効にしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="fb015-119">This Warning event indicates that the SSO affiliate application has been disabled by an Application Administrator.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fb015-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fb015-120">User Action</span></span>  
 <span data-ttu-id="fb015-121">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="fb015-121">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="fb015-122">アプリケーション管理者に問い合わせて、SSO 関連アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb015-122">Contact your Application Administrator to enable the SSO affiliate application.</span></span> <span data-ttu-id="fb015-123">SSO 管理ツール (GUI またはコマンド ライン) を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb015-123">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="fb015-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="fb015-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="fb015-125">関連アプリケーションを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="fb015-125">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  

- [<span data-ttu-id="fb015-126">関連アプリケーションを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="fb015-126">How to Disable an Affiliate Application</span></span>](../core/how-to-disable-an-affiliate-application.md)

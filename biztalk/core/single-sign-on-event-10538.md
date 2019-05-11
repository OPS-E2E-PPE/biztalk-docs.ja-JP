---
title: シングル サインオン:イベント 10538 |Microsoft Docs
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
ms.openlocfilehash: d9d1a1b8b09d9bc4725c55060aebe705f256e691
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250378"
---
# <a name="single-sign-on-event-10538"></a><span data-ttu-id="fecb7-102">シングル サインオン:イベント 10538</span><span class="sxs-lookup"><span data-stu-id="fecb7-102">Single Sign-On: Event 10538</span></span>
## <a name="details"></a><span data-ttu-id="fecb7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fecb7-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="fecb7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fecb7-104">Product Name</span></span>   |                         <span data-ttu-id="fecb7-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fecb7-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="fecb7-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fecb7-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="fecb7-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fecb7-107">Event ID</span></span>     |                                   <span data-ttu-id="fecb7-108">10538</span><span class="sxs-lookup"><span data-stu-id="fecb7-108">10538</span></span>                                   |
|  <span data-ttu-id="fecb7-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fecb7-109">Event Source</span></span>   |                                  <span data-ttu-id="fecb7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fecb7-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="fecb7-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fecb7-111">Component</span></span>    |                                    <span data-ttu-id="fecb7-112">CO</span><span class="sxs-lookup"><span data-stu-id="fecb7-112">CO</span></span>                                     |
|  <span data-ttu-id="fecb7-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fecb7-113">Symbolic Name</span></span>  |                           <span data-ttu-id="fecb7-114">SSO_WARN_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="fecb7-114">SSO_WARN_APP_DISABLED</span></span>                           |
|  <span data-ttu-id="fecb7-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fecb7-115">Message Text</span></span>   | <span data-ttu-id="fecb7-116">アプリケーションは、現在 disabled.%r です。</span><span class="sxs-lookup"><span data-stu-id="fecb7-116">The application is currently disabled.%r</span></span><br /><br /> <span data-ttu-id="fecb7-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="fecb7-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="fecb7-118">説明</span><span class="sxs-lookup"><span data-stu-id="fecb7-118">Explanation</span></span>  
 <span data-ttu-id="fecb7-119">この警告イベントは、SSO 関連アプリケーションが無効になっている、アプリケーション管理者によってを示します。</span><span class="sxs-lookup"><span data-stu-id="fecb7-119">This Warning event indicates that the SSO affiliate application has been disabled by an Application Administrator.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fecb7-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fecb7-120">User Action</span></span>  
 <span data-ttu-id="fecb7-121">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fecb7-121">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="fecb7-122">SSO 関連アプリケーションを有効にする、アプリケーション管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="fecb7-122">Contact your Application Administrator to enable the SSO affiliate application.</span></span> <span data-ttu-id="fecb7-123">これ行う SSO 管理ツール (GUI またはコマンドライン) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fecb7-123">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="fecb7-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="fecb7-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="fecb7-125">関連アプリケーションを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="fecb7-125">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  

- [<span data-ttu-id="fecb7-126">関連アプリケーションを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="fecb7-126">How to Disable an Affiliate Application</span></span>](../core/how-to-disable-an-affiliate-application.md)

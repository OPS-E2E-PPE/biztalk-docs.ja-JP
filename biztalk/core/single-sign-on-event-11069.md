---
title: 'シングル サインオン: イベント 11069 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1accfe68-000c-4b5e-909c-244e18eba110
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e9df27e7a5ac5f4fcedb10935fb8e63a6e0bea0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986163"
---
# <a name="single-sign-on-event-11069"></a><span data-ttu-id="c8fe6-102">シングル サインオン: イベント 11069</span><span class="sxs-lookup"><span data-stu-id="c8fe6-102">Single Sign-On: Event 11069</span></span>
## <a name="details"></a><span data-ttu-id="c8fe6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c8fe6-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c8fe6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c8fe6-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="c8fe6-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c8fe6-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="c8fe6-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c8fe6-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="c8fe6-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c8fe6-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="c8fe6-108">11069</span><span class="sxs-lookup"><span data-stu-id="c8fe6-108">11069</span></span>                                                                                                         |
|  <span data-ttu-id="c8fe6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c8fe6-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="c8fe6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c8fe6-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="c8fe6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c8fe6-111">Component</span></span>    |                                                                                                          <span data-ttu-id="c8fe6-112">なし</span><span class="sxs-lookup"><span data-stu-id="c8fe6-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="c8fe6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c8fe6-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="c8fe6-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="c8fe6-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span></span>                                                                                              |
|  <span data-ttu-id="c8fe6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c8fe6-115">Message Text</span></span>   | <span data-ttu-id="c8fe6-116">現在、この SSO サーバーでは、PCNS からの Windows パスワード変更ができないように構成されています。</span><span class="sxs-lookup"><span data-stu-id="c8fe6-116">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span> <span data-ttu-id="c8fe6-117">'ssoconfig -allowPS PCNS yes' または SSO 管理 MMC を使用します。%r</span><span class="sxs-lookup"><span data-stu-id="c8fe6-117">Use 'ssoconfig -allowPS PCNS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="c8fe6-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c8fe6-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c8fe6-119">クライアント ユーザー: %2</span><span class="sxs-lookup"><span data-stu-id="c8fe6-119">Client User: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c8fe6-120">説明</span><span class="sxs-lookup"><span data-stu-id="c8fe6-120">Explanation</span></span>  
 <span data-ttu-id="c8fe6-121">現在、この SSO サーバーでは、PCNS からの Windows パスワード変更ができないように構成されています。</span><span class="sxs-lookup"><span data-stu-id="c8fe6-121">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c8fe6-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c8fe6-122">User Action</span></span>  
 <span data-ttu-id="c8fe6-123">PCNS からの Windows パスワードの変更を許可する、**サーバー スナップイン**、**パスワード同期プロパティ**] タブで [ **PCNS からのパスワード同期を許可します。**</span><span class="sxs-lookup"><span data-stu-id="c8fe6-123">To allow Windows password changes from PCNS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from PCNS.**</span></span>  
  
 <span data-ttu-id="c8fe6-124">詳細については、[サーバー スナップインを使用する](../core/how-to-use-the-servers-snap-in.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8fe6-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>
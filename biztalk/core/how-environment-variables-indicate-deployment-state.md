---
title: 環境変数が展開の状態を指定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d21baa6ef6e6d82fc179497b4993cf3af6fb1a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983987"
---
# <a name="how-environment-variables-indicate-deployment-state"></a><span data-ttu-id="cdf0b-102">環境変数と展開状態の対応関係</span><span class="sxs-lookup"><span data-stu-id="cdf0b-102">How Environment Variables Indicate Deployment State</span></span>
<span data-ttu-id="cdf0b-103">処理前または処理後のスクリプトを呼び出すと、これらのスクリプトでは環境変数 BTAD_ChangeRequestAction、BTAD_InstallMode、および BTAD_HostClass を確認することにより、実行中の展開の状態 (インストール、インポート、削除、アンインストール、インポート ロールバック、インストール ロールバック) が判断されます。</span><span class="sxs-lookup"><span data-stu-id="cdf0b-103">Once invoked, a pre- or post-processing script can determine in which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode and BTAD_HostClass.</span></span>  

 <span data-ttu-id="cdf0b-104">次の表に、これら 3 つの環境変数の組み合わせとそれに対応する展開状態を示します。</span><span class="sxs-lookup"><span data-stu-id="cdf0b-104">The following table describes the combinations of the three variables that indicate the different deployment states.</span></span>  


|       <span data-ttu-id="cdf0b-105">展開状態</span><span class="sxs-lookup"><span data-stu-id="cdf0b-105">Deployment State</span></span>        |     <span data-ttu-id="cdf0b-106">予期される値</span><span class="sxs-lookup"><span data-stu-id="cdf0b-106">Expected Values</span></span>      |
|-------------------------------|--------------------------|
|                               | <span data-ttu-id="cdf0b-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="cdf0b-107">BTAD_ChangeRequestAction</span></span> |
| <span data-ttu-id="cdf0b-108">インポート (フラグの上書きなし)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-108">Import without overwrite flag</span></span> |          <span data-ttu-id="cdf0b-109">作成</span><span class="sxs-lookup"><span data-stu-id="cdf0b-109">Create</span></span>          |
|  <span data-ttu-id="cdf0b-110">インポート (フラグの上書きあり)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-110">Import with overwrite flag</span></span>   |          <span data-ttu-id="cdf0b-111">更新</span><span class="sxs-lookup"><span data-stu-id="cdf0b-111">Update</span></span>          |
|            <span data-ttu-id="cdf0b-112">インストール</span><span class="sxs-lookup"><span data-stu-id="cdf0b-112">Install</span></span>            |          <span data-ttu-id="cdf0b-113">更新</span><span class="sxs-lookup"><span data-stu-id="cdf0b-113">Update</span></span>          |
|           <span data-ttu-id="cdf0b-114">Uninstall</span><span class="sxs-lookup"><span data-stu-id="cdf0b-114">Uninstall</span></span>           |          <span data-ttu-id="cdf0b-115">DELETE</span><span class="sxs-lookup"><span data-stu-id="cdf0b-115">Delete</span></span>          |
|        <span data-ttu-id="cdf0b-116">インポート ロールバック</span><span class="sxs-lookup"><span data-stu-id="cdf0b-116">Import rollback</span></span>        |          <span data-ttu-id="cdf0b-117">DELETE</span><span class="sxs-lookup"><span data-stu-id="cdf0b-117">Delete</span></span>          |
|       <span data-ttu-id="cdf0b-118">インストール ロールバック</span><span class="sxs-lookup"><span data-stu-id="cdf0b-118">Install rollback</span></span>        |          <span data-ttu-id="cdf0b-119">DELETE</span><span class="sxs-lookup"><span data-stu-id="cdf0b-119">Delete</span></span>          |

## <a name="see-also"></a><span data-ttu-id="cdf0b-120">参照</span><span class="sxs-lookup"><span data-stu-id="cdf0b-120">See Also</span></span>  
 <span data-ttu-id="cdf0b-121">[前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="cdf0b-121">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 <span data-ttu-id="cdf0b-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span><span class="sxs-lookup"><span data-stu-id="cdf0b-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span></span>  
 <span data-ttu-id="cdf0b-123">[BTAD_InstallMode](../core/btad-installmode.md) </span><span class="sxs-lookup"><span data-stu-id="cdf0b-123">[BTAD_InstallMode](../core/btad-installmode.md) </span></span>  
 [<span data-ttu-id="cdf0b-124">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="cdf0b-124">BTAD_HostClass</span></span>](../core/btad-hostclass.md)
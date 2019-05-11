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
ms.openlocfilehash: 5fc27a85f36b83b3fd3c0bd782807fa4f5b73364
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387461"
---
# <a name="how-environment-variables-indicate-deployment-state"></a><span data-ttu-id="4d7ed-102">環境変数と展開状態の対応関係</span><span class="sxs-lookup"><span data-stu-id="4d7ed-102">How Environment Variables Indicate Deployment State</span></span>
<span data-ttu-id="4d7ed-103">展開の状態の前または処理後のスクリプトを調べる、呼び出されると (インストール、インポート、削除、アンインストール、インポート ロールバック、またはインストール ロールバック) により、環境変数 BTAD_ChangeRequestAction、BTAD_InstallMode、実行中におよび BTAD_HostClass を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d7ed-103">Once invoked, a pre- or post-processing script can determine in which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode and BTAD_HostClass.</span></span>  

 <span data-ttu-id="4d7ed-104">次の表では、さまざまな展開の状態を示す 3 つの変数の組み合わせについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4d7ed-104">The following table describes the combinations of the three variables that indicate the different deployment states.</span></span>  


|       <span data-ttu-id="4d7ed-105">展開状態</span><span class="sxs-lookup"><span data-stu-id="4d7ed-105">Deployment State</span></span>        |     <span data-ttu-id="4d7ed-106">予期される値</span><span class="sxs-lookup"><span data-stu-id="4d7ed-106">Expected Values</span></span>      |
|-------------------------------|--------------------------|
|                               | <span data-ttu-id="4d7ed-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="4d7ed-107">BTAD_ChangeRequestAction</span></span> |
| <span data-ttu-id="4d7ed-108">インポート フラグの上書きなし</span><span class="sxs-lookup"><span data-stu-id="4d7ed-108">Import without overwrite flag</span></span> |          <span data-ttu-id="4d7ed-109">作成</span><span class="sxs-lookup"><span data-stu-id="4d7ed-109">Create</span></span>          |
|  <span data-ttu-id="4d7ed-110">上書きフラグにインポートする.</span><span class="sxs-lookup"><span data-stu-id="4d7ed-110">Import with overwrite flag</span></span>   |          <span data-ttu-id="4d7ed-111">更新</span><span class="sxs-lookup"><span data-stu-id="4d7ed-111">Update</span></span>          |
|            <span data-ttu-id="4d7ed-112">インストール</span><span class="sxs-lookup"><span data-stu-id="4d7ed-112">Install</span></span>            |          <span data-ttu-id="4d7ed-113">更新</span><span class="sxs-lookup"><span data-stu-id="4d7ed-113">Update</span></span>          |
|           <span data-ttu-id="4d7ed-114">アンインストール</span><span class="sxs-lookup"><span data-stu-id="4d7ed-114">Uninstall</span></span>           |          <span data-ttu-id="4d7ed-115">DELETE</span><span class="sxs-lookup"><span data-stu-id="4d7ed-115">Delete</span></span>          |
|        <span data-ttu-id="4d7ed-116">インポート ロールバック</span><span class="sxs-lookup"><span data-stu-id="4d7ed-116">Import rollback</span></span>        |          <span data-ttu-id="4d7ed-117">DELETE</span><span class="sxs-lookup"><span data-stu-id="4d7ed-117">Delete</span></span>          |
|       <span data-ttu-id="4d7ed-118">インストール ロールバック</span><span class="sxs-lookup"><span data-stu-id="4d7ed-118">Install rollback</span></span>        |          <span data-ttu-id="4d7ed-119">DELETE</span><span class="sxs-lookup"><span data-stu-id="4d7ed-119">Delete</span></span>          |

## <a name="see-also"></a><span data-ttu-id="4d7ed-120">参照</span><span class="sxs-lookup"><span data-stu-id="4d7ed-120">See Also</span></span>  
 <span data-ttu-id="4d7ed-121">[前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="4d7ed-121">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 <span data-ttu-id="4d7ed-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span><span class="sxs-lookup"><span data-stu-id="4d7ed-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span></span>  
 <span data-ttu-id="4d7ed-123">[BTAD_InstallMode](../core/btad-installmode.md) </span><span class="sxs-lookup"><span data-stu-id="4d7ed-123">[BTAD_InstallMode](../core/btad-installmode.md) </span></span>  
 [<span data-ttu-id="4d7ed-124">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="4d7ed-124">BTAD_HostClass</span></span>](../core/btad-hostclass.md)
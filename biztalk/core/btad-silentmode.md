---
title: BTAD_SilentMode |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_SilentMode [environment variable], about BTAS_SilentMode
- BTAD_SilentMode [environment variable]
- BTAD_SilentMode [environment variable], warnings
ms.assetid: 271835cf-1587-44c5-b5af-b4df4e981ab4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9433dde06cf40b0c7c94091f48af4f4b37f9bdf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357811"
---
# <a name="btadsilentmode"></a><span data-ttu-id="f0647-102">BTAD_SilentMode</span><span class="sxs-lookup"><span data-stu-id="f0647-102">BTAD_SilentMode</span></span>
<span data-ttu-id="f0647-103">BTAD_SilentMode は、サイレント モードでスクリプトを実行するためのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0647-103">BTAD_SilentMode specifies options for running the script in silent mode.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0647-104">コメント</span><span class="sxs-lookup"><span data-stu-id="f0647-104">Remarks</span></span>  
 <span data-ttu-id="f0647-105">サイレント モードのオプションを指定するときに BTS インストーラーはその値を BTAD_SilentMode 変数に配置します。</span><span class="sxs-lookup"><span data-stu-id="f0647-105">When you specify an option for silent mode, BTS Installer places its value into the BTAD_SilentMode variable.</span></span>  
  
 <span data-ttu-id="f0647-106">BTAD_SilentMode の既定値は、2、サイレント モードで実行するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0647-106">The default value of BTAD_SilentMode is 2, which specifies that the script runs in silent mode.</span></span> <span data-ttu-id="f0647-107">次の表では、BTAD_SilentMode の使用可能な値について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0647-107">The following table describes the possible values for BTAD_SilentMode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f0647-108">スクリプトから BizTalk Server のユーザー インターフェイスを起動する場合のモーダル ダイアログ ボックス可能性がありますいないを表示するまたはが困難に表示および消去したり、フォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="f0647-108">If you start the BizTalk Server user interface from scripts, modal dialog boxes may not be visible or have focus, making them difficult to view and dismiss.</span></span> <span data-ttu-id="f0647-109">BizTalk データベースはモーダル ダイアログ ボックスが開いている間ロックされ、アクセス不可能になります。</span><span class="sxs-lookup"><span data-stu-id="f0647-109">The BizTalk databases can become locked and inaccessible while modal dialog boxes are open.</span></span> <span data-ttu-id="f0647-110">このため、実稼働システムでは、すべてのスクリプトはサイレント モードで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0647-110">For this reason, on production systems, all scripts should run in silent mode.</span></span>  
  
|<span data-ttu-id="f0647-111">値</span><span class="sxs-lookup"><span data-stu-id="f0647-111">Value</span></span>|<span data-ttu-id="f0647-112">Description</span><span class="sxs-lookup"><span data-stu-id="f0647-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f0647-113">0</span><span class="sxs-lookup"><span data-stu-id="f0647-113">0</span></span>|<span data-ttu-id="f0647-114">ユーザー インターフェイス (UI) のレベルは変更されません。</span><span class="sxs-lookup"><span data-stu-id="f0647-114">Does not change the user interface (UI) level.</span></span>|  
|<span data-ttu-id="f0647-115">1</span><span class="sxs-lookup"><span data-stu-id="f0647-115">1</span></span>|<span data-ttu-id="f0647-116">既定の UI レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0647-116">Uses the default UI level.</span></span>|  
|<span data-ttu-id="f0647-117">2</span><span class="sxs-lookup"><span data-stu-id="f0647-117">2</span></span>|<span data-ttu-id="f0647-118">(既定値) のサイレント インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0647-118">Performs a silent installation (the default).</span></span>|  
|<span data-ttu-id="f0647-119">3</span><span class="sxs-lookup"><span data-stu-id="f0647-119">3</span></span>|<span data-ttu-id="f0647-120">単純な進行状況とエラー処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="f0647-120">Provides simple progress and error handling.</span></span>|  
|<span data-ttu-id="f0647-121">4</span><span class="sxs-lookup"><span data-stu-id="f0647-121">4</span></span>|<span data-ttu-id="f0647-122">作成した UI を提供します。ウィザードを抑制します。</span><span class="sxs-lookup"><span data-stu-id="f0647-122">Provides authored UI; suppresses wizards.</span></span>|  
|<span data-ttu-id="f0647-123">0x80</span><span class="sxs-lookup"><span data-stu-id="f0647-123">0x80</span></span>|<span data-ttu-id="f0647-124">上記の値と組み合わせると、スクリプトが正常に実行された場合、またはエラーがあった場合、Windows インストーラーはモーダル ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f0647-124">If combined with any above value, Windows Installer displays a modal dialog box if the script has executed successfully or if there has been an error.</span></span> <span data-ttu-id="f0647-125">ユーザーが操作を取り消した場合、ダイアログ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f0647-125">No dialog box is displayed if the user cancels the operation.</span></span>|  
|<span data-ttu-id="f0647-126">0x40</span><span class="sxs-lookup"><span data-stu-id="f0647-126">0x40</span></span>|<span data-ttu-id="f0647-127">3 つの値と組み合わせると、Windows インストーラーは進行状況 ダイアログ ボックスが表示されますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f0647-127">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="f0647-128">0x20</span><span class="sxs-lookup"><span data-stu-id="f0647-128">0x20</span></span>|<span data-ttu-id="f0647-129">3 つの値と組み合わせると、Windows インストーラーは進行状況 ダイアログ ボックスが表示されますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f0647-129">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="f0647-130">0x100</span><span class="sxs-lookup"><span data-stu-id="f0647-130">0x100</span></span>|<span data-ttu-id="f0647-131">3 つの値と組み合わせると、Windows インストーラーは進行状況 ダイアログ ボックスが表示されますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f0647-131">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0647-132">参照</span><span class="sxs-lookup"><span data-stu-id="f0647-132">See Also</span></span>  
 <span data-ttu-id="f0647-133">[前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f0647-133">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="f0647-134">環境変数と展開状態の対応関係</span><span class="sxs-lookup"><span data-stu-id="f0647-134">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)
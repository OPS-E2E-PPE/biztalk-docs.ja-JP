---
title: BTAD_SilentMode |Microsoft ドキュメント
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
ms.openlocfilehash: 31715835c98d2f60a3b5f1c18251571ea57641d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231330"
---
# <a name="btadsilentmode"></a><span data-ttu-id="b16f7-102">BTAD_SilentMode</span><span class="sxs-lookup"><span data-stu-id="b16f7-102">BTAD_SilentMode</span></span>
<span data-ttu-id="b16f7-103">BTAD_SilentMode は、スクリプトをサイレント モードで実行するためのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b16f7-103">BTAD_SilentMode specifies options for running the script in silent mode.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b16f7-104">解説</span><span class="sxs-lookup"><span data-stu-id="b16f7-104">Remarks</span></span>  
 <span data-ttu-id="b16f7-105">サイレント モードのオプションを指定すると、BTS インストーラーはその値を BTAD_SilentMode 変数に設定します。</span><span class="sxs-lookup"><span data-stu-id="b16f7-105">When you specify an option for silent mode, BTS Installer places its value into the BTAD_SilentMode variable.</span></span>  
  
 <span data-ttu-id="b16f7-106">BTAD_SilentMode の既定値は 2 で、スクリプトをサイレント モードで実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="b16f7-106">The default value of BTAD_SilentMode is 2, which specifies that the script runs in silent mode.</span></span> <span data-ttu-id="b16f7-107">BTAD_SilentMode で使用できる値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="b16f7-107">The following table describes the possible values for BTAD_SilentMode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b16f7-108">スクリプトから BizTalk Server のユーザー インターフェイスを開始すると、モーダル ダイアログ ボックスが表示されない場合やフォーカスがない場合があり、表示や終了が困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b16f7-108">If you start the BizTalk Server user interface from scripts, modal dialog boxes may not be visible or have focus, making them difficult to view and dismiss.</span></span> <span data-ttu-id="b16f7-109">BizTalk データベースになり、ロックされたアクセスできないモーダル ダイアログ ボックスが開いている間です。</span><span class="sxs-lookup"><span data-stu-id="b16f7-109">The BizTalk databases can become locked and inaccessible while modal dialog boxes are open.</span></span> <span data-ttu-id="b16f7-110">このため、実稼働システムでは、すべてのスクリプトをサイレント モードで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b16f7-110">For this reason, on production systems, all scripts should run in silent mode.</span></span>  
  
|<span data-ttu-id="b16f7-111">値</span><span class="sxs-lookup"><span data-stu-id="b16f7-111">Value</span></span>|<span data-ttu-id="b16f7-112">説明</span><span class="sxs-lookup"><span data-stu-id="b16f7-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b16f7-113">0</span><span class="sxs-lookup"><span data-stu-id="b16f7-113">0</span></span>|<span data-ttu-id="b16f7-114">ユーザー インターフェイス (UI) のレベルを変更しません。</span><span class="sxs-lookup"><span data-stu-id="b16f7-114">Does not change the user interface (UI) level.</span></span>|  
|<span data-ttu-id="b16f7-115">1</span><span class="sxs-lookup"><span data-stu-id="b16f7-115">1</span></span>|<span data-ttu-id="b16f7-116">既定の UI レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b16f7-116">Uses the default UI level.</span></span>|  
|<span data-ttu-id="b16f7-117">2</span><span class="sxs-lookup"><span data-stu-id="b16f7-117">2</span></span>|<span data-ttu-id="b16f7-118">サイレント インストールを実行します (既定値)。</span><span class="sxs-lookup"><span data-stu-id="b16f7-118">Performs a silent installation (the default).</span></span>|  
|<span data-ttu-id="b16f7-119">3</span><span class="sxs-lookup"><span data-stu-id="b16f7-119">3</span></span>|<span data-ttu-id="b16f7-120">簡単な進行状況とエラーの処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="b16f7-120">Provides simple progress and error handling.</span></span>|  
|<span data-ttu-id="b16f7-121">4</span><span class="sxs-lookup"><span data-stu-id="b16f7-121">4</span></span>|<span data-ttu-id="b16f7-122">作成した UI を提供し、ウィザードを起動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="b16f7-122">Provides authored UI; suppresses wizards.</span></span>|  
|<span data-ttu-id="b16f7-123">0x80</span><span class="sxs-lookup"><span data-stu-id="b16f7-123">0x80</span></span>|<span data-ttu-id="b16f7-124">前の値のいずれかと組み合わせると、Windows インストーラーは、スクリプトが正常に実行した場合、またはエラーが発生した場合に、モーダル ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="b16f7-124">If combined with any above value, Windows Installer displays a modal dialog box if the script has executed successfully or if there has been an error.</span></span> <span data-ttu-id="b16f7-125">ユーザーが操作を取り消した場合は、ダイアログ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b16f7-125">No dialog box is displayed if the user cancels the operation.</span></span>|  
|<span data-ttu-id="b16f7-126">0x40</span><span class="sxs-lookup"><span data-stu-id="b16f7-126">0x40</span></span>|<span data-ttu-id="b16f7-127">値 3 と組み合わせると、Windows インストーラーは、進行状況ダイアログ ボックスは表示しますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示しません。</span><span class="sxs-lookup"><span data-stu-id="b16f7-127">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="b16f7-128">0x20</span><span class="sxs-lookup"><span data-stu-id="b16f7-128">0x20</span></span>|<span data-ttu-id="b16f7-129">値 3 と組み合わせると、Windows インストーラーは、進行状況ダイアログ ボックスは表示しますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示しません。</span><span class="sxs-lookup"><span data-stu-id="b16f7-129">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="b16f7-130">0x100</span><span class="sxs-lookup"><span data-stu-id="b16f7-130">0x100</span></span>|<span data-ttu-id="b16f7-131">値 3 と組み合わせると、Windows インストーラーは、進行状況ダイアログ ボックスは表示しますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示しません。</span><span class="sxs-lookup"><span data-stu-id="b16f7-131">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b16f7-132">参照</span><span class="sxs-lookup"><span data-stu-id="b16f7-132">See Also</span></span>  
 <span data-ttu-id="b16f7-133">[前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="b16f7-133">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="b16f7-134">環境変数が展開の状態を指定する方法</span><span class="sxs-lookup"><span data-stu-id="b16f7-134">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)
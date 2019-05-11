---
title: BTSTask のコンソールの色を編集する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 725dcb7b-5a19-4166-9d1c-93f30ddca201
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71d902e18c851d3ae2ae432fa1e39d5db4e75206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338076"
---
# <a name="how-to-edit-the-console-colors-for-btstask"></a><span data-ttu-id="38979-102">BTSTask のコンソールの色を編集する方法</span><span class="sxs-lookup"><span data-stu-id="38979-102">How to Edit the Console Colors for BTSTask</span></span>
<span data-ttu-id="38979-103">このトピックでは、BTSTask がコンソールに出力する、前景色を編集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38979-103">This topic describes how to edit the foreground colors that BTSTask outputs to the console.</span></span> <span data-ttu-id="38979-104">コンソールの背景色が白の場合、既定の BTSTask コンソールの出力を読むことが困難になり、コンソールの前景色の色を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38979-104">If your console background color is white, you will have difficulty reading the default BTSTask console output and will need to modify the console foreground colors.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="38979-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="38979-105">Prerequisites</span></span>  
 <span data-ttu-id="38979-106">このトピックの手順を実行するに含まれている BTSTask.exe.config ファイルに対する読み取り/書き込みアクセス許可が必要、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="38979-106">To perform the procedure in this topic, you must have Read/Write permissions on the BTSTask.exe.config file contained in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder.</span></span>  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a><span data-ttu-id="38979-107">BTSTask のコンソールの前景色を編集するには</span><span class="sxs-lookup"><span data-stu-id="38979-107">To edit the console foreground colors for BTSTask</span></span>  
  
1. <span data-ttu-id="38979-108">BTSTask を実行するコンピューターで、BTSTask.exe.config を開きます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]またはテキスト エディターまたは XML エディター。</span><span class="sxs-lookup"><span data-stu-id="38979-108">On the computer where you want to run BTSTask, open BTSTask.exe.config in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or a text or XML editor.</span></span> <span data-ttu-id="38979-109">このファイルにある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="38979-109">This file is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder.</span></span>  
  
2. <span data-ttu-id="38979-110">に従って必要なエラー メッセージ、警告、およびについては、それぞれ、コンソールの前景の色など、Console.ForegroundColor.Warning、console.foregroundcolor.info のキーの値を編集し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="38979-110">Edit the values for the Console.ForegroundColor.Error, Console.ForegroundColor.Warning, and Console.ForegroundColor.Info keys according to the console foreground colors that you want for error messages, warnings, and information, respectively, and then save the file.</span></span> <span data-ttu-id="38979-111">(モノクロの場合、削除、値を編集するのではなく、これら 3 つのエントリ)。</span><span class="sxs-lookup"><span data-stu-id="38979-111">(For monochrome, delete these three entries, rather than editing their values.)</span></span>  
  
    <span data-ttu-id="38979-112">前景の色に使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="38979-112">The available values for foreground colors are as follows:</span></span>  
  
    <span data-ttu-id="38979-113">0:黒</span><span class="sxs-lookup"><span data-stu-id="38979-113">0: Black</span></span>  
  
    <span data-ttu-id="38979-114">1:DarkBlue</span><span class="sxs-lookup"><span data-stu-id="38979-114">1: DarkBlue</span></span>  
  
    <span data-ttu-id="38979-115">2:DarkGreen</span><span class="sxs-lookup"><span data-stu-id="38979-115">2: DarkGreen</span></span>  
  
    <span data-ttu-id="38979-116">3:DarkCyan</span><span class="sxs-lookup"><span data-stu-id="38979-116">3: DarkCyan</span></span>  
  
    <span data-ttu-id="38979-117">4:DarkRed</span><span class="sxs-lookup"><span data-stu-id="38979-117">4: DarkRed</span></span>  
  
    <span data-ttu-id="38979-118">5:DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="38979-118">5: DarkMagenta</span></span>  
  
    <span data-ttu-id="38979-119">6:DarkYellow</span><span class="sxs-lookup"><span data-stu-id="38979-119">6: DarkYellow</span></span>  
  
    <span data-ttu-id="38979-120">7:灰色</span><span class="sxs-lookup"><span data-stu-id="38979-120">7: Gray</span></span>  
  
    <span data-ttu-id="38979-121">8:濃い灰色</span><span class="sxs-lookup"><span data-stu-id="38979-121">8: DarkGray</span></span>  
  
    <span data-ttu-id="38979-122">9:[青]</span><span class="sxs-lookup"><span data-stu-id="38979-122">9: Blue</span></span>  
  
    <span data-ttu-id="38979-123">10:[緑]</span><span class="sxs-lookup"><span data-stu-id="38979-123">10: Green</span></span>  
  
    <span data-ttu-id="38979-124">11:シアン</span><span class="sxs-lookup"><span data-stu-id="38979-124">11: Cyan</span></span>  
  
    <span data-ttu-id="38979-125">12:[赤]</span><span class="sxs-lookup"><span data-stu-id="38979-125">12: Red</span></span>  
  
    <span data-ttu-id="38979-126">13:赤紫</span><span class="sxs-lookup"><span data-stu-id="38979-126">13: Magenta</span></span>  
  
    <span data-ttu-id="38979-127">14:黄</span><span class="sxs-lookup"><span data-stu-id="38979-127">14: Yellow</span></span>  
  
    <span data-ttu-id="38979-128">15:White</span><span class="sxs-lookup"><span data-stu-id="38979-128">15: White</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38979-129">参照</span><span class="sxs-lookup"><span data-stu-id="38979-129">See Also</span></span>  
 [<span data-ttu-id="38979-130">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="38979-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)
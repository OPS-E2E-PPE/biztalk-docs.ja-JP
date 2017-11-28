---
title: "BTSTask のコンソールの色を編集する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725dcb7b-5a19-4166-9d1c-93f30ddca201
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d68529f01ab8131739d735ad82d804b41a9c021
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-edit-the-console-colors-for-btstask"></a><span data-ttu-id="36c8f-102">BTSTask のコンソールの色を編集する方法</span><span class="sxs-lookup"><span data-stu-id="36c8f-102">How to Edit the Console Colors for BTSTask</span></span>
<span data-ttu-id="36c8f-103">ここでは、BTSTask がコンソールに出力する際に使用される前景色の編集方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36c8f-103">This topic describes how to edit the foreground colors that BTSTask outputs to the console.</span></span> <span data-ttu-id="36c8f-104">コンソールの背景色が白だと、既定の BTSTask コンソールの出力が読みづらくなってしまうため、前景色の変更が必要になります。</span><span class="sxs-lookup"><span data-stu-id="36c8f-104">If your console background color is white, you will have difficulty reading the default BTSTask console output and will need to modify the console foreground colors.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="36c8f-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="36c8f-105">Prerequisites</span></span>  
 <span data-ttu-id="36c8f-106">このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール フォルダーに格納されている BTSTask.exe.config ファイルに対する読み取り/書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="36c8f-106">To perform the procedure in this topic, you must have Read/Write permissions on the BTSTask.exe.config file contained in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder.</span></span>  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a><span data-ttu-id="36c8f-107">BTSTask のコンソールの前景色を編集するには</span><span class="sxs-lookup"><span data-stu-id="36c8f-107">To edit the console foreground colors for BTSTask</span></span>  
  
1.  <span data-ttu-id="36c8f-108">BTSTask を実行するコンピューターから、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、テキスト エディター、または XML エディターを使用して、BTSTask.exe.config を開きます。</span><span class="sxs-lookup"><span data-stu-id="36c8f-108">On the computer where you want to run BTSTask, open BTSTask.exe.config in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or a text or XML editor.</span></span> <span data-ttu-id="36c8f-109">このファイルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール フォルダーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="36c8f-109">This file is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder.</span></span>  
  
2.  <span data-ttu-id="36c8f-110">エラー メッセージ、警告、情報など、各種のコンソール出力に使用する前景色に応じて、Console.ForegroundColor.Error、Console.ForegroundColor.Warning、Console.ForegroundColor.Info の各キーの値を編集し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="36c8f-110">Edit the values for the Console.ForegroundColor.Error, Console.ForegroundColor.Warning, and Console.ForegroundColor.Info keys according to the console foreground colors that you want for error messages, warnings, and information, respectively, and then save the file.</span></span> <span data-ttu-id="36c8f-111">(モノクロの場合は、値を編集するのではなく、これらの 3 つのエントリを削除してください。)</span><span class="sxs-lookup"><span data-stu-id="36c8f-111">(For monochrome, delete these three entries, rather than editing their values.)</span></span>  
  
     <span data-ttu-id="36c8f-112">前景色に使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="36c8f-112">The available values for foreground colors are as follows:</span></span>  
  
     <span data-ttu-id="36c8f-113">0: 黒</span><span class="sxs-lookup"><span data-stu-id="36c8f-113">0: Black</span></span>  
  
     <span data-ttu-id="36c8f-114">1: DarkBlue</span><span class="sxs-lookup"><span data-stu-id="36c8f-114">1: DarkBlue</span></span>  
  
     <span data-ttu-id="36c8f-115">2: DarkGreen</span><span class="sxs-lookup"><span data-stu-id="36c8f-115">2: DarkGreen</span></span>  
  
     <span data-ttu-id="36c8f-116">3: DarkCyan</span><span class="sxs-lookup"><span data-stu-id="36c8f-116">3: DarkCyan</span></span>  
  
     <span data-ttu-id="36c8f-117">4: DarkRed</span><span class="sxs-lookup"><span data-stu-id="36c8f-117">4: DarkRed</span></span>  
  
     <span data-ttu-id="36c8f-118">5: DarkMagenta</span><span class="sxs-lookup"><span data-stu-id="36c8f-118">5: DarkMagenta</span></span>  
  
     <span data-ttu-id="36c8f-119">6: DarkYellow</span><span class="sxs-lookup"><span data-stu-id="36c8f-119">6: DarkYellow</span></span>  
  
     <span data-ttu-id="36c8f-120">7: 灰色</span><span class="sxs-lookup"><span data-stu-id="36c8f-120">7: Gray</span></span>  
  
     <span data-ttu-id="36c8f-121">8: DarkGray</span><span class="sxs-lookup"><span data-stu-id="36c8f-121">8: DarkGray</span></span>  
  
     <span data-ttu-id="36c8f-122">9: 青</span><span class="sxs-lookup"><span data-stu-id="36c8f-122">9: Blue</span></span>  
  
     <span data-ttu-id="36c8f-123">10: 緑</span><span class="sxs-lookup"><span data-stu-id="36c8f-123">10: Green</span></span>  
  
     <span data-ttu-id="36c8f-124">11: シアン</span><span class="sxs-lookup"><span data-stu-id="36c8f-124">11: Cyan</span></span>  
  
     <span data-ttu-id="36c8f-125">12: 赤</span><span class="sxs-lookup"><span data-stu-id="36c8f-125">12: Red</span></span>  
  
     <span data-ttu-id="36c8f-126">13: マゼンタ</span><span class="sxs-lookup"><span data-stu-id="36c8f-126">13: Magenta</span></span>  
  
     <span data-ttu-id="36c8f-127">14: 黄色</span><span class="sxs-lookup"><span data-stu-id="36c8f-127">14: Yellow</span></span>  
  
     <span data-ttu-id="36c8f-128">15: 白</span><span class="sxs-lookup"><span data-stu-id="36c8f-128">15: White</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c8f-129">参照</span><span class="sxs-lookup"><span data-stu-id="36c8f-129">See Also</span></span>  
 [<span data-ttu-id="36c8f-130">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="36c8f-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)
---
title: BizTalk Server ツールのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 038a5f5c-d6eb-42db-88d6-70f3deba7a8a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b492c4ee6d22c1eb360f24c60efee1c1106d3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292924"
---
# <a name="troubleshooting-biztalk-server-tools"></a><span data-ttu-id="de7dd-102">BizTalk Server ツールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="de7dd-102">Troubleshooting BizTalk Server Tools</span></span>
<span data-ttu-id="de7dd-103">このトピックでは、1 か所に含まれているツールを使用しているときに発生する一般的な問題について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="de7dd-103">This topic provides a centralized location for information about common problems encountered while using the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="de7dd-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="de7dd-104">Known Issues</span></span>  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a><span data-ttu-id="de7dd-105">BizTalk Server のツールとユーティリティでは、その UAC をサポートする Windows システムでは正しく機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de7dd-105">BizTalk Server Tools and Utilities May Not Function Correctly on a Windows System That Supports UAC</span></span>  
 <span data-ttu-id="de7dd-106">**問題**</span><span class="sxs-lookup"><span data-stu-id="de7dd-106">**Problem**</span></span>  
  
 <span data-ttu-id="de7dd-107">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ユーザー アカウント制御 (UAC) に付属のツールをサポートするシステムがインストールされている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が正常に起動しない可能性がありますまたは正しく機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de7dd-107">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a system that supports User Account Control (UAC), the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may not launch successfully, or may not function correctly.</span></span>  
  
 <span data-ttu-id="de7dd-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="de7dd-108">**Cause**</span></span>  
  
 <span data-ttu-id="de7dd-109">アプリケーションを実行してフラグが設定された特定の特権レベルでは、必要なレベルが、アプリケーションを実行しているユーザーの場合よりも高い場合、UAC がプロンプトにアプリケーション特権を一時的に昇格することができますが表示されます、必要なレベルです。</span><span class="sxs-lookup"><span data-stu-id="de7dd-109">When running an application that has been flagged for a specific privilege level, if the required level is higher than that of the user running the application, the UAC will display a prompt that allows you to temporarily elevate the application privilege to the required level.</span></span> <span data-ttu-id="de7dd-110">付属のツール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ツールは、アプリケーションを実行しているユーザーの現在の特権レベルで実行しようしより高い権限レベルがある場合は失敗するために特権の昇格を自動的に要求を有効にする適切なフラグがありません必須。</span><span class="sxs-lookup"><span data-stu-id="de7dd-110">The tools shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have the correct flags enabled to automatically request privilege elevation, so the tool will attempt to run at the current privilege level of the user running the application and will fail if a higher privilege level is required.</span></span>  
  
 <span data-ttu-id="de7dd-111">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="de7dd-111">**Resolution**</span></span>  
  
 <span data-ttu-id="de7dd-112">この問題を解決するには、管理者特権を持つすべての BizTalk Server ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="de7dd-112">To resolve this problem, run all BizTalk Server tools with Administrative privileges.</span></span> <span data-ttu-id="de7dd-113">管理者特権を持つ、ツールを実行するアプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="de7dd-113">To run a tool with Administrative privileges, right-click the application and then select **Run as administrator**.</span></span>  
  
 <span data-ttu-id="de7dd-114">ユーザー アカウント制御の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167)します。</span><span class="sxs-lookup"><span data-stu-id="de7dd-114">For more information about the User Account Control, see [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167).</span></span>  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a><span data-ttu-id="de7dd-115">BizTalk マッパー ツールボックスが空ある場合があります。</span><span class="sxs-lookup"><span data-stu-id="de7dd-115">Sometimes BizTalk Mapper Toolbox May Appear Empty</span></span>  
 <span data-ttu-id="de7dd-116">**問題**</span><span class="sxs-lookup"><span data-stu-id="de7dd-116">**Problem**</span></span>  
  
 <span data-ttu-id="de7dd-117">場合によっては、Visual Studio でマッパー ツールボックスを開くも、ツールボックスに functoid がまったくは表示されません。</span><span class="sxs-lookup"><span data-stu-id="de7dd-117">Sometimes, when you open the Mapper toolbox in Visual Studio, you do not see any functoids in the toolbox.</span></span>  
  
 <span data-ttu-id="de7dd-118">**原因**</span><span class="sxs-lookup"><span data-stu-id="de7dd-118">**Cause**</span></span>  
  
 <span data-ttu-id="de7dd-119">Visual Studio のアドインや修正プログラムのインストール/アンインストールによる破損があります。</span><span class="sxs-lookup"><span data-stu-id="de7dd-119">Might be a probable corruption by install/uninstall of Visual Studio add-ins and/or patch(es).</span></span>  
  
 <span data-ttu-id="de7dd-120">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="de7dd-120">**Resolution**</span></span>  
  
 <span data-ttu-id="de7dd-121">この問題を解決するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="de7dd-121">To resolve this problem:</span></span>  
  
1.  <span data-ttu-id="de7dd-122">Visual Studio の実行中のすべてのインスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="de7dd-122">Close all running instances of Visual Studio.</span></span>  
  
2.  <span data-ttu-id="de7dd-123">開始**Visual Studio コマンド プロンプト**に管理者として。</span><span class="sxs-lookup"><span data-stu-id="de7dd-123">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
3.  <span data-ttu-id="de7dd-124">コマンド プロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="de7dd-124">At the command prompt, type the following command:</span></span>  
  
    ```  
    devenv.exe /setup  
    ```
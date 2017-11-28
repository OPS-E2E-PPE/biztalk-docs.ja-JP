---
title: "BizTalk Server ツールのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 038a5f5c-d6eb-42db-88d6-70f3deba7a8a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7aedd8977042d15176781b0595bd5bb225a2fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-tools"></a><span data-ttu-id="553bb-102">BizTalk Server ツールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="553bb-102">Troubleshooting BizTalk Server Tools</span></span>
<span data-ttu-id="553bb-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属するツールの使用時に発生する一般的な問題に関する情報をまとめて提供します。</span><span class="sxs-lookup"><span data-stu-id="553bb-103">This topic provides a centralized location for information about common problems encountered while using the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="553bb-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="553bb-104">Known Issues</span></span>  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a><span data-ttu-id="553bb-105">UAC をサポートする Windows システムでは、BizTalk Server のツールおよびユーティリティが正しく機能しない場合がある</span><span class="sxs-lookup"><span data-stu-id="553bb-105">BizTalk Server Tools and Utilities May Not Function Correctly on a Windows System That Supports UAC</span></span>  
 <span data-ttu-id="553bb-106">**問題**</span><span class="sxs-lookup"><span data-stu-id="553bb-106">**Problem**</span></span>  
  
 <span data-ttu-id="553bb-107">ユーザー アカウント制御 (UAC) をサポートするシステムに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属するツールが正常に起動しない、または正しく機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="553bb-107">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a system that supports User Account Control (UAC), the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may not launch successfully, or may not function correctly.</span></span>  
  
 <span data-ttu-id="553bb-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="553bb-108">**Cause**</span></span>  
  
 <span data-ttu-id="553bb-109">特定の特権レベルのフラグが設定されたアプリケーションを実行する場合、アプリケーションを実行するユーザーのレベルよりも高いレベルが必要なときは、UAC のメッセージが表示され、ユーザーは一時的にアプリケーション特権を必要なレベルに昇格できます。</span><span class="sxs-lookup"><span data-stu-id="553bb-109">When running an application that has been flagged for a specific privilege level, if the required level is higher than that of the user running the application, the UAC will display a prompt that allows you to temporarily elevate the application privilege to the required level.</span></span> <span data-ttu-id="553bb-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属するツールは、特権昇格の自動要求を可能にする正しいフラグが設定されていないため、アプリケーションを実行しているユーザーの現在の特権レベルで実行を試み、より高いレベルが要求される場合はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="553bb-110">The tools shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have the correct flags enabled to automatically request privilege elevation, so the tool will attempt to run at the current privilege level of the user running the application and will fail if a higher privilege level is required.</span></span>  
  
 <span data-ttu-id="553bb-111">**解決策**</span><span class="sxs-lookup"><span data-stu-id="553bb-111">**Resolution**</span></span>  
  
 <span data-ttu-id="553bb-112">この問題を解決するには、すべての BizTalk Server ツールを管理者特権で実行します。</span><span class="sxs-lookup"><span data-stu-id="553bb-112">To resolve this problem, run all BizTalk Server tools with Administrative privileges.</span></span> <span data-ttu-id="553bb-113">管理者特権を持つ、ツールを実行するアプリケーションを右クリックし **管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="553bb-113">To run a tool with Administrative privileges, right-click the application and then select **Run as administrator**.</span></span>  
  
 <span data-ttu-id="553bb-114">ユーザー アカウント制御の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167)です。</span><span class="sxs-lookup"><span data-stu-id="553bb-114">For more information about the User Account Control, see [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167).</span></span>  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a><span data-ttu-id="553bb-115">BizTalk マッパー ツールボックスが空のように見える場合がある</span><span class="sxs-lookup"><span data-stu-id="553bb-115">Sometimes BizTalk Mapper Toolbox May Appear Empty</span></span>  
 <span data-ttu-id="553bb-116">**問題**</span><span class="sxs-lookup"><span data-stu-id="553bb-116">**Problem**</span></span>  
  
 <span data-ttu-id="553bb-117">Visual Studio でマッパー ツールボックスを開いたときに、ツールボックスに Functoid がまったく表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="553bb-117">Sometimes, when you open the Mapper toolbox in Visual Studio, you do not see any functoids in the toolbox.</span></span>  
  
 <span data-ttu-id="553bb-118">**原因**</span><span class="sxs-lookup"><span data-stu-id="553bb-118">**Cause**</span></span>  
  
 <span data-ttu-id="553bb-119">Visual Studio のアドインや修正プログラムのインストールまたはアンインストールによる破損の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="553bb-119">Might be a probable corruption by install/uninstall of Visual Studio add-ins and/or patch(es).</span></span>  
  
 <span data-ttu-id="553bb-120">**解決策**</span><span class="sxs-lookup"><span data-stu-id="553bb-120">**Resolution**</span></span>  
  
 <span data-ttu-id="553bb-121">この問題を解決するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="553bb-121">To resolve this problem:</span></span>  
  
1.  <span data-ttu-id="553bb-122">Visual Studio の実行中のすべてのインスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="553bb-122">Close all running instances of Visual Studio.</span></span>  
  
2.  <span data-ttu-id="553bb-123">開始**Visual Studio コマンド プロンプト**を管理者として。</span><span class="sxs-lookup"><span data-stu-id="553bb-123">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
3.  <span data-ttu-id="553bb-124">コマンド プロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="553bb-124">At the command prompt, type the following command:</span></span>  
  
    ```  
    devenv.exe /setup  
    ```
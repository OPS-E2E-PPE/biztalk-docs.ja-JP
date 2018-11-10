---
title: アセンブリを GAC にインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6afc2f81-fa28-4144-b4bd-21c8f35f2270
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e843d74b5420f8973f9d3663cfd05210c26996
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752367"
---
# <a name="how-to-install-an-assembly-in-the-gac"></a><span data-ttu-id="1e687-102">GAC にアセンブリをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="1e687-102">How to Install an Assembly in the GAC</span></span>
<span data-ttu-id="1e687-103">手動でインストールしてに付属する Gacutil ツールを使用してグローバル アセンブリ キャッシュ (GAC) 内の BizTalk アセンブリをアンインストール[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1e687-103">Manually install and uninstall a BizTalk assembly in the global assembly cache (GAC) using the Gacutil tool included with [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1e687-104">使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、BizTalk アセンブリがから配置されている場合、GAC に自動的にインストールすることが[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1e687-104">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can have BizTalk assemblies automatically installed in the GAC when they are deployed from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="1e687-105">このオプションで、BizTalk プロジェクトの展開のプロパティ設定します。参照してください[Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)します。</span><span class="sxs-lookup"><span data-stu-id="1e687-105">Set this option in the Deployment Properties of the BizTalk project; see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span> <span data-ttu-id="1e687-106">このメソッドを使用して、BizTalk 以外の .NET アセンブリを GAC; にインストールすることはできませんこのトピックの説明に従って、手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e687-106">You cannot, use this method to install non-BizTalk .NET assemblies in the GAC; you must install them manually, as described in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e687-107">アセンブリを BizTalk アプリケーションに展開した後も、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用してアセンブリの展開オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1e687-107">You can also specify deployment options for assemblies after they are deployed into a BizTalk application by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="1e687-108">参照してください[BizTalk アセンブリの展開オプションを変更する方法](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)、および[.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="1e687-108">See [How to Modify the Deployment Options of a BizTalk Assembly](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md), and [How to Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1e687-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="1e687-109">Prerequisites</span></span>  
<span data-ttu-id="1e687-110">GAC への書き込み権限を持つアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="1e687-110">Sign in with an account that has Write permission to the GAC.</span></span> <span data-ttu-id="1e687-111">ローカル コンピューターの管理者アカウントには、このアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="1e687-111">The Administrators account on the local computer has this permission.</span></span>  

  
## <a name="install-using-gacutil"></a><span data-ttu-id="1e687-112">Gacutil を使用してインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e687-112">Install using gacutil</span></span>
  
1.  <span data-ttu-id="1e687-113">ローカル コンピューターに BizTalk アセンブリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1e687-113">Copy the BizTalk assembly to your local computer.</span></span>  
  
2.  <span data-ttu-id="1e687-114">開いている**Visual Studio 用開発者コマンド プロンプト**管理者として。</span><span class="sxs-lookup"><span data-stu-id="1e687-114">Open **Developer Command Prompt for Visual Studio** as administrator.</span></span>  
  
3.  <span data-ttu-id="1e687-115">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1e687-115">Type the following:</span></span>  
  
     `gacutil /i path_to_assembly_file /f`

    <span data-ttu-id="1e687-116">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1e687-116">For example, type:</span></span>  
    `gacutil /i c:\temp\filename.dll /f`
    
<span data-ttu-id="1e687-117">`/f`オプションには、同じアセンブリ名を持つ既存のアセンブリが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="1e687-117">The `/f` option overwrites any existing assembly that has the same assembly name.</span></span> <span data-ttu-id="1e687-118">Gacutil コマンドおよびオプションの詳細については、次のように入力します。`gacutil /?`します。</span><span class="sxs-lookup"><span data-stu-id="1e687-118">For more info on the gacutil commands and options, type `gacutil /?`.</span></span> 

## <a name="uninstall-using-gacutil"></a><span data-ttu-id="1e687-119">Gacutil を使用したアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e687-119">Uninstall using gacutil</span></span>
<span data-ttu-id="1e687-120">グローバル アセンブリ キャッシュからアセンブリをアンインストールする (GAC) が完全にアプリケーションを展開解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e687-120">Uninstalling an assembly from the global assembly cache (GAC) is necessary to completely undeploy an application.</span></span> <span data-ttu-id="1e687-121">このプロセスを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="1e687-121">You can automate this process.</span></span> <span data-ttu-id="1e687-122">運用環境にアプリケーションを展開する前に、アプリケーションのアンインストール時に GAC からアセンブリを自動的にアンインストールする処理前のスクリプトを記述します。</span><span class="sxs-lookup"><span data-stu-id="1e687-122">Before deploying the application into a production environment, write a pre-processing script that uninstalls the assembly from the GAC automatically when the application is uninstalled.</span></span> <span data-ttu-id="1e687-123">参照してください[前処理および後処理のスクリプト アプリケーション展開のカスタマイズを使用した](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="1e687-123">See [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
 <span data-ttu-id="1e687-124">追加のファイルおよび設定を削除するのにスクリプトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1e687-124">You can also use a script to remove additional files and settings.</span></span> <span data-ttu-id="1e687-125">参照してください[他のファイルと BizTalk アプリケーションの設定を削除する方法](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="1e687-125">See [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
 
#### <a name="using-the-windows-interface"></a><span data-ttu-id="1e687-126">Windows インターフェイスを使用する場合</span><span class="sxs-lookup"><span data-stu-id="1e687-126">Using the Windows interface</span></span>  
  
1.  <span data-ttu-id="1e687-127">Systemdrive%\Windows\Assembly に開きます。</span><span class="sxs-lookup"><span data-stu-id="1e687-127">Open to %systemdrive%\Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="1e687-128">アプリケーションに含まれる各アセンブリ ファイルを右クリックして**アンインストール**、し、**はい**を確認します。</span><span class="sxs-lookup"><span data-stu-id="1e687-128">Right-click each assembly file included in your application, select **Uninstall**, and then select **Yes** to confirm.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="1e687-129">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="1e687-129">Using the command line</span></span>  
  
1.  <span data-ttu-id="1e687-130">開いている**Visual Studio 用開発者コマンド プロンプト**管理者として。</span><span class="sxs-lookup"><span data-stu-id="1e687-130">Open **Developer Command Prompt for Visual Studio** as administrator.</span></span> 
  
2.  <span data-ttu-id="1e687-131">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1e687-131">Type the following:</span></span>  
  
     <span data-ttu-id="1e687-132">`gacutil /u` \<*完全修飾アセンブリ名*\></span><span class="sxs-lookup"><span data-stu-id="1e687-132">`gacutil /u` \<*fully qualified assembly name*\></span></span>  
  
     <span data-ttu-id="1e687-133">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1e687-133">For example, type:</span></span>  
     `gacutil /u "hello,Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"`
       
## <a name="see-also"></a><span data-ttu-id="1e687-134">参照</span><span class="sxs-lookup"><span data-stu-id="1e687-134">See Also</span></span>  
 [<span data-ttu-id="1e687-135">Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="1e687-135">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
<span data-ttu-id="1e687-136">[BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1e687-136">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 <span data-ttu-id="1e687-137">[BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="1e687-137">[How to Uninstall a BizTalk Application](../core/how-to-uninstall-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="1e687-138">BizTalk グループから BizTalk アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="1e687-138">How to Delete a BizTalk Application from the BizTalk Group</span></span>](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)
 

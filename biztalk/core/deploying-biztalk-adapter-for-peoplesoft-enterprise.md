---
title: PeopleSoft アプリケーションのインポート |Microsoft ドキュメント
description: BizTalk Server に、PeopleSoft アダプターのアプリケーションをインポートする XML バインド ファイルを使用してインポートするときに、制限事項を読み取る
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f53d1b4-e1df-41ff-b554-1bb1d20b9111
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed076bd238eff5106bb0b2f08449144d922fed4d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25970824"
---
# <a name="deploy-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="d96d0-103">BizTalk Adapter for PeopleSoft Enterprise 展開します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-103">Deploy BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="d96d0-104">ここでは、BizTalk Adapter for PeopleSoft Enterprise の展開に関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-104">This section provides information about deploying BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

## <a name="overview"></a><span data-ttu-id="d96d0-105">概要</span><span class="sxs-lookup"><span data-stu-id="d96d0-105">Overview</span></span>
<span data-ttu-id="d96d0-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。</span><span class="sxs-lookup"><span data-stu-id="d96d0-106">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d96d0-107"> により、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="d96d0-107"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="d96d0-108">使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-108">You use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform these tasks:</span></span>  
  
-   <span data-ttu-id="d96d0-109">BizTalk 構成データベースで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-109">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="d96d0-110">グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール</span><span class="sxs-lookup"><span data-stu-id="d96d0-110">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="d96d0-111">バインド ファイルに対する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリのバインド情報のインポートまたはエクスポート</span><span class="sxs-lookup"><span data-stu-id="d96d0-111">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files.</span></span>  
  
<span data-ttu-id="d96d0-112">使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="d96d0-112">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d96d0-113">Microsoft BizTalk Adapter for PeopleSoft Enterprise の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="d96d0-113">The Microsoft BizTalk Adapter for PeopleSoft Enterprise only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="d96d0-114">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d96d0-114">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="d96d0-115">セットアップを確認します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-115">Confirm your setup</span></span>
<span data-ttu-id="d96d0-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。</span><span class="sxs-lookup"><span data-stu-id="d96d0-116">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="d96d0-117">CLASSPATH が PeopleSoft 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="d96d0-117">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="d96d0-118">新しいコンピュータで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-118">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="d96d0-119">新しいコンピュータで、応答用のフォルダが存在し、同じである。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-119">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="d96d0-120">PeopleSoft Enterprise システム パスワードが構成に存在する場合、パスワードが \*\*\*\*\* としてバインド ファイルに保存されている。</span><span class="sxs-lookup"><span data-stu-id="d96d0-120">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="d96d0-121">参照してください**制限**」を参照します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-121">See **Limitations** in this topic.</span></span>

> [!NOTE]
>  <span data-ttu-id="d96d0-122">展開すると、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d96d0-122">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="d96d0-123">バインド ファイルとアセンブリを展開先のコンピュータに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d96d0-123">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="d96d0-124">バインド ファイルをインポートする方法を手順に沿ってを参照してください。[を BizTalk グループにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="d96d0-124">For step-by-step directions about importing binding files, see [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md).</span></span> 
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="d96d0-125">ターゲット コンピューターをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="d96d0-125">Clean the target computer</span></span>
<span data-ttu-id="d96d0-126">新しいアプリケーションの配置ターゲット コンピューターのクリーニング、送信ポートを削除、および受信場所をオーケストレーションにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="d96d0-126">To clean the target computer for deploying the new application, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="d96d0-127">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d96d0-127">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
<span data-ttu-id="d96d0-128">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span><span class="sxs-lookup"><span data-stu-id="d96d0-128">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
<span data-ttu-id="d96d0-129">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span><span class="sxs-lookup"><span data-stu-id="d96d0-129">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
<span data-ttu-id="d96d0-130">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-130">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a><span data-ttu-id="d96d0-131">制限事項</span><span class="sxs-lookup"><span data-stu-id="d96d0-131">Limitations</span></span>
<span data-ttu-id="d96d0-132">によってエクスポートされるバインド ファイルにアスタリスク (\*) でトランスポート アダプターのパスワードが格納されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、され、同じ形式で管理コンポーネントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d96d0-132">The Transport Adapter password is stored as asterisks (******) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="d96d0-133">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="d96d0-133">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="d96d0-134">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d96d0-134">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="d96d0-135">次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96d0-135">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="d96d0-136">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d96d0-136">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="d96d0-137">この場合、インポート操作が完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96d0-137">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  

### <a name="work-around-the-password-limitation"></a><span data-ttu-id="d96d0-138">パスワードの制限を回避するには</span><span class="sxs-lookup"><span data-stu-id="d96d0-138">Work around the password limitation</span></span>  

<span data-ttu-id="d96d0-139">**オプション 1**</span><span class="sxs-lookup"><span data-stu-id="d96d0-139">**Option 1**</span></span>   
  
-   <span data-ttu-id="d96d0-140">インポートする前に、アスタリスクをプレーン テキストで置き換えることによって、バインド ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-140">Before you import, update the binding file by replacing the asterisks with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="d96d0-141">この操作は、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="d96d0-141">This practice is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="d96d0-142">インポートする前に、無効な値 (つまり、正しくないパスワード)、アスタリスクを置き換えてバインディング fileby を更新します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-142">Before you import, update the binding fileby replacing the asterisks with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="d96d0-143">インポートした後で正しいパスワードを入力してください、**トランスポートのプロパティ**BizTalk Server 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="d96d0-143">After you import, enter the correct password in the **Transport Properties** in BizTalk Server Administration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d96d0-144">この対処方法を使用できるのは、対象のコンピューターに Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされているか、カスタム ツールを開発する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d96d0-144">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
<span data-ttu-id="d96d0-145">**オプション 2**</span><span class="sxs-lookup"><span data-stu-id="d96d0-145">**Option 2**</span></span>  
  
-   <span data-ttu-id="d96d0-146">パスワードではなく、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-146">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span> <span data-ttu-id="d96d0-147">SSO オプションを使用するには、バインド ファイルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96d0-147">Using the SSO option requires an import of the binding file.</span></span>  
  
- <span data-ttu-id="d96d0-148">論理システムと送信を確認し、サービスを受信します。</span><span class="sxs-lookup"><span data-stu-id="d96d0-148">Verify the logical system and the Transmit and Receive services.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="d96d0-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="d96d0-149">Next steps</span></span>
[<span data-ttu-id="d96d0-150">BizTalk Server 例外処理を使用して、オーケストレーションで</span><span class="sxs-lookup"><span data-stu-id="d96d0-150">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling2.md)
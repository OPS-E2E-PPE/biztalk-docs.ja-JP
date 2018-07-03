---
title: TIBCO EMS のバインドのインポート |Microsoft Docs
description: BizTalk Server でバインドのインポート機能を使用して TIBCO Enterprise Message Service のアプリケーション用 BizTalk アダプターの展開します。
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69dae448-4ec6-4a56-a628-bb447bc21b62
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90d083833e7961770c6ecd535e9ed3e5143be30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981363"
---
# <a name="deploy-tibco-ems-ports-and-assemblies"></a><span data-ttu-id="848cc-103">TIBCO EMS のポートとアセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="848cc-103">Deploy TIBCO EMS ports and assemblies</span></span>

## <a name="overview"></a><span data-ttu-id="848cc-104">概要</span><span class="sxs-lookup"><span data-stu-id="848cc-104">Overview</span></span>
<span data-ttu-id="848cc-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとターゲット コンピューター上のアセンブリを複製することができます。</span><span class="sxs-lookup"><span data-stu-id="848cc-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="848cc-106"> エクスポートは、ポートおよび受信場所の構成を XML ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="848cc-106"> exports send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="848cc-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="848cc-107">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
- <span data-ttu-id="848cc-108">BizTalk 構成データベースで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除します。</span><span class="sxs-lookup"><span data-stu-id="848cc-108">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
- <span data-ttu-id="848cc-109">グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール</span><span class="sxs-lookup"><span data-stu-id="848cc-109">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
- <span data-ttu-id="848cc-110">バインド ファイルに対する、BizTalk アセンブリのバインド情報のインポートまたはエクスポート</span><span class="sxs-lookup"><span data-stu-id="848cc-110">Import or export BizTalk assembly binding information to and from binding files.</span></span>  
  
  <span data-ttu-id="848cc-111">使用する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="848cc-111">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="848cc-112">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service の場合のみ、ソース (開発) コンピューターに Visual Studio がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="848cc-112">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="848cc-113">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="848cc-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="848cc-114">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="848cc-114">Confirm your setup</span></span>
<span data-ttu-id="848cc-115">BizTalk Server を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。</span><span class="sxs-lookup"><span data-stu-id="848cc-115">Before you use BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="848cc-116">新しいコンピューターで、応答用のフォルダーが存在し、同じである。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="848cc-116">The folders for the responses must exist and be identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="848cc-117">TIBCO Enterprise Message Service システム パスワードが構成に存在する場合、パスワードが \*\*\*\*\* としてバインド ファイルに保存される必要があります。</span><span class="sxs-lookup"><span data-stu-id="848cc-117">TIBCO Enterprise Message Service system passwords, if present in the configuration, must be saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="848cc-118">参照してください**制限**このトピックの「します。</span><span class="sxs-lookup"><span data-stu-id="848cc-118">See **Limitations** in this topic.</span></span>


## <a name="clean-the-target-computer"></a><span data-ttu-id="848cc-119">ターゲット コンピューターをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="848cc-119">Clean the target computer</span></span>
<span data-ttu-id="848cc-120">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="848cc-120">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="848cc-121">バインド ファイル (およびアセンブリ) を展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="848cc-121">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  

<span data-ttu-id="848cc-122">をインポートする前に、送信ポートを削除し、受信場所、オーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="848cc-122">Before you import, remove any send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="848cc-123">Microsoft Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="848cc-123">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs`  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs`
  

<span data-ttu-id="848cc-124">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="848cc-124">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a><span data-ttu-id="848cc-125">制限事項</span><span class="sxs-lookup"><span data-stu-id="848cc-125">Limitations</span></span>
<span data-ttu-id="848cc-126">トランスポート アダプターのパスワードは、星として格納されます (\*\*\*\*\*\*)、BizTalk Server によってエクスポートされるバインド ファイルにされ、同じ管理コンポーネントに渡されます形式です。</span><span class="sxs-lookup"><span data-stu-id="848cc-126">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="848cc-127">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="848cc-127">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="848cc-128">使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページ。</span><span class="sxs-lookup"><span data-stu-id="848cc-128">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="848cc-129">これは、既知の制限です。</span><span class="sxs-lookup"><span data-stu-id="848cc-129">This is a known limitation.</span></span> <span data-ttu-id="848cc-130">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="848cc-130">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="848cc-131">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="848cc-131">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="848cc-132">次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="848cc-132">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="848cc-133">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="848cc-133">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="848cc-134">この場合、インポート操作が正常に完了した後は、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="848cc-134">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
 
### <a name="password-limitation-workaround"></a><span data-ttu-id="848cc-135">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="848cc-135">Password Limitation Workaround</span></span>  
 <span data-ttu-id="848cc-136">このパスワードの制限に対処するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="848cc-136">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="848cc-137">アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="848cc-137">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="848cc-138">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="848cc-138">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="848cc-139">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="848cc-139">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="848cc-140">使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページ。</span><span class="sxs-lookup"><span data-stu-id="848cc-140">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="848cc-141">この対処方法を使用できるのは、対象のコンピューターに Visual Studio がインストールされているか、カスタム ツールを開発する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="848cc-141">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="848cc-142">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="848cc-142">Verify the Logical system and the Transmit and Receive services.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="848cc-143">次のステップ</span><span class="sxs-lookup"><span data-stu-id="848cc-143">Next steps</span></span>
[<span data-ttu-id="848cc-144">BizTalk Server 例外処理を使用して、オーケストレーションで</span><span class="sxs-lookup"><span data-stu-id="848cc-144">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling5.md)
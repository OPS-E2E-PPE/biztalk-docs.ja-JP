---
title: インストールに関するエラー メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, error message
- error messages, installation
ms.assetid: 593b033f-03da-43ae-a948-f87aa5e4bccd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2513ed65a332839cf1cbeef1b64e99c169b66ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382173"
---
# <a name="installation-error-message"></a><span data-ttu-id="ebaf9-102">インストールに関するエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="ebaf9-102">Installation Error Message</span></span>
<span data-ttu-id="ebaf9-103">送信を定義する、TIBCO Enterprise Message Service の Microsoft BizTalk Adapter をインストールまたは受信した後、場所は、次のエラーを可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-103">After you install Microsoft BizTalk Adapter for TIBCO Enterprise Message Service, defining a send or receive location for it might result in the following error:</span></span>  
  
 <span data-ttu-id="ebaf9-104">メッセージング エンジンは、受信 URL を追加できませんでした"\<送信/受信場所 URL\>"アダプター"TIBCO EMS"にします。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-104">The Messaging Engine failed to add a receive URL "\< send/receive location URL\>" to the adapter "TIBCO EMS".</span></span> <span data-ttu-id="ebaf9-105">理由: "ファイルまたはアセンブリ名 TIBCO。EMS、またはその依存関係の 1 つが見つかりません。"</span><span class="sxs-lookup"><span data-stu-id="ebaf9-105">Reason: "File or assembly name TIBCO.EMS, or one of its dependencies, was not found."</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="ebaf9-106">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="ebaf9-106">Possible Causes</span></span>  
 <span data-ttu-id="ebaf9-107">このエラーは、次の原因の 1 つは、通常は。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-107">This error usually has one of the following causes.</span></span>  
  
### <a name="assembly-not-in-gac"></a><span data-ttu-id="ebaf9-108">アセンブリを GAC に存在しません。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-108">Assembly Not in GAC</span></span>  
 <span data-ttu-id="ebaf9-109">BizTalk Adapter for TIBCO EMS は、.NET Framework アプリケーションであり、TIBCO、.NET Framework アセンブリを使用します。EMS します。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-109">BizTalk Adapter for TIBCO EMS is a .NET Framework application, and uses the .NET Framework assembly, TIBCO.EMS.</span></span> <span data-ttu-id="ebaf9-110">このアセンブリは、実行時に .NET Framework 用 .NET Framework グローバル アセンブリ キャッシュ (GAC) に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-110">This assembly must be present in the .NET Framework global assembly cache (GAC) for the .NET Framework to find it at run time.</span></span>  
  
#### <a name="solution"></a><span data-ttu-id="ebaf9-111">ソリューション</span><span class="sxs-lookup"><span data-stu-id="ebaf9-111">Solution</span></span>  
 <span data-ttu-id="ebaf9-112">アセンブリが GAC に存在するかどうかを判断するには、コマンド プロンプトを開きし、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-112">To determine if the assembly is present in the GAC, open a command prompt and type the following command:</span></span>  
  
 `GACUTIL /L TIBCO.EMS`  
  
 <span data-ttu-id="ebaf9-113">結果項目が表示されない場合は、GAC にアセンブリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-113">If the result shows zero items, you must add the assembly to the GAC.</span></span> <span data-ttu-id="ebaf9-114">これを行うには、コマンド プロンプトを開き、TIBCO EMS のインストール クライアントの \cs ディレクトリ (既定のインストール場所は C:\TIBCO\EMS\Clients\CS) に移動して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-114">To do this, open a command prompt, change directories to your TIBCO EMS installation clients\cs directory (the default installation location is C:\TIBCO\EMS\Clients\CS), and run the following command:</span></span>  
  
 `GACUTIL /i TIBCO.EMS.DLL`  
  
### <a name="different-version-of-assembly-in-gac"></a><span data-ttu-id="ebaf9-115">アセンブリが GAC 内の別のバージョン</span><span class="sxs-lookup"><span data-stu-id="ebaf9-115">Different Version of Assembly in GAC</span></span>  
 <span data-ttu-id="ebaf9-116">TIBCO します。EMS.dll アセンブリが GAC には、TIBCO EMS 用 BizTalk アダプターを構築するために使用する 1 つから別のバージョン。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-116">The TIBCO.EMS.dll assembly is in the GAC, but it is a different version from the one used to build BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="ebaf9-117">場合、TIBCO します。コンピューターにインストールされている EMS.dll はから製品バージョン 4.2 以降 (TIBCO で情報を確認できます)、アダプタのビルドに使用するバージョンと互換性が必要です。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-117">If the TIBCO.EMS.dll that is installed on the computer is from a product version 4.2 or above, it should be compatible with the version used to build the adapter (you can verify that information with TIBCO).</span></span>  
  
#### <a name="solution"></a><span data-ttu-id="ebaf9-118">ソリューション</span><span class="sxs-lookup"><span data-stu-id="ebaf9-118">Solution</span></span>  
 <span data-ttu-id="ebaf9-119">.NET Framework では、この問題を回避する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-119">The .NET Framework provides a way to work around this problem.</span></span> <span data-ttu-id="ebaf9-120">呼び出された*バインド リダイレクト*、構成ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-120">It is called *binding redirection*, which uses a configuration file.</span></span>  
  
 <span data-ttu-id="ebaf9-121">エラー メッセージを削除するこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-121">Follow these steps to eliminate the error message:</span></span>  
  
1. <span data-ttu-id="ebaf9-122">任意のテキスト エディターでは、ファイル BTSNTSVC.exe.config を開きます。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-122">With any text editor, open the file BTSNTSVC.exe.config.</span></span>  
  
    <span data-ttu-id="ebaf9-123">ファイルがである、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディレクトリ (既定のインストール場所は: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-123">The file is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directory (the default installation location is: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]).</span></span>  
  
2. <span data-ttu-id="ebaf9-124">子として、BTSNTSVC.exe.config ファイルに次のエントリを追加、 \<assemblyBinding\>要素。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-124">Add the following entry to the BTSNTSVC.exe.config file, as a child of the \<assemblyBinding\> element:</span></span>  
  
```  
<dependentAssembly>  
    <assemblyIdentity name='TIBCO.EMS'  
        publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
    <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
        newVersion='1.0.0.0' />  
</dependentAssembly>  
```  
  
 <span data-ttu-id="ebaf9-125">BTSNTSVC.exe.config ファイルが変更されていない場合、 \<assemblyBinding\>要素にいない次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-125">If the BTSNTSVC.exe.config file has not been previously modified, the \<assemblyBinding\> element would not look like this:</span></span>  
  
```  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
    <probing privatePath="BizTalk Assemblies;Developer  
        Tools;Tracking;Tracking\interop" />  
    <dependentAssembly>  
        <assemblyIdentity name='TIBCO.EMS'  
            publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
        <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
            newVersion='1.0.0.0' />  
    </dependentAssembly>  
</assemblyBinding>  
```  
  
1. <span data-ttu-id="ebaf9-126">コマンド プロンプトでコマンドを入力:`GACUTIL /L TIBCO.EMS`します。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-126">In a command prompt, type the command: `GACUTIL /L TIBCO.EMS`.</span></span>  
  
2. <span data-ttu-id="ebaf9-127">TIBCO をコピーします。EMS の出力からのアセンブリ バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-127">Copy the TIBCO.EMS assembly version number from the output.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="ebaf9-128">2 つのバージョン番号が表示されます。 1 つは gacutil ユーティリティのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-128">Two version numbers appear: one is the version number of the gacutil utility.</span></span> <span data-ttu-id="ebaf9-129">2 番目のバージョンの番号は、直後に表示する**バージョン =** します。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-129">You want the second version number, which appears just after **Version=**.</span></span>  
  
3. <span data-ttu-id="ebaf9-130">直後に、引用符の間、BTSNTSVC.exe.config ファイルにバージョン番号を貼り付ける**newVersion =** (前の例の XML 文字を太字)。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-130">Paste the version number in the BTSNTSVC.exe.config file, between the quotation marks, right after **newVersion=** (bold characters in the previous XML example).</span></span>  
  
4. <span data-ttu-id="ebaf9-131">変更した BTSNTSVC.exe.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-131">Save the modified BTSNTSVC.exe.config file.</span></span>  
  
5. <span data-ttu-id="ebaf9-132">再起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト。</span><span class="sxs-lookup"><span data-stu-id="ebaf9-132">Restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebaf9-133">参照</span><span class="sxs-lookup"><span data-stu-id="ebaf9-133">See Also</span></span>  
 [<span data-ttu-id="ebaf9-134">TIBCO Enterprise Message Service のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ebaf9-134">Troubleshooting TIBCO Enterprise Message Service</span></span>](../core/troubleshooting-tibco-enterprise-message-service.md)
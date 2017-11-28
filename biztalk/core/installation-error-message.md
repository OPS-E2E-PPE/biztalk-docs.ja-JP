---
title: "インストールに関するエラー メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation, error message
- error messages, installation
ms.assetid: 593b033f-03da-43ae-a948-f87aa5e4bccd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d3f7bbe9440c737b803eb1e6ae04e96449bf4f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installation-error-message"></a><span data-ttu-id="dfcf3-102">インストールに関するエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="dfcf3-102">Installation Error Message</span></span>
<span data-ttu-id="dfcf3-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service をインストールした後に、送信場所または受信場所を定義すると、次のエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-103">After you install Microsoft BizTalk Adapter for TIBCO Enterprise Message Service, defining a send or receive location for it might result in the following error:</span></span>  
  
 <span data-ttu-id="dfcf3-104">メッセージング エンジンが受信 URL に追加できませんでした"\<送信/受信場所の URL >"アダプター"TIBCO EMS"にします。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-104">The Messaging Engine failed to add a receive URL "\< send/receive location URL>" to the adapter "TIBCO EMS".</span></span> <span data-ttu-id="dfcf3-105">理由:"ファイルまたはアセンブリ名 TIBCO。EMS、またはその依存関係の 1 つが見つかりませんでした。"</span><span class="sxs-lookup"><span data-stu-id="dfcf3-105">Reason: "File or assembly name TIBCO.EMS, or one of its dependencies, was not found."</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="dfcf3-106">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="dfcf3-106">Possible Causes</span></span>  
 <span data-ttu-id="dfcf3-107">通常、このエラーの原因は以下のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-107">This error usually has one of the following causes.</span></span>  
  
### <a name="assembly-not-in-gac"></a><span data-ttu-id="dfcf3-108">アセンブリが GAC に存在しない</span><span class="sxs-lookup"><span data-stu-id="dfcf3-108">Assembly Not in GAC</span></span>  
 <span data-ttu-id="dfcf3-109">BizTalk Adapter for TIBCO EMS は .NET Framework アプリケーションであり、.NET Framework アセンブリ TIBCO.EMS を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-109">BizTalk Adapter for TIBCO EMS is a .NET Framework application, and uses the .NET Framework assembly, TIBCO.EMS.</span></span> <span data-ttu-id="dfcf3-110">このアセンブリは、.NET Framework が実行時に特定できるように、.NET Framework グローバル アセンブリ キャッシュ (GAC) に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-110">This assembly must be present in the .NET Framework global assembly cache (GAC) for the .NET Framework to find it at run time.</span></span>  
  
#### <a name="solution"></a><span data-ttu-id="dfcf3-111">解決方法</span><span class="sxs-lookup"><span data-stu-id="dfcf3-111">Solution</span></span>  
 <span data-ttu-id="dfcf3-112">アセンブリが GAC に存在するかどうかを判断するには、コマンド プロンプトを開き、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-112">To determine if the assembly is present in the GAC, open a command prompt and type the following command:</span></span>  
  
 `GACUTIL /L TIBCO.EMS`  
  
 <span data-ttu-id="dfcf3-113">結果に項目が表示されない場合は、アセンブリを GAC に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-113">If the result shows zero items, you must add the assembly to the GAC.</span></span> <span data-ttu-id="dfcf3-114">そのためには、コマンド プロンプトを開き、ディレクトリを TIBCO EMS のインストール クライアントの \cs ディレクトリ (既定のインストール場所は C:\TIBCO\EMS\Clients\CS) に変更し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-114">To do this, open a command prompt, change directories to your TIBCO EMS installation clients\cs directory (the default installation location is C:\TIBCO\EMS\Clients\CS), and run the following command:</span></span>  
  
 `GACUTIL /i TIBCO.EMS.DLL`  
  
### <a name="different-version-of-assembly-in-gac"></a><span data-ttu-id="dfcf3-115">GAC のアセンブリのバージョンが異なる</span><span class="sxs-lookup"><span data-stu-id="dfcf3-115">Different Version of Assembly in GAC</span></span>  
 <span data-ttu-id="dfcf3-116">TIBCO.EMS.dll アセンブリは GAC に存在していますが、バージョンが BizTalk Adapter for TIBCO EMS のビルドに使用されたバージョンとは異なります。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-116">The TIBCO.EMS.dll assembly is in the GAC, but it is a different version from the one used to build BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="dfcf3-117">コンピュータにインストールされた TIBCO.EMS.dll が Version 4.2 以上の場合は、アダプタのビルドに使用されたバージョンと互換性があります (TIBCO で情報を確認できます)。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-117">If the TIBCO.EMS.dll that is installed on the computer is from a product version 4.2 or above, it should be compatible with the version used to build the adapter (you can verify that information with TIBCO).</span></span>  
  
#### <a name="solution"></a><span data-ttu-id="dfcf3-118">解決方法</span><span class="sxs-lookup"><span data-stu-id="dfcf3-118">Solution</span></span>  
 <span data-ttu-id="dfcf3-119">.NET Framework にはこの問題を回避する方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-119">The .NET Framework provides a way to work around this problem.</span></span> <span data-ttu-id="dfcf3-120">呼び出された*バインディングのリダイレクト*、構成ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-120">It is called *binding redirection*, which uses a configuration file.</span></span>  
  
 <span data-ttu-id="dfcf3-121">エラー メッセージが表示されないようにするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-121">Follow these steps to eliminate the error message:</span></span>  
  
1.  <span data-ttu-id="dfcf3-122">任意のテキスト エディタを使用して、ファイル BTSNTSVC.exe.config を開きます。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-122">With any text editor, open the file BTSNTSVC.exe.config.</span></span>  
  
     <span data-ttu-id="dfcf3-123">ファイルは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ディレクトリ (既定のインストール場所は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]) にあります。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-123">The file is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directory (the default installation location is: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]).</span></span>  
  
2.  <span data-ttu-id="dfcf3-124">子として、次のエントリを BTSNTSVC.exe.config ファイルに追加、 \<assemblyBinding > 要素。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-124">Add the following entry to the BTSNTSVC.exe.config file, as a child of the \<assemblyBinding> element:</span></span>  
  
```  
<dependentAssembly>  
    <assemblyIdentity name='TIBCO.EMS'  
        publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
    <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
        newVersion='1.0.0.0' />  
</dependentAssembly>  
```  
  
 <span data-ttu-id="dfcf3-125">BTSNTSVC.exe.config ファイルが変更されていない場合、 \<assemblyBinding > 要素は次のようになりますできません。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-125">If the BTSNTSVC.exe.config file has not been previously modified, the \<assemblyBinding> element would not look like this:</span></span>  
  
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
  
1.  <span data-ttu-id="dfcf3-126">コマンド プロンプトでコマンドを入力:`GACUTIL /L TIBCO.EMS`です。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-126">In a command prompt, type the command: `GACUTIL /L TIBCO.EMS`.</span></span>  
  
2.  <span data-ttu-id="dfcf3-127">出力から TIBCO.EMS アセンブリ バージョン番号をコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-127">Copy the TIBCO.EMS assembly version number from the output.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="dfcf3-128">2 つのバージョン番号が表示されます。1 つは gacutil ユーティリティのバージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-128">Two version numbers appear: one is the version number of the gacutil utility.</span></span> <span data-ttu-id="dfcf3-129">2 番目のバージョンの番号は、直後に表示する**バージョン =**です。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-129">You want the second version number, which appears just after **Version=**.</span></span>  
  
3.  <span data-ttu-id="dfcf3-130">直後に、引用符の間、BTSNTSVC.exe.config ファイルにバージョン番号を貼り付け**newVersion =** (前の XML 例内の文字を太字)。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-130">Paste the version number in the BTSNTSVC.exe.config file, between the quotation marks, right after **newVersion=** (bold characters in the previous XML example).</span></span>  
  
4.  <span data-ttu-id="dfcf3-131">変更した BTSNTSVC.exe.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-131">Save the modified BTSNTSVC.exe.config file.</span></span>  
  
5.  <span data-ttu-id="dfcf3-132">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストを再起動します。</span><span class="sxs-lookup"><span data-stu-id="dfcf3-132">Restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcf3-133">参照</span><span class="sxs-lookup"><span data-stu-id="dfcf3-133">See Also</span></span>  
 [<span data-ttu-id="dfcf3-134">TIBCO Enterprise Message Service のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dfcf3-134">Troubleshooting TIBCO Enterprise Message Service</span></span>](../core/troubleshooting-tibco-enterprise-message-service.md)
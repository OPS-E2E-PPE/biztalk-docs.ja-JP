---
title: JD Edwards EnterpriseOne アプリケーションのインポート |Microsoft Docs
description: セットアップを確認、アプリケーションのバインド ファイルをインポート、および BizTalk で JD Edwards EnterpriseOne アダプターの制限を確認します。
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 852f948b-48ba-4ae2-b1eb-7c88c1542a52
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c6f24ff4cb7060d0cddf29d82f4035d8407dca
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753194"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a><span data-ttu-id="034ae-103">JD Edwards EnterpriseOne アプリケーションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="034ae-103">Import the JD Edwards EnterpriseOne application</span></span>
  
## <a name="overview"></a><span data-ttu-id="034ae-104">概要</span><span class="sxs-lookup"><span data-stu-id="034ae-104">Overview</span></span>
<span data-ttu-id="034ae-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとターゲット コンピューター上のアセンブリを複製することができます。</span><span class="sxs-lookup"><span data-stu-id="034ae-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="034ae-106">により、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="034ae-106">exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="034ae-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="034ae-107">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
- <span data-ttu-id="034ae-108">BizTalk 構成データベース内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除する</span><span class="sxs-lookup"><span data-stu-id="034ae-108">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database</span></span>  
  
- <span data-ttu-id="034ae-109">グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールまたはアンインストールする</span><span class="sxs-lookup"><span data-stu-id="034ae-109">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
- <span data-ttu-id="034ae-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリのバインド情報をバインド ファイルからインポートする、またはバインド ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="034ae-110">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files</span></span>  
  
<span data-ttu-id="034ae-111">使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="034ae-111">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="034ae-112">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="034ae-112">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="034ae-113">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="034ae-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="034ae-114">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="034ae-114">Confirm your setup</span></span>
<span data-ttu-id="034ae-115">BizTalk Server を使用してバインド ファイルをインポートする前に、以下の項目について確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="034ae-115">Before you use the BizTalk Server to import a binding file, you must verify the following:</span></span>  
  
-   <span data-ttu-id="034ae-116">CLASSPATH が JD Edwards EnterpriseOne 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="034ae-116">The CLASSPATH is pointing to a specific location for the JD Edwards EnterpriseOne-specific files.</span></span> <span data-ttu-id="034ae-117">新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="034ae-117">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="034ae-118">新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="034ae-118">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="034ae-119">JD Edwards EnterpriseOne システムのパスワードは、構成に存在する場合、として保存されます\* \* \* \* \*バインド ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="034ae-119">JD Edwards EnterpriseOne system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="034ae-120">詳細については、次を参照してください。**制限**このトピックの「します。</span><span class="sxs-lookup"><span data-stu-id="034ae-120">For more information, see **Limitations** in this topic.</span></span>

## <a name="clean-the-target-computer"></a><span data-ttu-id="034ae-121">ターゲット コンピューターをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="034ae-121">Clean the target computer</span></span>
<span data-ttu-id="034ae-122">バインド ファイルとアセンブリを展開先のコンピューターに再展開すると、送信ポートと受信場所が、再インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="034ae-122">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
<span data-ttu-id="034ae-123">インポートする前に、送信ポートを削除して、受信場所をオーケストレーションにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="034ae-123">Before you import, remove Send ports and Receive locations bound to the orchestration.</span></span> <span data-ttu-id="034ae-124">Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="034ae-124">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="034ae-125">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="034ae-125">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="034ae-126">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="034ae-126">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  

<span data-ttu-id="034ae-127">たとえば、コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="034ae-127">For example, from a command prompt run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
## <a name="limitations"></a><span data-ttu-id="034ae-128">制限事項</span><span class="sxs-lookup"><span data-stu-id="034ae-128">Limitations</span></span>
<span data-ttu-id="034ae-129">トランスポート アダプターのパスワードは、星として格納されます (\*\*\*\*\*\*) によってエクスポートされるバインド ファイルに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で管理コンポーネントに渡すと、同じ形式です。</span><span class="sxs-lookup"><span data-stu-id="034ae-129">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="034ae-130">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="034ae-130">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="034ae-131">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="034ae-131">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="034ae-132">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="034ae-132">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="034ae-133">次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="034ae-133">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="034ae-134">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="034ae-134">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="034ae-135">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="034ae-135">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
### <a name="work-around-the-password-limitation"></a><span data-ttu-id="034ae-136">パスワードの制限を回避するには</span><span class="sxs-lookup"><span data-stu-id="034ae-136">Work around the password limitation</span></span>  
  
1.  <span data-ttu-id="034ae-137">パスワードではなく、エンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="034ae-137">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="034ae-138">SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。</span><span class="sxs-lookup"><span data-stu-id="034ae-138">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="034ae-139">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="034ae-139">Verify the Logical system and the Transmit and Receive services.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="034ae-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="034ae-140">Next steps</span></span>
[<span data-ttu-id="034ae-141">BizTalk Server 例外処理を使用して、オーケストレーションで</span><span class="sxs-lookup"><span data-stu-id="034ae-141">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling3.md)
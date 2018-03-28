---
title: BizTalk Adapter for JD Edwards OneWorld にインポート |Microsoft ドキュメント
description: アプリケーション バインド ファイルをインポートし、JD Edwards OneWorld アダプターは、BizTalk の制限事項の確認
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f308d2fe-39dd-4008-94ed-292c4c26fe06
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a452d61b3bdb5f5d0fee9e0916811645938d70
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a><span data-ttu-id="89147-103">JD Edwards EnterpriseOne アプリケーションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="89147-103">Import the JD Edwards EnterpriseOne application</span></span>
  
## <a name="overview"></a><span data-ttu-id="89147-104">概要</span><span class="sxs-lookup"><span data-stu-id="89147-104">Overview</span></span>
<span data-ttu-id="89147-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。</span><span class="sxs-lookup"><span data-stu-id="89147-105">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="89147-106">BizTalk Server により、送信ポートおよび受信場所の構成が XML ファイルにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="89147-106">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="89147-107">BizTalk Server を使用すると、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="89147-107">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="89147-108">BizTalk 構成データベース内の BizTalk Server アセンブリを展開または削除する</span><span class="sxs-lookup"><span data-stu-id="89147-108">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="89147-109">グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールまたはアンインストールする</span><span class="sxs-lookup"><span data-stu-id="89147-109">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="89147-110">BizTalk Server アセンブリのバインド情報をバインド ファイルからインポートする、またはバインド ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="89147-110">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  

<span data-ttu-id="89147-111">使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="89147-111">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89147-112">Microsoft BizTalk Adapter for JD Edwards OneWorld の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="89147-112">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="89147-113">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="89147-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="89147-114">セットアップを確認します。</span><span class="sxs-lookup"><span data-stu-id="89147-114">Confirm your setup</span></span>
<span data-ttu-id="89147-115">バインド ファイルをインポートする BizTalk Server を使用する前に、次の操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="89147-115">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="89147-116">CLASSPATH が JD Edwards 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="89147-116">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="89147-117">新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="89147-117">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="89147-118">新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="89147-118">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="89147-119">JD Edwards システム パスワードが構成に存在する場合、パスワードが \*\*\*\*\* としてバインド ファイルに保存されている。</span><span class="sxs-lookup"><span data-stu-id="89147-119">JD Edwards system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="89147-120">参照してください**制限**」を参照します。</span><span class="sxs-lookup"><span data-stu-id="89147-120">See **Limitations** in this topic.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="89147-121">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="89147-121">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="89147-122">バインド ファイルとアセンブリを展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="89147-122">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="89147-123">ターゲット コンピューターをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="89147-123">Clean the target computer</span></span>
<span data-ttu-id="89147-124">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="89147-124">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="89147-125">バインド ファイル (およびアセンブリ) を展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="89147-125">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
<span data-ttu-id="89147-126">インポートすると、前に、送信ポートを削除し、受信場所、オーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="89147-126">Before you import, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="89147-127">Microsoft Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="89147-127">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="89147-128">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="89147-128">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="89147-129">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="89147-129">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
<span data-ttu-id="89147-130">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="89147-130">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="limitations"></a><span data-ttu-id="89147-131">制限事項</span><span class="sxs-lookup"><span data-stu-id="89147-131">Limitations</span></span>
<span data-ttu-id="89147-132">アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) を BizTalk 展開ウィザードによってエクスポートされ、同じ形式で管理コンポーネントに渡されるバインド ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="89147-132">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="89147-133">アスタリスクをランダムな英数字の値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="89147-133">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="89147-134">使用して、正しいパスワードを入力し、 **トランスポートのプロパティ** 、バインド ファイルをインポートした後のページです。</span><span class="sxs-lookup"><span data-stu-id="89147-134">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="89147-135">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="89147-135">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="89147-136">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="89147-136">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="89147-137">次に、ファイルを使用してバインド情報をインポートするときはトランスポートのプロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89147-137">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="89147-138">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="89147-138">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="89147-139">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89147-139">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89147-140">.Msi ファイルをインポートするときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise アダプターのいずれかのバインド情報を含むアプリケーションをインポート エラー メッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89147-140">When importing an .msi file into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="89147-141">サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[ http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us)です。</span><span class="sxs-lookup"><span data-stu-id="89147-141">A supported hotfix is available from Microsoft along with a full description of the error at [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).</span></span>  
  
### <a name="work-around-the-password-limitation"></a><span data-ttu-id="89147-142">パスワードの制限を回避するには</span><span class="sxs-lookup"><span data-stu-id="89147-142">Work around the password limitation</span></span>  

<span data-ttu-id="89147-143">**オプション 1**</span><span class="sxs-lookup"><span data-stu-id="89147-143">**Option 1**</span></span>  

- <span data-ttu-id="89147-144">インポートする前に、アスタリスクをプレーン テキストで置き換えることによって、バインド ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="89147-144">Before you import, update the binding file by replacing the asterisks with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="89147-145">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="89147-145">This is not recommended for security reasons.</span></span>  
  
- <span data-ttu-id="89147-146">インポートする前を無効な値 (つまり、正しくないパスワード)、アスタリスクを置き換えることで、バインド ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="89147-146">Before you import, update the binding file by replacing the asterisks with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="89147-147">インポートした後を使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="89147-147">After you import, enter the correct password using the **Transport Properties**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="89147-148">この対処する場合のみ使用できます、ターゲット コンピューター上またはカスタム ツールを開発することにより、Microsoft Visual Studio がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="89147-148">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
<span data-ttu-id="89147-149">**オプション 2**</span><span class="sxs-lookup"><span data-stu-id="89147-149">**Option 2**</span></span>  
  
1.  <span data-ttu-id="89147-150">パスワードではなく、エンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="89147-150">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="89147-151">SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。</span><span class="sxs-lookup"><span data-stu-id="89147-151">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="89147-152">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="89147-152">Verify the Logical system and the Transmit and Receive services.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="89147-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="89147-153">Next steps</span></span>
[<span data-ttu-id="89147-154">BizTalk Server 例外処理を使用して、オーケストレーションで</span><span class="sxs-lookup"><span data-stu-id="89147-154">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling1.md)
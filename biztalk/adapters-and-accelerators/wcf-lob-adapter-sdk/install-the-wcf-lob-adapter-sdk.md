---
title: WCF LOB Adapter SDK のインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41b9b34b-3fbb-480f-a335-a218eab33693
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95fba9830bd97dd619cd16d18c0363a4525d1397
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999707"
---
# <a name="install-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="7fbb7-102">WCF LOB Adapter SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-102">Install the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="7fbb7-103">インストールし、構成、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-103">Install and configure the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> 

## <a name="requirements"></a><span data-ttu-id="7fbb7-104">要件</span><span class="sxs-lookup"><span data-stu-id="7fbb7-104">Requirements</span></span> 
<span data-ttu-id="7fbb7-105">次のコンポーネントをインストールするシステムをインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-105">Install following components on the system where you install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> 

> [!NOTE]
> <span data-ttu-id="7fbb7-106">**サポートされているバージョンの一覧については**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-106">**For a list of the supported versions**, see:</span></span> 
> 
> [<span data-ttu-id="7fbb7-107">BizTalk Server 2016 のハードウェア/ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="7fbb7-107">Hardware and Software Requirements for BizTalk Server 2016</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
> [<span data-ttu-id="7fbb7-108">BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="7fbb7-108">Hardware and Software Requirements for BizTalk Server 2013 and 2013 R2</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)

|                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                         <span data-ttu-id="7fbb7-109">Windows</span><span class="sxs-lookup"><span data-stu-id="7fbb7-109">Windows</span></span>                                          | <span data-ttu-id="7fbb7-110">x86 または x64</span><span class="sxs-lookup"><span data-stu-id="7fbb7-110">x86 or x64</span></span> <br/><br/><span data-ttu-id="7fbb7-111">必要な OS リソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-111">Required OS resources include:</span></span><br/> <ul><li><span data-ttu-id="7fbb7-112">OleTx トランザクションをサポートするために必要な Microsoft 分散トランザクション コーディネーター (MSDTC)。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-112">Microsoft Distributed Transaction Coordinator (MSDTC) : Required to support OleTx transactions</span></span></li><li><span data-ttu-id="7fbb7-113">信頼性の高いメッセージングをサポートするために必要なメッセージ キュー (MSMQ)。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-113">Message Queuing (MSMQ) : Required to support reliable messaging</span></span></li><li><span data-ttu-id="7fbb7-114">IIS でアプリケーションをホストするかどうかに必要なインターネット インフォメーション サービス (IIS)。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-114">Internet Information Services (IIS) : Required if you want to host your application in IIS</span></span></li><li><span data-ttu-id="7fbb7-115">WAS でアプリケーションをホストするかどうかに必要な Windows プロセス アクティブ化サービス (WAS)。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-115">Windows Process Activation Service (WAS) : Required if you want to host your application in WAS</span></span></li></ul> |
|                             <span data-ttu-id="7fbb7-116">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="7fbb7-116">Windows Communication Foundation</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|        [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]        |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|       [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]       |                                                                                                                                     <span data-ttu-id="7fbb7-117">カスタム アダプターを構築しているかどうか、またはで構築された、アダプターを使用するソリューションの開発に必要な[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-117">Required if you are building custom adapters, or developing solutions that use the adapters built with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>                                                                                                                                      |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] |                                                                                                                                                                 <span data-ttu-id="7fbb7-118">アダプターを使用するかどうかに必要な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-118">Required if you use the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>                                                                                                                                                                 |

## <a name="install"></a><span data-ttu-id="7fbb7-119">インストール</span><span class="sxs-lookup"><span data-stu-id="7fbb7-119">Install</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="7fbb7-120">Visual Studio のすべてのインスタンスを閉じる</span><span class="sxs-lookup"><span data-stu-id="7fbb7-120">Close all instances of Visual Studio</span></span>
> * <span data-ttu-id="7fbb7-121">**完了**セットアップは、BizTalk Server がコンピューターにインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-121">To do a **Complete** setup, confirm that BizTalk Server is installed on the computer.</span></span>  

1. <span data-ttu-id="7fbb7-122">実行、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe**管理者として。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-122">Run the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe** as Administrator.</span></span>

2. <span data-ttu-id="7fbb7-123">選択**インストール Microsoft BizTalk Adapters**、し、 **Microsoft WCF LOB アダプター SDK のインストール**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-123">Select **Install Microsoft BizTalk Adapters**, and then select **Install Microsoft WCF LOB Adapter SDK**.</span></span>  

3. <span data-ttu-id="7fbb7-124">**ようこそ**画面で、**次**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-124">On the **Welcome** screen, select **Next**.</span></span>  

4. <span data-ttu-id="7fbb7-125">ライセンス契約に同意して、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-125">Accept the license agreement, and select **Next**.</span></span>  

5. <span data-ttu-id="7fbb7-126">**セットアップの種類の選択**インストールの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-126">In **Choose Setup Type**, select the type of installation:</span></span>  

   -   <span data-ttu-id="7fbb7-127">共通の実行時とツールをインストールする選択**標準**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-127">To install the common run time and tools, select **Typical**.</span></span>  

   -   <span data-ttu-id="7fbb7-128">インストールとインストール場所にする機能を選択するには、次のように選択します。**カスタム**、しをインストールする機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-128">To select the features that you want to install and the installation location, select **Custom**, and then select the features you want to install.</span></span>  

   -   <span data-ttu-id="7fbb7-129">すべての機能をインストールする選択**完了**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-129">To install all the features, select **Complete**.</span></span>  

6. <span data-ttu-id="7fbb7-130">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-130">Select **Install**.</span></span>  

## <a name="update-or-remove"></a><span data-ttu-id="7fbb7-131">更新または削除します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-131">Update or remove</span></span>

1. <span data-ttu-id="7fbb7-132">開いている**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-132">Open **Programs and Feature**.</span></span> 

2. <span data-ttu-id="7fbb7-133">一覧で、次のように選択します。 **Windows Communication Foundation LOB Adapter SDK**、し、**変更**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-133">In the list, select **Windows Communication Foundation LOB Adapter SDK**, and then select **Change**.</span></span>  

3. <span data-ttu-id="7fbb7-134">**ようこそ**画面で、**次**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-134">On the **Welcome** screen, select **Next**.</span></span>  

4. <span data-ttu-id="7fbb7-135">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-135">Do one of the following:</span></span>  

   - <span data-ttu-id="7fbb7-136">インストールするコンポーネントを選択する**変更**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-136">To select the components that you want to install, select **Change**.</span></span>  

   - <span data-ttu-id="7fbb7-137">最新のインストールのエラーを修復するには、選択**修復**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-137">To repair errors in the most recent installation, select **Repair**.</span></span>  

   - <span data-ttu-id="7fbb7-138">削除する、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、コンピューターから次のように選択します。**削除**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-138">To remove the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] from the computer, select **Remove**.</span></span>  

5. <span data-ttu-id="7fbb7-139">インストールを変更する場合。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-139">If you choose to modify the installation:</span></span>  

   1.  <span data-ttu-id="7fbb7-140">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-140">Select **Next**.</span></span>  

   2.  <span data-ttu-id="7fbb7-141">選択**変更**、し、**完了**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-141">Select **Change**, and then select **Finish**.</span></span>  

6. <span data-ttu-id="7fbb7-142">インストールを修復する場合、 **WCF LOB Adapter SDK の修復の準備完了**ダイアログ ボックスで、**修復**、し、**完了**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-142">If you choose to repair the installation, in the **Ready to repair WCF LOB Adapter SDK** dialog box, select **Repair**, and then select **Finish**.</span></span>  

7. <span data-ttu-id="7fbb7-143">アダプターを削除する場合、 **WCF LOB Adapter SDK を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-143">If you choose to remove the adapters, in the **Ready to remove WCF LOB Adapter SDK** dialog box, select **Remove**, and then select **Finish**.</span></span>  


#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="7fbb7-144">WCF LOB Adapter SDK をアンインストールした後にカスタム アダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-144">Remove custom adapters after uninstalling the WCF LOB Adapter SDK</span></span>  

 <span data-ttu-id="7fbb7-145">使用して、カスタム アダプターを開発した場合、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、これらのアダプターをコンピューターに登録されているとは、次の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-145">If you have developed any custom adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and you have registered these adapters on your computer, you must also complete the following procedure.</span></span>  

1.  <span data-ttu-id="7fbb7-146">グローバル アセンブリ キャッシュ (GAC) から、カスタム アダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-146">Remove the custom adapter from the global assembly cache (GAC).</span></span>  

    1.  <span data-ttu-id="7fbb7-147">開く、 **Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-147">Open a **Visual Studio command prompt**.</span></span>  

    2.  <span data-ttu-id="7fbb7-148">カスタムの削除**アダプター .dll**を使用して、GAC から**コマンド gacutil/u**します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-148">Remove the custom **adapter .dll** from the GAC using **command gacutil /u**.</span></span>  

2.  <span data-ttu-id="7fbb7-149">Machine.config からアダプターのカスタム バインディングへの参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-149">Remove the references to the custom adapter binding from machine.config</span></span>  

    1.  <span data-ttu-id="7fbb7-150">Machine.config ファイルに移動して\<*システム ドライブ*\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-150">Go to the machine.config file under \<*system drive*\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

    2.  <span data-ttu-id="7fbb7-151">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-151">Open the file by using a text editor.</span></span>  

    3.  <span data-ttu-id="7fbb7-152">要素の bindingExtensions、クライアントおよび bindingElementExtensions system.serviceModel\extensions 下を検索します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-152">Search for the element bindingExtensions, client and bindingElementExtensions under system.serviceModel\extensions.</span></span>  

    4.  <span data-ttu-id="7fbb7-153">カスタム アダプターに関連する WCF バインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-153">Remove the WCF binding that pertains to your custom adapter.</span></span>  

## <a name="do-a-silent-installation"></a><span data-ttu-id="7fbb7-154">サイレント インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-154">Do a silent installation</span></span>  
 <span data-ttu-id="7fbb7-155">サイレント インストールでは、テスト シナリオや大規模なエンタープライズ展開の一部として最適です。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-155">A silent installation is ideal for test scenarios or as part of a large-scale enterprise deployment.</span></span> [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<span data-ttu-id="7fbb7-156"> コマンド ライン パラメーターは、サイレント インストールを実行する AdapterFramework.msi で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-156"> provides command line parameters that you can use with AdapterFramework.msi to perform a silent installation.</span></span>  

> [!NOTE]
>  <span data-ttu-id="7fbb7-157">サイレント インストールを実行するには、コンピューターの管理者があります。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-157">To perform silent installation, you should be an Administrator on the computer.</span></span> 


1. <span data-ttu-id="7fbb7-158">管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-158">Open a command prompt as administrator.</span></span>  

2. <span data-ttu-id="7fbb7-159">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-159">Type the following:</span></span>

   ```  
   AdapterFramework.msi /quiet MUOPTIN=”Yes”  
   ```  

   <span data-ttu-id="7fbb7-160">AdapterFramework.msi と組み合わせて、次のコマンド ライン オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-160">Use the following command line options in conjunction with AdapterFramework.msi:</span></span>  

   * <span data-ttu-id="7fbb7-161">使用`/quiet`をインストールする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]サイレント モードでします。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-161">Use `/quiet` to install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] silently.</span></span>  

   * <span data-ttu-id="7fbb7-162">MUOPTIN を使用して、="Yes"&#124;"No"を指定する場合、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Microsoft Update と更新プログラムを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-162">Use MUOPTIN=”Yes”&#124;”No” to indicate if the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] should check for updates with Microsoft Update.</span></span>  

       <span data-ttu-id="7fbb7-163">[はい] に設定すると[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]で Microsoft Update の更新プログラムを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-163">When set to Yes, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] checks for updates through Microsoft Update.</span></span> <span data-ttu-id="7fbb7-164">設定するとまったく[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]Microsoft Update による更新プログラムをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-164">When set to no [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not check for updates with Microsoft Update.</span></span>  

> [!NOTE]
>  <span data-ttu-id="7fbb7-165">コマンド ライン インストールの追加オプションを表示するには、次のように入力します。`AdapterFramework.msi /?`コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="7fbb7-165">To display additional options for command line installation, type `AdapterFramework.msi /?`at the command prompt.</span></span>  


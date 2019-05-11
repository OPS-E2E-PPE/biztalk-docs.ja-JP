---
title: 構成 FileAct および InterAct アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d3876ff-e8e4-47f4-9ca8-d4dad419ed67
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa2cb8756ce5d00109fbb17d042f43ec4a782b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367284"
---
# <a name="configure-the-fileact-and-interact-adapter"></a><span data-ttu-id="e7a6a-102">構成 FileAct および InterAct アダプター</span><span class="sxs-lookup"><span data-stu-id="e7a6a-102">Configure the FileAct and InterAct Adapter</span></span>
<span data-ttu-id="e7a6a-103">使用されるさまざまな成果物を構成、[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]ランタイム。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-103">Configure the different artifacts used by the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] runtime.</span></span> 

  
## <a name="prerequisites"></a><span data-ttu-id="e7a6a-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="e7a6a-104">Prerequisites</span></span>  
   
- <span data-ttu-id="e7a6a-105">インストールします [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7a6a-105">Install the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]</span></span>
  
- <span data-ttu-id="e7a6a-106">メンバーとしてサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループ</span><span class="sxs-lookup"><span data-stu-id="e7a6a-106">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group</span></span>
  
- <span data-ttu-id="e7a6a-107">SQL Server が実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-107">Confirm SQL Server is running</span></span>
  
## <a name="step-1-configure-the-fileact-and-interact-adapter"></a><span data-ttu-id="e7a6a-108">手順 1:FileAct および InterAct アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-108">Step 1: Configure the FileAct and InterAct adapter</span></span>  
  
1.  <span data-ttu-id="e7a6a-109">**Microsoft BizTalk FileAct と対話するアダプターの構成**ウィザードに移動して**概要**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-109">In the **Microsoft BizTalk FileAct and InterAct Adapter Configuration** wizard, go to **Overview**.</span></span> <span data-ttu-id="e7a6a-110">左側のウィンドウで次のように選択します。**ランタイム**アダプターのランタイム コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-110">In the left pane, select **Runtime** to configure the runtime components of the adapters.</span></span>  
  
2.  <span data-ttu-id="e7a6a-111">**のランタイム構成** **アカウント**COM + ストア アンド フォワード モードの構成を入力する省略記号 [...] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-111">In **Runtime Configuration**, under **Account**, select the ellipsis […] to enter the COM plus configuration for the Store and Forward mode.</span></span>  
  
3.  <span data-ttu-id="e7a6a-112">**ユーザーの資格情報**、ユーザー名を入力します (で、 *domain \user name*形式) と COM + の構成で使用するアカウントのパスワード。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-112">In **User Credentials**, enter the user name (in the *domain\user name* format) and password for the account used in the COM plus configuration.</span></span> <span data-ttu-id="e7a6a-113">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-113">Select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7a6a-114">A**ユーザーの資格情報**入力したアカウントに推奨されるよりも高い特権がある場合に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-114">A **User Credentials** warning appears if the account you entered has higher privileges than are recommended.</span></span> <span data-ttu-id="e7a6a-115">選択**はい**を続行します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-115">Select **Yes** to continue.</span></span>
  
4.  <span data-ttu-id="e7a6a-116">選択**構成の適用**FileAct と対話するアダプターに COM + 構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-116">Select **Apply configuration** to apply the COM plus configuration to the FileAct and InterAct Adapter.</span></span>  
  
5.  <span data-ttu-id="e7a6a-117">**概要**、レビュー、および選択**次**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-117">In the **Summary**, review, and select **Next**.</span></span>  
  
6.  <span data-ttu-id="e7a6a-118">構成が完了したら、コンポーネントの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-118">When the configuration completes, review the list of components.</span></span> <span data-ttu-id="e7a6a-119">チェック マークは、コンポーネントが正常に構成されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-119">A check mark means that the component is configured successfully.</span></span> <span data-ttu-id="e7a6a-120">"X"は、そのコンポーネントに問題があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-120">An "X" means that there is a problem with that component.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7a6a-121">使用して、 **Logfile**構成イベントを表示するリンク。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-121">Use the **Logfile** link to view the configuration events.</span></span>  
  
7.  <span data-ttu-id="e7a6a-122">選択**完了**構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-122">Select **Finish** to complete the configuration.</span></span> <span data-ttu-id="e7a6a-123">**概要**ランタイム コンポーネントの現在の構成状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-123">The **Overview** shows the current configuration status for the Runtime components.</span></span>  

<span data-ttu-id="e7a6a-124">次に、これらのアダプターを実行するには、ホストとホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-124">Next, create the host and host instances to run these adapters.</span></span>

## <a name="step-2-create-the-host-and-host-instances"></a><span data-ttu-id="e7a6a-125">手順 2:ホストとホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-125">Step 2: Create the host and host instances</span></span>

<span data-ttu-id="e7a6a-126">FileAct アダプターの専用ホストと InterAct アダプターの個別の専用ホストを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-126">We recommend that you create a dedicated host for the FileAct adapter and a separate dedicated host for the InterAct adapter.</span></span> <span data-ttu-id="e7a6a-127">アダプターごとに少なくとも 1 つのホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-127">For each adapter, create at least one host instance.</span></span>  

<span data-ttu-id="e7a6a-128">[BizTalk ホストとホスト インスタンスを管理する](../../core/managing-biztalk-hosts-and-host-instances.md)ホストとホスト インスタンスを作成する手順を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-128">[Managing BizTalk Hosts and Host Instances](../../core/managing-biztalk-hosts-and-host-instances.md) list the steps to create hosts and host instances.</span></span> 

<span data-ttu-id="e7a6a-129">作成されたら、次の手順は、送信ハンドラーを追加し、SWIFT Alliance ゲートウェイ (SAG) で作成したクライアントのメッセージのパートナーを使用するがします。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-129">Once created, the next step is to add the send handler, and use the Client Message Partner you created in the SWIFT Alliance Gateway (SAG).</span></span>

## <a name="step-3-create-the-send-handler"></a><span data-ttu-id="e7a6a-130">手順 3:送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-130">Step 3: Create the send handler</span></span>

<span data-ttu-id="e7a6a-131">FileAct および InterAct ハンドラーのプロパティとして送信、送信ポートの構成値、個々 の FileAct プロパティが設定されていないか InterAct 送信ポートします。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-131">You use the FileAct and InterAct send handler properties as the send port configuration values, if the properties are not set on the individual FileAct or InterAct send port.</span></span> 
  
1. <span data-ttu-id="e7a6a-132">**BizTalk Server 管理**コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-132">In the **BizTalk Server Administration** console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2. <span data-ttu-id="e7a6a-133">選択、 **FileAct**または**InterAct**アダプター。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-133">Select the **FileAct** or **InterAct** adapter.</span></span> <span data-ttu-id="e7a6a-134">右側のウィンドウで、送信ハンドラをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-134">In the right pane, double-click the send handler.</span></span>  
  
3. <span data-ttu-id="e7a6a-135">**ホスト名**ドロップダウン リストで、前のセクションで作成したホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-135">In the **Host name** drop-down list, select the host you created in the previous section.</span></span> <span data-ttu-id="e7a6a-136">選び**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-136">Then select **Properties**.</span></span>  
  
4. <span data-ttu-id="e7a6a-137">**トランスポートのプロパティ**を選択、**引数**プロパティとしては、次の引数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-137">In the **Transport Properties**, select the **Argument** property, and enter the following argument as:</span></span>  
  
    `-SagMessagePartner <Client Message Partner created in SAG\>`
  
   > [!NOTE]
   >  <span data-ttu-id="e7a6a-138">置換 <`Client Message Partner created in SAG`> クライアント メッセージのパートナーの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-138">Replace <`Client Message Partner created in SAG`> with the name of the client message partner.</span></span> <span data-ttu-id="e7a6a-139">暗号モード、FACrypto モード、およびしプロパティの既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-139">Leave the default values for the Crypto Mode, FACrypto Mode, and LogMessages properties.</span></span>  
  
5. <span data-ttu-id="e7a6a-140">選択 **[ok]** 変更を保存し、[プロパティ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-140">Select **OK** to save your changes, and then to close the properties window.</span></span> 
  
6. <span data-ttu-id="e7a6a-141">**プラットフォームの設定**、**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-141">Under **Platform Settings**, select **Host Instances**.</span></span>  
  
7. <span data-ttu-id="e7a6a-142">ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-142">Restart the host instances:</span></span> 

   - <span data-ttu-id="e7a6a-143">FileAct のホスト インスタンスを右クリックし、**再起動**</span><span class="sxs-lookup"><span data-stu-id="e7a6a-143">Right-click the FileAct host instance, and **Restart**</span></span>
   - <span data-ttu-id="e7a6a-144">InterAct のホスト インスタンスを右クリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-144">Right-click the InterAct host instance, and **Restart**.</span></span>  

<span data-ttu-id="e7a6a-145">次に、SWIFTNet に paramfile に FileAct を有効にする、サーバー メッセージ パートナーを入力し、InterAct アダプターの受信します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-145">Next, enter the server message partners in the SWIFTNet paramfile to enable the FileAct and InterAct receive adapters.</span></span>
  
## <a name="step-4-configure-the-swiftnet-param-file"></a><span data-ttu-id="e7a6a-146">手順 4:SWIFTNet param ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-146">Step 4: Configure the SWIFTNet param file</span></span>

<span data-ttu-id="e7a6a-147">有効にするには、FileAct および InterAct アダプターは SWIFTNet に paramfile に入力する必要があります SAG で作成したパートナー サーバーのメッセージの値で初期化するためを受信します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-147">To enable the FileAct and InterAct receive adapters to initialize with the values, the Server message partners created in SAG must be entered in the SWIFTNet paramfile.</span></span> <span data-ttu-id="e7a6a-148">Paramfile に通常格納されて`c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-148">The paramfile is typically located in `c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`.</span></span> <span data-ttu-id="e7a6a-149">開始する前に paramfile を構成する**SnlReceiver.exe**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-149">After you configure the paramfile, start **SnlReceiver.exe**.</span></span>  
  
1. <span data-ttu-id="e7a6a-150">開く、 **SWIFTNet に paramfile**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-150">Open the **SWIFTNet paramfile**.</span></span> <span data-ttu-id="e7a6a-151">マークされた場所に"\*\*\*"、以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-151">In the location marked with "\*\*\*" add the following.</span></span> <span data-ttu-id="e7a6a-152">なお、`AdapterType`値を指定できます`Interact`または`Fileact`します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-152">Note that the `AdapterType` value can be `Interact` or `Fileact`.</span></span>  
  
     ```spawn "snlreceiver -SagMessagePartner <Server MessagePartnerName\> -AdapterMode <AdapterType\>"```  
       
  
   ```  
    username:snlowner  
    subsystem_name:SampleSubsystem  
    #subsystem_group: SampleSubsystem  
    #subsystem_dependency:Support,Swarm  
    subsystem_nature:critical  
    subsystem_start:  
    ***  
    *END  
    subsystem_stop:  
    *KILL9:snlreceiver  
    *END  
    subsystem_status:  
    *NB:1:snlreceiver  
    *END  
    start_event:SNL001:subsystem SampleSubsystem is up  
    stop_event:SNL002:subsystem SampleSubsystem is down  
   ```  
  
> [!NOTE]
>  <span data-ttu-id="e7a6a-153">SNLreceiver を開始する前に、受信ポートを有効にする (FileAct または対話) を使用するアダプター。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-153">Before you start SNLreceiver, enable the receive ports for the adapter you are using (FileAct or InterAct).</span></span>  
  
2. <span data-ttu-id="e7a6a-154">開始および停止 SnlReceiver.exe:</span><span class="sxs-lookup"><span data-stu-id="e7a6a-154">Start and stop SnlReceiver.exe:</span></span>

    1.  <span data-ttu-id="e7a6a-155">デスクトップで、選択、**リモート API**リモート API のコマンド プロンプトを開くにはアイコン。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-155">On the desktop, select the **Remote API** icon to open the Remote API command prompt.</span></span>  
  
    2.  <span data-ttu-id="e7a6a-156">コマンド プロンプトで、「`Swiftnet start`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-156">At the command prompt, type `Swiftnet start`.</span></span> <span data-ttu-id="e7a6a-157">SnlReceiver.exe を開始するには ENTER を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-157">Select ENTER to start SnlReceiver.exe.</span></span>  
  
    3.  <span data-ttu-id="e7a6a-158">コマンド プロンプトで、「`Swiftnet stop`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-158">At the command prompt, type `Swiftnet stop`.</span></span> <span data-ttu-id="e7a6a-159">SnlReceiver.exe を停止するには ENTER を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-159">Select ENTER to stop SnlReceiver.exe.</span></span>  

  
<span data-ttu-id="e7a6a-160">次に、ファイルを更新**autoexec.bat** SWIFT 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-160">Next, update the file **autoexec.bat** to set the SWIFT environment variables.</span></span>

## <a name="step-5-update-autoexecbat-to-configure-the-receive-adapters"></a><span data-ttu-id="e7a6a-161">手順 5:受信アダプターを構成する更新プログラムの autoexec.bat です。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-161">Step 5: Update autoexec.bat to configure the receive adapters</span></span>

<span data-ttu-id="e7a6a-162">更新プログラム、 **autoexec.bat**をインストールしたコンピューターで、SWIFT 環境変数を設定するファイル、[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-162">Update the **autoexec.bat** file to set the SWIFT environment variables on the computer where you installed the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] receive adapters.</span></span> <span data-ttu-id="e7a6a-163">環境変数は、パスにインストールされている受信アダプターがあるシステムから生成される`c:\SWIFTAlliance`という名前の受信アダプターのインスタンスと**Ra1**します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-163">The environment variables are generated from the system that has the receive adapter installed in the path `c:\SWIFTAlliance` with an instance of the receive adapter named **Ra1**.</span></span> <span data-ttu-id="e7a6a-164">適切に構成の SWIFT 環境変数を更新します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-164">Update the SWIFT environment variables appropriately for your configuration.</span></span>  
  
 <span data-ttu-id="e7a6a-165">Autoexe.bat ファイルのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-165">The following is a sample of the autoexe.bat file:</span></span>
  
```  
SET COMPUTERNAME=<Machine Name>  
SET GENLOG_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET GENUTIL_DIR=C:\SWIFTAlliance\RA\bin  
SET HOMEDRIVE=C:  
SET LOGONSERVER=\\SERVERNAME  
SET OSA_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET OSA_INSTANCE=Ra1  
SET PKIEXECDIR=C:\SWIFTAlliance\RA  
SET SAGRA_HOME=C:\SWIFTAlliance\RA  
SET SESSIONNAME=RDP-Tcp#1  
SET SLP_ENV=DEFAULT  
SET SLP_FILE=server.slp  
SET SNL_DOMAIN_NAME=Ra1  
SET SPK_DATA_DIR=C:\SWIFTAlliance\RA\data\pki  
SET SWNET_BIN_PATH=C:\SWIFTAlliance\RA\Ra1\bin  
SET SWNET_CFG_PATH=C:\SWIFTAlliance\RA\Ra1\cfg  
SET SWNET_HOME=C:\SWIFTAlliance\RA  
SET SWNET_HOST=HOSTNAME  
SET SWNET_INST=Ra1  
SET SWNET_LOG_PATH=C:\SWIFTAlliance\RA\Ra1\log  
SET SWNET_SLP_PATH=C:\SWIFTAlliance\RA\data\  
SET SWNET_VERSION=5.0.20  
SET SWTRACE=C:\SWIFTAlliance\RA\Ra1\log  
SET Path=%PATH%;C:\SWIFTAlliance\RA\bin  
SET Path=%PATH%;C:\SWIFTAlliance\RA\lib  
  
```  
  
## <a name="see-some-examples"></a><span data-ttu-id="e7a6a-166">いくつかの例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-166">See some examples</span></span>
<span data-ttu-id="e7a6a-167">FileAct および InterAct メッセージの例については、次を参照してください。[サンプルを操作および FileAct メッセージ](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7a6a-167">For examples of FileAct and InterAct messages, see [Sample InterAct and FileAct Messages](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a6a-168">参照</span><span class="sxs-lookup"><span data-stu-id="e7a6a-168">See Also</span></span>  

[<span data-ttu-id="e7a6a-169">FileAct および InterAct アダプターをインストールする</span><span class="sxs-lookup"><span data-stu-id="e7a6a-169">Install the FileAct and InterAct Adapter</span></span>](../../adapters-and-accelerators/fileact-interact/install-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="e7a6a-170">FileAct および InterAct アダプターをアンインストールまたは修復する</span><span class="sxs-lookup"><span data-stu-id="e7a6a-170">Uninstall or repair the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="e7a6a-171">インストールに関する既知の問題の確認</span><span class="sxs-lookup"><span data-stu-id="e7a6a-171">Read the installation known issues</span></span>](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)

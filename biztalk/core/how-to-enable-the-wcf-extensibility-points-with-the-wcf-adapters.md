---
title: "WCF アダプターで WCF 機能拡張ポイントを有効にする |Microsoft ドキュメント"
description: "アセンブリをインストールし、machine.config の構成、拡張 BizTalk 管理者を追加作成する受信場所で BizTalk Server で WCF アダプターの WCF 機能拡張ポイントを有効にするには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c2af105-5272-4a6a-95d2-066312ab788e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2881ddd83ebeb31a9f5ff3da6ed858f158751d64
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters"></a><span data-ttu-id="68708-103">WCF アダプターを使用して WCF 機能拡張ポイントを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="68708-103">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>
<span data-ttu-id="68708-104">次の 3 つの WCF 機能拡張ポイントを有効にする — 動作拡張機能、バインド要素の拡張機能、およびバインド拡張機能: Wcf-custom および Wcf-customisolated アダプタを使用しています。</span><span class="sxs-lookup"><span data-stu-id="68708-104">Enable three WCF extensibility points—behavior extension, binding element extension, and binding extension—with the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="68708-105">これを行うには、まず WCF 機能拡張ポイントを実装するアセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールし、コンピューターの machine.config ファイルを変更した後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して WCF-Custom アダプターまたは WCF-CustomIsolated アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-105">To do so, you first install the assemblies implementing the WCF extensibility points in the global assembly cache (GAC), then modify the machine.config file on your computers, and then configure the WCF-Custom or the WCF-CustomIsolated adapter by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
<span data-ttu-id="68708-106">参照してください[WCF の拡張](https://docs.microsoft.com/dotnet/framework/wcf/extending/extending-wcf)の詳細については、WCF 機能拡張ポイントです。</span><span class="sxs-lookup"><span data-stu-id="68708-106">See [Extending WCF](https://docs.microsoft.com/dotnet/framework/wcf/extending/extending-wcf) for more info on WCF extensibility points.</span></span>
  
 
## <a name="prerequisites"></a><span data-ttu-id="68708-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="68708-107">Prerequisites</span></span>  
<span data-ttu-id="68708-108">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="68708-108">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="68708-109">[展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)詳細な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="68708-109">[Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md) provides more info.</span></span>  
  
## <a name="install-assemblies-implementing-a-wcf-extensibility-point-in-the-gac"></a><span data-ttu-id="68708-110">GAC に WCF 機能拡張ポイントを実装するアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="68708-110">Install assemblies implementing a WCF extensibility point in the GAC</span></span>  
  
1.  <span data-ttu-id="68708-111">WCF 機能拡張ポイントを実装するアセンブリを、ローカル コンピューター上のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="68708-111">Copy the assemblies implementing the WCF extensibility point to a folder on your local computer.</span></span>  
  
2.  <span data-ttu-id="68708-112">WCF 機能拡張ポイントが使用するアセンブリがある場合、そのアセンブリをローカル コンピューター上のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="68708-112">Copy the assemblies that the WCF extensibility point uses, if any, to a folder on your local computer.</span></span>  
  
3.  <span data-ttu-id="68708-113">開始、 **Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="68708-113">Start the **Visual Studio Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="68708-114">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="68708-114">Type the following command:</span></span>  
  
     <span data-ttu-id="68708-115">**gacutil.exe/if"\<**  *アセンブリ .dll ファイルのパスを*  **\>"**</span><span class="sxs-lookup"><span data-stu-id="68708-115">**gacutil.exe /if "\<** *path to the assembly .dll file* **\>"**</span></span>  
  
5.  <span data-ttu-id="68708-116">これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="68708-116">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
6.  <span data-ttu-id="68708-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトで、手順 1. と 2. でコピーしたすべてのアセンブリについて手順 4. と 5. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="68708-117">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, repeat steps 4 and 5 against all the assemblies you copied in steps 1 and 2 of this procedure.</span></span>  
  
7.  <span data-ttu-id="68708-118">複数ある場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターと管理コンピューターは、すべてのコンピューターに 1 ~ 6 のこの手順を手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="68708-118">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 6 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68708-119">WCF アダプターの WCF 機能拡張ポイントを有効にするには、アダプターを実行している BizTalk ホスト インスタンスが、WCF 機能拡張ポイントが実装されているアセンブリを実行時に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="68708-119">To enable WCF extensibility points for the WCF adapters, the BizTalk Host instance running the adapter must be able to load at run time the assemblies where the WCF extensibility points are implemented.</span></span>  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-extension"></a><span data-ttu-id="68708-120">WCF バインド拡張機能の machine.config ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-120">Configure the machine.config file for a WCF binding extension</span></span>  
  
1.  <span data-ttu-id="68708-121">コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。</span><span class="sxs-lookup"><span data-stu-id="68708-121">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="68708-122">メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel\>\\< 拡張\>**要素内にその要素の追加、  **\<構成\>** 、machine.config の要素ファイル、および追加し、  **\<bindingExtensions\>** 内の WCF バインド拡張機能要素 **\<system.serverModel\>\\< 拡張\>**要素。</span><span class="sxs-lookup"><span data-stu-id="68708-122">In Notepad, if the machine.config file does not have the **\<system.serverModel\>\\<extensions\>** elements, add those elements inside the **\<configuration\>** element of the machine.config file, and then add the **\<bindingExtensions\>** element for a WCF binding extension inside the **\<system.serverModel\>\\<extensions\>** elements.</span></span> <span data-ttu-id="68708-123">たとえば、netHttpBinding、カスタム バインド拡張機能を有効にする次のコードを追加、 **\<構成\>** machine.config ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="68708-123">For example, to enable a custom binding extension, netHttpBinding, add the following code inside the **\<configuration\>** element of the machine.config file:</span></span>  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <bindingExtensions>  
          <add name="netHttpBinding" type="Microsoft.Samples.Channels.NetHttpBindingCollectionElement, NetHttpBinding, Version=3.0.0.0, Culture=neutral, PublicKeyToken=5b637b51c4aaa2a8" />  
        </bindingExtensions>        
      </extensions>  
    </system.serviceModel>  
    ```  
  
    > [!NOTE]
    >  - <span data-ttu-id="68708-124">コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。</span><span class="sxs-lookup"><span data-stu-id="68708-124">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
    >  - <span data-ttu-id="68708-125">参照してください[bindingExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingextensions)この要素上です。</span><span class="sxs-lookup"><span data-stu-id="68708-125">See [bindingExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingextensions) on this element.</span></span>
  
3.  <span data-ttu-id="68708-126">メモ帳で、machine.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="68708-126">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="68708-127">複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="68708-127">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68708-128">BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="68708-128">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="configure-a-wcf-binding-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="68708-129">BizTalk 管理コンソールを使用して WCF バインド拡張機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-129">Configure a WCF binding extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="68708-130">開いている**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="68708-130">Open **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68708-131">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-131">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="68708-132">WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-132">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="68708-133">WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-133">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="68708-134">WCF 機能拡張ポイントを使用する受信場所を構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所\>*です。</span><span class="sxs-lookup"><span data-stu-id="68708-134">If you want to configure a receive location to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location\>*.</span></span>  
  
    -   <span data-ttu-id="68708-135">**受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。</span><span class="sxs-lookup"><span data-stu-id="68708-135">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="68708-136">WCF 機能拡張ポイントを使用する送信ポートを構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート\>*です。</span><span class="sxs-lookup"><span data-stu-id="68708-136">If you want to configure a send port to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port\>*.</span></span>  
  
    -   <span data-ttu-id="68708-137">**送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="68708-137">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="68708-138">トランスポートのプロパティ ダイアログ ボックスで、**バインディング** タブで、バインド拡張機能を選択し、他のトランスポートの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-138">In the transport properties dialog box, on the **Binding** tab, select the binding extension, and then configure the rest of the settings for the transport.</span></span>  
  
7.  <span data-ttu-id="68708-139">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="68708-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-element-extension"></a><span data-ttu-id="68708-140">WCF バインド要素拡張機能の machine.config ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-140">Configure the machine.config file for a WCF binding element extension</span></span>  
  
1.  <span data-ttu-id="68708-141">コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。</span><span class="sxs-lookup"><span data-stu-id="68708-141">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="68708-142">メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel\>\\< 拡張\>**要素内にその要素の追加、  **\<構成\>** 、machine.config の要素ファイル、および追加し、  **\<bindingElementExtensions\>**  WCF バインド要素の要素内に拡張機能、  **\<system.serverModel\>\\< 拡張\>**要素。</span><span class="sxs-lookup"><span data-stu-id="68708-142">In Notepad, if the machine.config file does not have the **\<system.serverModel\>\\<extensions\>** elements, add those elements inside the **\<configuration\>** element of the machine.config file, and then add the **\<bindingElementExtensions\>** element for a WCF binding element extension inside the **\<system.serverModel\>\\<extensions\>** elements.</span></span> <span data-ttu-id="68708-143">たとえば、droppingInterceptor、カスタム バインディング要素拡張を有効にする次のコードを追加、 **\<構成\>** machine.config ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="68708-143">For example, to enable a custom binding element extension, droppingInterceptor, add the following code inside the **\<configuration\>** element of the machine.config file:</span></span>  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <bindingElementExtensions>  
          <add name="droppingInterceptor" type="Microsoft.ServiceModel.Samples.DroppingServerElement, MessageInterceptor, Version=0.0.0.0, Culture=neutral, PublicKeyToken=098514eef14aa34a"/>  
        </bindingElementExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
    > [!NOTE]
    > - <span data-ttu-id="68708-144">コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。</span><span class="sxs-lookup"><span data-stu-id="68708-144">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
    > - <span data-ttu-id="68708-145">参照してください[bindingElementExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingelementextensions)この要素上です。</span><span class="sxs-lookup"><span data-stu-id="68708-145">See [bindingElementExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingelementextensions) on this element.</span></span>
  
3.  <span data-ttu-id="68708-146">メモ帳で、machine.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="68708-146">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="68708-147">複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="68708-147">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68708-148">BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="68708-148">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="configure-a-wcf-binding-element-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="68708-149">BizTalk 管理コンソールを使用して WCF バインド要素拡張機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-149">Configure a WCF binding element extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="68708-150">開いている**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="68708-150">Open **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68708-151">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-151">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="68708-152">WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-152">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="68708-153">WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-153">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="68708-154">WCF 機能拡張ポイントを使用する受信場所を構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所\>*です。</span><span class="sxs-lookup"><span data-stu-id="68708-154">If you want to configure a receive location to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location\>*.</span></span>  
  
    -   <span data-ttu-id="68708-155">**受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。</span><span class="sxs-lookup"><span data-stu-id="68708-155">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="68708-156">WCF 機能拡張ポイントを使用する送信ポートを構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート\>*です。</span><span class="sxs-lookup"><span data-stu-id="68708-156">If you want to configure a send port to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port\>*.</span></span>  
  
    -   <span data-ttu-id="68708-157">**送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="68708-157">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="68708-158">トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブの 、**バインディングの種類**ドロップダウン リストで、 **customBinding**です。</span><span class="sxs-lookup"><span data-stu-id="68708-158">In the transport properties dialog box, on the **Binding** tab, in the **Binding Type** drop-down list, select **customBinding**.</span></span>  
  
7.  <span data-ttu-id="68708-159">トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブでのクライアント領域を右クリックし、**バインド**一覧をクリックして**拡張機能を追加**です。</span><span class="sxs-lookup"><span data-stu-id="68708-159">In the transport properties dialog box, on the **Binding** tab, right-click the client area of the **Binding** list, and then click **Add extension**.</span></span>  
  
8.  <span data-ttu-id="68708-160">**バインディング要素拡張機能の選択**ダイアログ ボックスをバインディング要素拡張を選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="68708-160">In the **Select Binding Element Extension** dialog box, select a binding element extension, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="68708-161">トランスポートのプロパティ ダイアログ ボックスで、**バインディング** タブで追加されたバインド要素の順序を調整、**バインディング**で追加したバインド要素拡張の種類に応じて一覧、次のように前の手順:</span><span class="sxs-lookup"><span data-stu-id="68708-161">In the transport properties dialog box, on the **Binding** tab, adjust the order of the binding elements added in the **Binding** list depending on the type of the binding element extension you added in the previous step as follows:</span></span>  
  
    -   <span data-ttu-id="68708-162">**バインディング**ボックスの一覧をバインド要素拡張を右クリックし、をクリックして**拡張機能を上へ移動**または**拡張機能を下へ移動**です。</span><span class="sxs-lookup"><span data-stu-id="68708-162">In the **Binding** list, right-click a binding element extension, and then click **Move extension up** or **Move extension down**.</span></span> <span data-ttu-id="68708-163">最下位のバインド要素拡張機能、**バインディング**一覧は、チャネル スタックの一番下のコンポーネントに対応しています。</span><span class="sxs-lookup"><span data-stu-id="68708-163">The lowest binding element extension in the **Binding** list corresponds to the bottom component of the channel stack.</span></span> <span data-ttu-id="68708-164">内の最上位のバインド要素、**バインディング**一覧は、通信スタックの一番上のコンポーネントに対応しています。</span><span class="sxs-lookup"><span data-stu-id="68708-164">The highest binding element in the **Binding** list corresponds to the top component of the communication stack.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="68708-165">参照してください[カスタム バインド](https://docs.microsoft.com/dotnet/framework/wcf/extending/custom-bindings)詳細については、カスタム バインドのバインド要素の特定の順序に関するします。</span><span class="sxs-lookup"><span data-stu-id="68708-165">See [Custom Bindings](https://docs.microsoft.com/dotnet/framework/wcf/extending/custom-bindings) for details about the specific order of the binding elements for the custom binding.</span></span>
  
10. <span data-ttu-id="68708-166">トランスポートのプロパティ ダイアログ ボックスで、他のトランスポートの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-166">In the transport properties dialog box, configure the rest of the settings for the transport.</span></span>  
  
11. <span data-ttu-id="68708-167">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="68708-167">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-behavior-extension"></a><span data-ttu-id="68708-168">WCF 動作拡張機能の machine.config ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-168">Configure the machine.config file for a WCF behavior extension</span></span>  
  
1.  <span data-ttu-id="68708-169">コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。</span><span class="sxs-lookup"><span data-stu-id="68708-169">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="68708-170">メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel\>\\< 拡張\>**要素内にその要素の追加、  **\<構成\>** 、machine.config の要素ファイル、および追加し、  **\<behaviorExtensions\>**  WCF 動作拡張機能の要素内部、  **\<system.serverModel\>\\< 拡張\>**要素。</span><span class="sxs-lookup"><span data-stu-id="68708-170">In Notepad, if the machine.config file does not have the **\<system.serverModel\>\\<extensions\>** elements, add those elements inside the **\<configuration\>** element of the machine.config file, and then add the **\<behaviorExtensions\>** element for a WCF behavior extension inside the **\<system.serverModel\>\\<extensions\>** elements.</span></span> <span data-ttu-id="68708-171">たとえば、schemaValidator、カスタム動作拡張機能を有効にする次のコードを追加、 **\<構成\>** machine.config ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="68708-171">For example, To enable a custom behavior extension, schemaValidator, add the following code inside the **\<configuration\>** element of the machine.config file:</span></span>  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ad307e213604f592"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
    > [!NOTE]
    >  - <span data-ttu-id="68708-172">コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。</span><span class="sxs-lookup"><span data-stu-id="68708-172">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
    >  - <span data-ttu-id="68708-173">参照してください[behaviorExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/behaviorextensions)この要素上です。</span><span class="sxs-lookup"><span data-stu-id="68708-173">See [behaviorExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/behaviorextensions) on this element.</span></span>
  
3.  <span data-ttu-id="68708-174">メモ帳で、machine.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="68708-174">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="68708-175">複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="68708-175">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68708-176">BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="68708-176">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="configure-a-wcf-behavior-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="68708-177">BizTalk 管理コンソールを使用して WCF 動作拡張機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-177">Configure a WCF behavior extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="68708-178">開いている**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="68708-178">Open **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68708-179">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-179">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="68708-180">WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-180">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="68708-181">WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="68708-181">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="68708-182">BizTalk 管理コンソールで、WCF 機能拡張ポイントを使用して、展開の受信場所を構成する場合**BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所\>*です。</span><span class="sxs-lookup"><span data-stu-id="68708-182">If you want to configure a receive location to use a WCF extensibility point, in the BizTalk Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location\>*.</span></span>  
  
    -   <span data-ttu-id="68708-183">**受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。</span><span class="sxs-lookup"><span data-stu-id="68708-183">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="68708-184">BizTalk 管理コンソールで、WCF 機能拡張ポイントを使用して、展開する送信ポートを構成する場合**BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート\>*です。</span><span class="sxs-lookup"><span data-stu-id="68708-184">If you want to configure a send port to use a WCF extensibility point, in the BizTalk Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port\>*.</span></span>  
  
    -   <span data-ttu-id="68708-185">**送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="68708-185">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="68708-186">トランスポートのプロパティ ダイアログ ボックスで、**動作** タブを右クリックして**ServiceBehavior**または**endpointbehavior**動作拡張機能の種類に応じて、**動作拡張機能の選択**ダイアログ ボックスでは、動作拡張機能を選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="68708-186">In the transport properties dialog box, on the **Behavior** tab, right-click **ServiceBehavior** or **EndpointBehavior** depending on the type of the behavior extension, and then, in the **Select Behavior Extension** dialog box, select the behavior extension, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="68708-187">トランスポートのプロパティ ダイアログ ボックスで、他のトランスポートの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="68708-187">In the transport properties dialog box, configure the rest of the settings for the transport.</span></span>  
  
8.  <span data-ttu-id="68708-188">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="68708-188">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
## <a name="configure-a-wcf-custom-receive-location-with-an-ssl-certificate"></a><span data-ttu-id="68708-189">WCF カスタムを構成する SSL 証明書を使用して受信場所</span><span class="sxs-lookup"><span data-stu-id="68708-189">Configure a WCF-Custom receive location with an SSL certificate</span></span>  
  
-   <span data-ttu-id="68708-190">Wcf-custom 受信場所がなどを使用して HTTP カーネル モード ドライバー (HTTP.sys) が発生する場合、 **httpsTransport**通信用に Secure Sockets Layer (SSL)、受信場所のバインド要素は、証明書が必要各ソケット (IP アドレスとポートの組み合わせ) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="68708-190">If a WCF-Custom receive location happens to use the HTTP kernel-mode driver (HTTP.sys) such as the **httpsTransport** binding element, for Secure Sockets Layer (SSL) communications, the receive location must have a certificate registered for each socket (IP address/port combination).</span></span> <span data-ttu-id="68708-191">SSL 証明書をコンピューター上のポートにバインドするには、HttpCfg.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="68708-191">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the computer.</span></span> <span data-ttu-id="68708-192">詳細については、次を参照してください。[操作方法: SSL 証明書を使用するポートを構成](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate)です。</span><span class="sxs-lookup"><span data-stu-id="68708-192">For more information, see [How To: Configure a Port with An SSL Certificate](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate).</span></span>
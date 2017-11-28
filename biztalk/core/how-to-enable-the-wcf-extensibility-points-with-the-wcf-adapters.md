---
title: "WCF アダプターで WCF 機能拡張ポイントを有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, WCF adapters
- WCF adapters, extensibility ports
ms.assetid: 0c2af105-5272-4a6a-95d2-066312ab788e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e481521ba651fe8c1e66ea4f730d05375451f111
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters"></a><span data-ttu-id="a16c2-102">WCF アダプターを使用して WCF 機能拡張ポイントを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="a16c2-102">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>
<span data-ttu-id="a16c2-103">このトピックでは、WCF-Custom アダプタおよび WCF-CustomIsolated アダプタを使用して、動作拡張機能、バインド要素拡張機能、およびバインド拡張機能の 3 つの WCF 機能拡張ポイントを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-103">This topic describes how to enable three WCF extensibility points—behavior extension, binding element extension, and binding extension—with the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="a16c2-104">これを行うには、まず WCF 機能拡張ポイントを実装するアセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールし、コンピューターの machine.config ファイルを変更した後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して WCF-Custom アダプターまたは WCF-CustomIsolated アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-104">To do so, you first install the assemblies implementing the WCF extensibility points in the global assembly cache (GAC), then modify the machine.config file on your computers, and then configure the WCF-Custom or the WCF-CustomIsolated adapter by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="a16c2-105">WCF 機能拡張ポイントの詳細についてで WCF の拡張」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=86380](http://go.microsoft.com/fwlink/?LinkId=86380)です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-105">For more information about the WCF extensibility points, see "Extending WCF" at [http://go.microsoft.com/fwlink/?LinkId=86380](http://go.microsoft.com/fwlink/?LinkId=86380).</span></span>  
  
 <span data-ttu-id="a16c2-106">WCF 機能拡張ポイントを有効にする方法の詳細についてを参照してください「SDK サンプル:: を使用してカスタム バインド拡張機能 with the Wcf-custom Adapters」 [http://go.microsoft.com/fwlink/?LinkId=65185](http://go.microsoft.com/fwlink/?LinkId=65185)です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-106">For more information about how to enable the WCF extensibility points, see "SDK Sample: Using Custom Binding Extensions with the WCF-Custom Adapters" at [http://go.microsoft.com/fwlink/?LinkId=65185](http://go.microsoft.com/fwlink/?LinkId=65185).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a16c2-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a16c2-107">Prerequisites</span></span>  
 <span data-ttu-id="a16c2-108">このトピックの手順を実行する必要がありますログインする必要がのメンバーであるアカウントを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="a16c2-108">To perform the procedures in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="a16c2-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-109">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-install-assemblies-implementing-a-wcf-extensibility-point-in-the-gac"></a><span data-ttu-id="a16c2-110">WCF 機能拡張ポイントを実装するアセンブリを GAC にインストールするには</span><span class="sxs-lookup"><span data-stu-id="a16c2-110">To install assemblies implementing a WCF extensibility point in the GAC</span></span>  
  
1.  <span data-ttu-id="a16c2-111">WCF 機能拡張ポイントを実装するアセンブリを、ローカル コンピューター上のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a16c2-111">Copy the assemblies implementing the WCF extensibility point to a folder on your local computer.</span></span>  
  
2.  <span data-ttu-id="a16c2-112">WCF 機能拡張ポイントが使用するアセンブリがある場合、そのアセンブリをローカル コンピューター上のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a16c2-112">Copy the assemblies that the WCF extensibility point uses, if any, to a folder on your local computer.</span></span>  
  
3.  <span data-ttu-id="a16c2-113">開始、 **Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-113">Start the **Visual Studio Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="a16c2-114">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-114">Type the following command:</span></span>  
  
     <span data-ttu-id="a16c2-115">**gacutil.exe/if"\<**  *アセンブリ .dll ファイルのパスを* **>"**</span><span class="sxs-lookup"><span data-stu-id="a16c2-115">**gacutil.exe /if "\<** *path to the assembly .dll file* **>"**</span></span>  
  
5.  <span data-ttu-id="a16c2-116">これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a16c2-116">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
6.  <span data-ttu-id="a16c2-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトで、手順 1. と 2. でコピーしたすべてのアセンブリについて手順 4. と 5. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-117">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, repeat steps 4 and 5 against all the assemblies you copied in steps 1 and 2 of this procedure.</span></span>  
  
7.  <span data-ttu-id="a16c2-118">複数ある場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターと管理コンピューターは、すべてのコンピューターに 1 ~ 6 のこの手順を手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-118">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 6 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-119">WCF アダプターの WCF 機能拡張ポイントを有効にするには、アダプターを実行している BizTalk ホスト インスタンスが、WCF 機能拡張ポイントが実装されているアセンブリを実行時に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16c2-119">To enable WCF extensibility points for the WCF adapters, the BizTalk Host instance running the adapter must be able to load at run time the assemblies where the WCF extensibility points are implemented.</span></span>  
  
### <a name="to-configure-the-machineconfig-file-for-a-wcf-binding-extension"></a><span data-ttu-id="a16c2-120">WCF バインド拡張機能の machine.config ファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="a16c2-120">To configure the machine.config file for a WCF binding extension</span></span>  
  
1.  <span data-ttu-id="a16c2-121">コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a16c2-121">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="a16c2-122">メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel >\\< 拡張\>**要素内にその要素の追加、  **\<構成 >** 、machine.config の要素ファイル、および追加し、  **\<bindingExtensions >**要素内の WCF バインド拡張機能、  **\<system.serverModel >\\< 拡張\>**要素。</span><span class="sxs-lookup"><span data-stu-id="a16c2-122">In Notepad, if the machine.config file does not have the **\<system.serverModel>\\<extensions\>** elements, add those elements inside the **\<configuration>** element of the machine.config file, and then add the **\<bindingExtensions>** element for a WCF binding extension inside the **\<system.serverModel>\\<extensions\>** elements.</span></span> <span data-ttu-id="a16c2-123">たとえば、netHttpBinding、カスタム バインド拡張機能を有効にする次のコードを追加、 **\<構成 >** machine.config ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="a16c2-123">For example, to enable a custom binding extension, netHttpBinding, add the following code inside the **\<configuration>** element of the machine.config file:</span></span>  
  
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
    >  <span data-ttu-id="a16c2-124">コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-124">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-125">詳細については、  **<bindingExtensions>** 要素を参照してください"<bindingExtensions>"で[http://go.microsoft.com/fwlink/?LinkID=86180](http://go.microsoft.com/fwlink/?LinkID=86180)です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-125">For more information about the **<bindingExtensions>** element, see "<bindingExtensions>" at [http://go.microsoft.com/fwlink/?LinkID=86180](http://go.microsoft.com/fwlink/?LinkID=86180).</span></span>  
  
3.  <span data-ttu-id="a16c2-126">メモ帳で、machine.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-126">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="a16c2-127">複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-127">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-128">BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16c2-128">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="to-configure-a-wcf-binding-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="a16c2-129">BizTalk 管理コンソールを使用して WCF バインド拡張機能を構成するには</span><span class="sxs-lookup"><span data-stu-id="a16c2-129">To configure a WCF binding extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="a16c2-130">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-130">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-131">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-131">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a16c2-132">WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-132">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="a16c2-133">WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-133">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="a16c2-134">WCF 機能拡張ポイントを使用する受信場所を構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所 >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-134">If you want to configure a receive location to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location>*.</span></span>  
  
    -   <span data-ttu-id="a16c2-135">**受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-135">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a16c2-136">WCF 機能拡張ポイントを使用する送信ポートを構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-136">If you want to configure a send port to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port>*.</span></span>  
  
    -   <span data-ttu-id="a16c2-137">**送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-137">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="a16c2-138">トランスポートのプロパティ ダイアログ ボックスで、**バインディング** タブで、バインド拡張機能を選択し、他のトランスポートの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-138">In the transport properties dialog box, on the **Binding** tab, select the binding extension, and then configure the rest of the settings for the transport.</span></span>  
  
7.  <span data-ttu-id="a16c2-139">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
### <a name="to-configure-the-machineconfig-file-for-a-wcf-binding-element-extension"></a><span data-ttu-id="a16c2-140">WCF バインド要素拡張機能の machine.config ファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="a16c2-140">To configure the machine.config file for a WCF binding element extension</span></span>  
  
1.  <span data-ttu-id="a16c2-141">コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a16c2-141">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="a16c2-142">メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel >\\< 拡張\>**要素内にその要素の追加、  **\<構成 >** 、machine.config の要素ファイル、および追加し、  **\<bindingElementExtensions >**要素内に WCF バインド要素拡張機能、  **\<system.serverModel >\\< 拡張\>**要素。</span><span class="sxs-lookup"><span data-stu-id="a16c2-142">In Notepad, if the machine.config file does not have the **\<system.serverModel>\\<extensions\>** elements, add those elements inside the **\<configuration>** element of the machine.config file, and then add the **\<bindingElementExtensions>** element for a WCF binding element extension inside the **\<system.serverModel>\\<extensions\>** elements.</span></span> <span data-ttu-id="a16c2-143">たとえば、droppingInterceptor、カスタム バインディング要素拡張を有効にする次のコードを追加、 **\<構成 >** machine.config ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="a16c2-143">For example, to enable a custom binding element extension, droppingInterceptor, add the following code inside the **\<configuration>** element of the machine.config file:</span></span>  
  
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
    >  <span data-ttu-id="a16c2-144">コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-144">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-145">詳細については、  **<bindingElementExtensions>** 要素を参照してください"<bindingElementExtensions>"で[http://go.microsoft.com/fwlink/?LinkId=86381](http://go.microsoft.com/fwlink/?LinkId=86381)です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-145">For more information about the **<bindingElementExtensions>** element, see "<bindingElementExtensions>" at [http://go.microsoft.com/fwlink/?LinkId=86381](http://go.microsoft.com/fwlink/?LinkId=86381).</span></span>  
  
3.  <span data-ttu-id="a16c2-146">メモ帳で、machine.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-146">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="a16c2-147">複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-147">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-148">BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16c2-148">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="to-configure-a-wcf-binding-element-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="a16c2-149">BizTalk 管理コンソールを使用して WCF バインド要素拡張機能を構成するには</span><span class="sxs-lookup"><span data-stu-id="a16c2-149">To configure a WCF binding element extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="a16c2-150">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-150">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-151">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-151">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a16c2-152">WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-152">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="a16c2-153">WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-153">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="a16c2-154">WCF 機能拡張ポイントを使用する受信場所を構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所 >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-154">If you want to configure a receive location to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location>*.</span></span>  
  
    -   <span data-ttu-id="a16c2-155">**受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-155">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a16c2-156">WCF 機能拡張ポイントを使用する送信ポートを構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-156">If you want to configure a send port to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port>*.</span></span>  
  
    -   <span data-ttu-id="a16c2-157">**送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-157">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="a16c2-158">トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブの 、**バインディングの種類**ドロップダウン リストで、 **customBinding**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-158">In the transport properties dialog box, on the **Binding** tab, in the **Binding Type** drop-down list, select **customBinding**.</span></span>  
  
7.  <span data-ttu-id="a16c2-159">トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブでのクライアント領域を右クリックし、**バインド**一覧をクリックして**拡張機能を追加**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-159">In the transport properties dialog box, on the **Binding** tab, right-click the client area of the **Binding** list, and then click **Add extension**.</span></span>  
  
8.  <span data-ttu-id="a16c2-160">**バインディング要素拡張機能の選択**ダイアログ ボックスをバインディング要素拡張を選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-160">In the **Select Binding Element Extension** dialog box, select a binding element extension, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="a16c2-161">トランスポートのプロパティ ダイアログ ボックスで、**バインディング** タブで追加されたバインド要素の順序を調整、**バインディング**で追加したバインド要素拡張の種類に応じて一覧、次のように前の手順:</span><span class="sxs-lookup"><span data-stu-id="a16c2-161">In the transport properties dialog box, on the **Binding** tab, adjust the order of the binding elements added in the **Binding** list depending on the type of the binding element extension you added in the previous step as follows:</span></span>  
  
    -   <span data-ttu-id="a16c2-162">**バインディング**ボックスの一覧をバインド要素拡張を右クリックし、をクリックして**拡張機能を上へ移動**または**拡張機能を下へ移動**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-162">In the **Binding** list, right-click a binding element extension, and then click **Move extension up** or **Move extension down**.</span></span> <span data-ttu-id="a16c2-163">最下位のバインド要素拡張機能、**バインディング**一覧は、チャネル スタックの一番下のコンポーネントに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a16c2-163">The lowest binding element extension in the **Binding** list corresponds to the bottom component of the channel stack.</span></span> <span data-ttu-id="a16c2-164">内の最上位のバインド要素、**バインディング**一覧は、通信スタックの一番上のコンポーネントに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a16c2-164">The highest binding element in the **Binding** list corresponds to the top component of the communication stack.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a16c2-165">詳細については、カスタム バインドのバインド要素の特定の順序で「カスタム バインディング」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=86383](http://go.microsoft.com/fwlink/?LinkId=86383)です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-165">For more information about the specific order of the binding elements for the custom binding, see "Custom Bindings" at [http://go.microsoft.com/fwlink/?LinkId=86383](http://go.microsoft.com/fwlink/?LinkId=86383).</span></span>  
  
10. <span data-ttu-id="a16c2-166">トランスポートのプロパティ ダイアログ ボックスで、他のトランスポートの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-166">In the transport properties dialog box, configure the rest of the settings for the transport.</span></span>  
  
11. <span data-ttu-id="a16c2-167">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-167">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
### <a name="to-configure-the-machineconfig-file-for-a-wcf-behavior-extension"></a><span data-ttu-id="a16c2-168">WCF 動作拡張機能の machine.config ファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="a16c2-168">To configure the machine.config file for a WCF behavior extension</span></span>  
  
1.  <span data-ttu-id="a16c2-169">コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a16c2-169">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="a16c2-170">メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel >\\< 拡張\>**要素内にその要素の追加、  **\<構成 >** 、machine.config の要素ファイル、および追加し、  **\<behaviorExtensions >**要素内に WCF 動作拡張機能、  **\<system.serverModel >\\< 拡張\>**要素。</span><span class="sxs-lookup"><span data-stu-id="a16c2-170">In Notepad, if the machine.config file does not have the **\<system.serverModel>\\<extensions\>** elements, add those elements inside the **\<configuration>** element of the machine.config file, and then add the **\<behaviorExtensions>** element for a WCF behavior extension inside the **\<system.serverModel>\\<extensions\>** elements.</span></span> <span data-ttu-id="a16c2-171">たとえば、schemaValidator、カスタム動作拡張機能を有効にする次のコードを追加、 **\<構成 >** machine.config ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="a16c2-171">For example, To enable a custom behavior extension, schemaValidator, add the following code inside the **\<configuration>** element of the machine.config file:</span></span>  
  
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
    >  <span data-ttu-id="a16c2-172">コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-172">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-173">詳細については、  **<behaviorExtensions>** 要素を参照してください"<behaviorExtensions>"で[http://go.microsoft.com/fwlink/?LinkId=86382](http://go.microsoft.com/fwlink/?LinkId=86382)です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-173">For more information about the **<behaviorExtensions>** element, see "<behaviorExtensions>" at  [http://go.microsoft.com/fwlink/?LinkId=86382](http://go.microsoft.com/fwlink/?LinkId=86382).</span></span>  
  
3.  <span data-ttu-id="a16c2-174">メモ帳で、machine.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-174">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="a16c2-175">複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-175">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-176">BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16c2-176">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="to-configure-a-wcf-behavior-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="a16c2-177">BizTalk 管理コンソールを使用して WCF 動作拡張機能を構成するには</span><span class="sxs-lookup"><span data-stu-id="a16c2-177">To configure a WCF behavior extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="a16c2-178">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-178">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a16c2-179">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-179">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a16c2-180">WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-180">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="a16c2-181">WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-181">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="a16c2-182">BizTalk 管理コンソールで、WCF 機能拡張ポイントを使用して、展開の受信場所を構成する場合**BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所 >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-182">If you want to configure a receive location to use a WCF extensibility point, in the BizTalk Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location>*.</span></span>  
  
    -   <span data-ttu-id="a16c2-183">**受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-183">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a16c2-184">BizTalk 管理コンソールで、WCF 機能拡張ポイントを使用して、展開する送信ポートを構成する場合**BizTalk グループ**、展開 *\<BizTalk アプリケーション >*の展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート >*です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-184">If you want to configure a send port to use a WCF extensibility point, in the BizTalk Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port>*.</span></span>  
  
    -   <span data-ttu-id="a16c2-185">**送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-185">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="a16c2-186">トランスポートのプロパティ ダイアログ ボックスで、**動作** タブを右クリックして**ServiceBehavior**または**endpointbehavior**動作拡張機能の種類に応じて、**動作拡張機能の選択**ダイアログ ボックスでは、動作拡張機能を選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-186">In the transport properties dialog box, on the **Behavior** tab, right-click **ServiceBehavior** or **EndpointBehavior** depending on the type of the behavior extension, and then, in the **Select Behavior Extension** dialog box, select the behavior extension, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a16c2-187">トランスポートのプロパティ ダイアログ ボックスで、他のトランスポートの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-187">In the transport properties dialog box, configure the rest of the settings for the transport.</span></span>  
  
8.  <span data-ttu-id="a16c2-188">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-188">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
### <a name="to-configure-a-wcf-custom-receive-location-with-an-ssl-certificate"></a><span data-ttu-id="a16c2-189">SSL 証明書を使用して WCF-Custom 受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="a16c2-189">To configure a WCF-Custom receive location with an SSL certificate</span></span>  
  
-   <span data-ttu-id="a16c2-190">Wcf-custom 受信場所がなどを使用して HTTP カーネル モード ドライバー (HTTP.sys) が発生する場合、 **httpsTransport**通信用に Secure Sockets Layer (SSL)、受信場所のバインド要素は、証明書が必要各ソケット (IP アドレスとポートの組み合わせ) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="a16c2-190">If a WCF-Custom receive location happens to use the HTTP kernel-mode driver (HTTP.sys) such as the **httpsTransport** binding element, for Secure Sockets Layer (SSL) communications, the receive location must have a certificate registered for each socket (IP address/port combination).</span></span> <span data-ttu-id="a16c2-191">SSL 証明書をコンピューター上のポートにバインドするには、HttpCfg.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a16c2-191">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the computer.</span></span> <span data-ttu-id="a16c2-192">詳細についてを参照してください「方法に:: 構成のポートで SSL 証明書を」 [http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384)です。</span><span class="sxs-lookup"><span data-stu-id="a16c2-192">For more information, see "How To: Configure a Port with An SSL Certificate" at [http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384).</span></span>
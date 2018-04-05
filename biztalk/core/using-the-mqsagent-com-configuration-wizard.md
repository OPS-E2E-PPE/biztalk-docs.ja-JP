---
title: MQSAgent COM + 構成ウィザードを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mqsagent.wizard
helpviewer_keywords:
- MQSeries adapters, MQSAgent COM+ Configuration Wizard
- configuring [MQSeries adapters], MQSAgent COM+ Configuration Wizard
- MQSAgent COM+ Configuration Wizard
ms.assetid: f106700a-7f57-4c83-9344-6525fc10544d
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6e8b625bcc3accbefda193c52459616691c265
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a><span data-ttu-id="32855-102">MQSAgent COM + 構成ウィザードの使用</span><span class="sxs-lookup"><span data-stu-id="32855-102">Using the MQSAgent COM+ Configuration Wizard</span></span>
<span data-ttu-id="32855-103">MQSAgent COM+ 構成ウィザードでは、アダプターの COM+ アプリケーション (MQSeries コンポーネント) 部分である MQSAgent を構成します。</span><span class="sxs-lookup"><span data-stu-id="32855-103">The MQSAgent COM+ Configuration Wizard configures the MQSAgent, the COM+ application (MQSeries component) part of the adapter.</span></span> <span data-ttu-id="32855-104">このウィザードでは、コンポーネントのアプリケーション ID、およびロール名とそのロールに含めるユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="32855-104">The wizard sets the application identity of the component, and the role name and users included in the role.</span></span> <span data-ttu-id="32855-105">MQSAgent COM + 構成ウィザードを使用して作成される MQSAgent COM + コンポーネントの名前は**MQSAgent2**です。</span><span class="sxs-lookup"><span data-stu-id="32855-105">The name of the MQSAgent COM+ component created with the MQSAgent COM+ Configuration Wizard is **MQSAgent2**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32855-106">MQSAgent COM+ アプリケーションは、64 ビット版の Windows サーバーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="32855-106">The MQSAgent COM+ application is supported on a 64-bit Windows server.</span></span> <span data-ttu-id="32855-107">WOW64 の下で 32 ビット プロセスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="32855-107">It will run as a 32-bit process under WOW64.</span></span> <span data-ttu-id="32855-108">64 ビット版の Windows Server で実行されている [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ベースのコンピューターは、MQSAgent がインストールされているリモートの 32 ビット コンピューターと通信できます。</span><span class="sxs-lookup"><span data-stu-id="32855-108">A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-based computer that is running on a 64-bit version of Windows Server can communicate with a remote 32-bit computer that has the MQSAgent installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32855-109">MQSeries エージェントと MQSAgent COM + 構成ウィザードの実行可能ファイル**MQSConfigWiz.exe** BizTalk Server 2009 から BizTalk Server までアップグレードする場合はインストールされません。</span><span class="sxs-lookup"><span data-stu-id="32855-109">The MQSeries Agent and the MQSAgent COM+ Configuration Wizard executable **MQSConfigWiz.exe** are not installed if you upgrade from BizTalk Server 2009 to BizTalk Server.</span></span> <span data-ttu-id="32855-110">セットアップを再実行して BizTalk Server 2009 から BizTalk Server までアップグレードした後は、選択、**変更**オプション、およびこれらのコンポーネントをインストールする追加のソフトウェア [MQSeries エージェント] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32855-110">After upgrading to BizTalk Server from BizTalk Server 2009 re-run setup, select the **Modify** option, and select the MQSeries Agent under the Additional Software to install these components.</span></span>  
  
## <a name="to-set-the-application-identity"></a><span data-ttu-id="32855-111">アプリケーション ID を設定するには</span><span class="sxs-lookup"><span data-stu-id="32855-111">To set the application identity</span></span>  
  
-   <span data-ttu-id="32855-112">使用して、**アプリケーション Id** MQSAgent COM + 構成ウィザードの次のように MQSAgent のアプリケーション id を設定するページ。</span><span class="sxs-lookup"><span data-stu-id="32855-112">Use the **Application Identity** page of the MQSAgent COM+ Configuration Wizard to set the application identity for the MQSAgent as follows:</span></span>  
  
    |<span data-ttu-id="32855-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32855-113">Use this</span></span>|<span data-ttu-id="32855-114">目的</span><span class="sxs-lookup"><span data-stu-id="32855-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="32855-115">**対話型のユーザー**</span><span class="sxs-lookup"><span data-stu-id="32855-115">**Interactive User**</span></span>|<span data-ttu-id="32855-116">アプリケーション ID に現在のログオン アカウントを使用する場合にこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="32855-116">Select this option to use the current logon account for the application identity.</span></span>|  
    |<span data-ttu-id="32855-117">**Local Service**</span><span class="sxs-lookup"><span data-stu-id="32855-117">**Local Service**</span></span>|<span data-ttu-id="32855-118">アプリケーション ID にビルトイン サービス アカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="32855-118">Set the application identity to a built-in service account.</span></span>|  
    |<span data-ttu-id="32855-119">**Network Service**</span><span class="sxs-lookup"><span data-stu-id="32855-119">**Network Service**</span></span>|<span data-ttu-id="32855-120">アプリケーション ID にネットワーク アクセス権付きのビルトイン サービス アカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="32855-120">Set the application identity to a built-in account with network access.</span></span>|  
    |<span data-ttu-id="32855-121">**このユーザー**</span><span class="sxs-lookup"><span data-stu-id="32855-121">**This user**</span></span>|<span data-ttu-id="32855-122">アプリケーション ID に、指定したユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="32855-122">Set the application identity to the indicated user name.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="32855-123">アプリケーション ID に管理権限を持つアカウントを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="32855-123">It is not recommended that you use an account with administrative permissions for the application identity.</span></span> <span data-ttu-id="32855-124">このアカウントには、MQSeries キューに対する必要最低限の権限 (読み取りと書き込みのアクセス許可) を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32855-124">The account must have the minimal rights required: read and write permission for the MQSeries queues.</span></span>  
  
## <a name="to-name-the-role-and-add-users-to-it"></a><span data-ttu-id="32855-125">ロールに名前を付けてユーザーを追加するには</span><span class="sxs-lookup"><span data-stu-id="32855-125">To name the role and add users to it</span></span>  
  
-   <span data-ttu-id="32855-126">使用して、**ロールの名前**MQSAgent COM + 構成ウィザードの次のように、役割に、名前とユーザーを割り当てるページ。</span><span class="sxs-lookup"><span data-stu-id="32855-126">Use the **Name of Role** page of the MQSAgent COM+ Configuration Wizard  to assign a name and users to the role as follows:</span></span>  
  
    |<span data-ttu-id="32855-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32855-127">Use this</span></span>|<span data-ttu-id="32855-128">目的</span><span class="sxs-lookup"><span data-stu-id="32855-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="32855-129">**ロールの名前**</span><span class="sxs-lookup"><span data-stu-id="32855-129">**Name of role**</span></span>|<span data-ttu-id="32855-130">ロールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="32855-130">Type the name of the role.</span></span>|  
    |<span data-ttu-id="32855-131">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="32855-131">**Users**</span></span>|<span data-ttu-id="32855-132">ロールに属しているユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="32855-132">Display the users that belong to the role.</span></span>|  
    |<span data-ttu-id="32855-133">**[追加]**</span><span class="sxs-lookup"><span data-stu-id="32855-133">**Add**</span></span>|<span data-ttu-id="32855-134">ユーザーをロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="32855-134">Add users to the role.</span></span> <span data-ttu-id="32855-135">これらのユーザーは、アダプターを使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービス アカウントです。</span><span class="sxs-lookup"><span data-stu-id="32855-135">These are the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service accounts using the adapter.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="32855-136">ロールには、アダプターにアクセスする必要のあるアカウントのみを追加してください。</span><span class="sxs-lookup"><span data-stu-id="32855-136">Add to the role only accounts requiring access to the adapter.</span></span>  
  
## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a><span data-ttu-id="32855-137">Windows Server 2008 コンピューター上の MSDTC のセキュリティ構成を [認証を必要としない] に設定するには</span><span class="sxs-lookup"><span data-stu-id="32855-137">To set the MSDTC Security configuration on the Windows Server 2008 computer to No Authentication Required</span></span>  
 <span data-ttu-id="32855-138">MQSAgent COM + アプリケーションがインストールされている場合、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]でコンピューターと、MQSeries アダプター (BizTalk Server と共にインストールされます) がインストールされている、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]コンピューター、MSDTC セキュリティ構成を[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]にコンピューターを設定する必要があります**認証を必要としない**です。</span><span class="sxs-lookup"><span data-stu-id="32855-138">If the MQSAgent COM+ application is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computer and the MQSeries Adapter (which is installed with BizTalk Server) is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer, the MSDTC Security configuration on the [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer must be set to **No Authentication Required**.</span></span> <span data-ttu-id="32855-139">MSDTC のセキュリティ構成を [認証を必要としない] に設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32855-139">Follow these steps to set the MSDTC security configuration to No Authentication Required:</span></span>  
  
1.  <span data-ttu-id="32855-140">をクリックして**開始**] をクリックし、**コントロール パネルの [**です。</span><span class="sxs-lookup"><span data-stu-id="32855-140">Click **Start** and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="32855-141">**［管理ツール］** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="32855-141">Double-click **Administrative Tools**.</span></span>  
  
3.  <span data-ttu-id="32855-142">ダブルクリックして**コンポーネント サービス**を起動する、**コンポーネント サービス**管理インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="32855-142">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  
  
4.  <span data-ttu-id="32855-143">展開**コンポーネント サービス**、展開**コンピューター**、順に展開**マイ コンピューター**です。</span><span class="sxs-lookup"><span data-stu-id="32855-143">Expand **Component Services**, expand **Computers**, and then expand **My Computer**.</span></span>  
  
5.  <span data-ttu-id="32855-144">右クリック**マイ コンピューター**  をクリックし、**プロパティ**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="32855-144">Right-click **My Computer** and click the **Properties** menu item.</span></span>  
  
6.  <span data-ttu-id="32855-145">**マイ コンピューター**ダイアログ ボックスで、をクリックして、 **MSDTC**  タブをクリックして**セキュリティ構成**です。</span><span class="sxs-lookup"><span data-stu-id="32855-145">In the **My Computer** dialog box, click the **MSDTC** tab and then click **Security Configuration**.</span></span>  
  
7.  <span data-ttu-id="32855-146">**セキュリティ構成** ダイアログ ボックスで、**トランザクション マネージャー通信**セクションで、**認証を必要としない**です。</span><span class="sxs-lookup"><span data-stu-id="32855-146">In the **Security Configuration** dialog box, in the **Transaction Manager Communication** section, select **No Authentication Required**.</span></span> <span data-ttu-id="32855-147">ダイアログ ボックスでメッセージが表示されたら、クリックして**はい**MS DTC サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="32855-147">If you are prompted with a dialog box, click **Yes** to restart the MS DTC Service.</span></span>  
  
8.  <span data-ttu-id="32855-148">MS DTC サービスが再起動した後にをクリックして**OK**  をクリック**ok**を閉じます、**マイ コンピューター**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="32855-148">After the MS DTC service has restarted, click **OK** and click **OK** again to close the **My Computer** dialog box.</span></span>  
  
9. <span data-ttu-id="32855-149">閉じる、**コンポーネント サービス**管理インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="32855-149">Close the **Component Services** management interface.</span></span>  
  
## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a><span data-ttu-id="32855-150">代替資格情報のセットで実行する MQSAgent ランタイム コンポーネントを構成するには</span><span class="sxs-lookup"><span data-stu-id="32855-150">To configure the MQSAgent runtime components to run under an alternative set of credentials</span></span>  
 <span data-ttu-id="32855-151">MQSAgent COM+ アプリケーションには、管理およびランタイム用のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="32855-151">The MQSAgent COM+ application includes components for both administration and runtime.</span></span> <span data-ttu-id="32855-152">セキュリティ上の理由でこの機能を異なる COM+ アプリケーションに分割する場合は、MQSAgent COM+ アプリケーションがインストールされているコンピューター上で次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="32855-152">If you want to separate this functionality into different COM+ applications for security purposes, follow these steps on the computer that the MQSAgent COM+ application is installed on:</span></span>  
  
1.  <span data-ttu-id="32855-153">MQSAgent COM+ コンポーネントに変更を加えられるようにします。</span><span class="sxs-lookup"><span data-stu-id="32855-153">Enable changes for the MQSAgent COM+ component.</span></span>  
  
    -   <span data-ttu-id="32855-154">をクリックして**開始**] をクリックし、**コントロール パネルの [**です。</span><span class="sxs-lookup"><span data-stu-id="32855-154">Click **Start** and then click **Control Panel**.</span></span>  
  
    -   <span data-ttu-id="32855-155">**［管理ツール］** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="32855-155">Double-click **Administrative Tools**.</span></span>  
  
    -   <span data-ttu-id="32855-156">ダブルクリックして**コンポーネント サービス**を起動する、**コンポーネント サービス**管理インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="32855-156">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  
  
    -   <span data-ttu-id="32855-157">展開**コンポーネント サービス**、展開**マイ コンピューター**、展開**COM + アプリケーション**を右クリックし、 **MQSAgent2** COM + アプリケーションクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="32855-157">Expand **Component Services**, expand **My Computer**, expand **COM+ Applications**, right-click the **MQSAgent2** COM+ application and then click **Properties**.</span></span>  
  
    -   <span data-ttu-id="32855-158">クリックして、 **[詳細設定]**タブおよびボックスをオフに**変更を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="32855-158">Click the **Advanced** tab and uncheck **Disable changes**.</span></span>  
  
    -   <span data-ttu-id="32855-159">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32855-159">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="32855-160">MQSAgent ランタイム コンポーネント用の新しい COM+ アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="32855-160">Create a new COM+ application for the MQSAgent runtime components.</span></span>  
  
    -   <span data-ttu-id="32855-161">右クリック**COM + アプリケーション**をクリックして**新規**、**アプリケーション**を表示する、 **COM + アプリケーション インストール ウィザード** をクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="32855-161">Right-click **COM+ Applications**, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="32855-162">をクリックして**空のアプリケーションを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="32855-162">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="32855-163">名前を入力します**MQSAgent2RunTime**の既定のオプションのままにして**サーバー アプリケーション**有効になっており、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="32855-163">Enter the name **MQSAgent2RunTime**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="32855-164">オプションを選択**このユーザー**、適切なアカウント情報を入力し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="32855-164">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="32855-165">このアカウントが必要**接続**と**put**や**取得**適切な IBM WebSphere MQ キューの Windows のアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="32855-165">This account should have **connect** and **put** and/or **get** permissions on the appropriate IBM WebSphere MQ for Windows queues.</span></span> <span data-ttu-id="32855-166">このアカウントに対する適切なアクセス許可を設定することができます、 **setmqaut**コマンドを使用して IBM WebSphere MQ とします。</span><span class="sxs-lookup"><span data-stu-id="32855-166">You can set the appropriate permissions for this account with the **setmqaut** command available with the IBM WebSphere MQ.</span></span> <span data-ttu-id="32855-167">詳細については、 **setmqaut**コマンドは、IBM WebSphere MQ のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32855-167">For more information about the **setmqaut** command see the IBM WebSphere MQ documentation.</span></span>  
  
    -   <span data-ttu-id="32855-168">をクリックして**次**上、**アプリケーション ロールの追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="32855-168">Click **Next** on the **Add Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="32855-169">をクリックして**次へ**上、**ロールにユーザーの追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="32855-169">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="32855-170">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32855-170">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="32855-171">ランタイム コンポーネントを、新しい COM+ アプリケーションに移動します。</span><span class="sxs-lookup"><span data-stu-id="32855-171">Move the runtime components to the new COM+ application</span></span>  
  
    -   <span data-ttu-id="32855-172">展開して、 **MQSAgent2** COM + アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="32855-172">Expand the **MQSAgent2** COM+ application.</span></span>  
  
    -   <span data-ttu-id="32855-173">展開**コンポーネント**です。</span><span class="sxs-lookup"><span data-stu-id="32855-173">Expand **Components**.</span></span>  
  
    -   <span data-ttu-id="32855-174">右クリックし、 **MQSAgent2.MQSAgent.1**コンポーネントとクリック**移動**を表示する、**コンポーネント (s) の移動** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="32855-174">Right-click the **MQSAgent2.MQSAgent.1** component and click **Move** to display the **Move components(s)** dialog box.</span></span>  
  
    -   <span data-ttu-id="32855-175">選択**MQSAgent2RunTime** **[の保存先を選択してください]** をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="32855-175">Select **MQSAgent2RunTime** under **Please select a destination** and click **OK**.</span></span>  
  
    -   <span data-ttu-id="32855-176">次の手順を繰り返して、 **MQSAgent2.MQSBroker.1**と**MQSAgent2.MQSProxy.1**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="32855-176">Repeat these steps for the **MQSAgent2.MQSBroker.1** and **MQSAgent2.MQSProxy.1** components.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32855-177">参照</span><span class="sxs-lookup"><span data-stu-id="32855-177">See Also</span></span>  
 <span data-ttu-id="32855-178">[MQSeries アダプターを構成する方法は、送信し、受信ハンドラー](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="32855-178">[How to Configure MQSeries Adapter Send and Receive Handlers](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span></span>  
 [<span data-ttu-id="32855-179">MQSeries アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="32855-179">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)
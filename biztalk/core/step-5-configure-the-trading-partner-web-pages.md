---
title: '手順 5: 取引先パートナーの Web ページの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38c3054d-932a-42b6-a821-8b30604d8426
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd0a9be1a7df1b506c169935d12b7636155615c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001195"
---
# <a name="step-5-configure-the-trading-partner-web-pages"></a><span data-ttu-id="466ac-102">手順 5: 取引先パートナーの Web ページを構成します。</span><span class="sxs-lookup"><span data-stu-id="466ac-102">Step 5: Configure the Trading Partner Web Pages</span></span>
<span data-ttu-id="466ac-103">![手順 5. の 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")</span><span class="sxs-lookup"><span data-stu-id="466ac-103">![Step 5 of 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")</span></span>  
  
 <span data-ttu-id="466ac-104">ここでは、次の作業を実行して取引先の Web ページを設定します。</span><span class="sxs-lookup"><span data-stu-id="466ac-104">In this step, you perform the following tasks to set up trading partner Web pages:</span></span>  
  
-   <span data-ttu-id="466ac-105">HTTP トランスポートに必要な BTS HTTP Receive ISAPI フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="466ac-105">Enable the BTS HTTP Receive ISAPI filter that is required for HTTP transport.</span></span>  
  
-   <span data-ttu-id="466ac-106">997 受信確認を HTTP トランスポートを使用してパートナー組織 Fabrikam にルーティングするように、フォルダと aspx ページを設定します。</span><span class="sxs-lookup"><span data-stu-id="466ac-106">Set up a folder and an aspx page to route the 997 acknowledgment to the partner organization Fabrikam using HTTP transport.</span></span> <span data-ttu-id="466ac-107">Fabrikam 仮想ディレクトリに 997 受信確認の削除、 \\_ 997tofabrikam フォルダーは、997 送信ポートの Destination_URL の設定の説明が示されています。</span><span class="sxs-lookup"><span data-stu-id="466ac-107">The Fabrikam virtual directory drops the 997 acknowledgment into the \\_997ToFabrikam folder, which is called out in the Destination_URL setting of the 997 send port.</span></span>  
  
-   <span data-ttu-id="466ac-108">元のメッセージをホーム組織 Contoso にルーティングするように ASPX ページを設定します。</span><span class="sxs-lookup"><span data-stu-id="466ac-108">Set up the ASPX page to route the original message to the home organization Contoso.</span></span> <span data-ttu-id="466ac-109">Contoso 仮想ディレクトリは、BTSHttpReceive.dll を使用して AS2 メッセージを受信し、それを受信場所に送信します。</span><span class="sxs-lookup"><span data-stu-id="466ac-109">The Contoso virtual directory uses BTSHttpReceive.dll to receive the AS2 message and submit it to the receive location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="466ac-110">このトピックで説明している手順は IIS 7.0 の場合の手順です。</span><span class="sxs-lookup"><span data-stu-id="466ac-110">The procedures provided in this topic are for IIS 7.0.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="466ac-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="466ac-111">Prerequisites</span></span>  
 <span data-ttu-id="466ac-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="466ac-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="466ac-113">BTS ISAPI フィルターを有効にするには</span><span class="sxs-lookup"><span data-stu-id="466ac-113">To enable the BTS ISAPI Filter</span></span>  
  
1. <span data-ttu-id="466ac-114">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="466ac-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2. <span data-ttu-id="466ac-115">ルート Web サーバーのエントリを選択し、**機能ビュー**、 をダブルクリックします**ハンドラー マッピング**し、**アクション**ウィンドウで、をクリックして**スクリプトマップの追加**.</span><span class="sxs-lookup"><span data-stu-id="466ac-115">Select the root Web server entry and in the **Features View**, double-click **Handler Mappings** and then in the **Actions** pane, click **Add Script Map**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="466ac-116">Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子 Web サイトにこのマッピングが適用されます。</span><span class="sxs-lookup"><span data-stu-id="466ac-116">Configuring the script mapping at the Web server level will cause this mapping to apply to all child Web sites.</span></span> <span data-ttu-id="466ac-117">特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="466ac-117">If you wish to restrict the mapping to a specific Web site or virtual folder, select the target site or folder instead of the Web server.</span></span>  
  
3. <span data-ttu-id="466ac-118">**スクリプト マップの追加** ダイアログ ボックスに、入力`BtsHttpReceive.dll`で、**要求パス**フィールド。</span><span class="sxs-lookup"><span data-stu-id="466ac-118">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4. <span data-ttu-id="466ac-119">**実行可能ファイル**フィールドに、をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive します。</span><span class="sxs-lookup"><span data-stu-id="466ac-119">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span> <span data-ttu-id="466ac-120">選択**BtsHttpReceive.dll**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="466ac-120">Select **BtsHttpReceive.dll**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="466ac-121">入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-121">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6. <span data-ttu-id="466ac-122">**要求の制限**ダイアログ ボックスで、**動詞**タブを選び**次の動詞のいずれか**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-122">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="466ac-123">入力`POST`動詞として。</span><span class="sxs-lookup"><span data-stu-id="466ac-123">Enter `POST` as the verb.</span></span>  
  
7. <span data-ttu-id="466ac-124">**アクセス**] タブで [**スクリプト**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-124">On the **Access** tab, select **Script**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="466ac-125">をクリックして **[ok]** ISAPI 拡張を許可するメッセージが表示されたら、クリックと**はい**。</span><span class="sxs-lookup"><span data-stu-id="466ac-125">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
9. <span data-ttu-id="466ac-126">BTSHttpReceive.dll エントリを右クリックし、**機能のアクセス許可の編集**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-126">Right-click the BTSHttpReceive.dll entry, and then select **Edit Feature Permissions**.</span></span>  
  
10. <span data-ttu-id="466ac-127">いることを確認**読み取り**、**スクリプト**と**Execute**クリックして選択すると、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="466ac-127">Ensure that **Read**, **Script** and **Execute** are selected, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="466ac-128">クリックして**機能ビュー**、し、ダブルクリック**ISAPI および CGI の制限**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-128">Click **Features View**, and then double-click **ISAPI and CGI Restrictions**.</span></span>  
  
12. <span data-ttu-id="466ac-129">BTSHTTPReceive.dll のエントリがあることを確認し、**制限**に設定されている**許可**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-129">Ensure that an entry for BTSHTTPReceive.dll exists, and that **Restriction** is set to **Allowed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="466ac-130">BTSHTTPReceive.dll の [ISAPI および CGI の制限] のエントリは、スクリプト マップの作成時に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="466ac-130">The ISAPI and CGI Restriction entry for BTSHTTPReceive.dll is created automatically when you create the script map.</span></span>  
  
### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="466ac-131">Fabrikam Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="466ac-131">To configure the Fabrikam Web page</span></span>  
  
1. <span data-ttu-id="466ac-132">IIS マネージャーで、右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-132">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2. <span data-ttu-id="466ac-133">**アプリケーション プールの追加** ダイアログ ボックスに、入力**BizTalkAppPool**で**名前**、し、 **.NET Framework v4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="466ac-133">In the **Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="466ac-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="466ac-134">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="466ac-135">コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="466ac-135">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3. <span data-ttu-id="466ac-136">選択**アプリケーション プール**の**機能ビュー**選択**BizTalkAppPool**、順にクリックします**詳細設定**で**アクション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="466ac-136">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4. <span data-ttu-id="466ac-137">**詳細設定**ダイアログ ボックスで、セット**を有効にする 32 ビット アプリケーション**に**True**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-137">In the **Advanced Settings** dialog box, set **Enable 32-Bit Applications** to **True**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="466ac-138">この手順は、64 ビットのコンピューター上で IIS を 32 ビット モードで実行する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="466ac-138">This step is required only on a 64-bit machine if you want IIS to run in a 32-bit mode.</span></span>  
  
5. <span data-ttu-id="466ac-139">選択**Identity**  をクリックし、**省略記号 (...)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="466ac-139">Select **Identity** and then click the **ellipsis (…)** button.</span></span>  
  
6. <span data-ttu-id="466ac-140">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-140">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
7. <span data-ttu-id="466ac-141">入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力します**パスワードの確認入力**をクリックして **。OK** 3 回の IIS マネージャーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="466ac-141">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
8. <span data-ttu-id="466ac-142">IIS マネージャーで、開く、**サイト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="466ac-142">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="466ac-143">右クリックし、**既定の Web サイト**、し、**アプリケーションの追加**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-143">Right-click the **Default Web Site**, and then select **Add Application**.</span></span>  
  
9. <span data-ttu-id="466ac-144">**アプリケーションの追加** ダイアログ ボックスに、入力**Fabrikam**で**エイリアス**、順にクリックします**選択**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-144">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
10. <span data-ttu-id="466ac-145">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-145">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
11. <span data-ttu-id="466ac-146">をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 \fabrikam、**物理パス**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-146">Click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam for the **Physical path**.</span></span>  
  
12. <span data-ttu-id="466ac-147">をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="466ac-147">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="466ac-148">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="466ac-148">Click **Close**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="466ac-149">IIS マネージャーでは、Fabrikam 仮想ディレクトリを選択し、**機能ビュー**、ダブルクリック**認証**。</span><span class="sxs-lookup"><span data-stu-id="466ac-149">In IIS Manager, select the Fabrikam virtual directory and in **Features View**, double-click **Authentication**.</span></span>  
  
14. <span data-ttu-id="466ac-150">**認証**を選択します**匿名認証**いることを確認し、**状態**は**有効**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-150">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="466ac-151">場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="466ac-151">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
### <a name="to-configure-the-contoso-web-page"></a><span data-ttu-id="466ac-152">Contoso Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="466ac-152">To configure the Contoso Web page</span></span>  
  
1. <span data-ttu-id="466ac-153">IIS マネージャーで、開く、**サイト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="466ac-153">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="466ac-154">右クリックし、**既定の Web サイト**選び**アプリケーションの追加**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-154">Right-click the **Default Web Site** and then select **Add Application**.</span></span>  
  
2. <span data-ttu-id="466ac-155">**アプリケーションの追加** ダイアログ ボックスに、入力**Contoso**で**エイリアス**、順にクリックします**選択**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-155">In the **Add Application** dialog box, enter **Contoso** in **Alias**, and then click **Select**.</span></span>  
  
3. <span data-ttu-id="466ac-156">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-156">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="466ac-157">BizTalkAppPool は以前に Fabrikam Web ページを構成したときに作成されており、管理者グループのメンバーであるユーザーの ID に設定されています。</span><span class="sxs-lookup"><span data-stu-id="466ac-157">The BizTalkAppPool was created previously when configuring the Fabrikam Web page, and should be set to the identity of a user that is a member of the administrators group.</span></span>  
  
4. <span data-ttu-id="466ac-158">をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-158">Click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
5. <span data-ttu-id="466ac-159">をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="466ac-159">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="466ac-160">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="466ac-160">Click **Close**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="466ac-161">IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-161">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
7. <span data-ttu-id="466ac-162">**認証**を選択します**匿名認証**いることを確認し、**状態**は**有効**します。</span><span class="sxs-lookup"><span data-stu-id="466ac-162">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="466ac-163">場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="466ac-163">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="466ac-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="466ac-164">Next Steps</span></span>  
 <span data-ttu-id="466ac-165">受信場所を構成する (**Receive_AS2**)」の説明に従って、Fabrikam から AS2 メッセージを受信する[手順 6: edi-as2 の受信場所を構成する](../core/step-6-configure-the-edi-as2-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="466ac-165">You configure the receive location (**Receive_AS2**) to receive the AS2 message from Fabrikam, as described in [Step 6: Configure the EDI-AS2 Receive Location](../core/step-6-configure-the-edi-as2-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466ac-166">参照</span><span class="sxs-lookup"><span data-stu-id="466ac-166">See Also</span></span>  
 [<span data-ttu-id="466ac-167">チュートリアル 3: AS2 チュートリアル</span><span class="sxs-lookup"><span data-stu-id="466ac-167">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)

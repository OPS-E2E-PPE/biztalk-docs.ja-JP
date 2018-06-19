---
title: '手順 1: AS2 チュートリアルの準備 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3421c33b-0ccd-4e9d-b1c3-b161278e4d98
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75c6be6fb76debac7f5a143fa1616a999dee326c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279546"
---
# <a name="step-1-prepare-for-the-as2-tutorial"></a><span data-ttu-id="9e834-102">手順 1: AS2 チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="9e834-102">Step 1: Prepare for the AS2 Tutorial</span></span>
<span data-ttu-id="9e834-103">![11 の手順 1.](../core/media/tut-step1-of-11.gif "Tut_Step1_of_11")</span><span class="sxs-lookup"><span data-stu-id="9e834-103">![Step 1 of 11](../core/media/tut-step1-of-11.gif "Tut_Step1_of_11")</span></span>  
  
 <span data-ttu-id="9e834-104">AS2 チュートリアルは 1 台のコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="9e834-104">The AS2 tutorial is run on a single computer.</span></span> <span data-ttu-id="9e834-105">このチュートリアルを準備するには、インストールして構成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」の説明に従って[BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)セクションです。</span><span class="sxs-lookup"><span data-stu-id="9e834-105">To prepare for the tutorial, you must install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as described in [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) section.</span></span> <span data-ttu-id="9e834-106">また、このトピックの説明に従って、BizTalk Server EDI アプリケーションへの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e834-106">You must also add a reference to the BizTalk Server EDI Application as described in this topic.</span></span> <span data-ttu-id="9e834-107">AS2 チュートリアルに必要なファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="9e834-107">The files required for the AS2 tutorial are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e834-108">このチュートリアルが機能するためには、インプロセス ホスト インスタンスと分離ホスト インスタンスの両方に同じログオン アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e834-108">For this tutorial to work, you need to use the same logon account for both the in-process host instance and the isolated host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e834-109">このチュートリアルが機能するためには、このチュートリアルで使用する BizTalk Server ホストが 32 ビットとマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e834-109">For this tutorial to work, the BizTalk Server host that is used for this tutorial must be marked as 32-bit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e834-110">このチュートリアルが機能するためには、IIS 7.0 または IIS 7.5 を使用するプラットフォームで実行し、アプリケーション プールの [32 ビット アプリケーションの有効化] を [True] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e834-110">For this tutorial to work, it must be run on a platform using IIS 7.0 or IIS 7.5, and the Enable 32-Bit Application Setting for the Application Pools must be set to True.</span></span>  
  
 <span data-ttu-id="9e834-111">AS2 チュートリアル フォルダーには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がテスト出力ファイルを書き込む 3 つのフォルダー (EDI payload、997、および MDN) があります。</span><span class="sxs-lookup"><span data-stu-id="9e834-111">The AS2 tutorial folders include three folders that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will write test output files to (the EDI payload, 997, and MDN).</span></span> <span data-ttu-id="9e834-112">これらのフォルダーは既に作成されていますが、997 フォルダーと MDN フォルダーのセキュリティ権限を設定する必要があります (次の手順を参照)。</span><span class="sxs-lookup"><span data-stu-id="9e834-112">These folder have already been created, but you must set the security permissions for two of the 997 and MDN folders (see the procedure below).</span></span>  
  
 <span data-ttu-id="9e834-113">チュートリアルに必要なフォルダーおよびファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e834-113">The folders and files required for the tutorial are as follows:</span></span>  
  
|<span data-ttu-id="9e834-114">Folder\File</span><span class="sxs-lookup"><span data-stu-id="9e834-114">Folder\File</span></span>|<span data-ttu-id="9e834-115">用途</span><span class="sxs-lookup"><span data-stu-id="9e834-115">Purpose</span></span>|  
|------------------|-------------|  
|<span data-ttu-id="9e834-116">\\_ 997tofabrikam</span><span class="sxs-lookup"><span data-stu-id="9e834-116">\\_997ToFabrikam</span></span>|<span data-ttu-id="9e834-117">この空のフォルダーは、EDI 処理後に返される 997 確認メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="9e834-117">This empty folder will receive the 997 acknowledgment message returned after EDI processing.</span></span> <span data-ttu-id="9e834-118">Fabrikam パーティで EDI メッセージを発信するアプリケーションをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="9e834-118">The folder simulates the application originating the EDI message at the Fabrikam party.</span></span>|  
|<span data-ttu-id="9e834-119">\\_EDIXMLToContoso</span><span class="sxs-lookup"><span data-stu-id="9e834-119">\\_EDIXMLToContoso</span></span>|<span data-ttu-id="9e834-120">この空のフォルダーは、BizTalk Server が EDI メッセージを処理した後 XML ペイロード ファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="9e834-120">This empty folder will receive the XML payload file after BizTalk Server has processed the EDI message.</span></span> <span data-ttu-id="9e834-121">EDI ペイロードの最終送信先である基幹業務アプリケーションをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="9e834-121">This folder simulates the line-of-business application that is the final destination of the EDI payload.</span></span>|  
|<span data-ttu-id="9e834-122">\\_MDNToFabrikam</span><span class="sxs-lookup"><span data-stu-id="9e834-122">\\_MDNToFabrikam</span></span>|<span data-ttu-id="9e834-123">この空のフォルダーは、AS2 処理後に BizTalk Server から返される MDN メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="9e834-123">This empty folder will receive the MDN message returned from BizTalk Server after AS2 processing.</span></span> <span data-ttu-id="9e834-124">Fabrikam パーティでアプリケーションをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="9e834-124">The folder simulates an application at the Fabrikam party.</span></span>|  
|<span data-ttu-id="9e834-125">\Fabrikam</span><span class="sxs-lookup"><span data-stu-id="9e834-125">\Fabrikam</span></span>|<span data-ttu-id="9e834-126">このフォルダーには、997 を _997ToFabrikam フォルダーに保存し、MDN を _MDNToFabrikam フォルダーに保存する Default.aspx ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="9e834-126">This folder contains the Default.aspx file that saves the 997 into the _997ToFabrikam folder and saves the MDN into the _MDNToFabrikam folder.</span></span>|  
|<span data-ttu-id="9e834-127">\Schemas</span><span class="sxs-lookup"><span data-stu-id="9e834-127">\Schemas</span></span>|<span data-ttu-id="9e834-128">このフォルダーには、X12_00401_864.xsd スキーマ、および BizTalk で EDI メッセージの処理に使用されるその他のスキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="9e834-128">This folder contains the X12_00401_864.xsd schema and other schemas that BizTalk uses to process the EDI message.</span></span> <span data-ttu-id="9e834-129">スキーマを展開するためにビルドおよび展開する Schemas.btproj プロジェクトもあります。</span><span class="sxs-lookup"><span data-stu-id="9e834-129">The folder also contains the Schemas.btproj project that you will build and deploy in order to deploy the schemas.</span></span>|  
|<span data-ttu-id="9e834-130">\Sender</span><span class="sxs-lookup"><span data-stu-id="9e834-130">\Sender</span></span>|<span data-ttu-id="9e834-131">このフォルダーには、Sender.exe を作成するためにビルドおよびコンパイルする Sender.csproj プロジェクトがあります。Sender.exe を使用して、(\AS2 Tutorial フォルダーにある) X12_00401_864.edi テスト メッセージを送信し、MDN を返します。</span><span class="sxs-lookup"><span data-stu-id="9e834-131">This folder contains the Sender.csproj project that you will build and compile to create Sender.exe, which you use to send the X12_00401_864.edi test message (in the \AS2 Tutorial folder) and to return the MDN.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="9e834-132">前提条件</span><span class="sxs-lookup"><span data-stu-id="9e834-132">Prerequisites</span></span>  
 <span data-ttu-id="9e834-133">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e834-133">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9e834-134">手順</span><span class="sxs-lookup"><span data-stu-id="9e834-134">Procedures</span></span>  
  
#### <a name="to-set-the-security-permission-for-the-997-and-mdn-folders"></a><span data-ttu-id="9e834-135">997 フォルダーと MDN フォルダーのセキュリティ権限を設定するには</span><span class="sxs-lookup"><span data-stu-id="9e834-135">To set the security permission for the 997 and MDN folders</span></span>  
  
1.  <span data-ttu-id="9e834-136">Windows エクスプローラで、移動、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_ 997tofabrikam フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="9e834-136">In Windows Explorer, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_997ToFabrikam folder.</span></span> <span data-ttu-id="9e834-137">右クリックし、 \\_ 997tofabrikam フォルダーをクリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-137">Right-click the \\_997ToFabrikam folder, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9e834-138">クリックして、**セキュリティ** タブをクリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-138">Click the **Security** tab, and then click **Edit**.</span></span> <span data-ttu-id="9e834-139">**権限**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-139">In the **Permissions** dialog box, click **Add**.</span></span>  
  
3.  <span data-ttu-id="9e834-140">**ユーザー、コンピューター、サービス アカウントまたはグループ**ダイアログ ボックスの オブジェクト名ペインで、入力`Everyone`、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-140">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, in the object names pane, enter `Everyone`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="9e834-141">選択**Everyone**で、**グループまたはユーザー名**ボックスで、チェック ボックスをクリックして**書き込み**(下にある、**許可**列)、で**権限** ウィンドウで、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-141">Select **Everyone** in the **Group or user names** box, click the check box for **Write** (under the **Allow** column) in the **Permissions** pane, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="9e834-142">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e834-142">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="9e834-143">次の手順を繰り返して、 \\_MDNToFabrikam フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="9e834-143">Repeat these steps for the \\_MDNToFabrikam folder.</span></span>  
  
#### <a name="to-mark-the-biztalk-server-host-as-32-bit"></a><span data-ttu-id="9e834-144">BizTalk Server ホストを 32 ビットとしてマークするには</span><span class="sxs-lookup"><span data-stu-id="9e834-144">To mark the BizTalk Server Host as 32-Bit</span></span>  
  
1.  > [!NOTE]
    >  <span data-ttu-id="9e834-145">AS2 パイプラインは、32 ビット プロセスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e834-145">The AS2 pipelines can only be used in a 32-bit process.</span></span> <span data-ttu-id="9e834-146">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が 64 ビット版のオペレーティング システムにインストールされている場合は、以下の手順を実行してホスト プロセスを 32 ビット専用としてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e834-146">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit operating system, the following steps must be performed to mark the host processes as 32-bit only.</span></span>  
  
     <span data-ttu-id="9e834-147">選択**開始**を選択**すべてのプログラム** **Microsoft BizTalk Server**、し、 **BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-147">Select **Start**, select **All Programs**, select **Microsoft BizTalk Server**, and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9e834-148">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、選択**プラットフォームの設定**、し、**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-148">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, select **Platform Settings**, and then select **Hosts**.</span></span>  
  
3.  <span data-ttu-id="9e834-149">このチュートリアルを使用し、選択するインプロセス ホストを右クリックし、詳細ウィンドウで、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-149">In the details pane, right-click the in-process host you want to use for this tutorial and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="9e834-150">**ホストのプロパティ**ダイアログ ボックスの**全般**] タブで [ **32 ビットのみ**、順にクリック **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="9e834-150">In the **Host Properties** dialog box, on the **General** tab, select **32-bit only**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="9e834-151">分離ホストについて手順 3. ～ 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9e834-151">Repeat steps 3-4 for the isolated host.</span></span>  
  
 <span data-ttu-id="9e834-152">BizTalk Server が 64 ビット版のオペレーティング システムにインストールされている場合は、32 ビットの BizTalk ホスト プロセスを使用するときに IIS も 32 ビット モードで実行されるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e834-152">If BizTalk Server is installed on a 64-bit operating system, you must also set IIS to run in 32-bit mode when using a 32-bit BizTalk host process.</span></span> <span data-ttu-id="9e834-153">IIS を設定するための手順の表示[手順 5: 取引先の Web ページを構成する](../core/step-5-configure-the-trading-partner-web-pages.md)IIS では、32 ビット ワーカー プロセスを設定することができます、アプリケーション プールごとです。</span><span class="sxs-lookup"><span data-stu-id="9e834-153">The instructions for setting IIS are presented within [Step 5: Configure the Trading Partner Web Pages](../core/step-5-configure-the-trading-partner-web-pages.md), as IIS allows you to set the 32-bit worker process on a per application pool basis.</span></span>  
  
#### <a name="to-add-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="9e834-154">BizTalk EDI アプリケーションへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="9e834-154">To add reference to the BizTalk EDI Application</span></span>  
  
1.  <span data-ttu-id="9e834-155">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**アプリケーション**ノード、EDI、BizTalk アプリケーション 1 などに使用するアプリケーションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9e834-155">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **Applications** node, right-click the application that you want to use for EDI, such as BizTalk Application 1.</span></span> <span data-ttu-id="9e834-156">指す**追加**、し、[参照] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e834-156">Point to **Add**, and then click References.</span></span>  
  
2.  <span data-ttu-id="9e834-157">**アプリケーション参照の追加**ダイアログ ボックスで、 **BizTalk EDI アプリケーション**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9e834-157">In the **Add Application Reference** dialog box, select **BizTalk EDI Application**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9e834-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="9e834-158">Next Steps</span></span>  
 <span data-ttu-id="9e834-159">サンプル X12 スキーマを展開する」の説明に従って[手順 2: を作成および展開サンプル X12 スキーマ](../core/step-2-create-and-deploy-the-sample-x12-schema.md)</span><span class="sxs-lookup"><span data-stu-id="9e834-159">You deploy the sample X12 schema as described in [Step 2: Create and Deploy the Sample X12 Schema](../core/step-2-create-and-deploy-the-sample-x12-schema.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e834-160">参照</span><span class="sxs-lookup"><span data-stu-id="9e834-160">See Also</span></span>  
 [<span data-ttu-id="9e834-161">チュートリアル 3: AS2 チュートリアル</span><span class="sxs-lookup"><span data-stu-id="9e834-161">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)
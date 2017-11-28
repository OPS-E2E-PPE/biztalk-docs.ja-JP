---
title: "BAM ポータルの構成をカスタマイズする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- BAM portal, timeout setting
- queries [BAM], timeout setting
- BAM portal, retry interval
- alerts, configuration options
- BAM portal, configuring
- BAM portal, portal banner
- clustering, NLB [BAM portal]
- BAM portal, Web.config file
- Kerberos protocol, BAM portal
- BAM portal, culture setting
- BAM portal, IIS
- IIS, BAM portal
- BAM portal, NLB cluster
- Web.config file
- BAM portal, 64-bit environments
- BAM portal, Kerberos protocol
- BAM portal, clustering
- 64-bit environments, BAM portal
- IIS, 64-bit support
- NLB system, BAM portal
- BAM portal, customizing
- configuring, BAM portal banner
- 64-bit support, IIS
- BAM portal, distributed environment
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: "47"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bad22e9bf2ecddcc50983078b21672f2c755c8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-the-bam-portal-configuration"></a><span data-ttu-id="7cff6-102">BAM ポータルの構成のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="7cff6-102">Customizing the BAM Portal Configuration</span></span>
<span data-ttu-id="7cff6-103">BAM ポータルには、構成可能なオプションが多数あります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-103">There are a number of configurable options on the BAM portal.</span></span> <span data-ttu-id="7cff6-104">次の手順では、最適なユーザー エクスペリエンスを取得する BAM ポータルを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-104">The following procedures show you how to modify the BAM portal to obtain the best user experience.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cff6-105">権限を借用した管理者以外のユーザーとしてポータルを構成するときに、資格情報の入力を求められることなく BAM ポータルの機能にアクセスするには、ログオフしてログオンし直すことが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-105">When configuring the portal as a non-administrator impersonated user, it may be necessary for you to log off and then log back on before you have access to the BAM portal features without being asked to enter your credentials.</span></span> <span data-ttu-id="7cff6-106">たとえば、次のシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-106">For example, consider the following scenario:</span></span>  
>   
>  <span data-ttu-id="7cff6-107">管理者以外の権限を借用したユーザーの Web サービスまたは BAM ポータルを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="7cff6-107">You configure the Web service or BAM portal with a non-administrator impersonated user.</span></span> <span data-ttu-id="7cff6-108">その後、Everyone グループがポータルにアクセスできないように、ポータルに対するアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-108">You then set permissions on the portal such that the Everyone group does not have access to the portal.</span></span> <span data-ttu-id="7cff6-109">PortalUsersGroup というローカル グループを作成して、そのグループをポータル ユーザー グループとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-109">You then create a local group called PortalUsersGroup and assign that group as the Portal Users group.</span></span> <span data-ttu-id="7cff6-110">つまり、そのグループのユーザーだけがポータルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-110">This means that only users in that group have access to the portal.</span></span> <span data-ttu-id="7cff6-111">BAM ポータルを構成した後、現在のユーザーをポータル ユーザー グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-111">After you have configured the BAM portal, add the current user to the Portal Users group.</span></span> <span data-ttu-id="7cff6-112">BAM ポータルを開くと、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-112">When you open the BAM portal, you will be asked for your credentials.</span></span> <span data-ttu-id="7cff6-113">ただし、ログオフしてログオンし直すと、資格情報を求められることなく BAM ポータルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-113">If you log off and log back on, however, you are able to open the BAM portal without being asked for your credentials.</span></span>  
>   
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7cff6-114">ローカル グループとユーザー アカウントを 1 台のコンピューター構成でのみサポートします。</span><span class="sxs-lookup"><span data-stu-id="7cff6-114"> supports local group and user accounts only in single computer configurations.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7cff6-115">単一および複数のコンピューター構成の両方では、ドメイン グループおよびユーザー アカウントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7cff6-115"> supports domain group and user accounts in both single and multiple computer configurations.</span></span>  
  
## <a name="running-the-bam-portal-in-a-64-bit-environment"></a><span data-ttu-id="7cff6-116">64 ビット環境での BAM ポータルの実行</span><span class="sxs-lookup"><span data-stu-id="7cff6-116">Running the BAM Portal in a 64-bit Environment</span></span>  
 <span data-ttu-id="7cff6-117">64 ビット環境でインターネット インフォメーション サービス (IIS) 6 を使用する場合、BAM ポータルを実行するには IIS を 32 ビット モードに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-117">If you are using Internet Information Services (IIS) 6 in a 64-bit environment, you must set IIS to 32-bit mode to run the BAM portal.</span></span> <span data-ttu-id="7cff6-118">モードの設定に関する詳細についてで「32 ビット バージョンの ASP.NET 1.1 と Windows の 64 ビット バージョンの ASP.NET 2.0 の 64 ビット バージョンを切り替える方法」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=61991](http://go.microsoft.com/fwlink/?LinkId=61991)です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-118">For additional information about setting the mode, see "How to switch between the 32-bit versions of ASP.NET 1.1 and the 64-bit version of ASP.NET 2.0 on a 64-bit version of Windows" at [http://go.microsoft.com/fwlink/?LinkId=61991](http://go.microsoft.com/fwlink/?LinkId=61991).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7cff6-119">IIS 7 は 32 ビット モードに設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7cff6-119">You do not have to set IIS7 to 32-bit mode.</span></span>  
  
#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a><span data-ttu-id="7cff6-120">64 ビット モードの IIS を 32 ビット モードに設定するには</span><span class="sxs-lookup"><span data-stu-id="7cff6-120">To set a 64-bit mode IIS installation to 32-bit mode</span></span>  
  
1.  <span data-ttu-id="7cff6-121">コマンド プロンプトを開き、実行、 **adsutil**コマンド。</span><span class="sxs-lookup"><span data-stu-id="7cff6-121">Open a command prompt and run the **adsutil** command.</span></span> <span data-ttu-id="7cff6-122">これを行うには、をクリックして**開始**をクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-122">To do this, click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="7cff6-123">コマンド プロンプトで、次を入力:`cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-123">Type the following at the command prompt: `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`.</span></span>  
  
3.  <span data-ttu-id="7cff6-124">コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-124">Close the command prompt.</span></span>  
  
## <a name="configuring-the-bam-portal-banner"></a><span data-ttu-id="7cff6-125">BAM ポータルのバナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-125">Configuring the BAM Portal Banner</span></span>  
 <span data-ttu-id="7cff6-126">BAM ポータル ページは、ユーザーのビジネスを表すテキストや画像を表示するように変更できます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-126">You can modify the BAM portal page to display similar text and graphics about your business:</span></span>  
  
-   <span data-ttu-id="7cff6-127">Windows Server System のロゴ (BAM ポータル ページの右上隅に配置されます)。</span><span class="sxs-lookup"><span data-stu-id="7cff6-127">The Windows Server System logo, which is located in the upper-right corner of the BAM portal page.</span></span>  
  
 <span data-ttu-id="7cff6-128">次の手順では、カスケード スタイル シート ファイル (.css ファイル) を編集して、BAM ポータルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="7cff6-128">In the following procedure you edit a cascading style sheet file (.css file) to customize the look of the BAM portal.</span></span> <span data-ttu-id="7cff6-129">指定されたクラスへの変更のみを行ってください。</span><span class="sxs-lookup"><span data-stu-id="7cff6-129">Modifications to the specified classes are the only modifications supported.</span></span> <span data-ttu-id="7cff6-130">クラスに変更を加えている途中でエラーが発生しても BAM ポータルが稼働し続けるように、変更による影響が最小限に留まるようになっています。</span><span class="sxs-lookup"><span data-stu-id="7cff6-130">As much as possible, the impact of modifications to classes has been isolated so that errors made during the modification process leave the BAM portal in a working state.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7cff6-131">データおよびポータルの機能は非表示に styles.css ファイル内の他のクラスを変更して、ポータルを使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="7cff6-131">Modifying other classes in the styles.css file will hide data and portal features, and may make the portal unusable.</span></span>  
  
#### <a name="to-configure-the-banner"></a><span data-ttu-id="7cff6-132">バナーを構成するには</span><span class="sxs-lookup"><span data-stu-id="7cff6-132">To configure the banner</span></span>  
  
1.  <span data-ttu-id="7cff6-133">BAM ポータルの web.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-133">Edit the BAM portal web.config file.</span></span> <span data-ttu-id="7cff6-134">これを行うには、をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-134">To do this, click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7cff6-135">メイン ページのクイック スタート コンテンツは、次の行を変更することで置き換え可能:\<キーを追加 ="MainPageContentUrl"value="~/MainPageContent.htm"/ >。</span><span class="sxs-lookup"><span data-stu-id="7cff6-135">The main page quick-start contents are replaceable by modifying the following line: \<add key="MainPageContentUrl" value="~/MainPageContent.htm"/>.</span></span> <span data-ttu-id="7cff6-136">変更**MainPageContent.htm**を独自の HTML ファイルを指す値フィールドにします。</span><span class="sxs-lookup"><span data-stu-id="7cff6-136">Change **MainPageContent.htm** in the value field to point to your own HTML file.</span></span> <span data-ttu-id="7cff6-137">HTML ファイルは、web.config ファイルと同じディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-137">The HTML file must be in the same directory as the web.config file.</span></span>  
  
3.  <span data-ttu-id="7cff6-138">Web.config ファイルに次の行を追加することによってテキストを識別するページを変更する:\<キーを追加"PortalTitle"の値を = ="New Identifying text"/>。</span><span class="sxs-lookup"><span data-stu-id="7cff6-138">Change the page identifying text by adding the following line to the web.config file: \<add key=”PortalTitle” value=”New Identifying text”/>.</span></span> <span data-ttu-id="7cff6-139">value フィールドを変更して、ポータルを識別するテキストを含めます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-139">Change the value field to contain the text to identify the portal.</span></span>  
  
4.  <span data-ttu-id="7cff6-140">BAM ポータルの styles.css ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-140">Edit the BAM portal styles.css file.</span></span> <span data-ttu-id="7cff6-141">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \styles.css」をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-141">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="7cff6-142">右上隅のロゴを変更します。この操作を行うには、.headerLogo div クラスを探して、background-image: url("../images/WSS_Logo.gif") という行を、作成した画像ファイルを指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-142">Change the logo in the upper-right corner by locating the .headerLogo div class and changing the following line:   background-image: url("../images/WSS_Logo.gif"); to point to the image file you have created.</span></span> <span data-ttu-id="7cff6-143">.gif 形式の画像を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7cff6-143">We recommend that you use a .gif format image.</span></span>  
  
6.  <span data-ttu-id="7cff6-144">SharePoint アイコンを変更するには、次の行には、.headerPageIcon div クラスを探して: 背景イメージ: url("../images/btsSuiteProduction.gif") です。ファイルを指す、イメージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="7cff6-144">Change the SharePoint icon by locating the .headerPageIcon div class and changing the following line: background-image: url("../images/btsSuiteProduction.gif"); to point to the image file you have created.</span></span>  
  
7.  <span data-ttu-id="7cff6-145">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-145">Save the file.</span></span>  
  
8.  <span data-ttu-id="7cff6-146">BAM ポータルを開いて、変更内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-146">Open the BAM portal to view your changes.</span></span>  
  
## <a name="modifying-the-bam-portal-webconfig-file"></a><span data-ttu-id="7cff6-147">BAM ポータルの web.config ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-147">Modifying the BAM Portal web.config File</span></span>  
 <span data-ttu-id="7cff6-148">SSL (Secure Sockets Layer) 用のエンタープライズ シングル サインオン (SSO) 証明書を使用するサーバー上に BAM ポータルが存在する場合、証明書の適切な URL を受け取るようにポータルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-148">If your BAM portal resides on a server that uses Enterprise Single Sign-On (SSO) certificates for Secure Sockets Layer (SSL), you must configure the portal to accept the proper URL for the certificate.</span></span>  
  
#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a><span data-ttu-id="7cff6-149">SSL サイトをサポートするように BAM ポータルを変更するには</span><span class="sxs-lookup"><span data-stu-id="7cff6-149">To modify the BAM portal to support SSL sites</span></span>  
  
1.  <span data-ttu-id="7cff6-150">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-150">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7cff6-151">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-151">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7cff6-152">SSL 対応のポータルの場所を指すように、ファイル内の次の 2 行を変更します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-152">Modify the following two lines in the file to point to the location of your SSL-enabled portal:</span></span>  
  
    ```  
    <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
    <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
    ```  
  
3.  <span data-ttu-id="7cff6-153">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-153">Save the file.</span></span>  
  
 <span data-ttu-id="7cff6-154">BAM ポータルでは、ポータルの構成に使用されているカルチャに従って書式設定されたデータが表示され受け取られます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-154">The BAM portal displays and accepts data formatted according to the culture for which it has been configured.</span></span> <span data-ttu-id="7cff6-155">構成は、web.config ファイルで指定されています。</span><span class="sxs-lookup"><span data-stu-id="7cff6-155">The configuration is specified in the web.config file.</span></span> <span data-ttu-id="7cff6-156">Web ポータルは、Internet Explorer から送信される「Accept Language」情報を無視します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-156">The Web portal ignores the “Accept Language” information sent by Internet Explorer.</span></span> <span data-ttu-id="7cff6-157">たとえば、日本語のカルチャ設定に設定されているし、米国を使用する BAM ポータルを構成する Internet Explorer を実行していること英語はカルチャ設定です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-157">For example, suppose that you are running Internet Explorer which is set for a Japanese culture setting and have configured the BAM portal to use the U.S. English culture setting.</span></span> <span data-ttu-id="7cff6-158">ここではデータ項目などが日付や整数が表示されます、受理、および米国に該当するルールを使用して並べ替える英語のカルチャ設定ではなく、日本語のカルチャ設定に該当するルール。</span><span class="sxs-lookup"><span data-stu-id="7cff6-158">In this case data items, such as dates and integers, will be displayed, accepted, and sorted using rules appropriate to the U.S. English culture setting rather than rules appropriate to the Japanese culture setting.</span></span> <span data-ttu-id="7cff6-159">日本語形式を使用して入力任意のカルチャに固有の情報が無効と見なされます、BAM ポータルで米国の書式設定されたデータを求めるため英語版です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-159">Any culture-specific information entered using Japanese formatting will be considered invalid by the BAM portal because it will expect data formatted for U.S. English.</span></span>  
  
 <span data-ttu-id="7cff6-160">カルチャ設定によって変化するデータの表示および書式設定に対して一貫性のある処理を実現するには、すべての BAM ポータル クライアントに適した言語を 1 つ選択します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-160">To obtain consistent handling of display and formatting of data that is variable based on the culture settings, choose a language that is appropriate for all BAM portal clients.</span></span> <span data-ttu-id="7cff6-161">このカルチャ用の BAM ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-161">Configure the BAM portal for this culture.</span></span> <span data-ttu-id="7cff6-162">Multilingual User Interface Pack をインストールして、すべてのクライアントが、選択したカルチャに設定されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-162">You must ensure that every client is set to the chosen culture by installing the Multilingual User Interface Pack.</span></span>  
  
 <span data-ttu-id="7cff6-163">英語 (米国) 以外のBAM の英語版のインストールを web.config ファイルのカルチャ パラメーターを設定するために必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-163">For non-U.S. English installations of BAM it may be necessary to set the culture parameter in the web.config file.</span></span> <span data-ttu-id="7cff6-164">この設定が必要になるのは、次の場合です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-164">Cases where you may need to do this are:</span></span>  
  
-   <span data-ttu-id="7cff6-165">日付と時刻の表示形式をローカライズする場合。</span><span class="sxs-lookup"><span data-stu-id="7cff6-165">To localize the format of date and time displays.</span></span>  
  
-   <span data-ttu-id="7cff6-166">通貨の表示形式をローカライズする場合。</span><span class="sxs-lookup"><span data-stu-id="7cff6-166">To localize the format of currency displays.</span></span>  
  
#### <a name="to-modify-the-culture-setting-of-the-portal"></a><span data-ttu-id="7cff6-167">ポータルのカルチャ設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="7cff6-167">To modify the culture setting of the portal</span></span>  
  
1.  <span data-ttu-id="7cff6-168">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-168">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7cff6-169">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-169">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7cff6-170">次の行で、適切なグローバリゼーション設定を反映するように、ファイル内のカルチャ属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-170">Modify the culture attributes in the following line in the file to reflect the appropriate globalization settings:</span></span>  
  
    ```  
    <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
    ```  
  
3.  <span data-ttu-id="7cff6-171">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-171">Save the file.</span></span>  
  
 <span data-ttu-id="7cff6-172">大量の SQL クエリの待機中にタイムアウトが発生する場合は、クエリ サービスのタイムアウト値を大きくすることが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-172">In cases where you are experiencing time-outs while waiting for large SQL queries, it may be necessary to increase the query service time-out value.</span></span>  
  
#### <a name="to-increase-the-query-service-time-out-value"></a><span data-ttu-id="7cff6-173">クエリ サービスのタイムアウト値を大きくには</span><span class="sxs-lookup"><span data-stu-id="7cff6-173">To increase the query service time-out value</span></span>  
  
1.  <span data-ttu-id="7cff6-174">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-174">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7cff6-175">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-175">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7cff6-176">QueryServiceTimeout の既定値は 45 秒です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-176">The default value for the QueryServiceTimeout is 45 seconds.</span></span> <span data-ttu-id="7cff6-177">タイムアウト間隔を増減するには、次の行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-177">Modify the value in the following line to increase or decrease the time-out interval:</span></span>  
  
    ```  
    <add key="QueryServiceTimeout" value="45" />  
    ```  
  
3.  <span data-ttu-id="7cff6-178">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-178">Save the file.</span></span>  
  
 <span data-ttu-id="7cff6-179">マルチサーバー環境では、サーバーがオフラインの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-179">In a multiserver environment there may be times when a server is offline.</span></span> <span data-ttu-id="7cff6-180">この場合、BAM ポータルが応答を停止する遅延時間が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-180">When this happens, users of the portal may experience time delays where the BAM portal stops responding.</span></span> <span data-ttu-id="7cff6-181">ユーザー エクスペリエンスを向上させるために、サーバーの再試行間隔を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-181">To improve the user experience you can modify the server retry interval.</span></span> <span data-ttu-id="7cff6-182">再試行間隔を適切な値に変更すると、いったん接続に失敗しても、BAM クエリ Web サービスでサーバーがオフラインであると見なされる時間が最短になります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-182">This creates a minimum time during which the BAM query Web service assumes that the server is offline after a connection has failed once.</span></span>  
  
 <span data-ttu-id="7cff6-183">値は、ローカル データベースがリモート データベースに接続しているときにタイムアウトした場合、データが不完全としてマークし、ローカル コンピューターは、指定した時間が経過するまで、リモート データベースへの接続にしませんを示します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-183">The value indicates that if a local database times out while trying to contact a remote database, the data is marked as incomplete and the local computer will not attempt to connect to the remote database until the specified time has elapsed.</span></span>  
  
#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a><span data-ttu-id="7cff6-184">マルチサーバー環境で分散アクティビティの再試行間隔を大きくするには</span><span class="sxs-lookup"><span data-stu-id="7cff6-184">To increase the retry interval for distributed activities in a multiserver environment</span></span>  
  
1.  <span data-ttu-id="7cff6-185">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-185">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7cff6-186">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-186">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7cff6-187">ServerRetryInterval の既定値は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-187">The default value for the ServerRetryInterval is five minutes.</span></span> <span data-ttu-id="7cff6-188">サーバーの再試行間隔を増加または減少するには、次の行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-188">Modify the value in the following line to increase or decrease the server retry interval:</span></span>  
  
    ```  
    <add key="ServerRetryInterval" value="5"/>  
    ```  
  
3.  <span data-ttu-id="7cff6-189">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-189">Save the file.</span></span>  
  
#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a><span data-ttu-id="7cff6-190">BAM ポータルに警告通知オプションを表示する方法を構成するには</span><span class="sxs-lookup"><span data-stu-id="7cff6-190">To configure how alert notification options are presented in the BAM portal</span></span>  
  
1.  <span data-ttu-id="7cff6-191">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-191">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7cff6-192">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-192">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7cff6-193">値フィールドを変更する、\<キーを追加"AlertNotificationOptions"の値を = =""/> 次の値のいずれかの有効な通知のオプションを指定するコンマ区切りの一覧を含む web.config ファイルの行。</span><span class="sxs-lookup"><span data-stu-id="7cff6-193">Modify the value field in the \<add key="AlertNotificationOptions" value="" /> line of the web.config file with a comma-delimited list specifying valid notification options with one of the following values.</span></span> <span data-ttu-id="7cff6-194">値が空の場合は、サーバーで使用可能なすべての通知オプションがサーバーから返される順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-194">An empty value displays all notification options available on the server in the order returned by the server.</span></span> <span data-ttu-id="7cff6-195">値が認識されない場合は、値が空の場合と同様に処理されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-195">Any unrecognized value is equivalent to an empty value.</span></span>  
  
    |<span data-ttu-id="7cff6-196">値</span><span class="sxs-lookup"><span data-stu-id="7cff6-196">Value</span></span>|<span data-ttu-id="7cff6-197">Description</span><span class="sxs-lookup"><span data-stu-id="7cff6-197">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="7cff6-198">ファイル, 電子メール</span><span class="sxs-lookup"><span data-stu-id="7cff6-198">File, Email</span></span>|<span data-ttu-id="7cff6-199">[ファイル] オプションと [電子メール] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-199">File and E-mail options are displayed.</span></span> <span data-ttu-id="7cff6-200">ドロップダウン リストでは、最初に [ファイル]、次に [電子メール] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-200">In the drop-down list, File is displayed first and then E-mail.</span></span>|  
    |<span data-ttu-id="7cff6-201">電子メール, ファイル</span><span class="sxs-lookup"><span data-stu-id="7cff6-201">Email, File</span></span>|<span data-ttu-id="7cff6-202">[ファイル] オプションと [電子メール] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-202">File and E-mail options are displayed.</span></span> <span data-ttu-id="7cff6-203">ドロップダウン リストでは、最初に [電子メール]、次に [ファイル] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-203">In the drop-down list, E-mail is displayed first and then File.</span></span>|  
    |<span data-ttu-id="7cff6-204">ファイル</span><span class="sxs-lookup"><span data-stu-id="7cff6-204">File</span></span>|<span data-ttu-id="7cff6-205">ポータルに、[ファイル] 通知のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-205">Only File notification is displayed in portal.</span></span>|  
    |<span data-ttu-id="7cff6-206">Email</span><span class="sxs-lookup"><span data-stu-id="7cff6-206">Email</span></span>|<span data-ttu-id="7cff6-207">ポータルに、[電子メール] 通知のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-207">Only E-mail notification is displayed in portal.</span></span>|  
  
3.  <span data-ttu-id="7cff6-208">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-208">Save the file.</span></span>  
  
## <a name="distributed-server-environments"></a><span data-ttu-id="7cff6-209">分散型サーバー環境</span><span class="sxs-lookup"><span data-stu-id="7cff6-209">Distributed Server Environments</span></span>  
 <span data-ttu-id="7cff6-210">BAM ポータルのインストールは、異なるサーバー上のアラートおよび BAM ポータルを配置する場合は、イベント ログに次のエラーが表示されます:"System.Reflection.TargetInvocationException: 呼び出しのターゲットが例外をスローしました。</span><span class="sxs-lookup"><span data-stu-id="7cff6-210">If your installation of the BAM portal places the alerts and the BAM portal on different servers, you will see the following error in the event log: "System.Reflection.TargetInvocationException: Exception has been thrown by the target of an invocation.</span></span> <span data-ttu-id="7cff6-211">---> レジストリ エントリを指定した Notification Services のインスタンスが見つかりませんでした。"</span><span class="sxs-lookup"><span data-stu-id="7cff6-211">---> The registry entries for the specified instance of Notification Services could not be found."</span></span>  
  
#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a><span data-ttu-id="7cff6-212">さまざまなサーバー上でポータルおよび警告を構成するには</span><span class="sxs-lookup"><span data-stu-id="7cff6-212">To configure the portal and alerts on different servers</span></span>  
  
1.  <span data-ttu-id="7cff6-213">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-213">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="7cff6-214">実行**C:\Program files \microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register bamalerts という名前のサーバー***\<サーバー名 >*置換 *\<サーバー名 >*サーバーの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-214">Run **C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register -name bamalerts -server***\<server name>* Replace *\<server name>* with the name of the server.</span></span>  
  
3.  <span data-ttu-id="7cff6-215"><localizedText>F5</localizedText> キーを押して、ブラウザーを更新します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-215">Press F5 to refresh your browser.</span></span>  
  
## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a><span data-ttu-id="7cff6-216">BAM ポータルによる Kerberos ネットワーク プロトコルの使用を許可する IIS の構成</span><span class="sxs-lookup"><span data-stu-id="7cff6-216">Configuring IIS to Allow the BAM Portal to Use the Kerberos Network Protocol</span></span>  
 <span data-ttu-id="7cff6-217">BAM ポータルで Kerberos ネットワーク プロトコルを使用する場合は、Web ポータルの ACL セキュリティを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-217">If you want to use the Kerberos network protocol with the BAM portal you must modify the ACL security for the Web portal.</span></span> <span data-ttu-id="7cff6-218">IIS が正しく構成されていない場合、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7cff6-218">If IIS is not configured properly, users will receive the following error:</span></span>  
  
 <span data-ttu-id="7cff6-219">HTTP エラー 401.1 - 権限がありません。 無効な資格情報により、アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="7cff6-219">HTTP Error 401.1 - Unauthorized: Access is denied due to invalid credentials.</span></span>  
  
 <span data-ttu-id="7cff6-220">IIS のセキュリティ設定を変更する方法の詳細については、サポート技術情報の記事を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922)です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-220">For additional information about modifying the IIS security settings, see the Knowledge Base article at [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922).</span></span>  
  
## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a><span data-ttu-id="7cff6-221">SQL Server 2008 の展開で BAM ポータルの集計 BAM データの表示</span><span class="sxs-lookup"><span data-stu-id="7cff6-221">Viewing Aggregate BAM Data in the BAM Portal in SQL Server 2008  Deployments</span></span>  
 <span data-ttu-id="7cff6-222">[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] を使用する展開環境で、BAM ポータルに接続しているクライアント コンピューターから BAM ポータルの集計データを表示するには、クライアント コンピューターに Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cff6-222">To view aggregate data in the BAM portal from a client computer connecting to the BAM portal when the deployment environment uses [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], you must install Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider on the client computer.</span></span> <span data-ttu-id="7cff6-223">Analysis Services がインストールされていない場合は、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cff6-223">If the analysis services are not installed users will receive the following error message:</span></span>  
  
 <span data-ttu-id="7cff6-224">サーバー  *\<servername >*通信できないか、ビジー状態です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-224">The server *\<servername>* cannot be contacted or is too busy.</span></span>  
  
 <span data-ttu-id="7cff6-225">Microsoft SQL Server 2008 用 Feature Pack をインストールするを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=70728](http://go.microsoft.com/fwlink/?LinkId=70728)です。</span><span class="sxs-lookup"><span data-stu-id="7cff6-225">To install the Feature Pack for Microsoft SQL Server 2008, see [http://go.microsoft.com/fwlink/?LinkId=70728](http://go.microsoft.com/fwlink/?LinkId=70728).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cff6-226">参照</span><span class="sxs-lookup"><span data-stu-id="7cff6-226">See Also</span></span>  
 [<span data-ttu-id="7cff6-227">BAM ポータルの計画</span><span class="sxs-lookup"><span data-stu-id="7cff6-227">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)
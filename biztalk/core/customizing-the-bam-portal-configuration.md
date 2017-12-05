---
title: "BAM ポータルの構成をカスタマイズする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: "47"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd99c0746c09f88d71e3a44e625ae5c52458f2f3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="customizing-the-bam-portal-configuration"></a><span data-ttu-id="7971f-102">BAM ポータルの構成のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="7971f-102">Customizing the BAM Portal Configuration</span></span>
<span data-ttu-id="7971f-103">BAM ポータルには、構成可能なオプションが多数あります。</span><span class="sxs-lookup"><span data-stu-id="7971f-103">There are a number of configurable options on the BAM portal.</span></span> <span data-ttu-id="7971f-104">次の手順では、最適なユーザー エクスペリエンスを取得する BAM ポータルを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7971f-104">The following procedures show you how to modify the BAM portal to obtain the best user experience.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7971f-105">権限を借用した管理者以外のユーザーとしてポータルを構成するときに、資格情報の入力を求められることなく BAM ポータルの機能にアクセスするには、ログオフしてログオンし直すことが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7971f-105">When configuring the portal as a non-administrator impersonated user, it may be necessary for you to log off and then log back on before you have access to the BAM portal features without being asked to enter your credentials.</span></span> <span data-ttu-id="7971f-106">たとえば、次のシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="7971f-106">For example, consider the following scenario:</span></span>  
>   
>  <span data-ttu-id="7971f-107">管理者以外の権限を借用したユーザーの Web サービスまたは BAM ポータルを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="7971f-107">You configure the Web service or BAM portal with a non-administrator impersonated user.</span></span> <span data-ttu-id="7971f-108">その後、Everyone グループがポータルにアクセスできないように、ポータルに対するアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="7971f-108">You then set permissions on the portal such that the Everyone group does not have access to the portal.</span></span> <span data-ttu-id="7971f-109">PortalUsersGroup というローカル グループを作成して、そのグループをポータル ユーザー グループとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7971f-109">You then create a local group called PortalUsersGroup and assign that group as the Portal Users group.</span></span> <span data-ttu-id="7971f-110">つまり、そのグループのユーザーだけがポータルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7971f-110">This means that only users in that group have access to the portal.</span></span> <span data-ttu-id="7971f-111">BAM ポータルを構成した後、現在のユーザーをポータル ユーザー グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="7971f-111">After you have configured the BAM portal, add the current user to the Portal Users group.</span></span> <span data-ttu-id="7971f-112">BAM ポータルを開くと、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="7971f-112">When you open the BAM portal, you will be asked for your credentials.</span></span> <span data-ttu-id="7971f-113">ただし、ログオフしてログオンし直すと、資格情報を求められることなく BAM ポータルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="7971f-113">If you log off and log back on, however, you are able to open the BAM portal without being asked for your credentials.</span></span>  
>   
>  <span data-ttu-id="7971f-114">BizTalk Server では、ローカル グループ アカウントとローカル ユーザー アカウントは、単一コンピューター構成でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7971f-114">BizTalk Server supports local group and user accounts only in single computer configurations.</span></span> <span data-ttu-id="7971f-115">また、ドメイン グループ アカウントとドメイン ユーザー アカウントは、単一および複数の両方のコンピュータ構成でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7971f-115">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span>  
  
## <a name="running-the-bam-portal-in-a-64-bit-environment"></a><span data-ttu-id="7971f-116">64 ビット環境での BAM ポータルの実行</span><span class="sxs-lookup"><span data-stu-id="7971f-116">Running the BAM Portal in a 64-bit Environment</span></span>  
 <span data-ttu-id="7971f-117">64 ビット環境でインターネット インフォメーション サービス (IIS) を使用している場合は、BAM ポータルを実行する 32 ビット モードに IIS を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7971f-117">If you are using Internet Information Services (IIS) in a 64-bit environment, you must set IIS to 32-bit mode to run the BAM portal.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="7971f-118">IIS 7 は 32 ビット モードに設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7971f-118">You do not have to set IIS7 to 32-bit mode.</span></span>  
  
#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a><span data-ttu-id="7971f-119">64 ビット モードの IIS を 32 ビット モードに設定するには</span><span class="sxs-lookup"><span data-stu-id="7971f-119">To set a 64-bit mode IIS installation to 32-bit mode</span></span>  
  
1.  <span data-ttu-id="7971f-120">コマンド プロンプトを開き、実行、 **adsutil**コマンド。</span><span class="sxs-lookup"><span data-stu-id="7971f-120">Open a command prompt and run the **adsutil** command.</span></span> <span data-ttu-id="7971f-121">これを行うには、をクリックして**開始**をクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="7971f-121">To do this, click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="7971f-122">コマンド プロンプトで、次を入力:`cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`です。</span><span class="sxs-lookup"><span data-stu-id="7971f-122">Type the following at the command prompt: `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`.</span></span>  
  
3.  <span data-ttu-id="7971f-123">コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7971f-123">Close the command prompt.</span></span>  
  
## <a name="configuring-the-bam-portal-banner"></a><span data-ttu-id="7971f-124">BAM ポータルのバナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7971f-124">Configuring the BAM Portal Banner</span></span>  
 <span data-ttu-id="7971f-125">BAM ポータル ページは、ユーザーのビジネスを表すテキストや画像を表示するように変更できます。</span><span class="sxs-lookup"><span data-stu-id="7971f-125">You can modify the BAM portal page to display similar text and graphics about your business:</span></span>  
  
-   <span data-ttu-id="7971f-126">Windows Server System のロゴ (BAM ポータル ページの右上隅に配置されます)。</span><span class="sxs-lookup"><span data-stu-id="7971f-126">The Windows Server System logo, which is located in the upper-right corner of the BAM portal page.</span></span>  
  
 <span data-ttu-id="7971f-127">次の手順では、カスケード スタイル シート ファイル (.css ファイル) を編集して、BAM ポータルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="7971f-127">In the following procedure you edit a cascading style sheet file (.css file) to customize the look of the BAM portal.</span></span> <span data-ttu-id="7971f-128">指定されたクラスへの変更のみを行ってください。</span><span class="sxs-lookup"><span data-stu-id="7971f-128">Modifications to the specified classes are the only modifications supported.</span></span> <span data-ttu-id="7971f-129">クラスに変更を加えている途中でエラーが発生しても BAM ポータルが稼働し続けるように、変更による影響が最小限に留まるようになっています。</span><span class="sxs-lookup"><span data-stu-id="7971f-129">As much as possible, the impact of modifications to classes has been isolated so that errors made during the modification process leave the BAM portal in a working state.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7971f-130">データおよびポータルの機能は非表示に styles.css ファイル内の他のクラスを変更して、ポータルを使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="7971f-130">Modifying other classes in the styles.css file will hide data and portal features, and may make the portal unusable.</span></span>  
  
#### <a name="to-configure-the-banner"></a><span data-ttu-id="7971f-131">バナーを構成するには</span><span class="sxs-lookup"><span data-stu-id="7971f-131">To configure the banner</span></span>  
  
1.  <span data-ttu-id="7971f-132">BAM ポータルの web.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="7971f-132">Edit the BAM portal web.config file.</span></span> <span data-ttu-id="7971f-133">これを行うには、をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7971f-133">To do this, click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7971f-134">メイン ページのクイック スタート コンテンツは、次の行を変更することで置き換え可能:\<キーを追加 ="MainPageContentUrl"value="~/MainPageContent.htm"/\>です。</span><span class="sxs-lookup"><span data-stu-id="7971f-134">The main page quick-start contents are replaceable by modifying the following line: \<add key="MainPageContentUrl" value="~/MainPageContent.htm"/\>.</span></span> <span data-ttu-id="7971f-135">変更**MainPageContent.htm**を独自の HTML ファイルを指す値フィールドにします。</span><span class="sxs-lookup"><span data-stu-id="7971f-135">Change **MainPageContent.htm** in the value field to point to your own HTML file.</span></span> <span data-ttu-id="7971f-136">HTML ファイルは、web.config ファイルと同じディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7971f-136">The HTML file must be in the same directory as the web.config file.</span></span>  
  
3.  <span data-ttu-id="7971f-137">Web.config ファイルに次の行を追加することによってテキストを識別するページを変更する:\<キーを追加 ="PortalTitle"値"New Identifying text"を =/\>です。</span><span class="sxs-lookup"><span data-stu-id="7971f-137">Change the page identifying text by adding the following line to the web.config file: \<add key=”PortalTitle” value=”New Identifying text”/\>.</span></span> <span data-ttu-id="7971f-138">value フィールドを変更して、ポータルを識別するテキストを含めます。</span><span class="sxs-lookup"><span data-stu-id="7971f-138">Change the value field to contain the text to identify the portal.</span></span>  
  
4.  <span data-ttu-id="7971f-139">BAM ポータルの styles.css ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="7971f-139">Edit the BAM portal styles.css file.</span></span> <span data-ttu-id="7971f-140">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \styles.css」をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7971f-140">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="7971f-141">右上隅のロゴを変更します。この操作を行うには、.headerLogo div クラスを探して、background-image: url("../images/WSS_Logo.gif") という行を、作成した画像ファイルを指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="7971f-141">Change the logo in the upper-right corner by locating the .headerLogo div class and changing the following line:   background-image: url("../images/WSS_Logo.gif"); to point to the image file you have created.</span></span> <span data-ttu-id="7971f-142">.gif 形式の画像を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7971f-142">We recommend that you use a .gif format image.</span></span>  
  
6.  <span data-ttu-id="7971f-143">SharePoint アイコンを変更するには、次の行には、.headerPageIcon div クラスを探して: 背景イメージ: url("../images/btsSuiteProduction.gif") です。ファイルを指す、イメージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="7971f-143">Change the SharePoint icon by locating the .headerPageIcon div class and changing the following line: background-image: url("../images/btsSuiteProduction.gif"); to point to the image file you have created.</span></span>  
  
7.  <span data-ttu-id="7971f-144">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7971f-144">Save the file.</span></span>  
  
8.  <span data-ttu-id="7971f-145">BAM ポータルを開いて、変更内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="7971f-145">Open the BAM portal to view your changes.</span></span>  
  
## <a name="modifying-the-bam-portal-webconfig-file"></a><span data-ttu-id="7971f-146">BAM ポータルの web.config ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="7971f-146">Modifying the BAM Portal web.config File</span></span>  
 <span data-ttu-id="7971f-147">SSL (Secure Sockets Layer) 用のエンタープライズ シングル サインオン (SSO) 証明書を使用するサーバー上に BAM ポータルが存在する場合、証明書の適切な URL を受け取るようにポータルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7971f-147">If your BAM portal resides on a server that uses Enterprise Single Sign-On (SSO) certificates for Secure Sockets Layer (SSL), you must configure the portal to accept the proper URL for the certificate.</span></span>  
  
#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a><span data-ttu-id="7971f-148">SSL サイトをサポートするように BAM ポータルを変更するには</span><span class="sxs-lookup"><span data-stu-id="7971f-148">To modify the BAM portal to support SSL sites</span></span>  
  
1.  <span data-ttu-id="7971f-149">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7971f-149">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7971f-150">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7971f-150">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7971f-151">SSL 対応のポータルの場所を指すように、ファイル内の次の 2 行を変更します。</span><span class="sxs-lookup"><span data-stu-id="7971f-151">Modify the following two lines in the file to point to the location of your SSL-enabled portal:</span></span>  
  
    ```  
    <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
    <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
    ```  
  
3.  <span data-ttu-id="7971f-152">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7971f-152">Save the file.</span></span>  
  
 <span data-ttu-id="7971f-153">BAM ポータルでは、ポータルの構成に使用されているカルチャに従って書式設定されたデータが表示され受け取られます。</span><span class="sxs-lookup"><span data-stu-id="7971f-153">The BAM portal displays and accepts data formatted according to the culture for which it has been configured.</span></span> <span data-ttu-id="7971f-154">構成は、web.config ファイルで指定されています。</span><span class="sxs-lookup"><span data-stu-id="7971f-154">The configuration is specified in the web.config file.</span></span> <span data-ttu-id="7971f-155">Web ポータルは、Internet Explorer から送信される「Accept Language」情報を無視します。</span><span class="sxs-lookup"><span data-stu-id="7971f-155">The Web portal ignores the “Accept Language” information sent by Internet Explorer.</span></span> <span data-ttu-id="7971f-156">たとえば、日本語のカルチャ設定に設定されているし、米国を使用する BAM ポータルを構成する Internet Explorer を実行していること英語はカルチャ設定です。</span><span class="sxs-lookup"><span data-stu-id="7971f-156">For example, suppose that you are running Internet Explorer which is set for a Japanese culture setting and have configured the BAM portal to use the U.S. English culture setting.</span></span> <span data-ttu-id="7971f-157">ここではデータ項目などが日付や整数が表示されます、受理、および米国に該当するルールを使用して並べ替える英語のカルチャ設定ではなく、日本語のカルチャ設定に該当するルール。</span><span class="sxs-lookup"><span data-stu-id="7971f-157">In this case data items, such as dates and integers, will be displayed, accepted, and sorted using rules appropriate to the U.S. English culture setting rather than rules appropriate to the Japanese culture setting.</span></span> <span data-ttu-id="7971f-158">日本語形式を使用して入力任意のカルチャに固有の情報が無効と見なされます、BAM ポータルで米国の書式設定されたデータを求めるため英語版です。</span><span class="sxs-lookup"><span data-stu-id="7971f-158">Any culture-specific information entered using Japanese formatting will be considered invalid by the BAM portal because it will expect data formatted for U.S. English.</span></span>  
  
 <span data-ttu-id="7971f-159">カルチャ設定によって変化するデータの表示および書式設定に対して一貫性のある処理を実現するには、すべての BAM ポータル クライアントに適した言語を 1 つ選択します。</span><span class="sxs-lookup"><span data-stu-id="7971f-159">To obtain consistent handling of display and formatting of data that is variable based on the culture settings, choose a language that is appropriate for all BAM portal clients.</span></span> <span data-ttu-id="7971f-160">このカルチャ用の BAM ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="7971f-160">Configure the BAM portal for this culture.</span></span> <span data-ttu-id="7971f-161">Multilingual User Interface Pack をインストールして、すべてのクライアントが、選択したカルチャに設定されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7971f-161">You must ensure that every client is set to the chosen culture by installing the Multilingual User Interface Pack.</span></span>  
  
 <span data-ttu-id="7971f-162">英語 (米国) 以外のBAM の英語版のインストールを web.config ファイルのカルチャ パラメーターを設定するために必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7971f-162">For non-U.S. English installations of BAM it may be necessary to set the culture parameter in the web.config file.</span></span> <span data-ttu-id="7971f-163">この設定が必要になるのは、次の場合です。</span><span class="sxs-lookup"><span data-stu-id="7971f-163">Cases where you may need to do this are:</span></span>  
  
-   <span data-ttu-id="7971f-164">日付と時刻の表示形式をローカライズする場合。</span><span class="sxs-lookup"><span data-stu-id="7971f-164">To localize the format of date and time displays.</span></span>  
  
-   <span data-ttu-id="7971f-165">通貨の表示形式をローカライズする場合。</span><span class="sxs-lookup"><span data-stu-id="7971f-165">To localize the format of currency displays.</span></span>  
  
#### <a name="to-modify-the-culture-setting-of-the-portal"></a><span data-ttu-id="7971f-166">ポータルのカルチャ設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="7971f-166">To modify the culture setting of the portal</span></span>  
  
1.  <span data-ttu-id="7971f-167">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7971f-167">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7971f-168">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7971f-168">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7971f-169">次の行で、適切なグローバリゼーション設定を反映するように、ファイル内のカルチャ属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="7971f-169">Modify the culture attributes in the following line in the file to reflect the appropriate globalization settings:</span></span>  
  
    ```  
    <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
    ```  
  
3.  <span data-ttu-id="7971f-170">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7971f-170">Save the file.</span></span>  
  
 <span data-ttu-id="7971f-171">大量の SQL クエリの待機中にタイムアウトが発生する場合は、クエリ サービスのタイムアウト値を大きくすることが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="7971f-171">In cases where you are experiencing time-outs while waiting for large SQL queries, it may be necessary to increase the query service time-out value.</span></span>  
  
#### <a name="to-increase-the-query-service-time-out-value"></a><span data-ttu-id="7971f-172">クエリ サービスのタイムアウト値を大きくには</span><span class="sxs-lookup"><span data-stu-id="7971f-172">To increase the query service time-out value</span></span>  
  
1.  <span data-ttu-id="7971f-173">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7971f-173">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7971f-174">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7971f-174">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7971f-175">QueryServiceTimeout の既定値は 45 秒です。</span><span class="sxs-lookup"><span data-stu-id="7971f-175">The default value for the QueryServiceTimeout is 45 seconds.</span></span> <span data-ttu-id="7971f-176">タイムアウト間隔を増減するには、次の行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7971f-176">Modify the value in the following line to increase or decrease the time-out interval:</span></span>  
  
    ```  
    <add key="QueryServiceTimeout" value="45" />  
    ```  
  
3.  <span data-ttu-id="7971f-177">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7971f-177">Save the file.</span></span>  
  
 <span data-ttu-id="7971f-178">マルチサーバー環境では、サーバーがオフラインの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7971f-178">In a multiserver environment there may be times when a server is offline.</span></span> <span data-ttu-id="7971f-179">この場合、BAM ポータルが応答を停止する遅延時間が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="7971f-179">When this happens, users of the portal may experience time delays where the BAM portal stops responding.</span></span> <span data-ttu-id="7971f-180">ユーザー エクスペリエンスを向上させるために、サーバーの再試行間隔を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7971f-180">To improve the user experience you can modify the server retry interval.</span></span> <span data-ttu-id="7971f-181">再試行間隔を適切な値に変更すると、いったん接続に失敗しても、BAM クエリ Web サービスでサーバーがオフラインであると見なされる時間が最短になります。</span><span class="sxs-lookup"><span data-stu-id="7971f-181">This creates a minimum time during which the BAM query Web service assumes that the server is offline after a connection has failed once.</span></span>  
  
 <span data-ttu-id="7971f-182">値は、ローカル データベースがリモート データベースに接続しているときにタイムアウトした場合、データが不完全としてマークし、ローカル コンピューターは、指定した時間が経過するまで、リモート データベースへの接続にしませんを示します。</span><span class="sxs-lookup"><span data-stu-id="7971f-182">The value indicates that if a local database times out while trying to contact a remote database, the data is marked as incomplete and the local computer will not attempt to connect to the remote database until the specified time has elapsed.</span></span>  
  
#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a><span data-ttu-id="7971f-183">マルチサーバー環境で分散アクティビティの再試行間隔を大きくするには</span><span class="sxs-lookup"><span data-stu-id="7971f-183">To increase the retry interval for distributed activities in a multiserver environment</span></span>  
  
1.  <span data-ttu-id="7971f-184">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7971f-184">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7971f-185">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7971f-185">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7971f-186">ServerRetryInterval の既定値は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="7971f-186">The default value for the ServerRetryInterval is five minutes.</span></span> <span data-ttu-id="7971f-187">サーバーの再試行間隔を増加または減少するには、次の行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7971f-187">Modify the value in the following line to increase or decrease the server retry interval:</span></span>  
  
    ```  
    <add key="ServerRetryInterval" value="5"/>  
    ```  
  
3.  <span data-ttu-id="7971f-188">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7971f-188">Save the file.</span></span>  
  
#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a><span data-ttu-id="7971f-189">BAM ポータルに警告通知オプションを表示する方法を構成するには</span><span class="sxs-lookup"><span data-stu-id="7971f-189">To configure how alert notification options are presented in the BAM portal</span></span>  
  
1.  <span data-ttu-id="7971f-190">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7971f-190">Open the web.config file using Notepad.</span></span> <span data-ttu-id="7971f-191">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7971f-191">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7971f-192">値フィールドを変更する、\<キーを追加"AlertNotificationOptions"の値を = =""/\>次の値のいずれかの有効な通知のオプションを指定するコンマ区切りの一覧を含む web.config ファイルの行。</span><span class="sxs-lookup"><span data-stu-id="7971f-192">Modify the value field in the \<add key="AlertNotificationOptions" value="" /\> line of the web.config file with a comma-delimited list specifying valid notification options with one of the following values.</span></span> <span data-ttu-id="7971f-193">値が空の場合は、サーバーで使用可能なすべての通知オプションがサーバーから返される順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-193">An empty value displays all notification options available on the server in the order returned by the server.</span></span> <span data-ttu-id="7971f-194">値が認識されない場合は、値が空の場合と同様に処理されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-194">Any unrecognized value is equivalent to an empty value.</span></span>  
  
    |<span data-ttu-id="7971f-195">値</span><span class="sxs-lookup"><span data-stu-id="7971f-195">Value</span></span>|<span data-ttu-id="7971f-196">Description</span><span class="sxs-lookup"><span data-stu-id="7971f-196">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="7971f-197">ファイル, 電子メール</span><span class="sxs-lookup"><span data-stu-id="7971f-197">File, Email</span></span>|<span data-ttu-id="7971f-198">[ファイル] オプションと [電子メール] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-198">File and E-mail options are displayed.</span></span> <span data-ttu-id="7971f-199">ドロップダウン リストでは、最初に [ファイル]、次に [電子メール] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-199">In the drop-down list, File is displayed first and then E-mail.</span></span>|  
    |<span data-ttu-id="7971f-200">電子メール, ファイル</span><span class="sxs-lookup"><span data-stu-id="7971f-200">Email, File</span></span>|<span data-ttu-id="7971f-201">[ファイル] オプションと [電子メール] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-201">File and E-mail options are displayed.</span></span> <span data-ttu-id="7971f-202">ドロップダウン リストでは、最初に [電子メール]、次に [ファイル] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-202">In the drop-down list, E-mail is displayed first and then File.</span></span>|  
    |<span data-ttu-id="7971f-203">ファイル</span><span class="sxs-lookup"><span data-stu-id="7971f-203">File</span></span>|<span data-ttu-id="7971f-204">ポータルに、[ファイル] 通知のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-204">Only File notification is displayed in portal.</span></span>|  
    |<span data-ttu-id="7971f-205">Email</span><span class="sxs-lookup"><span data-stu-id="7971f-205">Email</span></span>|<span data-ttu-id="7971f-206">ポータルに、[電子メール] 通知のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-206">Only E-mail notification is displayed in portal.</span></span>|  
  
3.  <span data-ttu-id="7971f-207">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7971f-207">Save the file.</span></span>  
  
## <a name="distributed-server-environments"></a><span data-ttu-id="7971f-208">分散型サーバー環境</span><span class="sxs-lookup"><span data-stu-id="7971f-208">Distributed Server Environments</span></span>  
 <span data-ttu-id="7971f-209">BAM ポータルのインストールは、異なるサーバー上のアラートおよび BAM ポータルを配置する場合は、イベント ログに次のエラーが表示されます:"System.Reflection.TargetInvocationException: 呼び出しのターゲットが例外をスローしました。</span><span class="sxs-lookup"><span data-stu-id="7971f-209">If your installation of the BAM portal places the alerts and the BAM portal on different servers, you will see the following error in the event log: "System.Reflection.TargetInvocationException: Exception has been thrown by the target of an invocation.</span></span> <span data-ttu-id="7971f-210">---> レジストリ エントリを指定した Notification Services のインスタンスが見つかりませんでした。"</span><span class="sxs-lookup"><span data-stu-id="7971f-210">---> The registry entries for the specified instance of Notification Services could not be found."</span></span>  
  
#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a><span data-ttu-id="7971f-211">さまざまなサーバー上でポータルおよび警告を構成するには</span><span class="sxs-lookup"><span data-stu-id="7971f-211">To configure the portal and alerts on different servers</span></span>  
  
1.  <span data-ttu-id="7971f-212">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7971f-212">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="7971f-213">実行**C:\Program files \microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register bamalerts という名前のサーバー***\<サーバー名\>* を置き換えます*\<サーバー名\>*サーバーの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7971f-213">Run **C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register -name bamalerts -server***\<server name\>* Replace *\<server name\>* with the name of the server.</span></span>  
  
3.  <span data-ttu-id="7971f-214"><localizedText>F5</localizedText> キーを押して、ブラウザーを更新します。</span><span class="sxs-lookup"><span data-stu-id="7971f-214">Press F5 to refresh your browser.</span></span>  
  
## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a><span data-ttu-id="7971f-215">BAM ポータルによる Kerberos ネットワーク プロトコルの使用を許可する IIS の構成</span><span class="sxs-lookup"><span data-stu-id="7971f-215">Configuring IIS to Allow the BAM Portal to Use the Kerberos Network Protocol</span></span>  
 <span data-ttu-id="7971f-216">BAM ポータルで Kerberos ネットワーク プロトコルを使用する場合は、Web ポータルの ACL セキュリティを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7971f-216">If you want to use the Kerberos network protocol with the BAM portal you must modify the ACL security for the Web portal.</span></span> <span data-ttu-id="7971f-217">IIS が正しく構成されていない場合、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7971f-217">If IIS is not configured properly, users will receive the following error:</span></span>  
  
 <span data-ttu-id="7971f-218">HTTP エラー 401.1 - 権限がありません。 無効な資格情報により、アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="7971f-218">HTTP Error 401.1 - Unauthorized: Access is denied due to invalid credentials.</span></span>  
  
 <span data-ttu-id="7971f-219">IIS のセキュリティ設定を変更する方法の詳細については、サポート技術情報の記事を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922)です。</span><span class="sxs-lookup"><span data-stu-id="7971f-219">For additional information about modifying the IIS security settings, see the Knowledge Base article at [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922).</span></span>  
  
## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a><span data-ttu-id="7971f-220">SQL Server 2008 の展開で BAM ポータルの集計 BAM データの表示</span><span class="sxs-lookup"><span data-stu-id="7971f-220">Viewing Aggregate BAM Data in the BAM Portal in SQL Server 2008  Deployments</span></span>  
 <span data-ttu-id="7971f-221">配置環境は、SQL Server 2008 を使用する場合に、BAM ポータルに接続するクライアント コンピューターから BAM ポータルの集計データを表示するには、クライアント コンピューターに Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7971f-221">To view aggregate data in the BAM portal from a client computer connecting to the BAM portal when the deployment environment uses SQL Server 2008, you must install Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider on the client computer.</span></span> <span data-ttu-id="7971f-222">Analysis Services がインストールされていない場合は、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7971f-222">If the analysis services are not installed users will receive the following error message:</span></span>  
  
 <span data-ttu-id="7971f-223">サーバー  *\<servername\>* 通信できないか、ビジー状態です。</span><span class="sxs-lookup"><span data-stu-id="7971f-223">The server *\<servername\>* cannot be contacted or is too busy.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="7971f-224">参照</span><span class="sxs-lookup"><span data-stu-id="7971f-224">See Also</span></span>  
 [<span data-ttu-id="7971f-225">BAM ポータルの計画</span><span class="sxs-lookup"><span data-stu-id="7971f-225">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)
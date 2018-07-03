---
title: BAM ポータル構成のカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f1cf1bf2cb2400d4209686e6b1d3d3b11a4461c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987339"
---
# <a name="customizing-the-bam-portal-configuration"></a><span data-ttu-id="c7988-102">BAM ポータルの構成のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c7988-102">Customizing the BAM Portal Configuration</span></span>
<span data-ttu-id="c7988-103">BAM ポータルには、構成可能なオプションが多数あります。</span><span class="sxs-lookup"><span data-stu-id="c7988-103">There are a number of configurable options on the BAM portal.</span></span> <span data-ttu-id="c7988-104">次の手順では、最適なユーザー エクスペリエンスを取得する BAM ポータルを変更する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="c7988-104">The following procedures show you how to modify the BAM portal to obtain the best user experience.</span></span>  

> [!NOTE]
>  <span data-ttu-id="c7988-105">権限を借用した管理者以外のユーザーとしてポータルを構成するときに、資格情報の入力を求められることなく BAM ポータルの機能にアクセスするには、ログオフしてログオンし直すことが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7988-105">When configuring the portal as a non-administrator impersonated user, it may be necessary for you to log off and then log back on before you have access to the BAM portal features without being asked to enter your credentials.</span></span> <span data-ttu-id="c7988-106">たとえば、次のシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="c7988-106">For example, consider the following scenario:</span></span>  
>   
>  <span data-ttu-id="c7988-107">管理者以外の権限を借用したユーザーでは、Web サービスまたは BAM ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="c7988-107">You configure the Web service or BAM portal with a non-administrator impersonated user.</span></span> <span data-ttu-id="c7988-108">その後、Everyone グループがポータルにアクセスできないように、ポータルに対するアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="c7988-108">You then set permissions on the portal such that the Everyone group does not have access to the portal.</span></span> <span data-ttu-id="c7988-109">PortalUsersGroup というローカル グループを作成して、そのグループをポータル ユーザー グループとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c7988-109">You then create a local group called PortalUsersGroup and assign that group as the Portal Users group.</span></span> <span data-ttu-id="c7988-110">つまり、そのグループのユーザーだけがポータルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c7988-110">This means that only users in that group have access to the portal.</span></span> <span data-ttu-id="c7988-111">BAM ポータルを構成した後、現在のユーザーをポータル ユーザー グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="c7988-111">After you have configured the BAM portal, add the current user to the Portal Users group.</span></span> <span data-ttu-id="c7988-112">BAM ポータルを開くと、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="c7988-112">When you open the BAM portal, you will be asked for your credentials.</span></span> <span data-ttu-id="c7988-113">ただし、ログオフしてログオンし直すと、資格情報を求められることなく BAM ポータルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c7988-113">If you log off and log back on, however, you are able to open the BAM portal without being asked for your credentials.</span></span>  
>   
>  <span data-ttu-id="c7988-114">BizTalk Server では、ローカル グループ アカウントとローカル ユーザー アカウントは、単一コンピューター構成でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7988-114">BizTalk Server supports local group and user accounts only in single computer configurations.</span></span> <span data-ttu-id="c7988-115">また、ドメイン グループ アカウントとドメイン ユーザー アカウントは、単一および複数の両方のコンピュータ構成でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7988-115">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span>  

## <a name="running-the-bam-portal-in-a-64-bit-environment"></a><span data-ttu-id="c7988-116">64 ビット環境での BAM ポータルの実行</span><span class="sxs-lookup"><span data-stu-id="c7988-116">Running the BAM Portal in a 64-bit Environment</span></span>  
 <span data-ttu-id="c7988-117">64 ビット環境でインターネット インフォメーション サービス (IIS) を使用する場合は、BAM ポータルを実行する 32 ビット モードに IIS を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7988-117">If you are using Internet Information Services (IIS) in a 64-bit environment, you must set IIS to 32-bit mode to run the BAM portal.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="c7988-118">IIS 7 は 32 ビット モードに設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c7988-118">You do not have to set IIS7 to 32-bit mode.</span></span>  

#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a><span data-ttu-id="c7988-119">64 ビット モードの IIS を 32 ビット モードに設定するには</span><span class="sxs-lookup"><span data-stu-id="c7988-119">To set a 64-bit mode IIS installation to 32-bit mode</span></span>  

1.  <span data-ttu-id="c7988-120">コマンド プロンプトを開き、実行、 **adsutil**コマンド。</span><span class="sxs-lookup"><span data-stu-id="c7988-120">Open a command prompt and run the **adsutil** command.</span></span> <span data-ttu-id="c7988-121">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="c7988-121">To do this, click **Start**, click **Run**, and then type **cmd**.</span></span>  

2.  <span data-ttu-id="c7988-122">コマンド プロンプトで、次の入力:`cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`します。</span><span class="sxs-lookup"><span data-stu-id="c7988-122">Type the following at the command prompt: `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`.</span></span>  

3.  <span data-ttu-id="c7988-123">コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c7988-123">Close the command prompt.</span></span>  

## <a name="configuring-the-bam-portal-banner"></a><span data-ttu-id="c7988-124">BAM ポータルのバナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c7988-124">Configuring the BAM Portal Banner</span></span>  
 <span data-ttu-id="c7988-125">BAM ポータル ページは、ユーザーのビジネスを表すテキストや画像を表示するように変更できます。</span><span class="sxs-lookup"><span data-stu-id="c7988-125">You can modify the BAM portal page to display similar text and graphics about your business:</span></span>  

- <span data-ttu-id="c7988-126">Windows Server System のロゴ (BAM ポータル ページの右上隅に配置されます)。</span><span class="sxs-lookup"><span data-stu-id="c7988-126">The Windows Server System logo, which is located in the upper-right corner of the BAM portal page.</span></span>  

  <span data-ttu-id="c7988-127">次の手順では、カスケード スタイル シート ファイル (.css ファイル) を編集して、BAM ポータルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="c7988-127">In the following procedure you edit a cascading style sheet file (.css file) to customize the look of the BAM portal.</span></span> <span data-ttu-id="c7988-128">指定されたクラスへの変更のみを行ってください。</span><span class="sxs-lookup"><span data-stu-id="c7988-128">Modifications to the specified classes are the only modifications supported.</span></span> <span data-ttu-id="c7988-129">クラスに変更を加えている途中でエラーが発生しても BAM ポータルが稼働し続けるように、変更による影響が最小限に留まるようになっています。</span><span class="sxs-lookup"><span data-stu-id="c7988-129">As much as possible, the impact of modifications to classes has been isolated so that errors made during the modification process leave the BAM portal in a working state.</span></span>  

> [!CAUTION]
>  <span data-ttu-id="c7988-130">データおよびポータルの機能は非表示に styles.css ファイルの他のクラスを変更して、ポータルを使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="c7988-130">Modifying other classes in the styles.css file will hide data and portal features, and may make the portal unusable.</span></span>  

#### <a name="to-configure-the-banner"></a><span data-ttu-id="c7988-131">バナーを構成するには</span><span class="sxs-lookup"><span data-stu-id="c7988-131">To configure the banner</span></span>  

1. <span data-ttu-id="c7988-132">BAM ポータルの web.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="c7988-132">Edit the BAM portal web.config file.</span></span> <span data-ttu-id="c7988-133">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c7988-133">To do this, click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="c7988-134">次の行を変更することで、メイン ページのクイック スタート コンテンツは置き換え可能な:\<追加キー ="MainPageContentUrl"value="~/MainPageContent.htm"/\>します。</span><span class="sxs-lookup"><span data-stu-id="c7988-134">The main page quick-start contents are replaceable by modifying the following line: \<add key="MainPageContentUrl" value="~/MainPageContent.htm"/\>.</span></span> <span data-ttu-id="c7988-135">変更**MainPageContent.htm**独自の HTML ファイルを指す値 フィールドにします。</span><span class="sxs-lookup"><span data-stu-id="c7988-135">Change **MainPageContent.htm** in the value field to point to your own HTML file.</span></span> <span data-ttu-id="c7988-136">HTML ファイルは、web.config ファイルと同じディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7988-136">The HTML file must be in the same directory as the web.config file.</span></span>  

3. <span data-ttu-id="c7988-137">Web.config ファイルに次の行を追加することでテキストを識別するページの変更:\<キーを追加 ="PortalTitle"value ="New Identifying text"/\>します。</span><span class="sxs-lookup"><span data-stu-id="c7988-137">Change the page identifying text by adding the following line to the web.config file: \<add key=”PortalTitle” value=”New Identifying text”/\>.</span></span> <span data-ttu-id="c7988-138">value フィールドを変更して、ポータルを識別するテキストを含めます。</span><span class="sxs-lookup"><span data-stu-id="c7988-138">Change the value field to contain the text to identify the portal.</span></span>  

4. <span data-ttu-id="c7988-139">BAM ポータルの styles.css ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="c7988-139">Edit the BAM portal styles.css file.</span></span> <span data-ttu-id="c7988-140">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css、をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c7988-140">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css, and then click **OK**.</span></span>  

5. <span data-ttu-id="c7988-141">右上隅のロゴを変更します。この操作を行うには、.headerLogo div クラスを探して、background-image: url("../images/WSS_Logo.gif") という行を、作成した画像ファイルを指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="c7988-141">Change the logo in the upper-right corner by locating the .headerLogo div class and changing the following line:   background-image: url("../images/WSS_Logo.gif"); to point to the image file you have created.</span></span> <span data-ttu-id="c7988-142">.gif 形式の画像を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7988-142">We recommend that you use a .gif format image.</span></span>  

6. <span data-ttu-id="c7988-143">SharePoint アイコンを変更、.headerPageIcon div クラスを次の行を変更する: 背景イメージ: url("../images/btsSuiteProduction.gif");作成したイメージ ファイルを指すようにします。</span><span class="sxs-lookup"><span data-stu-id="c7988-143">Change the SharePoint icon by locating the .headerPageIcon div class and changing the following line: background-image: url("../images/btsSuiteProduction.gif"); to point to the image file you have created.</span></span>  

7. <span data-ttu-id="c7988-144">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c7988-144">Save the file.</span></span>  

8. <span data-ttu-id="c7988-145">BAM ポータルを開いて、変更内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="c7988-145">Open the BAM portal to view your changes.</span></span>  

## <a name="modifying-the-bam-portal-webconfig-file"></a><span data-ttu-id="c7988-146">BAM ポータルの web.config ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="c7988-146">Modifying the BAM Portal web.config File</span></span>  
 <span data-ttu-id="c7988-147">SSL (Secure Sockets Layer) 用のエンタープライズ シングル サインオン (SSO) 証明書を使用するサーバー上に BAM ポータルが存在する場合、証明書の適切な URL を受け取るようにポータルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7988-147">If your BAM portal resides on a server that uses Enterprise Single Sign-On (SSO) certificates for Secure Sockets Layer (SSL), you must configure the portal to accept the proper URL for the certificate.</span></span>  

#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a><span data-ttu-id="c7988-148">SSL サイトをサポートするように BAM ポータルを変更するには</span><span class="sxs-lookup"><span data-stu-id="c7988-148">To modify the BAM portal to support SSL sites</span></span>  

1. <span data-ttu-id="c7988-149">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7988-149">Open the web.config file using Notepad.</span></span> <span data-ttu-id="c7988-150">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c7988-150">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="c7988-151">SSL 対応のポータルの場所を指すように、ファイル内の次の 2 行を変更します。</span><span class="sxs-lookup"><span data-stu-id="c7988-151">Modify the following two lines in the file to point to the location of your SSL-enabled portal:</span></span>  

   ```  
   <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
   <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
   ```  

3. <span data-ttu-id="c7988-152">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c7988-152">Save the file.</span></span>  

   <span data-ttu-id="c7988-153">BAM ポータルでは、ポータルの構成に使用されているカルチャに従って書式設定されたデータが表示され受け取られます。</span><span class="sxs-lookup"><span data-stu-id="c7988-153">The BAM portal displays and accepts data formatted according to the culture for which it has been configured.</span></span> <span data-ttu-id="c7988-154">構成は、web.config ファイルで指定されています。</span><span class="sxs-lookup"><span data-stu-id="c7988-154">The configuration is specified in the web.config file.</span></span> <span data-ttu-id="c7988-155">Web ポータルは、Internet Explorer から送信される「Accept Language」情報を無視します。</span><span class="sxs-lookup"><span data-stu-id="c7988-155">The Web portal ignores the “Accept Language” information sent by Internet Explorer.</span></span> <span data-ttu-id="c7988-156">たとえば、日本語のカルチャ設定に設定されており、米国を使用する BAM ポータルが構成されている Internet Explorer を実行していること英語はカルチャ設定です。</span><span class="sxs-lookup"><span data-stu-id="c7988-156">For example, suppose that you are running Internet Explorer which is set for a Japanese culture setting and have configured the BAM portal to use the U.S. English culture setting.</span></span> <span data-ttu-id="c7988-157">ここでデータ項目では、日付や整数が表示されますなどが受け入れられ、米国に該当するルールを使用して並べ替える英語のカルチャ設定ではなく、日本語のカルチャの設定に該当するルール。</span><span class="sxs-lookup"><span data-stu-id="c7988-157">In this case data items, such as dates and integers, will be displayed, accepted, and sorted using rules appropriate to the U.S. English culture setting rather than rules appropriate to the Japanese culture setting.</span></span> <span data-ttu-id="c7988-158">日本語形式を使用して入力のカルチャに固有の情報が無効と見なされる、BAM ポータルで米国の書式設定されたデータを求めるため、英語版です。</span><span class="sxs-lookup"><span data-stu-id="c7988-158">Any culture-specific information entered using Japanese formatting will be considered invalid by the BAM portal because it will expect data formatted for U.S. English.</span></span>  

   <span data-ttu-id="c7988-159">カルチャ設定によって変化するデータの表示および書式設定に対して一貫性のある処理を実現するには、すべての BAM ポータル クライアントに適した言語を 1 つ選択します。</span><span class="sxs-lookup"><span data-stu-id="c7988-159">To obtain consistent handling of display and formatting of data that is variable based on the culture settings, choose a language that is appropriate for all BAM portal clients.</span></span> <span data-ttu-id="c7988-160">このカルチャ用の BAM ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="c7988-160">Configure the BAM portal for this culture.</span></span> <span data-ttu-id="c7988-161">Multilingual User Interface Pack をインストールして、すべてのクライアントが、選択したカルチャに設定されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7988-161">You must ensure that every client is set to the chosen culture by installing the Multilingual User Interface Pack.</span></span>  

   <span data-ttu-id="c7988-162">米国以外のBAM の英語版のインストール、web.config ファイルのカルチャ パラメーターを設定するために必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7988-162">For non-U.S. English installations of BAM it may be necessary to set the culture parameter in the web.config file.</span></span> <span data-ttu-id="c7988-163">この設定が必要になるのは、次の場合です。</span><span class="sxs-lookup"><span data-stu-id="c7988-163">Cases where you may need to do this are:</span></span>  

-   <span data-ttu-id="c7988-164">日付と時刻の表示形式をローカライズする場合。</span><span class="sxs-lookup"><span data-stu-id="c7988-164">To localize the format of date and time displays.</span></span>  

-   <span data-ttu-id="c7988-165">通貨の表示形式をローカライズする場合。</span><span class="sxs-lookup"><span data-stu-id="c7988-165">To localize the format of currency displays.</span></span>  

#### <a name="to-modify-the-culture-setting-of-the-portal"></a><span data-ttu-id="c7988-166">ポータルのカルチャ設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="c7988-166">To modify the culture setting of the portal</span></span>  

1. <span data-ttu-id="c7988-167">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7988-167">Open the web.config file using Notepad.</span></span> <span data-ttu-id="c7988-168">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c7988-168">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="c7988-169">適切なグローバリゼーション設定を反映するように、ファイルに次の行でカルチャ属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="c7988-169">Modify the culture attributes in the following line in the file to reflect the appropriate globalization settings:</span></span>  

   ```  
   <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
   ```  

3. <span data-ttu-id="c7988-170">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c7988-170">Save the file.</span></span>  

   <span data-ttu-id="c7988-171">大量の SQL クエリの待機中にタイムアウトが発生する場合は、クエリ サービスのタイムアウト値を大きくすることが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c7988-171">In cases where you are experiencing time-outs while waiting for large SQL queries, it may be necessary to increase the query service time-out value.</span></span>  

#### <a name="to-increase-the-query-service-time-out-value"></a><span data-ttu-id="c7988-172">クエリ サービスのタイムアウト値を大きくには</span><span class="sxs-lookup"><span data-stu-id="c7988-172">To increase the query service time-out value</span></span>  

1. <span data-ttu-id="c7988-173">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7988-173">Open the web.config file using Notepad.</span></span> <span data-ttu-id="c7988-174">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c7988-174">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="c7988-175">QueryServiceTimeout の既定値は 45 秒です。</span><span class="sxs-lookup"><span data-stu-id="c7988-175">The default value for the QueryServiceTimeout is 45 seconds.</span></span> <span data-ttu-id="c7988-176">タイムアウト間隔を増減するには、次の行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="c7988-176">Modify the value in the following line to increase or decrease the time-out interval:</span></span>  

   ```  
   <add key="QueryServiceTimeout" value="45" />  
   ```  

3. <span data-ttu-id="c7988-177">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c7988-177">Save the file.</span></span>  

   <span data-ttu-id="c7988-178">マルチサーバー環境では、サーバーがオフラインの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c7988-178">In a multiserver environment there may be times when a server is offline.</span></span> <span data-ttu-id="c7988-179">この場合、BAM ポータルが応答を停止する遅延時間が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="c7988-179">When this happens, users of the portal may experience time delays where the BAM portal stops responding.</span></span> <span data-ttu-id="c7988-180">ユーザー エクスペリエンスを向上させるために、サーバーの再試行間隔を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c7988-180">To improve the user experience you can modify the server retry interval.</span></span> <span data-ttu-id="c7988-181">再試行間隔を適切な値に変更すると、いったん接続に失敗しても、BAM クエリ Web サービスでサーバーがオフラインであると見なされる時間が最短になります。</span><span class="sxs-lookup"><span data-stu-id="c7988-181">This creates a minimum time during which the BAM query Web service assumes that the server is offline after a connection has failed once.</span></span>  

   <span data-ttu-id="c7988-182">値は、ローカル データベースがリモート データベースに接続しているときにタイムアウトした場合、データが不完全としてマークし、ローカル コンピューターは、指定した時間が経過するまで、リモート データベースに接続しませんを示します。</span><span class="sxs-lookup"><span data-stu-id="c7988-182">The value indicates that if a local database times out while trying to contact a remote database, the data is marked as incomplete and the local computer will not attempt to connect to the remote database until the specified time has elapsed.</span></span>  

#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a><span data-ttu-id="c7988-183">マルチサーバー環境で分散アクティビティの再試行間隔を大きくするには</span><span class="sxs-lookup"><span data-stu-id="c7988-183">To increase the retry interval for distributed activities in a multiserver environment</span></span>  

1. <span data-ttu-id="c7988-184">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7988-184">Open the web.config file using Notepad.</span></span> <span data-ttu-id="c7988-185">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c7988-185">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="c7988-186">ServerRetryInterval の既定値は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="c7988-186">The default value for the ServerRetryInterval is five minutes.</span></span> <span data-ttu-id="c7988-187">サーバーの再試行間隔を増加または減少するには、次の行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="c7988-187">Modify the value in the following line to increase or decrease the server retry interval:</span></span>  

   ```  
   <add key="ServerRetryInterval" value="5"/>  
   ```  

3. <span data-ttu-id="c7988-188">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c7988-188">Save the file.</span></span>  

#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a><span data-ttu-id="c7988-189">BAM ポータルに警告通知オプションを表示する方法を構成するには</span><span class="sxs-lookup"><span data-stu-id="c7988-189">To configure how alert notification options are presented in the BAM portal</span></span>  

1. <span data-ttu-id="c7988-190">メモ帳を使用して web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7988-190">Open the web.config file using Notepad.</span></span> <span data-ttu-id="c7988-191">をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c7988-191">Click **Start**, click **Run**, type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then click **OK**.</span></span>  

2. <span data-ttu-id="c7988-192">値フィールドを変更する、\<キーを追加"AlertNotificationOptions"の値を = =""/\>次の値のいずれかの通知オプションを指定するコンマ区切りのリストを含む web.config ファイルの行。</span><span class="sxs-lookup"><span data-stu-id="c7988-192">Modify the value field in the \<add key="AlertNotificationOptions" value="" /\> line of the web.config file with a comma-delimited list specifying valid notification options with one of the following values.</span></span> <span data-ttu-id="c7988-193">値が空の場合は、サーバーで使用可能なすべての通知オプションがサーバーから返される順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-193">An empty value displays all notification options available on the server in the order returned by the server.</span></span> <span data-ttu-id="c7988-194">値が認識されない場合は、値が空の場合と同様に処理されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-194">Any unrecognized value is equivalent to an empty value.</span></span>  


   |    <span data-ttu-id="c7988-195">値</span><span class="sxs-lookup"><span data-stu-id="c7988-195">Value</span></span>    |                                              <span data-ttu-id="c7988-196">説明</span><span class="sxs-lookup"><span data-stu-id="c7988-196">Description</span></span>                                               |
   |-------------|--------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="c7988-197">ファイル, 電子メール</span><span class="sxs-lookup"><span data-stu-id="c7988-197">File, Email</span></span> | <span data-ttu-id="c7988-198">[ファイル] オプションと [電子メール] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-198">File and E-mail options are displayed.</span></span> <span data-ttu-id="c7988-199">ドロップダウン リストでは、最初に [ファイル]、次に [電子メール] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-199">In the drop-down list, File is displayed first and then E-mail.</span></span> |
   | <span data-ttu-id="c7988-200">電子メール, ファイル</span><span class="sxs-lookup"><span data-stu-id="c7988-200">Email, File</span></span> | <span data-ttu-id="c7988-201">[ファイル] オプションと [電子メール] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-201">File and E-mail options are displayed.</span></span> <span data-ttu-id="c7988-202">ドロップダウン リストでは、最初に [電子メール]、次に [ファイル] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-202">In the drop-down list, E-mail is displayed first and then File.</span></span> |
   |    <span data-ttu-id="c7988-203">ファイル</span><span class="sxs-lookup"><span data-stu-id="c7988-203">File</span></span>     |                             <span data-ttu-id="c7988-204">ポータルに、[ファイル] 通知のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-204">Only File notification is displayed in portal.</span></span>                             |
   |    <span data-ttu-id="c7988-205">Email</span><span class="sxs-lookup"><span data-stu-id="c7988-205">Email</span></span>    |                            <span data-ttu-id="c7988-206">ポータルに、[電子メール] 通知のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-206">Only E-mail notification is displayed in portal.</span></span>                            |


3. <span data-ttu-id="c7988-207">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c7988-207">Save the file.</span></span>  

## <a name="distributed-server-environments"></a><span data-ttu-id="c7988-208">分散型サーバー環境</span><span class="sxs-lookup"><span data-stu-id="c7988-208">Distributed Server Environments</span></span>  
 <span data-ttu-id="c7988-209">BAM ポータルのインストールでは、異なるサーバーで、アラートと、BAM ポータルを配置、する場合は、イベント ログに次のエラーが表示されます:"System.Reflection.TargetInvocationException: 呼び出しのターゲットが例外をスローしました。</span><span class="sxs-lookup"><span data-stu-id="c7988-209">If your installation of the BAM portal places the alerts and the BAM portal on different servers, you will see the following error in the event log: "System.Reflection.TargetInvocationException: Exception has been thrown by the target of an invocation.</span></span> <span data-ttu-id="c7988-210">---> レジストリの Notification Services の指定したインスタンスのエントリが見つかりませんでした。"</span><span class="sxs-lookup"><span data-stu-id="c7988-210">---> The registry entries for the specified instance of Notification Services could not be found."</span></span>  

#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a><span data-ttu-id="c7988-211">さまざまなサーバー上でポータルおよび警告を構成するには</span><span class="sxs-lookup"><span data-stu-id="c7988-211">To configure the portal and alerts on different servers</span></span>  

1. <span data-ttu-id="c7988-212">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7988-212">Open a command prompt.</span></span>  

2. <span data-ttu-id="c7988-213">実行**C:\Program files \microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register bamalerts という名前のサーバー**<em>\<サーバー名\></em> を置き換えます*\<サーバー名\>* サーバーの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c7988-213">Run **C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register -name bamalerts -server**<em>\<server name\></em> Replace *\<server name\>* with the name of the server.</span></span>  

3. <span data-ttu-id="c7988-214"><localizedText>F5</localizedText> キーを押して、ブラウザーを更新します。</span><span class="sxs-lookup"><span data-stu-id="c7988-214">Press F5 to refresh your browser.</span></span>  

## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a><span data-ttu-id="c7988-215">BAM ポータルによる Kerberos ネットワーク プロトコルの使用を許可する IIS の構成</span><span class="sxs-lookup"><span data-stu-id="c7988-215">Configuring IIS to Allow the BAM Portal to Use the Kerberos Network Protocol</span></span>  
 <span data-ttu-id="c7988-216">BAM ポータルを使用した Kerberos ネットワーク プロトコルを使用する場合は、Web ポータルの ACL セキュリティを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7988-216">If you want to use the Kerberos network protocol with the BAM portal you must modify the ACL security for the Web portal.</span></span> <span data-ttu-id="c7988-217">IIS が正しく構成されていない場合、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c7988-217">If IIS is not configured properly, users will receive the following error:</span></span>  

 <span data-ttu-id="c7988-218">HTTP エラー 401.1 - 権限がありません: 無効な資格情報により、アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="c7988-218">HTTP Error 401.1 - Unauthorized: Access is denied due to invalid credentials.</span></span>  

 <span data-ttu-id="c7988-219">IIS のセキュリティ設定を変更する方法の詳細についてにあるサポート技術情報の記事を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922)します。</span><span class="sxs-lookup"><span data-stu-id="c7988-219">For additional information about modifying the IIS security settings, see the Knowledge Base article at [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922).</span></span>  

## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a><span data-ttu-id="c7988-220">BAM ポータルの SQL Server 2008 の展開での集計 BAM データの表示</span><span class="sxs-lookup"><span data-stu-id="c7988-220">Viewing Aggregate BAM Data in the BAM Portal in SQL Server 2008  Deployments</span></span>  
 <span data-ttu-id="c7988-221">デプロイ環境は、SQL Server 2008 を使用する BAM ポータルに接続するクライアント コンピューターから BAM ポータルの集計データを表示するには、クライアント コンピューターの Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7988-221">To view aggregate data in the BAM portal from a client computer connecting to the BAM portal when the deployment environment uses SQL Server 2008, you must install Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider on the client computer.</span></span> <span data-ttu-id="c7988-222">Analysis Services がインストールされていない場合は、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7988-222">If the analysis services are not installed users will receive the following error message:</span></span>  

 <span data-ttu-id="c7988-223">サーバー *\<servername\>* 接続できないか、ビジー状態です。</span><span class="sxs-lookup"><span data-stu-id="c7988-223">The server *\<servername\>* cannot be contacted or is too busy.</span></span>  



## <a name="see-also"></a><span data-ttu-id="c7988-224">参照</span><span class="sxs-lookup"><span data-stu-id="c7988-224">See Also</span></span>  
 [<span data-ttu-id="c7988-225">BAM ポータルの計画</span><span class="sxs-lookup"><span data-stu-id="c7988-225">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)
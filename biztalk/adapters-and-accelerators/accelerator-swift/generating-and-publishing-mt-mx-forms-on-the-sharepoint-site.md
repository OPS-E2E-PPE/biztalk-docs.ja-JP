---
title: "生成して、SharePoint サイトで MT MX フォームを公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e2bd45c54bfc312a52d199a2f117a108207cdf5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a><span data-ttu-id="da6f3-102">生成して、SharePoint サイトで MT/MX フォームの発行</span><span class="sxs-lookup"><span data-stu-id="da6f3-102">Generating and Publishing MT/MX Forms on the SharePoint Site</span></span>
<span data-ttu-id="da6f3-103">**生成して、SharePoint サイトで MT/MX フォームを公開します。**</span><span class="sxs-lookup"><span data-stu-id="da6f3-103">**To generate and publish MT/MX forms on a SharePoint site:**</span></span>  
  
1.  <span data-ttu-id="da6f3-104">フォーム ジェネレーター ユーティリティをダウンロードし、ローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="da6f3-104">Download the Form Generator Utility and save it locally on the computer.</span></span>  
  
2.  <span data-ttu-id="da6f3-105">開く、 **FormGenerator.sln**上のダウンロード フォルダーから、ソリューションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="da6f3-105">Open the **FormGenerator.sln** from the folder downloaded above and compile the solution.</span></span>  
  
3.  <span data-ttu-id="da6f3-106">コマンド プロンプトでコンパイルされた実行可能ファイル (FormGenerator.exe) のフォルダーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="da6f3-106">At a command prompt, access the folder of compiled executable (FormGenerator.exe).</span></span> <span data-ttu-id="da6f3-107">たとえば、デバッグ モードでこのユーティリティを構築した場合は、アクセス、 **.\bin\debug**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="da6f3-107">For example, if you have built the utility in debug mode, access the **..\bin\debug** folder.</span></span>  
  
4.  <span data-ttu-id="da6f3-108">入力 FormGenerator.exe [-b] [-\<いいえ。</span><span class="sxs-lookup"><span data-stu-id="da6f3-108">Type FormGenerator.exe [-b] [-\<No.</span></span> <span data-ttu-id="da6f3-109">テンプレート フォルダーのパス >]</span><span class="sxs-lookup"><span data-stu-id="da6f3-109">of Template folder paths>]</span></span>  
  
     <span data-ttu-id="da6f3-110">`<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="da6f3-110">`<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`.</span></span> <span data-ttu-id="da6f3-111">パラメーターを新しく作成したフォルダー名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="da6f3-111">Replace the parameters with the newly-created folder names.</span></span>  
  
5.  <span data-ttu-id="da6f3-112">上記のコマンドは、MX メッセージの修復に必要なエンベロープ スキーマも生成されます。</span><span class="sxs-lookup"><span data-stu-id="da6f3-112">The above command will also generate the Envelope schema needed for MX message repair.</span></span>  
  
6.  <span data-ttu-id="da6f3-113">出力フォルダーに移動して\<DestinationFolderPath >。</span><span class="sxs-lookup"><span data-stu-id="da6f3-113">Go to output folder \<DestinationFolderPath>.</span></span> <span data-ttu-id="da6f3-114">\<DestinationFolderPath >、フォームを生成する InfoPath フォーム テンプレートのフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="da6f3-114">In \<DestinationFolderPath>, open the folder of the InfoPath form template for which you want to generate the form.</span></span> <span data-ttu-id="da6f3-115">たとえば、MT103 InfoPath フォームを作成する場合は、し、DestinationFolderPath、MT103 フォルダーを開くし、TemplateDS.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="da6f3-115">For example, if you want to generate the MT103 InfoPath form, then open the MT103 folder at the DestinationFolderPath and open the TemplateDS.sln.</span></span>  
  
7.  <span data-ttu-id="da6f3-116">ソリューション エクスプ ローラーでダブルクリックして、 **manifest.xsf**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-116">In the Solution Explorer, double click the **manifest.xsf**.</span></span> <span data-ttu-id="da6f3-117">開いたを取得するには、しばらく時間がかかります InfoPath フォームのデザイン ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="da6f3-117">It will open the design file of the InfoPath form which will take some time to get opened.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="da6f3-118">MX メッセージ manifest.xsf は、2 ~ 5 分に開く取得にかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da6f3-118">The MX messages manifest.xsf might take 2-5 minutes to get opened.</span></span>  
  
8.  <span data-ttu-id="da6f3-119">Manifest.xsf に移動**ツール]、[フォームのオプション - > セキュリティおよび信頼**メニュー オプション。</span><span class="sxs-lookup"><span data-stu-id="da6f3-119">In the manifest.xsf, go to **Tools ->Form Options-> Security and Trust** menu option.</span></span> <span data-ttu-id="da6f3-120">チェック、**完全信頼**オプションは、アクセス許可を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da6f3-120">Check the **Full Trust** option must be enabled for the permission.</span></span>  
  
9. <span data-ttu-id="da6f3-121">選択、**このフォーム テンプレートの署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="da6f3-121">Select the **Sign this form Template** checkbox.</span></span> <span data-ttu-id="da6f3-122">をクリックして**証明書を選択**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-122">Click **Select certificate**.</span></span> <span data-ttu-id="da6f3-123">これには、フォームに署名する証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="da6f3-123">In this, select the certificate with which you want to sign the form.</span></span> <span data-ttu-id="da6f3-124">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6f3-124">Click **OK**.</span></span>  
  
10. <span data-ttu-id="da6f3-125">保存**manifest.xsf**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-125">Save **manifest.xsf**.</span></span>  
  
11. <span data-ttu-id="da6f3-126">移動して**ビューのデザイン タスク]-> [**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-126">Go to **View -> Design Tasks**.</span></span> <span data-ttu-id="da6f3-127">デザイン タスク ウィンドウで、をクリックして**フォーム テンプレートの発行**オプション。</span><span class="sxs-lookup"><span data-stu-id="da6f3-127">On the Design Tasks pane, click **Publish Form Template** option.</span></span>  
  
12. <span data-ttu-id="da6f3-128">発行ウィザード ウィンドウで次のように選択します。**ネットワークの場所に** をクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-128">In the publishing wizard window, select **To a network location** and click **Next**.</span></span>  
  
13. <span data-ttu-id="da6f3-129">フォーム テンプレートのパスとファイル名 ボックスで、次のように入力します**http://localhost/sites/BASSite/Templates/\<MessageType > .xsn**および種類 **\<MessageType >**フォーム。テンプレート名 テキスト ボックスをクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-129">In the Form template path and file name textbox, type **http://localhost/sites/BASSite/Templates/\<MessageType>.xsn** and type **\<MessageType>** in the Form Template name textbox and click **Next**.</span></span>  
  
14. <span data-ttu-id="da6f3-130">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6f3-130">Click **Next**.</span></span>  
  
15. <span data-ttu-id="da6f3-131">をクリックして**発行および閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-131">Click **Publish and close**.</span></span>  
  
16. <span data-ttu-id="da6f3-132">Internet Explorer で、SharePoint サイトを開く**http://localhost/sites/bassite/templates**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-132">In the Internet Explorer, open your SharePoint site **http://localhost/sites/bassite/templates**.</span></span>  
  
17. <span data-ttu-id="da6f3-133">指す **\<MessageType >**、横にある下矢印をクリックし、をクリックして、**プロパティの編集**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-133">Point to **\<MessageType>**, click the down arrow next to it, and then click **Edit Properties**.</span></span>  
  
18. <span data-ttu-id="da6f3-134">テンプレートで:\< MessageType > ウィンドウで、[Namespace] ボックスで。</span><span class="sxs-lookup"><span data-stu-id="da6f3-134">In the Templates:\< MessageType> window, in the Namespace box:</span></span>  
  
    -   <span data-ttu-id="da6f3-135">MT InfoPath フォームを生成する場合は、入力: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**</span><span class="sxs-lookup"><span data-stu-id="da6f3-135">If you are generating MT InfoPath forms, type: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**</span></span>  
  
    -   <span data-ttu-id="da6f3-136">MX InfoPath フォームを生成する場合は、入力: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName >**</span><span class="sxs-lookup"><span data-stu-id="da6f3-136">If you are generating MX InfoPath forms, type: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName>**</span></span>  
  
         <span data-ttu-id="da6f3-137">これは、対応するテンプレートを使用してメッセージ インスタンスを特定するに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="da6f3-137">This will help in identifying the message instance with the corresponding template.</span></span>  
  
19. <span data-ttu-id="da6f3-138">をクリックして**を保存して閉じます**です。</span><span class="sxs-lookup"><span data-stu-id="da6f3-138">Click **Save and Close**.</span></span>
---
title: "BizTalk ESB Toolkit のサンプル アプリケーション |Microsoft ドキュメント"
description: "ESB Toolkit のサンプル アプリケーションをインストールし、BizTalk Server で使用する方法についてクイック リンク"
caps.latest.revision: "5"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: f9d1af5c2bc8c16ec14f8e13109f0edfe13b86cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-esb-toolkit-sample-applications"></a><span data-ttu-id="3cebb-103">BizTalk ESB Toolkit のサンプル アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3cebb-103">BizTalk ESB Toolkit Sample Applications</span></span>
<span data-ttu-id="3cebb-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB 動作、およびその用途、ESB のパイプライン コンポーネントを表示する、いくつかのサンプル アプリケーションをインストールして実行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cebb-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several sample applications that you can install and run to see how the ESB works and how it uses some of the ESB pipeline components.</span></span> <span data-ttu-id="3cebb-105">調整して、独自のアプリケーションのサンプルで使用される手法とコードを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3cebb-105">You can adapt and modify the code and techniques used in the samples for your own applications.</span></span>  
  
## <a name="install-the-sample-applications"></a><span data-ttu-id="3cebb-106">サンプル アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3cebb-106">Install the sample applications</span></span>  
  
1.  <span data-ttu-id="3cebb-107">C: ドライブのルートでプロジェクトをという名前のフォルダーを作成し、このフォルダー内で Microsoft.Practices.ESB をという名前のサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-107">Create a folder named Projects in the root of your C: drive, and create a subfolder named Microsoft.Practices.ESB within this folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3cebb-108">現在のリリースでサポートされているインストールは C:\Projects\Microsoft.Practices.ESB フォルダー内に存在するファイルです。</span><span class="sxs-lookup"><span data-stu-id="3cebb-108">In the current release, the supported installation is for the files to reside in the folder C:\Projects\Microsoft.Practices.ESB.</span></span> <span data-ttu-id="3cebb-109">サンプルに付属している BizTalk バインド ファイルは、このパスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3cebb-109">The BizTalk binding files that ship with the samples depend on this path.</span></span>  
  
2.  <span data-ttu-id="3cebb-110">インストールするときに、 [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)、という名前の指定したインストール場所に ESBSource.zip の .zip ファイルが含まれています (既定では、C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="3cebb-110">When you install the [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), it includes a .zip file called ESBSource.zip in the installation location you specified (by default, C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]).</span></span> <span data-ttu-id="3cebb-111">C:\Projects\Microsoft.Practices.ESB フォルダーに ESBSource.zip ファイルを解凍します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-111">Uncompress the ESBSource.zip file into the C:\Projects\Microsoft.Practices.ESB folder.</span></span> <span data-ttu-id="3cebb-112">フォルダーの名前を作成これ**キー**と**ソース**サンプル キーとコードとソース コード サンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cebb-112">This creates folders named **Keys** and **Source** that contain the sample key and the samples with source code.</span></span> <span data-ttu-id="3cebb-113">ソース フォルダーには、サンプル アプリケーションのソース コードとキー フォルダーには、サンプル アプリケーションでアセンブリの署名に使用される公開キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cebb-113">The Source folder contains the source code for the sample application, and the Keys folder contains the public keys used to sign the assemblies in the sample applications.</span></span>  
  
3.  <span data-ttu-id="3cebb-114">サンプルを実行する前に、サンプルが正常にインストールできるように、C:\Projects\Microsoft.Practices.ESB\ フォルダーの読み取り専用の属性を削除します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-114">Before you run the samples, remove the read-only attribute on the C:\Projects\Microsoft.Practices.ESB\ folder so that the samples install correctly.</span></span>  
  
4.  <span data-ttu-id="3cebb-115">前に PowerShell スクリプトを使用していない場合は、管理者として PowerShell を開き、次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cebb-115">If you have not used PowerShell scripts before, you must open PowerShell as an Administrator and run the following command:</span></span>  
  
    ```  
    set-executionpolicy unrestricted  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="3cebb-116">PowerShell の詳細については、次を参照してください、 [Windows PowerShell のブログ](http://go.microsoft.com/fwlink/?LinkId=187593)([http://go.microsoft.com/fwlink/?。LinkId = 187593](http://go.microsoft.com/fwlink/?LinkId=187593)) および[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId = 187594](http://go.microsoft.com/fwlink/?LinkId=187594)) MSDN のです。</span><span class="sxs-lookup"><span data-stu-id="3cebb-116">For more information about PowerShell, see the [Windows PowerShell Blog](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) and [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId=187594](http://go.microsoft.com/fwlink/?LinkId=187594)) on MSDN.</span></span>  
  
5.  <span data-ttu-id="3cebb-117">管理者としてコマンド プロンプトを開き、WCF スクリプト マップが登録されていることを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-117">Open a command prompt as an administrator and run the following command to ensure WCF script maps are registered:</span></span>  
  
    ```  
    C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="3cebb-118">サンプル コードへのアクセスを取得するために、ESBSource.zip ファイルを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cebb-118">You need to open the ESBSource.zip file in order to get an access to the Samples code.</span></span>  

## <a name="sample-applications"></a><span data-ttu-id="3cebb-119">サンプル アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3cebb-119">Sample applications</span></span>  
 <span data-ttu-id="3cebb-120">次のトピックでは、サンプル アプリケーションについて説明し、該当する場合は、追加のインストール手順を含めます。</span><span class="sxs-lookup"><span data-stu-id="3cebb-120">The following topics describe the sample applications and include additional installation instructions where applicable:</span></span>  
  
-   [<span data-ttu-id="3cebb-121">例外の管理のサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3cebb-121">Installing the Exception Management Samples</span></span>](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [<span data-ttu-id="3cebb-122">修復と再送信のカスタム例外ハンドラーのサンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3cebb-122">Running the Repair and Resubmit Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="3cebb-123">カスタム例外ハンドラーのサンプルを保持するメッセージを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3cebb-123">Running the Message Persisting Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="3cebb-124">メッセージのルーティング ESB 処理サンプル BizTalk を実行できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3cebb-124">Running the BizTalk Failed Message Routing ESB Processing Sample</span></span>](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [<span data-ttu-id="3cebb-125">インストールして、Itinerary ランプでサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-125">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [<span data-ttu-id="3cebb-126">インストールして、JMS MQRFH2 コンポーネント サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-126">Installing and Running the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="3cebb-127">インストールして、Namespace コンポーネント サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-127">Installing and Running the Namespace Component Sample</span></span>](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [<span data-ttu-id="3cebb-128">インストールして、変換サービス サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-128">Installing and Running the Transformation Service Sample</span></span>](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [<span data-ttu-id="3cebb-129">インストールして、動的な解決サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-129">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="3cebb-130">インストールして、BizTalk Operations サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-130">Installing and Running the BizTalk Operations Sample</span></span>](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [<span data-ttu-id="3cebb-131">インストールして、リゾルバー サービスのサンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3cebb-131">Installing and Running the Resolver Service Sample</span></span>](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [<span data-ttu-id="3cebb-132">インストールして、スキャッター/ギャザー サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-132">Installing and Running the Scatter-Gather Sample</span></span>](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [<span data-ttu-id="3cebb-133">インストールして、メッセージ強化サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-133">Installing and Running the Message Enrichment Sample</span></span>](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [<span data-ttu-id="3cebb-134">インストールして、複数の Web サービス サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-134">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [<span data-ttu-id="3cebb-135">インストールして、デザイナーの機能拡張のサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cebb-135">Installing and Running the Designer Extensibility Sample</span></span>](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [<span data-ttu-id="3cebb-136">例外処理サービスのサンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3cebb-136">Running the Exception Handling Service Sample</span></span>](../esb-toolkit/running-the-exception-handling-service-sample.md)
---
title: BizTalk ESB Toolkit のサンプル アプリケーション |Microsoft Docs
description: ESB Toolkit のサンプル アプリケーションをインストールして、BizTalk Server で使用する方法のクイック リンクを取得
caps.latest.revision: 5
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: 81f44a6a34493210b44916a8a88cc85ad693480c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975515"
---
# <a name="biztalk-esb-toolkit-sample-applications"></a><span data-ttu-id="bb2d5-103">BizTalk ESB Toolkit のサンプル アプリケーション</span><span class="sxs-lookup"><span data-stu-id="bb2d5-103">BizTalk ESB Toolkit Sample Applications</span></span>
<span data-ttu-id="bb2d5-104">Microsoft BizTalk ESB Toolkit には、いくつかのサンプル アプリケーション インストールして、方法、ESB の機能と、ESB の一部を使用する方法は、パイプライン コンポーネントを実行することができますにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-104">The Microsoft BizTalk ESB Toolkit includes several sample applications that you can install and run to see how the ESB works and how it uses some of the ESB pipeline components.</span></span> <span data-ttu-id="bb2d5-105">適応し、独自のアプリケーションのサンプルで使用する手法とコードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-105">You can adapt and modify the code and techniques used in the samples for your own applications.</span></span>  
  
## <a name="install-the-sample-applications"></a><span data-ttu-id="bb2d5-106">サンプル アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-106">Install the sample applications</span></span>  
  
1. <span data-ttu-id="bb2d5-107">C: ドライブのルートにプロジェクトをという名前のフォルダーを作成し、このフォルダー内で Microsoft.Practices.ESB をという名前のサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-107">Create a folder named Projects in the root of your C: drive, and create a subfolder named Microsoft.Practices.ESB within this folder.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bb2d5-108">現在のリリースで C:\Projects\Microsoft.Practices.ESB フォルダー内に存在するファイルはサポートされているインストールです。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-108">In the current release, the supported installation is for the files to reside in the folder C:\Projects\Microsoft.Practices.ESB.</span></span> <span data-ttu-id="bb2d5-109">サンプルに付属している BizTalk バインド ファイルは、このパスに依存します。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-109">The BizTalk binding files that ship with the samples depend on this path.</span></span>  
  
2. <span data-ttu-id="bb2d5-110">インストールするときに、 [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)ESBSource.zip を指定したインストール場所 (既定では C:\Program files \microsoft BizTalk ESB Toolkit) と呼ばれる .zip ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-110">When you install the [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), it includes a .zip file called ESBSource.zip in the installation location you specified (by default, C:\Program Files\Microsoft BizTalk ESB Toolkit).</span></span> <span data-ttu-id="bb2d5-111">C:\Projects\Microsoft.Practices.ESB フォルダーに ESBSource.zip ファイルを解凍します。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-111">Uncompress the ESBSource.zip file into the C:\Projects\Microsoft.Practices.ESB folder.</span></span> <span data-ttu-id="bb2d5-112">これは、フォルダーの名前を作成します。**キー**と**ソース**サンプル キーとソース コードとサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-112">This creates folders named **Keys** and **Source** that contain the sample key and the samples with source code.</span></span> <span data-ttu-id="bb2d5-113">ソース フォルダーには、サンプル アプリケーションのソース コードが含まれていて、[キー] フォルダーにサンプル アプリケーションでは、アセンブリの署名に使用される公開キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-113">The Source folder contains the source code for the sample application, and the Keys folder contains the public keys used to sign the assemblies in the sample applications.</span></span>  
  
3. <span data-ttu-id="bb2d5-114">サンプルを実行する前に、サンプルが正しくインストールするため、C:\Projects\Microsoft.Practices.ESB\ フォルダーに対する読み取り専用属性を削除します。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-114">Before you run the samples, remove the read-only attribute on the C:\Projects\Microsoft.Practices.ESB\ folder so that the samples install correctly.</span></span>  
  
4. <span data-ttu-id="bb2d5-115">前に PowerShell スクリプトを使用していない場合は、管理者として PowerShell を開き、次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-115">If you have not used PowerShell scripts before, you must open PowerShell as an Administrator and run the following command:</span></span>  
  
   ```  
   set-executionpolicy unrestricted  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="bb2d5-116">PowerShell の詳細については、次を参照してください、 [Windows PowerShell ブログ](http://go.microsoft.com/fwlink/?LinkId=187593)([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) と[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([ http://go.microsoft.com/fwlink/?LinkId=187594 。](http://go.microsoft.com/fwlink/?LinkId=187594)) msdn です。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-116">For more information about PowerShell, see the [Windows PowerShell Blog](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) and [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId=187594](http://go.microsoft.com/fwlink/?LinkId=187594)) on MSDN.</span></span>  
  
5. <span data-ttu-id="bb2d5-117">管理者としてコマンド プロンプトを開き、WCF スクリプト マップが登録されていることを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-117">Open a command prompt as an administrator and run the following command to ensure WCF script maps are registered:</span></span>  
  
   ```  
   C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
   ```  
  
> [!NOTE]
>  <span data-ttu-id="bb2d5-118">サンプル コードへのアクセスを取得するために、ESBSource.zip ファイルを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-118">You need to open the ESBSource.zip file in order to get an access to the Samples code.</span></span>  

## <a name="sample-applications"></a><span data-ttu-id="bb2d5-119">サンプル アプリケーション</span><span class="sxs-lookup"><span data-stu-id="bb2d5-119">Sample applications</span></span>  
 <span data-ttu-id="bb2d5-120">次のトピックでは、サンプル アプリケーションを記述し、該当する場合は、追加のインストール手順を含めます。</span><span class="sxs-lookup"><span data-stu-id="bb2d5-120">The following topics describe the sample applications and include additional installation instructions where applicable:</span></span>  
  
-   [<span data-ttu-id="bb2d5-121">例外管理サンプルをインストールする</span><span class="sxs-lookup"><span data-stu-id="bb2d5-121">Installing the Exception Management Samples</span></span>](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [<span data-ttu-id="bb2d5-122">カスタム例外ハンドラーの修復と再送信のサンプルを実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-122">Running the Repair and Resubmit Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="bb2d5-123">メッセージ永続化カスタム例外ハンドラーのサンプルを実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-123">Running the Message Persisting Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="bb2d5-124">BizTalk エラー メッセージ ルーティング ESB 処理サンプルを実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-124">Running the BizTalk Failed Message Routing ESB Processing Sample</span></span>](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [<span data-ttu-id="bb2d5-125">スケジュール オンランプ サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-125">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [<span data-ttu-id="bb2d5-126">JMS MQRFH2 コンポーネント サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-126">Installing and Running the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="bb2d5-127">名前空間コンポーネント サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-127">Installing and Running the Namespace Component Sample</span></span>](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [<span data-ttu-id="bb2d5-128">変換サービス サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-128">Installing and Running the Transformation Service Sample</span></span>](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [<span data-ttu-id="bb2d5-129">動的解決サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-129">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="bb2d5-130">BizTalk 操作サンプルのインストールと実行</span><span class="sxs-lookup"><span data-stu-id="bb2d5-130">Installing and Running the BizTalk Operations Sample</span></span>](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [<span data-ttu-id="bb2d5-131">リゾルバー サービス サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-131">Installing and Running the Resolver Service Sample</span></span>](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [<span data-ttu-id="bb2d5-132">スキャッター/ギャザー サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-132">Installing and Running the Scatter-Gather Sample</span></span>](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [<span data-ttu-id="bb2d5-133">メッセージ強化サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-133">Installing and Running the Message Enrichment Sample</span></span>](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [<span data-ttu-id="bb2d5-134">複数の Web サービス サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-134">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [<span data-ttu-id="bb2d5-135">デザイナー機能拡張サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-135">Installing and Running the Designer Extensibility Sample</span></span>](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [<span data-ttu-id="bb2d5-136">例外処理サービス サンプルを実行する</span><span class="sxs-lookup"><span data-stu-id="bb2d5-136">Running the Exception Handling Service Sample</span></span>](../esb-toolkit/running-the-exception-handling-service-sample.md)
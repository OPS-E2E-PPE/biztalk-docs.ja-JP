---
title: 管理 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, examples
- utilities, SSOMANAGE
- examples, SSO
- SSOMANAGE command line utility
ms.assetid: f738e344-4d81-4557-b399-68b59c413245
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32fb8d27057f1fca3b75f20aab715649fb95b8cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329076"
---
# <a name="manage-biztalk-server-sample"></a><span data-ttu-id="3dda2-102">管理 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="3dda2-102">Manage (BizTalk Server Sample)</span></span>
<span data-ttu-id="3dda2-103">シングル サインオン (SSO) 管理のサンプルは、以下の種類の管理操作を実行するために、コマンド ライン ユーティリティ ssomanage.exe で使用できる .xml ファイルを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-103">The Manage Single Sign-On (SSO) sample demonstrates how to construct .xml files that you can use with the ssomanage.exe command-line utility to perform the following types of administration operations:</span></span>  
  
- <span data-ttu-id="3dda2-104">SSO システム レベルでのグローバル情報の更新</span><span class="sxs-lookup"><span data-stu-id="3dda2-104">Update global information at the SSO system level</span></span>  
  
- <span data-ttu-id="3dda2-105">関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-105">Create affiliate applications</span></span>  
  
- <span data-ttu-id="3dda2-106">ユーザー マッピングの作成</span><span class="sxs-lookup"><span data-stu-id="3dda2-106">Create user mappings</span></span>  
  
  <span data-ttu-id="3dda2-107">エンタープライズ シングル サインオンに関する概念については、次を参照してください。[を使用して SSO](../core/using-sso.md)します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-107">For conceptual information about Enterprise Single Sign-On, see [Using SSO](../core/using-sso.md).</span></span>  
  
  <span data-ttu-id="3dda2-108">プログラムでユーザーのマッピング、関連アプリケーションの作成など、SSO を構成する方法を示すサンプルについては、次を参照してください。 [HTTPSSO (BizTalk Server サンプル)](../core/httpsso-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-108">For a sample that shows how to programmatically configure SSO, such as creating affiliate applications and user mappings, see [HTTPSSO (BizTalk Server Sample)](../core/httpsso-biztalk-server-sample.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="3dda2-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="3dda2-109">What This Sample Does</span></span>  
 <span data-ttu-id="3dda2-110">このサンプルには、上記の種類の操作のそれぞれに対する XSD とサンプル .xml ファイルのペアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dda2-110">This sample includes pairs of XSD and sample .xml files for each of these types of operations.</span></span> <span data-ttu-id="3dda2-111">サンプル .xml ファイルの値は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="3dda2-111">The values in the sample .xml files are not valid.</span></span> <span data-ttu-id="3dda2-112">各自の要件に合わせて値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dda2-112">You must make changes to the values that are appropriate to your specific requirements.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="3dda2-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="3dda2-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="3dda2-114">*\<パスのサンプル\>* \SSO\Manage\\</span><span class="sxs-lookup"><span data-stu-id="3dda2-114">*\<Samples Path\>* \SSO\Manage\\</span></span>  
  
 <span data-ttu-id="3dda2-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="3dda2-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="3dda2-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="3dda2-116">File(s)</span></span>|<span data-ttu-id="3dda2-117">説明</span><span class="sxs-lookup"><span data-stu-id="3dda2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3dda2-118">AffiliateApplication.xml、GlobalInfo.xml、UserMapping.xml</span><span class="sxs-lookup"><span data-stu-id="3dda2-118">AffiliateApplication.xml, GlobalInfo.xml, UserMapping.xml</span></span>|<span data-ttu-id="3dda2-119">コマンド ライン ユーティリティ ssomanage.exe に引数を渡すサンプル .xml ファイルです。変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="3dda2-119">Sample .xml files that you can, after modification, pass as arguments to the command-line utility ssomanage.exe.</span></span>|  
|<span data-ttu-id="3dda2-120">AffiliateApplication.xsd、GlobalInfo.xsd、UserMapping.xsd</span><span class="sxs-lookup"><span data-stu-id="3dda2-120">AffiliateApplication.xsd, GlobalInfo.xsd, UserMapping.xsd</span></span>|<span data-ttu-id="3dda2-121">可能な要素と属性を完全に記述した、対応する .xml ファイルのスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="3dda2-121">Schema files for the corresponding .xml files, providing complete descriptions of their possible elements and attributes.</span></span> <span data-ttu-id="3dda2-122">これらのファイルを使用して、他のソースから受信した、対応する .xml ファイルを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="3dda2-122">You can use these files to validate corresponding .xml files received from other sources.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="3dda2-123">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="3dda2-123">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="3dda2-124">このサンプルは XSD (XML Schema Definition) 言語のファイルと .xml ファイルのみで構成され、後者は変更してコマンド ライン ユーティリティ ssomanage.exe に渡すため、このサンプルでビルドが必要なものはありません。</span><span class="sxs-lookup"><span data-stu-id="3dda2-124">Because this sample consists of only XML Schema definition language (XSD) and .xml files, the latter of which you can modify and then pass to the command-line utility ssomanage.exe, there is nothing to build in this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="3dda2-125">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="3dda2-125">Running This Sample</span></span>  
 <span data-ttu-id="3dda2-126">このサンプルには、以下の 3 つの異なるモードでコマンド ライン ユーティリティ ssomanage.exe を実行するための、サンプルの .xml ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dda2-126">This sample includes sample .xml files for running the command-line utility ssomanage.exe in the following three different modes:</span></span>  
  
- <span data-ttu-id="3dda2-127">**SSO システム レベルのグローバル情報を更新します。**</span><span class="sxs-lookup"><span data-stu-id="3dda2-127">**Update global information at the SSO system level.**</span></span> <span data-ttu-id="3dda2-128">この種の操作を実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-128">To perform this type of operation, perform the following steps:</span></span>  
  
  1. <span data-ttu-id="3dda2-129">各自の構成に合わせてファイル GlobalInfo.xml を編集します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-129">Edit the file GlobalInfo.xml as required for your specific configuration.</span></span>  
  
  2. <span data-ttu-id="3dda2-130">以下のように、適切な引数を指定してコマンド ライン ユーティリティ ssomanage.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-130">Run the ssomanage.exe command-line utility with the appropriate arguments, as follows:</span></span>  
  
     ```  
     ssomanage –updatedb GlobalInfo.xml  
     ```  
  
     <span data-ttu-id="3dda2-131">環境に合わせてファイル GlobalInfo.xml 内の値を編集します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-131">Ensure that you edit the values in the file GlobalInfo.xml to match your environment.</span></span> <span data-ttu-id="3dda2-132">たとえば、SSO 管理者アカウントは有効な Windows アカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dda2-132">For example, the SSO Admin account must be a valid Windows account.</span></span> <span data-ttu-id="3dda2-133">SSO 管理者アカウントと SSO 関連管理者アカウントの両方が、Windows のグローバル ドメイン グループ アカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dda2-133">Both the SSO Admin account and SSO Affiliate Admin account must be Windows Global Domain Group accounts.</span></span>  
  
- <span data-ttu-id="3dda2-134">**関連アプリケーションを作成します。**</span><span class="sxs-lookup"><span data-stu-id="3dda2-134">**Create affiliate applications.**</span></span> <span data-ttu-id="3dda2-135">この種の操作を実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-135">To perform this type of operation, perform the following steps:</span></span>  
  
- <span data-ttu-id="3dda2-136">各自の構成要件に合わせてファイル AffiliateApplication.xml を編集します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-136">Edit the file AffiliateApplication.xml as required for your specific configuration.</span></span>  
  
  - <span data-ttu-id="3dda2-137">次のように、適切な引数でコマンド ライン ユーティリティ ssomanage.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-137">Run the command-line utility ssomanage.exe with the appropriate arguments, as follows:</span></span>  
  
    ```  
    ssomanage –createapps AffiliateApplication.xml  
    ```  
  
    <span data-ttu-id="3dda2-138">同時に複数の関連アプリケーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3dda2-138">You can create more than one affiliate application at the same time.</span></span>  
  
- <span data-ttu-id="3dda2-139">**ユーザー マッピングを作成します。**</span><span class="sxs-lookup"><span data-stu-id="3dda2-139">**Create user mappings.**</span></span> <span data-ttu-id="3dda2-140">この種の操作を実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-140">To perform this type of operation, perform the following steps:</span></span>  
  
  1. <span data-ttu-id="3dda2-141">各自の構成に合わせてファイル UserMapping.xml を編集します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-141">Edit the file UserMapping.xmlas required for your specific configuration.</span></span>  
  
  2. <span data-ttu-id="3dda2-142">次のように、適切な引数でコマンド ライン ユーティリティ ssomanage.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="3dda2-142">Run the command-line utility ssomanage.exe with the appropriate arguments, as follows:</span></span>  
  
     ```  
     ssomanage –createmappings UserMapping.xml  
     ```  
  
     <span data-ttu-id="3dda2-143">1 つ以上の関連アプリケーションに対して同時に複数のマッピングを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3dda2-143">You can create more than one mapping for one or more affiliate applications at the same time.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="3dda2-144">コメント</span><span class="sxs-lookup"><span data-stu-id="3dda2-144">Comments</span></span>  
 <span data-ttu-id="3dda2-145">このサンプルに付属しているサンプル .xml ファイルを変更した後、特に変更によってファイルに機密情報を追加する場合は、これらのファイルをファイル システム内で十分に保護してください。</span><span class="sxs-lookup"><span data-stu-id="3dda2-145">After making changes to the sample .xml files provided with this sample, especially where such changes involve including sensitive information in the files, ensure that these files are well protected in your file system.</span></span> <span data-ttu-id="3dda2-146">たとえば、これらのファイルを不注意で共有ファイルに格納しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="3dda2-146">For example, ensure that they are not inadvertently placed in a folder that is shared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dda2-147">参照</span><span class="sxs-lookup"><span data-stu-id="3dda2-147">See Also</span></span>  
 [<span data-ttu-id="3dda2-148">SSO (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="3dda2-148">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)
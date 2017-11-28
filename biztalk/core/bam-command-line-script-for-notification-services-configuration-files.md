---
title: "サービス構成ファイルの通知用の BAM コマンド ライン スクリプト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa4a460-58f9-439d-af28-0a9cb2288236
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6950326994e99dcbc2ecff49a36f7441f3c219d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a><span data-ttu-id="4a6fb-102">Notification Services 構成ファイル用の BAM コマンド ライン スクリプト</span><span class="sxs-lookup"><span data-stu-id="4a6fb-102">BAM Command-Line Script for Notification Services Configuration Files</span></span>
<span data-ttu-id="4a6fb-103">管理者は、ProcessBamNSFiles.vbs スクリプトを使用して、BAM 警告の SQL Server Notification Services の動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-103">Administrators use the ProcessBamNSFiles.vbs script to customize the behavior of SQL Server Notification Services for BAM alerts.</span></span> <span data-ttu-id="4a6fb-104">このスクリプトを使用して、Notification Services のアプリケーション定義ファイル (ADF) や Notification Services の構成ファイルを取得できます。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-104">You can use the script to obtain the Notification Services application definition file (ADF) and Notification Services configuration file.</span></span> <span data-ttu-id="4a6fb-105">これらのファイルに変更を加えた後、スクリプトを使って変更内容を適用できます。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-105">These files can be modified and then the script can be used to apply the changes.</span></span>  
  
 <span data-ttu-id="4a6fb-106">スクリプトは、通常のコマンド プロンプトからではなく、Notification Services のコマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-106">You run the script from a Notification Services command prompt and not from a typical command prompt.</span></span> <span data-ttu-id="4a6fb-107">通常のコマンド プロンプトからスクリプトを実行すると、スクリプトが適切に実行されません。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-107">Running the script from a typical command prompt will cause the script to execute incorrectly.</span></span> <span data-ttu-id="4a6fb-108">スクリプトの実行時には、すべてのパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-108">When running the script all parameters are mandatory.</span></span>  
  
## <a name="get-command"></a><span data-ttu-id="4a6fb-109">Get コマンド</span><span class="sxs-lookup"><span data-stu-id="4a6fb-109">Get command</span></span>  
 <span data-ttu-id="4a6fb-110">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="4a6fb-110">**Usage**</span></span>  
  
 <span data-ttu-id="4a6fb-111">**cscript ProcessBamNSFiles-取得\<構成ファイルのパス > \<ADF ファイルのパス >\<プライマリ インポート サーバー >\<プライマリ インポート データベース >**</span><span class="sxs-lookup"><span data-stu-id="4a6fb-111">**cscript ProcessBamNSFiles -Get \<configuration file path> \<ADF file path>  \<primary import server> \<primary import database>**</span></span>  
  
|<span data-ttu-id="4a6fb-112">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a6fb-112">Parameter</span></span>|<span data-ttu-id="4a6fb-113">Description</span><span class="sxs-lookup"><span data-stu-id="4a6fb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a6fb-114">構成ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="4a6fb-114">configuration file path</span></span>|<span data-ttu-id="4a6fb-115">構成ファイルの保存先の名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-115">Specifies the name and location in which to store the configuration file.</span></span>|  
|<span data-ttu-id="4a6fb-116">ADF ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="4a6fb-116">ADF file path</span></span>|<span data-ttu-id="4a6fb-117">ADF ファイルの保存先の名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-117">Specifies the name and location in which to store the ADF file.</span></span>|  
|<span data-ttu-id="4a6fb-118">プライマリ インポート サーバー</span><span class="sxs-lookup"><span data-stu-id="4a6fb-118">primary import server</span></span>|<span data-ttu-id="4a6fb-119">BAM プライマリ インポート データベースが格納されているコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-119">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="4a6fb-120">プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="4a6fb-120">primary import database</span></span>|<span data-ttu-id="4a6fb-121">BAM プライマリ インポート データベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-121">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="4a6fb-122">BAM プライマリ インポート データベースから Notification Services の構成ファイルおよびアプリケーション定義ファイルを取得し、それらを指定されたパスに保存します。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-122">Retrieves the Notification Services configuration and application definition files from the BAM Primary Import database and saves them to specified paths.</span></span>  
  
## <a name="update-command"></a><span data-ttu-id="4a6fb-123">Update コマンド</span><span class="sxs-lookup"><span data-stu-id="4a6fb-123">Update command</span></span>  
 <span data-ttu-id="4a6fb-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="4a6fb-124">**Usage**</span></span>  
  
 <span data-ttu-id="4a6fb-125">**cscript ProcessBamNSFiles-更新\<configfilepath >\<構成ファイルのパス > \<primaryimport サーバー >\<プライマリ インポート データベース >**</span><span class="sxs-lookup"><span data-stu-id="4a6fb-125">**cscript ProcessBamNSFiles -Update \<configfilepath> \<adffilepath>  \<primaryimport server> \<primary import db>**</span></span>  
  
|<span data-ttu-id="4a6fb-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a6fb-126">Parameter</span></span>|<span data-ttu-id="4a6fb-127">Description</span><span class="sxs-lookup"><span data-stu-id="4a6fb-127">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a6fb-128">構成ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="4a6fb-128">configuration file path</span></span>|<span data-ttu-id="4a6fb-129">最新の Notification Services 構成ファイルの名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-129">Specifies the name and location from which to update the Notification Services configuration information.</span></span>|  
|<span data-ttu-id="4a6fb-130">ADF ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="4a6fb-130">ADF file path</span></span>|<span data-ttu-id="4a6fb-131">最新の ADF ファイルの名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-131">Specifies the name and location from which to update the ADF information.</span></span>|  
|<span data-ttu-id="4a6fb-132">プライマリ インポート サーバー</span><span class="sxs-lookup"><span data-stu-id="4a6fb-132">primary import server</span></span>|<span data-ttu-id="4a6fb-133">BAM プライマリ インポート データベースが格納されているコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-133">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="4a6fb-134">プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="4a6fb-134">primary import database</span></span>|<span data-ttu-id="4a6fb-135">BAM プライマリ インポート データベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-135">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="4a6fb-136">Notification Services を呼び出し、指定されたファイルの情報で設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-136">Calls Notification Services and updates the settings with the information in the specified files.</span></span> <span data-ttu-id="4a6fb-137">構成ファイルと ADF ファイルは、BAM プライマリ インポート データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-137">The configuration and ADF files are stored in the BAM Primary Import database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6fb-138">参照</span><span class="sxs-lookup"><span data-stu-id="4a6fb-138">See Also</span></span>  
 [<span data-ttu-id="4a6fb-139">BAM コマンド ライン ツール</span><span class="sxs-lookup"><span data-stu-id="4a6fb-139">BAM Command-Line Tools</span></span>](../core/bam-command-line-tools.md)
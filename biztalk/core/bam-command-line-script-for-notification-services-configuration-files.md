---
title: 通知用の BAM コマンド ライン スクリプト サービス構成ファイル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa4a460-58f9-439d-af28-0a9cb2288236
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf28ea2c1ff0defd7696b548ff86bc050259925d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528716"
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a><span data-ttu-id="381a7-102">サービス構成ファイルの通知用の BAM コマンド ライン スクリプト</span><span class="sxs-lookup"><span data-stu-id="381a7-102">BAM Command-Line Script for Notification Services Configuration Files</span></span>
<span data-ttu-id="381a7-103">管理者は、ProcessBamNSFiles.vbs スクリプトを使用して、BAM 警告用 SQL Server Notification Services の動作をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="381a7-103">Administrators use the ProcessBamNSFiles.vbs script to customize the behavior of SQL Server Notification Services for BAM alerts.</span></span> <span data-ttu-id="381a7-104">Notification Services application 定義ファイル (ADF) と Notification Services 構成ファイルを取得するのにスクリプトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="381a7-104">You can use the script to obtain the Notification Services application definition file (ADF) and Notification Services configuration file.</span></span> <span data-ttu-id="381a7-105">これらのファイルを変更して、スクリプトを使用して、変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="381a7-105">These files can be modified and then the script can be used to apply the changes.</span></span>  
  
 <span data-ttu-id="381a7-106">通常コマンド プロンプトではなく、Notification Services コマンド プロンプトからスクリプトを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="381a7-106">You run the script from a Notification Services command prompt and not from a typical command prompt.</span></span> <span data-ttu-id="381a7-107">一般的なコマンド プロンプトからスクリプトを実行すると、正しく実行するスクリプトが。</span><span class="sxs-lookup"><span data-stu-id="381a7-107">Running the script from a typical command prompt will cause the script to execute incorrectly.</span></span> <span data-ttu-id="381a7-108">スクリプトを実行している場合は、すべてのパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="381a7-108">When running the script all parameters are mandatory.</span></span>  
  
## <a name="get-command"></a><span data-ttu-id="381a7-109">Get コマンド</span><span class="sxs-lookup"><span data-stu-id="381a7-109">Get command</span></span>  
 <span data-ttu-id="381a7-110">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="381a7-110">**Usage**</span></span>  
  
 <span data-ttu-id="381a7-111">**cscript ProcessBamNSFiles-取得\<構成ファイルのパス\> \<ADF ファイルのパス\>\<プライマリ インポート サーバー\> \<プライマリ インポート データベース  \>**</span><span class="sxs-lookup"><span data-stu-id="381a7-111">**cscript ProcessBamNSFiles -Get \<configuration file path\> \<ADF file path\>  \<primary import server\> \<primary import database\>**</span></span>  
  
|<span data-ttu-id="381a7-112">パラメーター</span><span class="sxs-lookup"><span data-stu-id="381a7-112">Parameter</span></span>|<span data-ttu-id="381a7-113">説明</span><span class="sxs-lookup"><span data-stu-id="381a7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="381a7-114">構成ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="381a7-114">configuration file path</span></span>|<span data-ttu-id="381a7-115">構成ファイルを格納する場所と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="381a7-115">Specifies the name and location in which to store the configuration file.</span></span>|  
|<span data-ttu-id="381a7-116">ADF ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="381a7-116">ADF file path</span></span>|<span data-ttu-id="381a7-117">ADF ファイルを格納する場所と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="381a7-117">Specifies the name and location in which to store the ADF file.</span></span>|  
|<span data-ttu-id="381a7-118">プライマリ インポート サーバー</span><span class="sxs-lookup"><span data-stu-id="381a7-118">primary import server</span></span>|<span data-ttu-id="381a7-119">BAM プライマリ インポート データベースが格納されているコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="381a7-119">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="381a7-120">プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="381a7-120">primary import database</span></span>|<span data-ttu-id="381a7-121">BAM プライマリ インポート データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="381a7-121">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="381a7-122">指定したパスを取得、Notification Services の構成およびアプリケーション定義ファイルを BAM プライマリ インポート データベースからとするために保存します。</span><span class="sxs-lookup"><span data-stu-id="381a7-122">Retrieves the Notification Services configuration and application definition files from the BAM Primary Import database and saves them to specified paths.</span></span>  
  
## <a name="update-command"></a><span data-ttu-id="381a7-123">Update コマンド</span><span class="sxs-lookup"><span data-stu-id="381a7-123">Update command</span></span>  
 <span data-ttu-id="381a7-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="381a7-124">**Usage**</span></span>  
  
 <span data-ttu-id="381a7-125">**cscript ProcessBamNSFiles-Update \<configfilepath\> \<構成\>\<primaryimport server\> \<プライマリ インポート db  \>**</span><span class="sxs-lookup"><span data-stu-id="381a7-125">**cscript ProcessBamNSFiles -Update \<configfilepath\> \<adffilepath\>  \<primaryimport server\> \<primary import db\>**</span></span>  
  
|<span data-ttu-id="381a7-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="381a7-126">Parameter</span></span>|<span data-ttu-id="381a7-127">説明</span><span class="sxs-lookup"><span data-stu-id="381a7-127">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="381a7-128">構成ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="381a7-128">configuration file path</span></span>|<span data-ttu-id="381a7-129">Notification Services の構成情報を更新する元の場所と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="381a7-129">Specifies the name and location from which to update the Notification Services configuration information.</span></span>|  
|<span data-ttu-id="381a7-130">ADF ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="381a7-130">ADF file path</span></span>|<span data-ttu-id="381a7-131">ADF の情報を更新する元の場所と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="381a7-131">Specifies the name and location from which to update the ADF information.</span></span>|  
|<span data-ttu-id="381a7-132">プライマリ インポート サーバー</span><span class="sxs-lookup"><span data-stu-id="381a7-132">primary import server</span></span>|<span data-ttu-id="381a7-133">BAM プライマリ インポート データベースが格納されているコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="381a7-133">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="381a7-134">プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="381a7-134">primary import database</span></span>|<span data-ttu-id="381a7-135">BAM プライマリ インポート データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="381a7-135">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="381a7-136">通知サービスを呼び出すし、指定されたファイルの情報と設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="381a7-136">Calls Notification Services and updates the settings with the information in the specified files.</span></span> <span data-ttu-id="381a7-137">構成ファイルと ADF ファイルは、BAM プライマリ インポート データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="381a7-137">The configuration and ADF files are stored in the BAM Primary Import database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381a7-138">参照</span><span class="sxs-lookup"><span data-stu-id="381a7-138">See Also</span></span>  
 [<span data-ttu-id="381a7-139">BAM コマンド ライン ツール</span><span class="sxs-lookup"><span data-stu-id="381a7-139">BAM Command-Line Tools</span></span>](../core/bam-command-line-tools.md)
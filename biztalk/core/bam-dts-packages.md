---
title: "BAM DTS パッケージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 105d1b42848b73505d9a82df07693111708ce802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-dts-packages"></a><span data-ttu-id="8b1ce-102">BAM DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="8b1ce-102">BAM DTS Packages</span></span>
<span data-ttu-id="8b1ce-103">管理者は、次の BAM DTS パッケージのパラメーターを更新できます。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-103">An administrator can update parameters for the following BAM DTS packages:</span></span>  
  
-   <span data-ttu-id="8b1ce-104">**CubeUpdate**データ変換サービス (DTS) パッケージは、スター スキーマ データベースと同じサーバーで常にあります。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-104">The **CubeUpdate** Data Transformation Services (DTS) package is always located on the same server as the Star Schema database.</span></span>  
  
-   <span data-ttu-id="8b1ce-105">**DataMaintenance** DTS パッケージは、プライマリ インポート データベースと同じサーバーで常にあります。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-105">The **DataMaintenance** DTS package is always located on the same server as the Primary Import database.</span></span>  
  
 <span data-ttu-id="8b1ce-106">DTS パッケージでは、BAMConfiguration.xml ファイルで次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-106">The DTS packages use the following parameters in the BAMConfiguration.xml file.</span></span>  
  
|<span data-ttu-id="8b1ce-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b1ce-107">Parameter</span></span>|<span data-ttu-id="8b1ce-108">Description</span><span class="sxs-lookup"><span data-stu-id="8b1ce-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b1ce-109">ConnectionTimeOut</span><span class="sxs-lookup"><span data-stu-id="8b1ce-109">ConnectionTimeOut</span></span>|<span data-ttu-id="8b1ce-110">DTS 接続のタイムアウト値 (秒単位) を整数で指定します。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-110">The DTS connection time out value (in seconds) is an integer.</span></span> <span data-ttu-id="8b1ce-111">ConnectionTimeOut パラメーターを指定しないと、構成ファイルでは既定値の 60 秒が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-111">If you omit the ConnectionTimeOut parameter, the configuration file uses 60 seconds, the default value.</span></span>|  
|<span data-ttu-id="8b1ce-112">暗号化</span><span class="sxs-lookup"><span data-stu-id="8b1ce-112">Encryption</span></span>|<span data-ttu-id="8b1ce-113">DTS パッケージによるデータの変換中、既定ではデータが暗号化されません (Encryption の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-113">By default, the DTS packages do not encrypt data while they transform the data (Encryption value is 0).</span></span> <span data-ttu-id="8b1ce-114">変換中にデータを暗号化するには Encryption の値を 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-114">Set Encryption to 1 to encrypt the data during transformation.</span></span>|  
|<span data-ttu-id="8b1ce-115">OwnerPassword</span><span class="sxs-lookup"><span data-stu-id="8b1ce-115">OwnerPassword</span></span>|<span data-ttu-id="8b1ce-116">DTS パッケージ所有者のパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-116">The password for the DTS package owner.</span></span> <span data-ttu-id="8b1ce-117">DTS パッケージの所有者は、DTS パッケージを開いて変更できます。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-117">DTS package owners can open and modify DTS packages.</span></span> <span data-ttu-id="8b1ce-118">DTS パッケージの所有者の詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-118">For information about DTS package owners, see SQL Server Books Online.</span></span>|  
|<span data-ttu-id="8b1ce-119">UserPassword</span><span class="sxs-lookup"><span data-stu-id="8b1ce-119">UserPassword</span></span>|<span data-ttu-id="8b1ce-120">DTS パッケージ ユーザーのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-120">The password for the DTS user.</span></span> <span data-ttu-id="8b1ce-121">DTS パッケージのユーザーは、DTS パッケージを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-121">DTS package users can run DTS packages.</span></span> <span data-ttu-id="8b1ce-122">DTS パッケージのユーザーの詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-122">For information about DTS package users, see SQL Server Books Online.</span></span>|  
  
 <span data-ttu-id="8b1ce-123">DTS パッケージは、BAMConfiguration.xml ファイルで次の名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-123">The DTS packages use the following naming conventions in the BAMConfiguration.xml file:</span></span>  
  
-   <span data-ttu-id="8b1ce-124">**CubeUpdate** DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="8b1ce-124">**CubeUpdate** DTS package</span></span>  
  
     <span data-ttu-id="8b1ce-125">**bam_an _\<** </span><span class="sxs-lookup"><span data-stu-id="8b1ce-125">**bam_AN_\<** </span></span>  
     <span data-ttu-id="8b1ce-126">***CubeName* >**、キューブ名は、キューブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-126">***CubeName* >**, where CubeName is the name of the cube.</span></span> <span data-ttu-id="8b1ce-127">BAM ブックでは、ビュー名からキューブ名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-127">The BAM workbook generates the cube name from the view name.</span></span> <span data-ttu-id="8b1ce-128">BAM 構成 XML ドキュメントでキューブ名を変更した場合、新しいキューブ名が DTS パッケージ名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-128">If you modify the cube name in the BAM configuration XML document, the new cube name is used in the DTS package name.</span></span>  
  
-   <span data-ttu-id="8b1ce-129">**DataMaintenance** DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="8b1ce-129">**DataMaintenance** DTS package</span></span>  
  
     <span data-ttu-id="8b1ce-130">**bam_dm _\<** </span><span class="sxs-lookup"><span data-stu-id="8b1ce-130">**bam_DM_\<** </span></span>  
     <span data-ttu-id="8b1ce-131">***ActivityName* >**ここで、アクティビティ名は、アクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-131">***ActivityName* >**, where ActivityName is the name of the activity.</span></span>  
  
 <span data-ttu-id="8b1ce-132">スケジュール済みの集計を集計するには、CubeUpdate DTS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-132">You run the CubeUpdate DTS package to aggregate the scheduled aggregation.</span></span> <span data-ttu-id="8b1ce-133">次のセクションでは、リアルタイムのデータ集計の時間帯を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b1ce-133">In the next section, you can specify the time window for real-time data aggregation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1ce-134">参照</span><span class="sxs-lookup"><span data-stu-id="8b1ce-134">See Also</span></span>  
 <span data-ttu-id="8b1ce-135">[BAM 構成スキーマ](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="8b1ce-135">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="8b1ce-136">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="8b1ce-136">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="8b1ce-137">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="8b1ce-137">Managing BAM</span></span>](../core/managing-bam.md)
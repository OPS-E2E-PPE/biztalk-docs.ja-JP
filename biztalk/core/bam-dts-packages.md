---
title: BAM DTS パッケージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a71431ee800c80c6972747f09b0e2420f961e33e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965064"
---
# <a name="bam-dts-packages"></a><span data-ttu-id="a0541-102">BAM DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="a0541-102">BAM DTS Packages</span></span>
<span data-ttu-id="a0541-103">管理者は、次の BAM DTS パッケージのパラメーターを更新できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-103">An administrator can update parameters for the following BAM DTS packages:</span></span>  
  
-   <span data-ttu-id="a0541-104">**CubeUpdate**データ変換サービス (DTS) パッケージは、スター スキーマ データベースと同じサーバーで常にあります。</span><span class="sxs-lookup"><span data-stu-id="a0541-104">The **CubeUpdate** Data Transformation Services (DTS) package is always located on the same server as the Star Schema database.</span></span>  
  
-   <span data-ttu-id="a0541-105">**DataMaintenance** DTS パッケージは、プライマリ インポート データベースと同じサーバーで常にあります。</span><span class="sxs-lookup"><span data-stu-id="a0541-105">The **DataMaintenance** DTS package is always located on the same server as the Primary Import database.</span></span>  
  
 <span data-ttu-id="a0541-106">DTS パッケージでは、BAMConfiguration.xml ファイルで次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0541-106">The DTS packages use the following parameters in the BAMConfiguration.xml file.</span></span>  
  
|<span data-ttu-id="a0541-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0541-107">Parameter</span></span>|<span data-ttu-id="a0541-108">Description</span><span class="sxs-lookup"><span data-stu-id="a0541-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0541-109">ConnectionTimeOut</span><span class="sxs-lookup"><span data-stu-id="a0541-109">ConnectionTimeOut</span></span>|<span data-ttu-id="a0541-110">DTS 接続のタイムアウト値 (秒単位) を整数で指定します。</span><span class="sxs-lookup"><span data-stu-id="a0541-110">The DTS connection time out value (in seconds) is an integer.</span></span> <span data-ttu-id="a0541-111">ConnectionTimeOut パラメーターを指定しないと、構成ファイルでは既定値の 60 秒が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0541-111">If you omit the ConnectionTimeOut parameter, the configuration file uses 60 seconds, the default value.</span></span>|  
|<span data-ttu-id="a0541-112">暗号化</span><span class="sxs-lookup"><span data-stu-id="a0541-112">Encryption</span></span>|<span data-ttu-id="a0541-113">DTS パッケージによるデータの変換中、既定ではデータが暗号化されません (Encryption の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="a0541-113">By default, the DTS packages do not encrypt data while they transform the data (Encryption value is 0).</span></span> <span data-ttu-id="a0541-114">変換中にデータを暗号化するには Encryption の値を 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="a0541-114">Set Encryption to 1 to encrypt the data during transformation.</span></span>|  
|<span data-ttu-id="a0541-115">OwnerPassword</span><span class="sxs-lookup"><span data-stu-id="a0541-115">OwnerPassword</span></span>|<span data-ttu-id="a0541-116">DTS パッケージ所有者のパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0541-116">The password for the DTS package owner.</span></span> <span data-ttu-id="a0541-117">DTS パッケージの所有者は、DTS パッケージを開いて変更できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-117">DTS package owners can open and modify DTS packages.</span></span> <span data-ttu-id="a0541-118">DTS パッケージの所有者の詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0541-118">For information about DTS package owners, see SQL Server Books Online.</span></span>|  
|<span data-ttu-id="a0541-119">UserPassword</span><span class="sxs-lookup"><span data-stu-id="a0541-119">UserPassword</span></span>|<span data-ttu-id="a0541-120">DTS パッケージ ユーザーのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0541-120">The password for the DTS user.</span></span> <span data-ttu-id="a0541-121">DTS パッケージのユーザーは、DTS パッケージを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-121">DTS package users can run DTS packages.</span></span> <span data-ttu-id="a0541-122">DTS パッケージのユーザーの詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0541-122">For information about DTS package users, see SQL Server Books Online.</span></span>|  
  
 <span data-ttu-id="a0541-123">DTS パッケージは、BAMConfiguration.xml ファイルで次の名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0541-123">The DTS packages use the following naming conventions in the BAMConfiguration.xml file:</span></span>  
  
-   <span data-ttu-id="a0541-124">**CubeUpdate** DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="a0541-124">**CubeUpdate** DTS package</span></span>  
  
     <span data-ttu-id="a0541-125">**bam_an _\<**   ***CubeName* \>** 、キューブ名は、キューブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0541-125">**bam_AN_\<** ***CubeName* \>**, where CubeName is the name of the cube.</span></span> <span data-ttu-id="a0541-126">BAM ブックでは、ビュー名からキューブ名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a0541-126">The BAM workbook generates the cube name from the view name.</span></span> <span data-ttu-id="a0541-127">BAM 構成 XML ドキュメントでキューブ名を変更した場合、新しいキューブ名が DTS パッケージ名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0541-127">If you modify the cube name in the BAM configuration XML document, the new cube name is used in the DTS package name.</span></span>  
  
-   <span data-ttu-id="a0541-128">**DataMaintenance** DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="a0541-128">**DataMaintenance** DTS package</span></span>  
  
     <span data-ttu-id="a0541-129">**bam_dm _\<**   ***ActivityName* \>** ここで、アクティビティ名は、アクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="a0541-129">**bam_DM_\<** ***ActivityName* \>**, where ActivityName is the name of the activity.</span></span>  
  
 <span data-ttu-id="a0541-130">スケジュール済みの集計を集計するには、CubeUpdate DTS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0541-130">You run the CubeUpdate DTS package to aggregate the scheduled aggregation.</span></span> <span data-ttu-id="a0541-131">次のセクションでは、リアルタイムのデータ集計の時間帯を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-131">In the next section, you can specify the time window for real-time data aggregation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0541-132">参照</span><span class="sxs-lookup"><span data-stu-id="a0541-132">See Also</span></span>  
 <span data-ttu-id="a0541-133">[BAM 構成スキーマ](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="a0541-133">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="a0541-134">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="a0541-134">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="a0541-135">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="a0541-135">Managing BAM</span></span>](../core/managing-bam.md)
---
title: BAM DTS パッケージ |Microsoft Docs
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
ms.openlocfilehash: 30cbcb583f1e175f5d65565c2108361ec9121721
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528886"
---
# <a name="bam-dts-packages"></a><span data-ttu-id="adb06-102">BAM DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="adb06-102">BAM DTS Packages</span></span>
<span data-ttu-id="adb06-103">管理者は、次の BAM DTS パッケージのパラメーターを更新できます。</span><span class="sxs-lookup"><span data-stu-id="adb06-103">An administrator can update parameters for the following BAM DTS packages:</span></span>  
  
- <span data-ttu-id="adb06-104">**CubeUpdate**データ変換サービス (DTS) パッケージは、スター スキーマ データベースと同じサーバー上にある常にします。</span><span class="sxs-lookup"><span data-stu-id="adb06-104">The **CubeUpdate** Data Transformation Services (DTS) package is always located on the same server as the Star Schema database.</span></span>  
  
- <span data-ttu-id="adb06-105">**DataMaintenance** DTS パッケージは、プライマリ インポート データベースと同じサーバー上にある常にします。</span><span class="sxs-lookup"><span data-stu-id="adb06-105">The **DataMaintenance** DTS package is always located on the same server as the Primary Import database.</span></span>  
  
  <span data-ttu-id="adb06-106">DTS パッケージは、BAMConfiguration.xml ファイルで、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="adb06-106">The DTS packages use the following parameters in the BAMConfiguration.xml file.</span></span>  
  
|<span data-ttu-id="adb06-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="adb06-107">Parameter</span></span>|<span data-ttu-id="adb06-108">説明</span><span class="sxs-lookup"><span data-stu-id="adb06-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="adb06-109">ConnectionTimeOut</span><span class="sxs-lookup"><span data-stu-id="adb06-109">ConnectionTimeOut</span></span>|<span data-ttu-id="adb06-110">DTS 接続のタイムアウト値 (秒) では、整数です。</span><span class="sxs-lookup"><span data-stu-id="adb06-110">The DTS connection time out value (in seconds) is an integer.</span></span> <span data-ttu-id="adb06-111">ConnectionTimeOut パラメーターを省略した場合、構成ファイルには、60 秒で、既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="adb06-111">If you omit the ConnectionTimeOut parameter, the configuration file uses 60 seconds, the default value.</span></span>|  
|<span data-ttu-id="adb06-112">暗号化</span><span class="sxs-lookup"><span data-stu-id="adb06-112">Encryption</span></span>|<span data-ttu-id="adb06-113">既定では、DTS パッケージはデータは暗号化データの変換中に (暗号化値は 0)。</span><span class="sxs-lookup"><span data-stu-id="adb06-113">By default, the DTS packages do not encrypt data while they transform the data (Encryption value is 0).</span></span> <span data-ttu-id="adb06-114">変換中にデータを暗号化するには 1 には、暗号化を設定します。</span><span class="sxs-lookup"><span data-stu-id="adb06-114">Set Encryption to 1 to encrypt the data during transformation.</span></span>|  
|<span data-ttu-id="adb06-115">OwnerPassword</span><span class="sxs-lookup"><span data-stu-id="adb06-115">OwnerPassword</span></span>|<span data-ttu-id="adb06-116">DTS パッケージの所有者のパスワード。</span><span class="sxs-lookup"><span data-stu-id="adb06-116">The password for the DTS package owner.</span></span> <span data-ttu-id="adb06-117">DTS パッケージの所有者が開き、DTS パッケージを変更できます。</span><span class="sxs-lookup"><span data-stu-id="adb06-117">DTS package owners can open and modify DTS packages.</span></span> <span data-ttu-id="adb06-118">DTS パッケージの所有者の詳細については、SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb06-118">For information about DTS package owners, see SQL Server Books Online.</span></span>|  
|<span data-ttu-id="adb06-119">UserPassword</span><span class="sxs-lookup"><span data-stu-id="adb06-119">UserPassword</span></span>|<span data-ttu-id="adb06-120">Dts パッケージ ユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="adb06-120">The password for the DTS user.</span></span> <span data-ttu-id="adb06-121">DTS パッケージのユーザーには、DTS パッケージを実行できます。</span><span class="sxs-lookup"><span data-stu-id="adb06-121">DTS package users can run DTS packages.</span></span> <span data-ttu-id="adb06-122">DTS パッケージのユーザーについては、SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb06-122">For information about DTS package users, see SQL Server Books Online.</span></span>|  
  
 <span data-ttu-id="adb06-123">DTS パッケージは、BAMConfiguration.xml ファイルで、次の名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="adb06-123">The DTS packages use the following naming conventions in the BAMConfiguration.xml file:</span></span>  
  
- <span data-ttu-id="adb06-124">**CubeUpdate** DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="adb06-124">**CubeUpdate** DTS package</span></span>  
  
   <span data-ttu-id="adb06-125">**bam_an _\<**  ***CubeName* \>** CubeName はキューブの名前です。</span><span class="sxs-lookup"><span data-stu-id="adb06-125">**bam_AN_\<** ***CubeName* \>**, where CubeName is the name of the cube.</span></span> <span data-ttu-id="adb06-126">BAM ブックでは、ビュー名からキューブ名を生成します。</span><span class="sxs-lookup"><span data-stu-id="adb06-126">The BAM workbook generates the cube name from the view name.</span></span> <span data-ttu-id="adb06-127">BAM 構成 XML ドキュメントでキューブ名を変更する場合、新しいキューブ名は、DTS パッケージ名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="adb06-127">If you modify the cube name in the BAM configuration XML document, the new cube name is used in the DTS package name.</span></span>  
  
- <span data-ttu-id="adb06-128">**DataMaintenance** DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="adb06-128">**DataMaintenance** DTS package</span></span>  
  
   <span data-ttu-id="adb06-129">**bam_dm _\<**  ***ActivityName* \>** ActivityName はアクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="adb06-129">**bam_DM_\<** ***ActivityName* \>**, where ActivityName is the name of the activity.</span></span>  
  
  <span data-ttu-id="adb06-130">スケジュール済みの集計を集計する CubeUpdate DTS パッケージを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="adb06-130">You run the CubeUpdate DTS package to aggregate the scheduled aggregation.</span></span> <span data-ttu-id="adb06-131">次のセクションでは、リアルタイムのデータ集計の時間枠を指定できます。</span><span class="sxs-lookup"><span data-stu-id="adb06-131">In the next section, you can specify the time window for real-time data aggregation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb06-132">参照</span><span class="sxs-lookup"><span data-stu-id="adb06-132">See Also</span></span>  
 <span data-ttu-id="adb06-133">[BAM 構成スキーマ](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="adb06-133">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="adb06-134">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="adb06-134">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="adb06-135">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="adb06-135">Managing BAM</span></span>](../core/managing-bam.md)
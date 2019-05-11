---
title: BtarnConfig | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, exporting configuration data
- BTARN, BtarnConfig utility
- BtarnConfig utility
- BTARN, importing configuration data
ms.assetid: 8c95be2a-7df5-47fb-ae2d-64fa27e2811a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50940e57a806f56ae874934052a4c5b7a03a13f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284896"
---
# <a name="btarnconfig"></a><span data-ttu-id="3350e-102">BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="3350e-102">BtarnConfig</span></span>
<span data-ttu-id="3350e-103">BtarnConfig ユーティリティを使用して構成データをインポートまたは、Microsoft® から構成データをエクスポートする[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="3350e-103">You use the BtarnConfig utility to import configuration data into, or export configuration data from, a Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] environment.</span></span> <span data-ttu-id="3350e-104">この構成データは、プロセス構成設定、ホーム組織、パートナー、および契約を含む、BTARN 管理コンソールを使用して設定したデータです。</span><span class="sxs-lookup"><span data-stu-id="3350e-104">This configuration data is the data that you set by using the BTARN Management Console, including process configuration settings, home organizations, partners, and agreements.</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="3350e-105">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="3350e-105">Location in SDK</span></span>  
 <span data-ttu-id="3350e-106">\<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="3350e-106">\<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  

## <a name="running-btarnconfig"></a><span data-ttu-id="3350e-107">Running BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="3350e-107">Running BtarnConfig</span></span>  

#### <a name="to-run-btarnconfig"></a><span data-ttu-id="3350e-108">BtarnConfig を実行するには</span><span class="sxs-lookup"><span data-stu-id="3350e-108">To run BtarnConfig</span></span>  

1. <span data-ttu-id="3350e-109">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3350e-109">Open a command prompt.</span></span>  

2. <span data-ttu-id="3350e-110">移動\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。</span><span class="sxs-lookup"><span data-stu-id="3350e-110">Move to \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  

3. <span data-ttu-id="3350e-111">コマンド プロンプトで「 **BtarnConfig**と、適切なスイッチを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3350e-111">At the command prompt, type **BtarnConfig**, type the appropriate switches, and then press ENTER.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3350e-112">次のセクションでは、スイッチについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3350e-112">The following section describes the switches.</span></span>  

## <a name="syntax-for-btarnconfig"></a><span data-ttu-id="3350e-113">BtarnConfig の構文</span><span class="sxs-lookup"><span data-stu-id="3350e-113">Syntax for BtarnConfig</span></span>  
 <span data-ttu-id="3350e-114">このコマンド ライン ツールの起動に使用する構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3350e-114">The following shows the syntax that you use to start this command-line tool:</span></span>  

### <a name="syntax-for-importing-configuration-data"></a><span data-ttu-id="3350e-115">構成データをインポートするための構文</span><span class="sxs-lookup"><span data-stu-id="3350e-115">Syntax for Importing Configuration Data</span></span>  

```  
BTARNCONFIG /IMPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  

### <a name="syntax-for-exporting-configuration-data"></a><span data-ttu-id="3350e-116">構成データをエクスポートするための構文</span><span class="sxs-lookup"><span data-stu-id="3350e-116">Syntax for Exporting Configuration Data</span></span>  

```  
BTARNCONFIG /EXPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  

### <a name="syntax-description"></a><span data-ttu-id="3350e-117">構文の説明</span><span class="sxs-lookup"><span data-stu-id="3350e-117">Syntax Description</span></span>  
 <span data-ttu-id="3350e-118">次の表では、BtarnConfig ユーティリティを使用する構文の各部について説明します。</span><span class="sxs-lookup"><span data-stu-id="3350e-118">The following table describes each part of the syntax that the BtarnConfig utility uses.</span></span>  


|       <span data-ttu-id="3350e-119">構文</span><span class="sxs-lookup"><span data-stu-id="3350e-119">Syntax</span></span>       |                                                                                                                          <span data-ttu-id="3350e-120">説明</span><span class="sxs-lookup"><span data-stu-id="3350e-120">Description</span></span>                                                                                                                          |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3350e-121">\<*filename*.xml\></span><span class="sxs-lookup"><span data-stu-id="3350e-121">\<*filename*.xml\></span></span> | <span data-ttu-id="3350e-122">インポートまたはエクスポートするファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="3350e-122">Full path of the file to import into or export from.</span></span> <span data-ttu-id="3350e-123">BTARN のパスを指定しない場合、パスが前提としています\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>してのアクセラレータSDK があります。</span><span class="sxs-lookup"><span data-stu-id="3350e-123">If you do not provide a path, BTARN assumes that the path is \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span> |
|    <span data-ttu-id="3350e-124">**/IMPORT**</span><span class="sxs-lookup"><span data-stu-id="3350e-124">**/IMPORT**</span></span>     |                                                                                          <span data-ttu-id="3350e-125">XML データをインポート\< *filename*.xml\> BTARN の構成にします。</span><span class="sxs-lookup"><span data-stu-id="3350e-125">Imports the XML data from \<*filename*.xml\> into the BTARN configuration.</span></span>                                                                                           |
|    <span data-ttu-id="3350e-126">**/EXPORT**</span><span class="sxs-lookup"><span data-stu-id="3350e-126">**/EXPORT**</span></span>     |                                                                                             <span data-ttu-id="3350e-127">XML データとしての BTARN の構成のエクスポート\< *filename*.xml\>します。</span><span class="sxs-lookup"><span data-stu-id="3350e-127">Exports the BTARN configuration as XML data into \<*filename*.xml\>.</span></span>                                                                                              |
|       <span data-ttu-id="3350e-128">**/H**</span><span class="sxs-lookup"><span data-stu-id="3350e-128">**/H**</span></span>       |                                                                                                   <span data-ttu-id="3350e-129">インポートまたはホーム組織の構成データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3350e-129">Imports or exports home-organization configuration data.</span></span>                                                                                                    |
|       <span data-ttu-id="3350e-130">**/P**</span><span class="sxs-lookup"><span data-stu-id="3350e-130">**/P**</span></span>       |                                                                                                        <span data-ttu-id="3350e-131">インポートまたはパートナーの構成データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3350e-131">Imports or exports partner configuration data.</span></span>                                                                                                         |
|       <span data-ttu-id="3350e-132">**/R**</span><span class="sxs-lookup"><span data-stu-id="3350e-132">**/R**</span></span>       |                                                                                                        <span data-ttu-id="3350e-133">インポートまたはプロセス構成データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3350e-133">Imports or exports process configuration data.</span></span>                                                                                                         |
|       <span data-ttu-id="3350e-134">**/A**</span><span class="sxs-lookup"><span data-stu-id="3350e-134">**/A**</span></span>       |                                                                                                       <span data-ttu-id="3350e-135">インポートまたはアグリーメントの構成データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3350e-135">Imports or exports agreement configuration data.</span></span>                                                                                                        |

## <a name="remarks"></a><span data-ttu-id="3350e-136">コメント</span><span class="sxs-lookup"><span data-stu-id="3350e-136">Remarks</span></span>  
 <span data-ttu-id="3350e-137">いずれかを指定しない場合、 **/H**、 **/P**、 **/R**、または **/A**スイッチ、BtarnConfig ユーティリティは、インポートまたはすべてのデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3350e-137">If you do not provide any one of the **/H**, **/P**, **/R**, or **/A** switches, the BtarnConfig utility imports or exports all the data.</span></span> <span data-ttu-id="3350e-138">BtarnConfig が次の順序で XML ファイルにデータをエクスポートする 1 つの操作のすべてのデータをエクスポートする場合: ホーム組織、パートナー、プロセス構成、およびアグリーメント。</span><span class="sxs-lookup"><span data-stu-id="3350e-138">When you export all the data in one operation, BtarnConfig exports the data into the XML file in the following order: home organizations, partners, process configuration, and agreements.</span></span>  

 <span data-ttu-id="3350e-139">インポートするファイルの構造上の問題がある場合は、BTARN スキーマの検証段階でエラーが検出され、任意のデータをインポートする前に、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="3350e-139">If there is a structural problem with the file that you are importing from, BTARN will detect the error during the schema validation stage, and the operation will fail before any data is imported.</span></span> <span data-ttu-id="3350e-140">重複するアイテムをインポートしようとしているなどの別のエラーが発生した場合または HTTPS が必要な PIP/アグリーメントし、インポート操作に失敗します。</span><span class="sxs-lookup"><span data-stu-id="3350e-140">If another error occurs, for example, you are trying to import a duplicate artifact or HTTPS is required for the PIP/agreement, then the import operation will fail.</span></span> <span data-ttu-id="3350e-141">ただし、すべてのデータまでにインポートされた構成でポイントが残ります。</span><span class="sxs-lookup"><span data-stu-id="3350e-141">However, all the data imported up to that point will remain in the configuration.</span></span>  

 <span data-ttu-id="3350e-142">BizTalk 管理者は、インポートまたは BtarnConfig を使用して構成データをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3350e-142">You must be a BizTalk administrator to import or export configuration data using BtarnConfig.</span></span> <span data-ttu-id="3350e-143">BizTalk 管理者でない場合は、いくつかのインポート操作が失敗するアクセスの問題があるためです。</span><span class="sxs-lookup"><span data-stu-id="3350e-143">If you are not a BizTalk administrator, some import operations may fail because of access issues.</span></span> <span data-ttu-id="3350e-144">ただし、同じ BtarnConfig コマンドで他のインポート操作が成功する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3350e-144">However,  other import operations in the same BtarnConfig command may succeed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3350e-145">参照</span><span class="sxs-lookup"><span data-stu-id="3350e-145">See Also</span></span>  
 [<span data-ttu-id="3350e-146">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="3350e-146">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)

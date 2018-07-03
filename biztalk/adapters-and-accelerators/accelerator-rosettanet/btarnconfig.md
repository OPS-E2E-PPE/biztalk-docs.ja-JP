---
title: BtarnConfig |Microsoft Docs
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
ms.openlocfilehash: 542ed5729ce4f5ed7ca4a6d453b3169bb1f43d01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991467"
---
# <a name="btarnconfig"></a><span data-ttu-id="ec85c-102">BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="ec85c-102">BtarnConfig</span></span>
<span data-ttu-id="ec85c-103">BtarnConfig ユーティリティを使用して構成データをインポートまたは、Microsoft® から構成データをエクスポートする[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="ec85c-103">You use the BtarnConfig utility to import configuration data into, or export configuration data from, a Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] environment.</span></span> <span data-ttu-id="ec85c-104">この構成データは、BTARN 管理コンソールを使用して設定するデータで、プロセス構成設定、ホーム組織、パートナー、アグリーメントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec85c-104">This configuration data is the data that you set by using the BTARN Management Console, including process configuration settings, home organizations, partners, and agreements.</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="ec85c-105">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="ec85c-105">Location in SDK</span></span>  
 <span data-ttu-id="ec85c-106">\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk</span><span class="sxs-lookup"><span data-stu-id="ec85c-106">\<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  

## <a name="running-btarnconfig"></a><span data-ttu-id="ec85c-107">BtarnConfig の実行</span><span class="sxs-lookup"><span data-stu-id="ec85c-107">Running BtarnConfig</span></span>  

#### <a name="to-run-btarnconfig"></a><span data-ttu-id="ec85c-108">BtarnConfig を実行するには</span><span class="sxs-lookup"><span data-stu-id="ec85c-108">To run BtarnConfig</span></span>  

1. <span data-ttu-id="ec85c-109">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ec85c-109">Open a command prompt.</span></span>  

2. <span data-ttu-id="ec85c-110">移動\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。</span><span class="sxs-lookup"><span data-stu-id="ec85c-110">Move to \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  

3. <span data-ttu-id="ec85c-111">コマンド プロンプトで「 **BtarnConfig**と、適切なスイッチを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ec85c-111">At the command prompt, type **BtarnConfig**, type the appropriate switches, and then press ENTER.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ec85c-112">スイッチについては次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="ec85c-112">The following section describes the switches.</span></span>  

## <a name="syntax-for-btarnconfig"></a><span data-ttu-id="ec85c-113">BtarnConfig の構文</span><span class="sxs-lookup"><span data-stu-id="ec85c-113">Syntax for BtarnConfig</span></span>  
 <span data-ttu-id="ec85c-114">以下に、このコマンドライン ツールを起動するための構文を示します。</span><span class="sxs-lookup"><span data-stu-id="ec85c-114">The following shows the syntax that you use to start this command-line tool:</span></span>  

### <a name="syntax-for-importing-configuration-data"></a><span data-ttu-id="ec85c-115">構成データをインポートするための構文</span><span class="sxs-lookup"><span data-stu-id="ec85c-115">Syntax for Importing Configuration Data</span></span>  

```  
BTARNCONFIG /IMPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  

### <a name="syntax-for-exporting-configuration-data"></a><span data-ttu-id="ec85c-116">構成データをエクスポートするための構文</span><span class="sxs-lookup"><span data-stu-id="ec85c-116">Syntax for Exporting Configuration Data</span></span>  

```  
BTARNCONFIG /EXPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  

### <a name="syntax-description"></a><span data-ttu-id="ec85c-117">構文の説明</span><span class="sxs-lookup"><span data-stu-id="ec85c-117">Syntax Description</span></span>  
 <span data-ttu-id="ec85c-118">次の表で、BtarnConfig が使用する構文の各部について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec85c-118">The following table describes each part of the syntax that the BtarnConfig utility uses.</span></span>  


|       <span data-ttu-id="ec85c-119">構文</span><span class="sxs-lookup"><span data-stu-id="ec85c-119">Syntax</span></span>       |                                                                                                                          <span data-ttu-id="ec85c-120">説明</span><span class="sxs-lookup"><span data-stu-id="ec85c-120">Description</span></span>                                                                                                                          |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ec85c-121">\<*ファイル名*.xml\></span><span class="sxs-lookup"><span data-stu-id="ec85c-121">\<*filename*.xml\></span></span> | <span data-ttu-id="ec85c-122">インポートまたはエクスポートするファイルのフルパス。</span><span class="sxs-lookup"><span data-stu-id="ec85c-122">Full path of the file to import into or export from.</span></span> <span data-ttu-id="ec85c-123">BTARN のパスを指定しない場合、パスが前提としています\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>してのアクセラレータSDK があります。</span><span class="sxs-lookup"><span data-stu-id="ec85c-123">If you do not provide a path, BTARN assumes that the path is \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span> |
|    <span data-ttu-id="ec85c-124">**/インポート**</span><span class="sxs-lookup"><span data-stu-id="ec85c-124">**/IMPORT**</span></span>     |                                                                                          <span data-ttu-id="ec85c-125">XML データをインポート\< *filename*.xml\> BTARN の構成にします。</span><span class="sxs-lookup"><span data-stu-id="ec85c-125">Imports the XML data from \<*filename*.xml\> into the BTARN configuration.</span></span>                                                                                           |
|    <span data-ttu-id="ec85c-126">**/EXPORT**</span><span class="sxs-lookup"><span data-stu-id="ec85c-126">**/EXPORT**</span></span>     |                                                                                             <span data-ttu-id="ec85c-127">XML データとしての BTARN の構成のエクスポート\< *filename*.xml\>します。</span><span class="sxs-lookup"><span data-stu-id="ec85c-127">Exports the BTARN configuration as XML data into \<*filename*.xml\>.</span></span>                                                                                              |
|       <span data-ttu-id="ec85c-128">**/H**</span><span class="sxs-lookup"><span data-stu-id="ec85c-128">**/H**</span></span>       |                                                                                                   <span data-ttu-id="ec85c-129">ホーム組織の構成データをインポートまたはエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ec85c-129">Imports or exports home-organization configuration data.</span></span>                                                                                                    |
|       <span data-ttu-id="ec85c-130">**/P**</span><span class="sxs-lookup"><span data-stu-id="ec85c-130">**/P**</span></span>       |                                                                                                        <span data-ttu-id="ec85c-131">取引先の構成データをインポートまたはエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ec85c-131">Imports or exports partner configuration data.</span></span>                                                                                                         |
|       <span data-ttu-id="ec85c-132">**/R**</span><span class="sxs-lookup"><span data-stu-id="ec85c-132">**/R**</span></span>       |                                                                                                        <span data-ttu-id="ec85c-133">プロセス構成データをインポートまたはエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ec85c-133">Imports or exports process configuration data.</span></span>                                                                                                         |
|       <span data-ttu-id="ec85c-134">**/A**</span><span class="sxs-lookup"><span data-stu-id="ec85c-134">**/A**</span></span>       |                                                                                                       <span data-ttu-id="ec85c-135">アグリーメントの構成データをインポートまたはエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ec85c-135">Imports or exports agreement configuration data.</span></span>                                                                                                        |

## <a name="remarks"></a><span data-ttu-id="ec85c-136">コメント</span><span class="sxs-lookup"><span data-stu-id="ec85c-136">Remarks</span></span>  
 <span data-ttu-id="ec85c-137">いずれかを指定しない場合、 **/H**、 **/P**、 **/R**、または **/A**スイッチ、BtarnConfig ユーティリティは、インポートまたはすべてのデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ec85c-137">If you do not provide any one of the **/H**, **/P**, **/R**, or **/A** switches, the BtarnConfig utility imports or exports all the data.</span></span> <span data-ttu-id="ec85c-138">一度の操作で全データをエクスポートする場合は、ホーム組織、取引先、プロセス構成、アグリーメントの順にデータが XML にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ec85c-138">When you export all the data in one operation, BtarnConfig exports the data into the XML file in the following order: home organizations, partners, process configuration, and agreements.</span></span>  

 <span data-ttu-id="ec85c-139">インポート元のファイルに構造上の問題がある場合は、スキーマ検証ステージでエラーが検出され、データがインポートされる前に操作に失敗します。</span><span class="sxs-lookup"><span data-stu-id="ec85c-139">If there is a structural problem with the file that you are importing from, BTARN will detect the error during the schema validation stage, and the operation will fail before any data is imported.</span></span> <span data-ttu-id="ec85c-140">別のエラーが発生した場合、たとえば重複項目をインポートしようとしている場合や、PIP/アグリーメントに HTTPS が必要な場合は、インポート操作に失敗します。</span><span class="sxs-lookup"><span data-stu-id="ec85c-140">If another error occurs, for example, you are trying to import a duplicate artifact or HTTPS is required for the PIP/agreement, then the import operation will fail.</span></span> <span data-ttu-id="ec85c-141">ただし、その時点までにインポートされたデータは構成に残ります。</span><span class="sxs-lookup"><span data-stu-id="ec85c-141">However, all the data imported up to that point will remain in the configuration.</span></span>  

 <span data-ttu-id="ec85c-142">BtarnConfig を使用して構成データをインポートまたはエクスポートするには、BizTalk 管理者でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ec85c-142">You must be a BizTalk administrator to import or export configuration data using BtarnConfig.</span></span> <span data-ttu-id="ec85c-143">BizTalk 管理者でない場合は、アクセス権の問題でインポート操作に失敗する可能性がありますが、</span><span class="sxs-lookup"><span data-stu-id="ec85c-143">If you are not a BizTalk administrator, some import operations may fail because of access issues.</span></span> <span data-ttu-id="ec85c-144">BtarnConfig コマンドを使用した他のインポート操作には成功する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ec85c-144">However,  other import operations in the same BtarnConfig command may succeed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ec85c-145">参照</span><span class="sxs-lookup"><span data-stu-id="ec85c-145">See Also</span></span>  
 [<span data-ttu-id="ec85c-146">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="ec85c-146">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)

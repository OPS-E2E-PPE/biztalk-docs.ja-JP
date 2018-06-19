---
title: RemoveResource コマンド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e2c6046-43d4-4ac1-a1b1-3795b4e44038
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d091c46ea25cbb2489264316239b6763d841a47e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269378"
---
# <a name="removeresource-command"></a><span data-ttu-id="dac3c-102">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="dac3c-102">RemoveResource Command</span></span>
<span data-ttu-id="dac3c-103">BizTalk 管理データベースからアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="dac3c-103">Removes (deletes) an artifact from the BizTalk Management database.</span></span> <span data-ttu-id="dac3c-104">アイテムが、グローバル アセンブリ キャッシュ (GAC)、ファイル システム、証明書ストア、インターネット インフォメーション サービス、または Windows レジストリに存在していた場合、このコマンドを実行しても、これらの場所からは削除されません。</span><span class="sxs-lookup"><span data-stu-id="dac3c-104">Running this command does not remove the artifact from the global assembly cache (GAC), file system, certificate store, Internet Information Services, or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="dac3c-105">BAM プライマリ インポート データベースの BAM 定義やルール エンジン データベースのポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="dac3c-105">It does not remove a BAM definition from the BAM Primary Import database nor does it remove policies from the Rule Engine database.</span></span> <span data-ttu-id="dac3c-106">このコマンドを実行してバインド ファイルを削除した場合、バインド ファイルが削除されるのみで、バインドそのものは変更されません。</span><span class="sxs-lookup"><span data-stu-id="dac3c-106">If you run this command to remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
 <span data-ttu-id="dac3c-107">このコマンドでは、次の種類のアイテムを削除できます。</span><span class="sxs-lookup"><span data-stu-id="dac3c-107">You can use this command to remove the following artifact types:</span></span>  
  
-   <span data-ttu-id="dac3c-108">.NET アセンブリ (System.BizTalk:Assembly)</span><span class="sxs-lookup"><span data-stu-id="dac3c-108">.NET assembly (System.BizTalk:Assembly)</span></span>  
  
-   <span data-ttu-id="dac3c-109">BAM 定義 (System.BizTalk:Bam)</span><span class="sxs-lookup"><span data-stu-id="dac3c-109">BAM definition (System.BizTalk:Bam)</span></span>  
  
-   <span data-ttu-id="dac3c-110">BizTalk アセンブリ (System.BizTalk:BizTalkAssembly)</span><span class="sxs-lookup"><span data-stu-id="dac3c-110">BizTalk assembly (System.BizTalk:BizTalkAssembly</span></span>  
  
-   <span data-ttu-id="dac3c-111">BizTalk バインド ファイル (System.BizTalk:BizTalkBinding)</span><span class="sxs-lookup"><span data-stu-id="dac3c-111">BizTalk binding file (System.BizTalk:BizTalkBinding)</span></span>  
  
-   <span data-ttu-id="dac3c-112">セキュリティ証明書 (System.BizTalk:Certificate)</span><span class="sxs-lookup"><span data-stu-id="dac3c-112">Security certificate (System.BizTalk:Certificate)</span></span>  
  
-   <span data-ttu-id="dac3c-113">COM コンポーネント (System.BizTalk:Com)</span><span class="sxs-lookup"><span data-stu-id="dac3c-113">COM component (System.BizTalk:Com)</span></span>  
  
-   <span data-ttu-id="dac3c-114">アドホック ファイル (System.BizTalk:File)</span><span class="sxs-lookup"><span data-stu-id="dac3c-114">Ad hoc file (System.BizTalk:File)</span></span>  
  
-   <span data-ttu-id="dac3c-115">処理後のスクリプト (System.BizTalk:PostProcessingScript)</span><span class="sxs-lookup"><span data-stu-id="dac3c-115">Postprocessing script (System.BizTalk:PostProcessingScript)</span></span>  
  
-   <span data-ttu-id="dac3c-116">処理前のスクリプト (System.BizTalk:PreProcessingScript)</span><span class="sxs-lookup"><span data-stu-id="dac3c-116">Preprocessing script (System.BizTalk:PreProcessingScript)</span></span>  
  
-   <span data-ttu-id="dac3c-117">ポリシーまたはルール (System.BizTalk:Rules)</span><span class="sxs-lookup"><span data-stu-id="dac3c-117">Policy or rule (System.BizTalk:Rules)</span></span>  
  
-   <span data-ttu-id="dac3c-118">仮想ディレクトリ (System.BizTalk:WebDirectory)</span><span class="sxs-lookup"><span data-stu-id="dac3c-118">Virtual directory (System.BizTalk:WebDirectory)</span></span>  
  
 <span data-ttu-id="dac3c-119">次の場合、削除操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="dac3c-119">The remove operation will fail in the following cases:</span></span>  
  
-   <span data-ttu-id="dac3c-120">他のアセンブリによって参照されている BizTalk アセンブリを削除しようとした場合。</span><span class="sxs-lookup"><span data-stu-id="dac3c-120">You attempt to remove a BizTalk assembly to which another assembly has a reference.</span></span>  
  
-   <span data-ttu-id="dac3c-121">送信ポートまたは受信ポートによって使用されているパイプラインを含む BizTalk アセンブリを削除しようとした場合。</span><span class="sxs-lookup"><span data-stu-id="dac3c-121">You attempt to remove a BizTalk assembly that includes a pipeline that is used by a send or receive port.</span></span>  
  
-   <span data-ttu-id="dac3c-122">送信ポートが使用しているマップを含む BizTalk アセンブリを削除しようとした場合。</span><span class="sxs-lookup"><span data-stu-id="dac3c-122">You attempt to remove a BizTalk assembly that includes a map used by a send port.</span></span>  
  
-   <span data-ttu-id="dac3c-123">削除しようとしている BizTalk アセンブリにオーケストレーションが含まれており、そのオーケストレーションが参加解除状態ではない、または、そのオーケストレーションに、中断されたインスタンスが存在する場合。</span><span class="sxs-lookup"><span data-stu-id="dac3c-123">You attempt to remove a BizTalk assembly that includes an orchestration that is not in an unenlisted state or that has a suspended instance.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="dac3c-124">使用方法</span><span class="sxs-lookup"><span data-stu-id="dac3c-124">Usage</span></span>  
 <span data-ttu-id="dac3c-125">**BTSTask RemoveResource/applicationname は:** *値* **/Luid:** *値*[**/Server:** *値*] [**/database:***値*]</span><span class="sxs-lookup"><span data-stu-id="dac3c-125">**BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="dac3c-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dac3c-126">Parameters</span></span>  
  
|<span data-ttu-id="dac3c-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dac3c-127">Parameter</span></span>|<span data-ttu-id="dac3c-128">必須</span><span class="sxs-lookup"><span data-stu-id="dac3c-128">Required</span></span>|<span data-ttu-id="dac3c-129">Description</span><span class="sxs-lookup"><span data-stu-id="dac3c-129">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="dac3c-130">**/ApplicationName** (または **/A**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="dac3c-130">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="dac3c-131">はい</span><span class="sxs-lookup"><span data-stu-id="dac3c-131">Yes</span></span>|<span data-ttu-id="dac3c-132">削除するリソース アイテムが存在する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="dac3c-132">Name of the BizTalk application containing the resource artifact to delete.</span></span> <span data-ttu-id="dac3c-133">名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="dac3c-133">If the name includes spaces, you must enclose it with double quotation marks (").</span></span>|  
|<span data-ttu-id="dac3c-134">**/Luid** (または **/L**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="dac3c-134">**/Luid** (or **/L**, see Remarks)</span></span>|<span data-ttu-id="dac3c-135">はい</span><span class="sxs-lookup"><span data-stu-id="dac3c-135">Yes</span></span>|<span data-ttu-id="dac3c-136">アイテムのローカル一意識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="dac3c-136">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="dac3c-137">使用して、LUID を取得することができます、 [ListApp コマンド](../core/listapp-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="dac3c-137">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
|<span data-ttu-id="dac3c-138">**/サーバー** (または **/S**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="dac3c-138">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="dac3c-139">不可</span><span class="sxs-lookup"><span data-stu-id="dac3c-139">No</span></span>|<span data-ttu-id="dac3c-140">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="dac3c-140">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="dac3c-141">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="dac3c-141">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="dac3c-142">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="dac3c-142">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="dac3c-143">例 :</span><span class="sxs-lookup"><span data-stu-id="dac3c-143">Examples:</span></span><br /><br /> <span data-ttu-id="dac3c-144">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="dac3c-144">Server=MyServer</span></span><br /><br /> <span data-ttu-id="dac3c-145">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="dac3c-145">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="dac3c-146">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dac3c-146">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="dac3c-147">**/データベース**(または **/D**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="dac3c-147">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="dac3c-148">不可</span><span class="sxs-lookup"><span data-stu-id="dac3c-148">No</span></span>|<span data-ttu-id="dac3c-149">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="dac3c-149">Name of the BizTalk Management database.</span></span> <span data-ttu-id="dac3c-150">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dac3c-150">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="dac3c-151">サンプル</span><span class="sxs-lookup"><span data-stu-id="dac3c-151">Sample</span></span>  
 <span data-ttu-id="dac3c-152">**BTSTask RemoveResource applicationname: myapplication/Luid:"MyApp.Orchestrations、バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="dac3c-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dac3c-153">解説</span><span class="sxs-lookup"><span data-stu-id="dac3c-153">Remarks</span></span>  
 <span data-ttu-id="dac3c-154">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="dac3c-154">Parameters are not case-sensitive.</span></span> <span data-ttu-id="dac3c-155">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="dac3c-155">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac3c-156">参照</span><span class="sxs-lookup"><span data-stu-id="dac3c-156">See Also</span></span>  
 <span data-ttu-id="dac3c-157">[BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dac3c-157">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="dac3c-158">アプリケーションからアイテムを削除する方法</span><span class="sxs-lookup"><span data-stu-id="dac3c-158">How to Remove an Artifact from an Application</span></span>](../core/how-to-remove-an-artifact-from-an-application.md)
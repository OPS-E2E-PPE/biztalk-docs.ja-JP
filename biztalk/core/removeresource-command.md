---
title: RemoveResource コマンド |Microsoft Docs
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
ms.openlocfilehash: dc7b5e6f5d254624f295aef16761d074379f3ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397919"
---
# <a name="removeresource-command"></a><span data-ttu-id="f21ea-102">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="f21ea-102">RemoveResource Command</span></span>
<span data-ttu-id="f21ea-103">(削除)、BizTalk 管理データベースからのアイテム。</span><span class="sxs-lookup"><span data-stu-id="f21ea-103">Removes (deletes) an artifact from the BizTalk Management database.</span></span> <span data-ttu-id="f21ea-104">このコマンドの実行は削除されません、成果物、グローバル アセンブリ キャッシュ (GAC)、ファイル システム、証明書ストア、インターネット インフォメーション サービス、または、Windows レジストリからこれらの場所のいずれかに存在する場合。</span><span class="sxs-lookup"><span data-stu-id="f21ea-104">Running this command does not remove the artifact from the global assembly cache (GAC), file system, certificate store, Internet Information Services, or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="f21ea-105">BAM 定義は、BAM プライマリ インポート データベースから削除されませんしても、ポリシー、ルール エンジン データベースからです。</span><span class="sxs-lookup"><span data-stu-id="f21ea-105">It does not remove a BAM definition from the BAM Primary Import database nor does it remove policies from the Rule Engine database.</span></span> <span data-ttu-id="f21ea-106">バインド ファイルを削除するには、このコマンドを実行すると、バインドされても変更されません: バインド ファイルのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="f21ea-106">If you run this command to remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
 <span data-ttu-id="f21ea-107">このコマンドを使用して、次の成果物の種類を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f21ea-107">You can use this command to remove the following artifact types:</span></span>  
  
- <span data-ttu-id="f21ea-108">.NET アセンブリ (System.BizTalk:Assembly)</span><span class="sxs-lookup"><span data-stu-id="f21ea-108">.NET assembly (System.BizTalk:Assembly)</span></span>  
  
- <span data-ttu-id="f21ea-109">BAM 定義 (System.BizTalk:Bam)</span><span class="sxs-lookup"><span data-stu-id="f21ea-109">BAM definition (System.BizTalk:Bam)</span></span>  
  
- <span data-ttu-id="f21ea-110">BizTalk アセンブリ (system.biztalk:biztalkassembly)</span><span class="sxs-lookup"><span data-stu-id="f21ea-110">BizTalk assembly (System.BizTalk:BizTalkAssembly</span></span>  
  
- <span data-ttu-id="f21ea-111">BizTalk バインド ファイル (System.BizTalk:BizTalkBinding)</span><span class="sxs-lookup"><span data-stu-id="f21ea-111">BizTalk binding file (System.BizTalk:BizTalkBinding)</span></span>  
  
- <span data-ttu-id="f21ea-112">セキュリティ証明書 (System.BizTalk:Certificate)</span><span class="sxs-lookup"><span data-stu-id="f21ea-112">Security certificate (System.BizTalk:Certificate)</span></span>  
  
- <span data-ttu-id="f21ea-113">COM コンポーネント (System.BizTalk:Com)</span><span class="sxs-lookup"><span data-stu-id="f21ea-113">COM component (System.BizTalk:Com)</span></span>  
  
- <span data-ttu-id="f21ea-114">アドホック ファイル (System.BizTalk:File)</span><span class="sxs-lookup"><span data-stu-id="f21ea-114">Ad hoc file (System.BizTalk:File)</span></span>  
  
- <span data-ttu-id="f21ea-115">処理後のスクリプト (System.BizTalk:PostProcessingScript)</span><span class="sxs-lookup"><span data-stu-id="f21ea-115">Postprocessing script (System.BizTalk:PostProcessingScript)</span></span>  
  
- <span data-ttu-id="f21ea-116">処理前のスクリプト (System.BizTalk:PreProcessingScript)</span><span class="sxs-lookup"><span data-stu-id="f21ea-116">Preprocessing script (System.BizTalk:PreProcessingScript)</span></span>  
  
- <span data-ttu-id="f21ea-117">ポリシーまたはルール (System.BizTalk:Rules)</span><span class="sxs-lookup"><span data-stu-id="f21ea-117">Policy or rule (System.BizTalk:Rules)</span></span>  
  
- <span data-ttu-id="f21ea-118">仮想ディレクトリ (System.BizTalk:WebDirectory)</span><span class="sxs-lookup"><span data-stu-id="f21ea-118">Virtual directory (System.BizTalk:WebDirectory)</span></span>  
  
  <span data-ttu-id="f21ea-119">次の場合、削除操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="f21ea-119">The remove operation will fail in the following cases:</span></span>  
  
- <span data-ttu-id="f21ea-120">別のアセンブリが参照を持っている BizTalk アセンブリを削除しようとするとします。</span><span class="sxs-lookup"><span data-stu-id="f21ea-120">You attempt to remove a BizTalk assembly to which another assembly has a reference.</span></span>  
  
- <span data-ttu-id="f21ea-121">ポートまたは受信ポート、送信で使用されるパイプラインを含む BizTalk アセンブリを削除しようとするとします。</span><span class="sxs-lookup"><span data-stu-id="f21ea-121">You attempt to remove a BizTalk assembly that includes a pipeline that is used by a send or receive port.</span></span>  
  
- <span data-ttu-id="f21ea-122">送信ポートで使用されるマップを含む BizTalk アセンブリを削除しようとするとします。</span><span class="sxs-lookup"><span data-stu-id="f21ea-122">You attempt to remove a BizTalk assembly that includes a map used by a send port.</span></span>  
  
- <span data-ttu-id="f21ea-123">参加解除状態でないか、中断されたインスタンスを持つオーケストレーションを含む BizTalk アセンブリを削除しようとするとします。</span><span class="sxs-lookup"><span data-stu-id="f21ea-123">You attempt to remove a BizTalk assembly that includes an orchestration that is not in an unenlisted state or that has a suspended instance.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f21ea-124">使用方法</span><span class="sxs-lookup"><span data-stu-id="f21ea-124">Usage</span></span>  
 <span data-ttu-id="f21ea-125">**BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="f21ea-125">**BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="f21ea-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f21ea-126">Parameters</span></span>  
  
|<span data-ttu-id="f21ea-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f21ea-127">Parameter</span></span>|<span data-ttu-id="f21ea-128">必須</span><span class="sxs-lookup"><span data-stu-id="f21ea-128">Required</span></span>|<span data-ttu-id="f21ea-129">説明</span><span class="sxs-lookup"><span data-stu-id="f21ea-129">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="f21ea-130">**/ApplicationName** (または **/A**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="f21ea-130">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="f21ea-131">はい</span><span class="sxs-lookup"><span data-stu-id="f21ea-131">Yes</span></span>|<span data-ttu-id="f21ea-132">削除するリソース アイテムが含まれる BizTalk アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="f21ea-132">Name of the BizTalk application containing the resource artifact to delete.</span></span> <span data-ttu-id="f21ea-133">名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="f21ea-133">If the name includes spaces, you must enclose it with double quotation marks (").</span></span>|  
|<span data-ttu-id="f21ea-134">**/Luid** (または **/L**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="f21ea-134">**/Luid** (or **/L**, see Remarks)</span></span>|<span data-ttu-id="f21ea-135">はい</span><span class="sxs-lookup"><span data-stu-id="f21ea-135">Yes</span></span>|<span data-ttu-id="f21ea-136">成果物のローカルで一意の識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="f21ea-136">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="f21ea-137">LUID を取得するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="f21ea-137">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
|<span data-ttu-id="f21ea-138">**/サーバー** (または **/S**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="f21ea-138">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="f21ea-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="f21ea-139">No</span></span>|<span data-ttu-id="f21ea-140">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="f21ea-140">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="f21ea-141">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="f21ea-141">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="f21ea-142">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="f21ea-142">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="f21ea-143">例 :</span><span class="sxs-lookup"><span data-stu-id="f21ea-143">Examples:</span></span><br /><br /> <span data-ttu-id="f21ea-144">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="f21ea-144">Server=MyServer</span></span><br /><br /> <span data-ttu-id="f21ea-145">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="f21ea-145">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="f21ea-146">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f21ea-146">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="f21ea-147">**/データベース**(または **/D**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="f21ea-147">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="f21ea-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="f21ea-148">No</span></span>|<span data-ttu-id="f21ea-149">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f21ea-149">Name of the BizTalk Management database.</span></span> <span data-ttu-id="f21ea-150">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f21ea-150">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="f21ea-151">サンプル</span><span class="sxs-lookup"><span data-stu-id="f21ea-151">Sample</span></span>  
 <span data-ttu-id="f21ea-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="f21ea-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f21ea-153">コメント</span><span class="sxs-lookup"><span data-stu-id="f21ea-153">Remarks</span></span>  
 <span data-ttu-id="f21ea-154">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="f21ea-154">Parameters are not case-sensitive.</span></span> <span data-ttu-id="f21ea-155">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="f21ea-155">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21ea-156">参照</span><span class="sxs-lookup"><span data-stu-id="f21ea-156">See Also</span></span>  
 <span data-ttu-id="f21ea-157">[BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f21ea-157">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="f21ea-158">アプリケーションからアイテムを削除する方法</span><span class="sxs-lookup"><span data-stu-id="f21ea-158">How to Remove an Artifact from an Application</span></span>](../core/how-to-remove-an-artifact-from-an-application.md)
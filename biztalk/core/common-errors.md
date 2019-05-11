---
title: 一般的なエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fe48a8e-def0-4a00-aa7f-9a49ae555351
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57eb84b31082f6175f4a68b081130216be06b63e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528208"
---
# <a name="common-errors"></a><span data-ttu-id="71e39-102">一般的なエラー</span><span class="sxs-lookup"><span data-stu-id="71e39-102">Common Errors</span></span>
<span data-ttu-id="71e39-103">このトピックでは、一般的なエラー メッセージが BizTalk マッパーを使用してマップを作成するときに発生する可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="71e39-103">This topic lists out common error messages you may encounter while creating maps using BizTalk Mapper.</span></span>  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a><span data-ttu-id="71e39-104">日付を解析するときにイベント ID 324 がエラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="71e39-104">You receive error event ID 324 when parsing dates</span></span>  
  
### <a name="problem"></a><span data-ttu-id="71e39-105">問題</span><span class="sxs-lookup"><span data-stu-id="71e39-105">Problem</span></span>  
 <span data-ttu-id="71e39-106">データベースを使用すると**値抽出**日付フィールド、ドキュメントを抽出するマップの functoid には送信ドキュメント定義に対して検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="71e39-106">When you use the Database **Value Extractor** functoid in a map to extract a date field, your document may fail validation against the outbound document definition.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="71e39-107">イベント ログに次のような検証エラーをログする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71e39-107">may log a validation error similar to the following in the event log:</span></span>  
  
 <span data-ttu-id="71e39-108">イベント ソース:BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="71e39-108">Event Source: BizTalk Server</span></span>  
  
 <span data-ttu-id="71e39-109">イベント カテゴリ:ドキュメントの処理</span><span class="sxs-lookup"><span data-stu-id="71e39-109">Event Category: Document Processing</span></span>  
  
 <span data-ttu-id="71e39-110">イベント ID:324</span><span class="sxs-lookup"><span data-stu-id="71e39-110">Event ID: 324</span></span>  
  
 <span data-ttu-id="71e39-111">説明:</span><span class="sxs-lookup"><span data-stu-id="71e39-111">Description:</span></span>  
  
 <span data-ttu-id="71e39-112">BizTalk Server でエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="71e39-112">An error occurred in BizTalk Server.</span></span>  
  
 <span data-ttu-id="71e39-113">詳細:</span><span class="sxs-lookup"><span data-stu-id="71e39-113">Details:</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="71e39-114">XML ドキュメントには、次の理由で検証が失敗しました。'10/12/1995 の解析中にエラー' date データ型として。</span><span class="sxs-lookup"><span data-stu-id="71e39-114">The XML document has failed validation for the following reason: Error parsing '10/12/1995' as date datatype.</span></span>  
  
 <span data-ttu-id="71e39-115">保留キュー ID:"{A1127909-CA36-4359-B672-7CBA8B60BDAF}"</span><span class="sxs-lookup"><span data-stu-id="71e39-115">Suspended Queue ID: "{A1127909-CA36-4359-B672-7CBA8B60BDAF}"</span></span>  
  
### <a name="cause"></a><span data-ttu-id="71e39-116">原因</span><span class="sxs-lookup"><span data-stu-id="71e39-116">Cause</span></span>  
 <span data-ttu-id="71e39-117">(データ ソースから返された) 日付形式は XML で必要な形式は、ISO 8601 形式ではありません。</span><span class="sxs-lookup"><span data-stu-id="71e39-117">The date format (as it is returned from the data source) is not in ISO 8601 format, which is the format required by XML.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="71e39-118">解決策</span><span class="sxs-lookup"><span data-stu-id="71e39-118">Resolution</span></span>  
 <span data-ttu-id="71e39-119">この問題を解決するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="71e39-119">To resolve this issue, do one of the following:</span></span>  
  
- <span data-ttu-id="71e39-120">Date データ型ではなく文字列データ型を使用して、送信ドキュメント定義を編集します。</span><span class="sxs-lookup"><span data-stu-id="71e39-120">Edit your outbound document definition to use a string datatype instead of a date datatype.</span></span>  
  
- <span data-ttu-id="71e39-121">カスタムを作成する[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**スクリプト**データベースの出力を変換する functoid**値抽出**functoid を ISO 8601 形式にします。</span><span class="sxs-lookup"><span data-stu-id="71e39-121">Create a custom [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**Script** functoid that will convert the output of the Database **Value Extractor** functoid into the ISO 8601 format.</span></span>  
  
  <span data-ttu-id="71e39-122">詳細については、サポート技術情報の記事を参照してください[278737](http://support.microsoft.com/kb/278737/en-us)します。</span><span class="sxs-lookup"><span data-stu-id="71e39-122">For more information, see KB article [278737](http://support.microsoft.com/kb/278737/en-us).</span></span>  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a><span data-ttu-id="71e39-123">内部コンパイラ エラー (アドレス 53624fd6 の 0xc0000005) をいつ受信する、マップのコンパイル</span><span class="sxs-lookup"><span data-stu-id="71e39-123">You receive Internal Compiler Error (0xc0000005 at address 53624FD6) when compiling the maps</span></span>  
  
### <a name="problem"></a><span data-ttu-id="71e39-124">問題</span><span class="sxs-lookup"><span data-stu-id="71e39-124">Problem</span></span>  
 <span data-ttu-id="71e39-125">大きなスキーマ、マップ、またはオーケストレーションで構成される 1 つの BizTalk プロジェクトをコンパイルするときに、コンパイラは、次のようなエラーを生成可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71e39-125">When you compile a single BizTalk project that consists of large schemas, maps, or orchestrations, the compiler may generate an error similar to the following:</span></span>  
  
 <span data-ttu-id="71e39-126">内部コンパイラ エラー (アドレス 53624fd6 の 0xc0000005): 可能性の高い原因は 'CODEGEN'。</span><span class="sxs-lookup"><span data-stu-id="71e39-126">Internal Compiler Error (0xc0000005 at address 53624FD6): likely culprit is 'CODEGEN'.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="71e39-127">原因</span><span class="sxs-lookup"><span data-stu-id="71e39-127">Cause</span></span>  
 <span data-ttu-id="71e39-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コンパイラには、単一のプロジェクトにおけるすべての文字列の合計サイズについて 16 MB の制限があります。</span><span class="sxs-lookup"><span data-stu-id="71e39-128">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler has a 16-megabyte limitation on the total size of all strings in a single project.</span></span> <span data-ttu-id="71e39-129">BizTalk プロジェクトをコンパイルしている間、コンパイラはアセンブリ作成のスキーマ、マップ、およびオーケストレーションをシリアル化し、これによってすべての文字列の合計サイズが増加し、制限を超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71e39-129">While compiling BizTalk projects, the compiler serializes schemas, maps, and orchestrations for creating the assemblies, and this increases the total size of all strings, which may exceed the limitation.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="71e39-130">解決策</span><span class="sxs-lookup"><span data-stu-id="71e39-130">Resolution</span></span>  
 <span data-ttu-id="71e39-131">この問題を解決するには、別の BizTalk プロジェクトにスキーマまたはマップを分離できます。</span><span class="sxs-lookup"><span data-stu-id="71e39-131">To resolve this issue, you can separate schemas or maps into different BizTalk projects.</span></span>  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a><span data-ttu-id="71e39-132">BizTalk アイテムの型名に関するエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="71e39-132">You receive errors about the Type Name of a BizTalk artifact</span></span>  
  
### <a name="problem"></a><span data-ttu-id="71e39-133">問題</span><span class="sxs-lookup"><span data-stu-id="71e39-133">Problem</span></span>  
 <span data-ttu-id="71e39-134">BizTalk プロジェクトでは、ファイル名にマップを作成**System.btm**または**Microsoft.btm**します。</span><span class="sxs-lookup"><span data-stu-id="71e39-134">In a BizTalk project, create a map with filename **System.btm** or **Microsoft.btm**.</span></span> <span data-ttu-id="71e39-135">プロジェクトをビルドすると、BizTalk マッパーには、次のいずれかのようなエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="71e39-135">When you build the project, the BizTalk Mapper generates an error similar to any of the following:</span></span>  
  
-   <span data-ttu-id="71e39-136">「型名 'SerializableAttribute' が存在しません...」</span><span class="sxs-lookup"><span data-stu-id="71e39-136">“The typename ‘SerializableAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="71e39-137">「型名 'NonSerializableAttribute' が存在しません...」</span><span class="sxs-lookup"><span data-stu-id="71e39-137">“The typename ‘NonSerializableAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="71e39-138">「型名 'SerializableAttributeAttribute' が存在しません...」</span><span class="sxs-lookup"><span data-stu-id="71e39-138">“The typename ‘SerializableAttributeAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="71e39-139">「型名 'XLANs' が存在しません...」</span><span class="sxs-lookup"><span data-stu-id="71e39-139">“The typename ‘XLANs’ does not exist…”</span></span>  
  
### <a name="cause"></a><span data-ttu-id="71e39-140">原因</span><span class="sxs-lookup"><span data-stu-id="71e39-140">Cause</span></span>  
 <span data-ttu-id="71e39-141">**型名**で、**プロパティ**グリッド必要はありません予約 .NET 名前空間など**システム**、 **Microsoft**など。</span><span class="sxs-lookup"><span data-stu-id="71e39-141">The **Type Name** in the **Properties** grid should not have any reserved .NET namespaces, such as **System**, **Microsoft**, etc.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="71e39-142">解決策</span><span class="sxs-lookup"><span data-stu-id="71e39-142">Resolution</span></span>  
 <span data-ttu-id="71e39-143">この問題を解決するには、これらの回避策のいずれかに従うことができます。</span><span class="sxs-lookup"><span data-stu-id="71e39-143">To resolve this issue, you can follow any of these workarounds:</span></span>  
  
-   <span data-ttu-id="71e39-144">.NET の予約語ではない任意の文字列にマップの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="71e39-144">Modify the name of the map to any string which is not a .NET reserved word.</span></span> <span data-ttu-id="71e39-145">既定では、BizTalk プロジェクト システムを作成、**型名**それぞれのアイテムの名前から。</span><span class="sxs-lookup"><span data-stu-id="71e39-145">By default, the BizTalk project system creates the **Type Name** from the name of the respective artifact.</span></span>  
  
     <span data-ttu-id="71e39-146">例。名前の新しいマップを作成する**Map1.btm**設定、**型名**プロパティの値を**Map1**します。</span><span class="sxs-lookup"><span data-stu-id="71e39-146">For e.g.: Creating a new map with name **Map1.btm** sets the **Type Name** property value to **Map1**.</span></span> <span data-ttu-id="71e39-147">ただし、既存の BizTalk アイテムは変更されません、**型名**します。</span><span class="sxs-lookup"><span data-stu-id="71e39-147">However, renaming an existing BizTalk artifact does not change the **Type Name**.</span></span>  
  
-   <span data-ttu-id="71e39-148">BizTalk プロジェクトの成果物のいずれかのファイル名は、.NET の予約された名前空間を確認します。</span><span class="sxs-lookup"><span data-stu-id="71e39-148">Ensure the filename of any of the artifacts in the BizTalk project is not a .NET reserved namespace.</span></span>  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a><span data-ttu-id="71e39-149">BizTalk アイテムのファイル名に関するエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="71e39-149">You receive errors about the File Name of a BizTalk artifact</span></span>  
  
### <a name="problem"></a><span data-ttu-id="71e39-150">問題</span><span class="sxs-lookup"><span data-stu-id="71e39-150">Problem</span></span>  
 <span data-ttu-id="71e39-151">BizTalk プロジェクトをビルドすると、BizTalk マッパーには、次のいずれかのようなエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="71e39-151">When you build a BizTalk project, the BizTalk Mapper generates an error similar to any of the following:</span></span>  
  
-   <span data-ttu-id="71e39-152">"ファイル\<filename\>が名前空間と型名のプロパティの値が重複します"。</span><span class="sxs-lookup"><span data-stu-id="71e39-152">“The File \<filename\> has duplicate values for namespace and type name properties.”</span></span>  
  
-   <span data-ttu-id="71e39-153">"名前空間\<名前\>'_' の定義が既に含まれています"。</span><span class="sxs-lookup"><span data-stu-id="71e39-153">“The namespace \<name\> already contains a definition for ‘_’.”</span></span>  
  
### <a name="cause"></a><span data-ttu-id="71e39-154">原因</span><span class="sxs-lookup"><span data-stu-id="71e39-154">Cause</span></span>  
 <span data-ttu-id="71e39-155">BizTalk プロジェクトには、次を確認します。</span><span class="sxs-lookup"><span data-stu-id="71e39-155">In the BizTalk project, check for the following:</span></span>  
  
-   <span data-ttu-id="71e39-156">複数のアイテムでは、同じファイル名があります。</span><span class="sxs-lookup"><span data-stu-id="71e39-156">Multiple artifacts have the same filename.</span></span> <span data-ttu-id="71e39-157">例: **Map1.xsd**と**Map1.btm**します。</span><span class="sxs-lookup"><span data-stu-id="71e39-157">For e.g., **Map1.xsd** and**Map1.btm**.</span></span>  
  
-   <span data-ttu-id="71e39-158">特殊文字のみのファイル名で構成されます (**~**、 **!**、  **@** など。)。</span><span class="sxs-lookup"><span data-stu-id="71e39-158">The filename comprises of only special characters (**~**, **!**, **@**, etc.).</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="71e39-159">解決策</span><span class="sxs-lookup"><span data-stu-id="71e39-159">Resolution</span></span>  
 <span data-ttu-id="71e39-160">この問題を解決するには、これらの回避策のいずれかに従うことができます。</span><span class="sxs-lookup"><span data-stu-id="71e39-160">To resolve this issue, you can follow any of these workarounds:</span></span>  
  
-   <span data-ttu-id="71e39-161">ファイルの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="71e39-161">Rename the files.</span></span> <span data-ttu-id="71e39-162">BizTalk プロジェクト内のすべての成果物のファイル名が一意で確認します。</span><span class="sxs-lookup"><span data-stu-id="71e39-162">Ensure the filenames for all artifacts in the BizTalk project are unique.</span></span>  
  
-   <span data-ttu-id="71e39-163">BizTalk プロジェクト内のすべてのアーティファクトが一意の型名を確認してください。</span><span class="sxs-lookup"><span data-stu-id="71e39-163">Ensure Type Name for all artifacts in the BizTalk project are unique.</span></span>  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a><span data-ttu-id="71e39-164">BizTalk マッパーで c# ワークフロー プロジェクトを構築するとすると、EnvDTE.dll のバージョンの競合に関する警告が表示します。</span><span class="sxs-lookup"><span data-stu-id="71e39-164">Building any C# workflow project with BizTalk Mapper shows a warning regarding version conflict for EnvDTE.dll</span></span>  
  
### <a name="problem"></a><span data-ttu-id="71e39-165">問題</span><span class="sxs-lookup"><span data-stu-id="71e39-165">Problem</span></span>  
 <span data-ttu-id="71e39-166">BizTalk マッパーで c# ワークフロー プロジェクトを構築するアクティビティは常に、EnvDTE.dll のバージョンの競合に関する次の警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="71e39-166">Building any C# workflow project with BizTalk Mapper acitivity always shows the following warning about version conflict for EnvDTE.dll.</span></span>  
  
 <span data-ttu-id="71e39-167">間の競合を解決する方法はありません"EnvDTE, バージョン 8.0.0.0、カルチャを = = neutral, PublicKeyToken = b03f5f7f11d50a3a"と"EnvDTE, バージョン 7.0.3300.0、カルチャを = = neutral, PublicKeyToken = b03f5f7f11d50a3a"。</span><span class="sxs-lookup"><span data-stu-id="71e39-167">No way to resolve conflict between "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" and "EnvDTE, Version=7.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a".</span></span> <span data-ttu-id="71e39-168">選択する"EnvDTE, バージョン 8.0.0.0、カルチャを = = neutral, PublicKeyToken = b03f5f7f11d50a3a"任意にします。</span><span class="sxs-lookup"><span data-stu-id="71e39-168">Choosing "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" arbitrarily.</span></span>  <span data-ttu-id="71e39-169">App.config のアセンブリの再割り当てを検討してください"EnvDTE, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a"バージョン「7.0.3300.0」からバージョン「8.0.0.0」[C:\Program Files (x86) \Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] から競合を解決し、警告を取り除きます。</span><span class="sxs-lookup"><span data-stu-id="71e39-169">Consider app.config remapping of assembly "EnvDTE, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" from Version "7.0.3300.0" [] to Version "8.0.0.0" [C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] to solve conflict and get rid of warning.</span></span> <span data-ttu-id="71e39-170">C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): warning MSB3247:同じ依存アセンブリの異なるバージョン間の競合が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="71e39-170">C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): warning MSB3247: Found conflicts between different versions of the same dependent assembly.</span></span>  
  
 <span data-ttu-id="71e39-171">WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe</span><span class="sxs-lookup"><span data-stu-id="71e39-171">WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe</span></span>  
  
### <a name="cause"></a><span data-ttu-id="71e39-172">原因</span><span class="sxs-lookup"><span data-stu-id="71e39-172">Cause</span></span>  
 <span data-ttu-id="71e39-173">これは、マッパー アクティビティを参照している Microsoft.BizTalk.Mapper.OM.dll が原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="71e39-173">This happens because of the Microsoft.BizTalk.Mapper.OM.dll which the Mapper activity references.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="71e39-174">解決策</span><span class="sxs-lookup"><span data-stu-id="71e39-174">Resolution</span></span>  
 <span data-ttu-id="71e39-175">警告を無視します。</span><span class="sxs-lookup"><span data-stu-id="71e39-175">Ignore the warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e39-176">参照</span><span class="sxs-lookup"><span data-stu-id="71e39-176">See Also</span></span>  
 [<span data-ttu-id="71e39-177">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="71e39-177">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)
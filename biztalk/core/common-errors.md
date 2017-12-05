---
title: "一般的なエラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4fe48a8e-def0-4a00-aa7f-9a49ae555351
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b882c44e69489114a2dd8084df71d6414df0cb5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="common-errors"></a><span data-ttu-id="c3884-102">一般的なエラー</span><span class="sxs-lookup"><span data-stu-id="c3884-102">Common Errors</span></span>
<span data-ttu-id="c3884-103">ここでは、BizTalk マッパーを使用してマップを作成しているときによく発生するエラー メッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="c3884-103">This topic lists out common error messages you may encounter while creating maps using BizTalk Mapper.</span></span>  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a><span data-ttu-id="c3884-104">日付の解析時にエラー イベント ID 324 が発生する</span><span class="sxs-lookup"><span data-stu-id="c3884-104">You receive error event ID 324 when parsing dates</span></span>  
  
### <a name="problem"></a><span data-ttu-id="c3884-105">問題</span><span class="sxs-lookup"><span data-stu-id="c3884-105">Problem</span></span>  
 <span data-ttu-id="c3884-106">データベースを使用すると**値抽出**日付フィールドをドキュメントを抽出するマップの functoid には、送信ドキュメント定義に対して検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="c3884-106">When you use the Database **Value Extractor** functoid in a map to extract a date field, your document may fail validation against the outbound document definition.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c3884-107">イベント ログに次のように、検証エラーをログ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3884-107"> may log a validation error similar to the following in the event log:</span></span>  
  
 <span data-ttu-id="c3884-108">BizTalk Server のイベント ソース:</span><span class="sxs-lookup"><span data-stu-id="c3884-108">Event Source: BizTalk Server</span></span>  
  
 <span data-ttu-id="c3884-109">イベント カテゴリ: ドキュメントの処理</span><span class="sxs-lookup"><span data-stu-id="c3884-109">Event Category: Document Processing</span></span>  
  
 <span data-ttu-id="c3884-110">イベント ID: 324</span><span class="sxs-lookup"><span data-stu-id="c3884-110">Event ID: 324</span></span>  
  
 <span data-ttu-id="c3884-111">説明:</span><span class="sxs-lookup"><span data-stu-id="c3884-111">Description:</span></span>  
  
 <span data-ttu-id="c3884-112">BizTalk Server でエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c3884-112">An error occurred in BizTalk Server.</span></span>  
  
 <span data-ttu-id="c3884-113">詳細:</span><span class="sxs-lookup"><span data-stu-id="c3884-113">Details:</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="c3884-114">次の理由により、XML ドキュメントを検証できませんでした: '10/12/1995 を解析中にエラー' date データ型として。</span><span class="sxs-lookup"><span data-stu-id="c3884-114">The XML document has failed validation for the following reason: Error parsing '10/12/1995' as date datatype.</span></span>  
  
 <span data-ttu-id="c3884-115">保留キュー ID:"{A1127909-CA36-4359-B672-7CBA8B60BDAF}"</span><span class="sxs-lookup"><span data-stu-id="c3884-115">Suspended Queue ID: "{A1127909-CA36-4359-B672-7CBA8B60BDAF}"</span></span>  
  
### <a name="cause"></a><span data-ttu-id="c3884-116">原因</span><span class="sxs-lookup"><span data-stu-id="c3884-116">Cause</span></span>  
 <span data-ttu-id="c3884-117">(データ ソースから返された) 日付形式が、XML で規定されている ISO 8601 形式ではありません。</span><span class="sxs-lookup"><span data-stu-id="c3884-117">The date format (as it is returned from the data source) is not in ISO 8601 format, which is the format required by XML.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="c3884-118">解決策</span><span class="sxs-lookup"><span data-stu-id="c3884-118">Resolution</span></span>  
 <span data-ttu-id="c3884-119">この問題を解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3884-119">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="c3884-120">送信ドキュメント定義を編集して、date データ型ではなく string データ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="c3884-120">Edit your outbound document definition to use a string datatype instead of a date datatype.</span></span>  
  
-   <span data-ttu-id="c3884-121">カスタム作成[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**スクリプト**データベースの出力を変換 functoid**値抽出**functoid を ISO 8601 形式にします。</span><span class="sxs-lookup"><span data-stu-id="c3884-121">Create a custom [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**Script** functoid that will convert the output of the Database **Value Extractor** functoid into the ISO 8601 format.</span></span>  
  
 <span data-ttu-id="c3884-122">詳細については、サポート技術情報の記事を参照してください[278737](http://support.microsoft.com/kb/278737/en-us)です。</span><span class="sxs-lookup"><span data-stu-id="c3884-122">For more information, see KB article [278737](http://support.microsoft.com/kb/278737/en-us).</span></span>  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a><span data-ttu-id="c3884-123">マップのコンパイル時に内部コンパイラ エラー (アドレス 53624FD6 の 0xc0000005) が発生する</span><span class="sxs-lookup"><span data-stu-id="c3884-123">You receive Internal Compiler Error (0xc0000005 at address 53624FD6) when compiling the maps</span></span>  
  
### <a name="problem"></a><span data-ttu-id="c3884-124">問題</span><span class="sxs-lookup"><span data-stu-id="c3884-124">Problem</span></span>  
 <span data-ttu-id="c3884-125">大きなスキーマ、マップ、またはオーケストレーションで構成された単一の BizTalk プロジェクトをコンパイルした場合、次のようなエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3884-125">When you compile a single BizTalk project that consists of large schemas, maps, or orchestrations, the compiler may generate an error similar to the following:</span></span>  
  
 <span data-ttu-id="c3884-126">内部コンパイラ エラー (アドレス 53624fd6 の 0xc0000005): 'CODEGEN' は、原因と考えられます。</span><span class="sxs-lookup"><span data-stu-id="c3884-126">Internal Compiler Error (0xc0000005 at address 53624FD6): likely culprit is 'CODEGEN'.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="c3884-127">原因</span><span class="sxs-lookup"><span data-stu-id="c3884-127">Cause</span></span>  
 <span data-ttu-id="c3884-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コンパイラには、単一のプロジェクトにおけるすべての文字列の合計サイズについて 16 MB の制限があります。</span><span class="sxs-lookup"><span data-stu-id="c3884-128">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler has a 16-megabyte limitation on the total size of all strings in a single project.</span></span> <span data-ttu-id="c3884-129">BizTalk プロジェクトをコンパイルしている間、コンパイラはアセンブリ作成のスキーマ、マップ、およびオーケストレーションをシリアル化し、これによってすべての文字列の合計サイズが増加し、制限を超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3884-129">While compiling BizTalk projects, the compiler serializes schemas, maps, and orchestrations for creating the assemblies, and this increases the total size of all strings, which may exceed the limitation.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="c3884-130">解決策</span><span class="sxs-lookup"><span data-stu-id="c3884-130">Resolution</span></span>  
 <span data-ttu-id="c3884-131">この問題を解決するには、スキーマまたはマップを個別の BizTalk プロジェクトに分離します。</span><span class="sxs-lookup"><span data-stu-id="c3884-131">To resolve this issue, you can separate schemas or maps into different BizTalk projects.</span></span>  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a><span data-ttu-id="c3884-132">BizTalk アイテムの型名についてのエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="c3884-132">You receive errors about the Type Name of a BizTalk artifact</span></span>  
  
### <a name="problem"></a><span data-ttu-id="c3884-133">問題</span><span class="sxs-lookup"><span data-stu-id="c3884-133">Problem</span></span>  
 <span data-ttu-id="c3884-134">BizTalk プロジェクトにファイル名で、マップの作成**System.btm**または**Microsoft.btm**です。</span><span class="sxs-lookup"><span data-stu-id="c3884-134">In a BizTalk project, create a map with filename **System.btm** or **Microsoft.btm**.</span></span> <span data-ttu-id="c3884-135">プロジェクトをビルドすると、BizTalk マッパーが次のようなエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c3884-135">When you build the project, the BizTalk Mapper generates an error similar to any of the following:</span></span>  
  
-   <span data-ttu-id="c3884-136">"型名 'SerializableAttribute' が存在しません..."</span><span class="sxs-lookup"><span data-stu-id="c3884-136">“The typename ‘SerializableAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="c3884-137">"型名 'NonSerializableAttribute' が存在しません..."</span><span class="sxs-lookup"><span data-stu-id="c3884-137">“The typename ‘NonSerializableAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="c3884-138">"型名 'SerializableAttributeAttribute' が存在しません..."</span><span class="sxs-lookup"><span data-stu-id="c3884-138">“The typename ‘SerializableAttributeAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="c3884-139">"型名 'XLANs' が存在しません..."</span><span class="sxs-lookup"><span data-stu-id="c3884-139">“The typename ‘XLANs’ does not exist…”</span></span>  
  
### <a name="cause"></a><span data-ttu-id="c3884-140">原因</span><span class="sxs-lookup"><span data-stu-id="c3884-140">Cause</span></span>  
 <span data-ttu-id="c3884-141">**型名**で、**プロパティ**グリッド必要はありません、予約された .NET 名前空間など**システム**、 **Microsoft**, などです。</span><span class="sxs-lookup"><span data-stu-id="c3884-141">The **Type Name** in the **Properties** grid should not have any reserved .NET namespaces, such as **System**, **Microsoft**, etc.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="c3884-142">解決策</span><span class="sxs-lookup"><span data-stu-id="c3884-142">Resolution</span></span>  
 <span data-ttu-id="c3884-143">この問題を解決するには、次のいずれかの対処方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3884-143">To resolve this issue, you can follow any of these workarounds:</span></span>  
  
-   <span data-ttu-id="c3884-144">マップの名前を、.NET の予約語ではない文字列に変更します。</span><span class="sxs-lookup"><span data-stu-id="c3884-144">Modify the name of the map to any string which is not a .NET reserved word.</span></span> <span data-ttu-id="c3884-145">既定では、BizTalk プロジェクト システムを作成、**型名**はそれぞれのアイテムの名前から。</span><span class="sxs-lookup"><span data-stu-id="c3884-145">By default, the BizTalk project system creates the **Type Name** from the name of the respective artifact.</span></span>  
  
     <span data-ttu-id="c3884-146">例:: 名前を持つ新しいマップを作成する**Map1.btm**設定、**型名**プロパティの値を**Map1**です。</span><span class="sxs-lookup"><span data-stu-id="c3884-146">For e.g.: Creating a new map with name **Map1.btm** sets the **Type Name** property value to **Map1**.</span></span> <span data-ttu-id="c3884-147">ただし、既存の BizTalk の名前を変更する成果物は変更されません、**型名**です。</span><span class="sxs-lookup"><span data-stu-id="c3884-147">However, renaming an existing BizTalk artifact does not change the **Type Name**.</span></span>  
  
-   <span data-ttu-id="c3884-148">BizTalk プロジェクトのアイテムのファイル名が .NET の予約された名前空間ではないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c3884-148">Ensure the filename of any of the artifacts in the BizTalk project is not a .NET reserved namespace.</span></span>  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a><span data-ttu-id="c3884-149">BizTalk アイテムのファイル名についてのエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="c3884-149">You receive errors about the File Name of a BizTalk artifact</span></span>  
  
### <a name="problem"></a><span data-ttu-id="c3884-150">問題</span><span class="sxs-lookup"><span data-stu-id="c3884-150">Problem</span></span>  
 <span data-ttu-id="c3884-151">BizTalk プロジェクトをビルドすると、BizTalk マッパーが次のようなエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c3884-151">When you build a BizTalk project, the BizTalk Mapper generates an error similar to any of the following:</span></span>  
  
-   <span data-ttu-id="c3884-152">"ファイル\<filename\>が名前空間と型名のプロパティの値が重複します"。</span><span class="sxs-lookup"><span data-stu-id="c3884-152">“The File \<filename\> has duplicate values for namespace and type name properties.”</span></span>  
  
-   <span data-ttu-id="c3884-153">"名前空間\<名前\>'_' の定義が既に含まれています"。</span><span class="sxs-lookup"><span data-stu-id="c3884-153">“The namespace \<name\> already contains a definition for ‘_’.”</span></span>  
  
### <a name="cause"></a><span data-ttu-id="c3884-154">原因</span><span class="sxs-lookup"><span data-stu-id="c3884-154">Cause</span></span>  
 <span data-ttu-id="c3884-155">BizTalk プロジェクトでは、次のことが検査されます。</span><span class="sxs-lookup"><span data-stu-id="c3884-155">In the BizTalk project, check for the following:</span></span>  
  
-   <span data-ttu-id="c3884-156">複数のアイテムが同じファイル名を持っている。</span><span class="sxs-lookup"><span data-stu-id="c3884-156">Multiple artifacts have the same filename.</span></span> <span data-ttu-id="c3884-157">例: **Map1.xsd**と**Map1.btm**です。</span><span class="sxs-lookup"><span data-stu-id="c3884-157">For e.g., **Map1.xsd** and**Map1.btm**.</span></span>  
  
-   <span data-ttu-id="c3884-158">特殊文字のみのファイル名で構成されます (**~**、 **!**、  **@** , などです。)。</span><span class="sxs-lookup"><span data-stu-id="c3884-158">The filename comprises of only special characters (**~**, **!**, **@**, etc.).</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="c3884-159">解決策</span><span class="sxs-lookup"><span data-stu-id="c3884-159">Resolution</span></span>  
 <span data-ttu-id="c3884-160">この問題を解決するには、次のいずれかの対処方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3884-160">To resolve this issue, you can follow any of these workarounds:</span></span>  
  
-   <span data-ttu-id="c3884-161">ファイルの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c3884-161">Rename the files.</span></span> <span data-ttu-id="c3884-162">BizTalk プロジェクトのすべてのアイテムのファイル名が一意であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3884-162">Ensure the filenames for all artifacts in the BizTalk project are unique.</span></span>  
  
-   <span data-ttu-id="c3884-163">BizTalk プロジェクトのすべてのアイテムの型名が一意であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3884-163">Ensure Type Name for all artifacts in the BizTalk project are unique.</span></span>  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a><span data-ttu-id="c3884-164">BizTalk マッパーを含む C# ワークフロー プロジェクトを構築すると、EnvDTE.dll のバージョンの競合に関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3884-164">Building any C# workflow project with BizTalk Mapper shows a warning regarding version conflict for EnvDTE.dll</span></span>  
  
### <a name="problem"></a><span data-ttu-id="c3884-165">問題</span><span class="sxs-lookup"><span data-stu-id="c3884-165">Problem</span></span>  
 <span data-ttu-id="c3884-166">BizTalk マッパー アクティビティを含む C# ワークフロー プロジェクトを構築すると、EnvDTE.dll のバージョンの競合に関する次の警告が常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3884-166">Building any C# workflow project with BizTalk Mapper acitivity always shows the following warning about version conflict for EnvDTE.dll.</span></span>  
  
 <span data-ttu-id="c3884-167">"EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" と "EnvDTE, Version=7.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" の間の競合を解決する方法がありません。</span><span class="sxs-lookup"><span data-stu-id="c3884-167">No way to resolve conflict between "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" and "EnvDTE, Version=7.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a".</span></span> <span data-ttu-id="c3884-168">任意で "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3884-168">Choosing "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" arbitrarily.</span></span>  <span data-ttu-id="c3884-169">競合を解決して警告を消去するために、app.config でアセンブリ "EnvDTE, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" をバージョン "7.0.3300.0" [] からバージョン "8.0.0.0" [C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] にマップし直してください。</span><span class="sxs-lookup"><span data-stu-id="c3884-169">Consider app.config remapping of assembly "EnvDTE, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" from Version "7.0.3300.0" [] to Version "8.0.0.0" [C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] to solve conflict and get rid of warning.</span></span> <span data-ttu-id="c3884-170">C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): 警告 msb 3247: 同じ依存アセンブリの異なるバージョン間の競合が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c3884-170">C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): warning MSB3247: Found conflicts between different versions of the same dependent assembly.</span></span>  
  
 <span data-ttu-id="c3884-171">WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe</span><span class="sxs-lookup"><span data-stu-id="c3884-171">WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe</span></span>  
  
### <a name="cause"></a><span data-ttu-id="c3884-172">原因</span><span class="sxs-lookup"><span data-stu-id="c3884-172">Cause</span></span>  
 <span data-ttu-id="c3884-173">これは、マッパー アクティビティが参照している Microsoft.BizTalk.Mapper.OM.dll が原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="c3884-173">This happens because of the Microsoft.BizTalk.Mapper.OM.dll which the Mapper activity references.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="c3884-174">解決策</span><span class="sxs-lookup"><span data-stu-id="c3884-174">Resolution</span></span>  
 <span data-ttu-id="c3884-175">警告を無視してください。</span><span class="sxs-lookup"><span data-stu-id="c3884-175">Ignore the warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3884-176">参照</span><span class="sxs-lookup"><span data-stu-id="c3884-176">See Also</span></span>  
 [<span data-ttu-id="c3884-177">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c3884-177">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)
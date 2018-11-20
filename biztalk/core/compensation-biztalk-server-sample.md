---
title: 補正 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- compensations, examples
- examples, compensations
- compensations, orchestrations
ms.assetid: 9d10c7be-6a4c-44cc-bf29-78ecdf147bd1
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8a2ba919a6d4ee5b84da8a9911604aff95a02e4
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630359"
---
# <a name="compensation-biztalk-server-sample"></a><span data-ttu-id="53962-102">補正 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="53962-102">Compensation (BizTalk Server Sample)</span></span>
<span data-ttu-id="53962-103">補正のサンプルを使用する方法を示します、**補正**のオーケストレーションの図形。</span><span class="sxs-lookup"><span data-stu-id="53962-103">The Compensation sample demonstrates how to use the **Compensate** shape in an orchestration.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="53962-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="53962-104">What This Sample Does</span></span>  
 <span data-ttu-id="53962-105">このサンプルでは、オーケストレーション内で既にコミットされたトランザクションを補正するため、次の一連の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="53962-105">This sample demonstrates how to compensate the transaction that has already been committed in the orchestration using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="53962-106">InfoPath フォームに顧客データを入力し、Web サービスとして公開されているオーケストレーションにデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="53962-106">Enter the customer data in the InfoPath form and submit the data to an orchestration that has been exposed as a Web service.</span></span>  
  
2.  <span data-ttu-id="53962-107">オーケストレーションには 2 つの並列アクションがあり、</span><span class="sxs-lookup"><span data-stu-id="53962-107">The orchestration has two parallel actions.</span></span> <span data-ttu-id="53962-108">1 つ目の並列アクションでは InfoPath フォームに受信確認を返し、2 つ目の並列アクションでは Northwind および BTSCompensationSampleMailingList データベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="53962-108">One returns an acknowledgment to the InfoPath form and the other updates the Northwind and BTSCompensationSampleMailingList databases.</span></span>  
  
3.  <span data-ttu-id="53962-109">2 番目のアクションで、オーケストレーション、受信メッセージをカスタマー リレーションシップ マネジメント (CRM) アプリケーションのメッセージ形式にマップし、更新、**顧客**Northwind データベースのテーブル。</span><span class="sxs-lookup"><span data-stu-id="53962-109">In the second action, the orchestration maps the incoming message to a customer relationship management (CRM) application message format and then updates the **Customers** table in the Northwind database.</span></span> <span data-ttu-id="53962-110">その後、BTSCompensationSampleMailingList データベースの Mailing List テーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="53962-110">After this, the Mailing List table in the BTSCompensationSampleMailingList database is updated.</span></span>  
  
4.  <span data-ttu-id="53962-111">どちらかの更新が失敗した場合は、外部アセンブリを呼び出すことによって Northwind データベースへの変更を補正し、元の顧客データをデータベースに再度書き込みます。</span><span class="sxs-lookup"><span data-stu-id="53962-111">If either update fails, the changes made to the Northwind database are compensated by calling an external assembly to write the original customer data back to the database.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="53962-112">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="53962-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="53962-113">A**スコープ**図形は、トランザクションの実行と補正を含む、例外処理は主に使用します。</span><span class="sxs-lookup"><span data-stu-id="53962-113">A **Scope** shape is primarily used for transactional execution and exception handling, including compensation.</span></span> <span data-ttu-id="53962-114">スコープは 2 つのブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="53962-114">A scope consists of two blocks.</span></span> <span data-ttu-id="53962-115">最初のブロックはコンテキスト ブロックであり、2 つ目のブロックは 1 つ以上の例外処理ブロックまたは補正ブロックです。</span><span class="sxs-lookup"><span data-stu-id="53962-115">The first block is the context block and the second block can be one or more exception-handling or compensation blocks.</span></span> <span data-ttu-id="53962-116">これは .NET プログラミング言語の try-catch ステートメントと類似しています。</span><span class="sxs-lookup"><span data-stu-id="53962-116">This is similar to the try-catch statement in the .NET programming language.</span></span> <span data-ttu-id="53962-117">UpdateContact.odx オーケストレーションには 2 つの並列アクションがあります。</span><span class="sxs-lookup"><span data-stu-id="53962-117">In the UpdateContact.odx orchestration, there are two parallel actions.</span></span> <span data-ttu-id="53962-118">Try ブロックには、右側の分岐で、**スコープ**Updated Backend Systems は、実行時間の長いトランザクションの種類と、トランザクション識別子は Upd_Backend という名前の図形。</span><span class="sxs-lookup"><span data-stu-id="53962-118">At the right-side branch, the try block is the **Scope** shape named Updated Backend Systems, which has a Long-Running transaction type and an Upd_Backend transaction identifier.</span></span> <span data-ttu-id="53962-119">フロー下方の catch ブロックは一般的な例外をキャッチして補正を開始します。</span><span class="sxs-lookup"><span data-stu-id="53962-119">Further down in the flow, there is a catch block that catches the general exception and initiates the compensation.</span></span>  
  
 <span data-ttu-id="53962-120">詳細については、**スコープ**図形は、「[スコープ](../core/scopes.md)します。</span><span class="sxs-lookup"><span data-stu-id="53962-120">For more information about the **Scope** shape, see [Scopes](../core/scopes.md).</span></span> <span data-ttu-id="53962-121">参照してください[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="53962-121">Also see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53962-122">トランザクションの種類をアトミックまたは長時間トランザクションに設定するには、オーケストレーション自体が長時間トランザクションであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="53962-122">The orchestration must itself be a long-running transaction for you to set the transaction type to Atomic or Long-Running.</span></span>  
  
 <span data-ttu-id="53962-123">Try ブロックでは、という名前の 2 つのスコープが**Update CRM**と**Update Mailing**します。</span><span class="sxs-lookup"><span data-stu-id="53962-123">In the try block, there are two scopes named **Update CRM** and **Update Mailing**.</span></span> <span data-ttu-id="53962-124">これらのスコープはどちらもアトミック トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="53962-124">Both of these scopes are atomic transactions.</span></span> <span data-ttu-id="53962-125">Update CRM スコープには try ブロックと補正ブロックがあります。</span><span class="sxs-lookup"><span data-stu-id="53962-125">In the Update CRM scope, there is a try block and a compensation block.</span></span> <span data-ttu-id="53962-126">try ブロックでは外部アセンブリへのメソッド呼び出しによって Northwind データベースを更新し、</span><span class="sxs-lookup"><span data-stu-id="53962-126">The try block updates the Northwind database through a method call to an external assembly.</span></span> <span data-ttu-id="53962-127">補正ブロックでは補正アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="53962-127">The compensation block is where the compensation action takes place.</span></span> <span data-ttu-id="53962-128">Update Backend Systems スコープで例外が発生した場合は、Undo CRM 式図形内のコードによってレコードを元の状態に更新します。</span><span class="sxs-lookup"><span data-stu-id="53962-128">When an exception happens in the Update Backend Systems scope, the code in Undo CRM Expression Shape updates the record back to its original state.</span></span> <span data-ttu-id="53962-129">これは、トリガー、**補正**例外のキャッチ ブロック内の図形。</span><span class="sxs-lookup"><span data-stu-id="53962-129">This is triggered by the **Compensate** shape in the Catch Exception block.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53962-130">アトミック トランザクションでは、トランザクション更新中にエラーが発生すると部分的な更新は自動的にロールバックされ、トランザクションの影響が除去されます。ただし、トランザクションで行われた .NET 呼び出しの影響は除去されません。</span><span class="sxs-lookup"><span data-stu-id="53962-130">Atomic transactions guarantee that any partial updates are rolled back automatically in the event of a failure during the transactional update, and that the effects of the transaction are erased (except for the effects of any .NET calls that are made in the transaction).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53962-131">長時間トランザクションは、その最後のステートメントが完了したときにコミットされたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="53962-131">A long-running transaction is considered committed when the last statement in it has completed.</span></span> <span data-ttu-id="53962-132">トランザクションが中断された場合、状態の自動的なロールバックは行われません。</span><span class="sxs-lookup"><span data-stu-id="53962-132">There is no automatic rollback of state in case of a transaction abort.</span></span> <span data-ttu-id="53962-133">これは、このサンプルで示される例外処理および補正処理を使ったプログラムによって実現できます。</span><span class="sxs-lookup"><span data-stu-id="53962-133">You can achieve this programmatically through the exception and compensation handlers demonstrated in this sample.</span></span>  
  
 <span data-ttu-id="53962-134">Catch ブロックで 1 つである**遅延**図形が 10 秒に設定します。</span><span class="sxs-lookup"><span data-stu-id="53962-134">In the catch block, there is one **Delay** shape set for ten seconds.</span></span> <span data-ttu-id="53962-135">補正アクションを遅らせる機能があります。</span><span class="sxs-lookup"><span data-stu-id="53962-135">This delays the compensation action.</span></span> <span data-ttu-id="53962-136">**補正**Upd_Backend トランザクションで補正アクションを開始図形。</span><span class="sxs-lookup"><span data-stu-id="53962-136">There is also a **Compensate** shape that initiates the compensation action in the Upd_Backend transaction.</span></span>  
  
 <span data-ttu-id="53962-137">オーケストレーションでは、入力メッセージを受信すると次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="53962-137">The following happens after the orchestration receives the input message:</span></span>  
  
1.  <span data-ttu-id="53962-138">UpdateCrm アセンブリによって Northwind データベースの行を更新します。</span><span class="sxs-lookup"><span data-stu-id="53962-138">The UpdateCrm assembly updates a row in the Northwind database.</span></span>  
  
2.  <span data-ttu-id="53962-139">UpdateMailingList アセンブリによって BTSCompensationSampleMailingList データベース内の一致するレコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="53962-139">The UpdateMailingList assembly updates a matching record in the BTSCompensationSampleMailingList database.</span></span>  
  
3.  <span data-ttu-id="53962-140">Northwind データベースの更新で失敗した場合は例外を返し、処理を終了します。</span><span class="sxs-lookup"><span data-stu-id="53962-140">In the event of a failure while updating the Northwind database, an exception is raised and the orchestration exits the process.</span></span>  
  
4.  <span data-ttu-id="53962-141">BTSCompensationSampleMailingList データベースの更新で失敗した場合は例外を返し、10 秒経過後、元の顧客データを Northwind データベースに再度書き込みます。</span><span class="sxs-lookup"><span data-stu-id="53962-141">In the event of a failure while updating the BTSCompensationSampleMailingList database, an exception is raised and a ten-second delay takes place before rewriting the original customer data back to the Northwind database.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="53962-142">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="53962-142">Where to Find This Sample</span></span>  
 <span data-ttu-id="53962-143">\<*パスのサンプル*\>\Orchestrations\Compensation\\</span><span class="sxs-lookup"><span data-stu-id="53962-143">\<*Samples Path*\>\Orchestrations\Compensation\\</span></span>  
  
 <span data-ttu-id="53962-144">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="53962-144">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="53962-145">ファイル</span><span class="sxs-lookup"><span data-stu-id="53962-145">File(s)</span></span>|<span data-ttu-id="53962-146">説明</span><span class="sxs-lookup"><span data-stu-id="53962-146">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53962-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="53962-147">Cleanup.bat</span></span>|<span data-ttu-id="53962-148">サンプルのアンインストールに使用するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="53962-148">Batch file used to uninstall the sample.</span></span>|  
|<span data-ttu-id="53962-149">CompensationOrchestration.btproj</span><span class="sxs-lookup"><span data-stu-id="53962-149">CompensationOrchestration.btproj</span></span>|<span data-ttu-id="53962-150">オーケストレーション プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="53962-150">Orchestration project.</span></span>|  
|<span data-ttu-id="53962-151">CompensationSample.sln</span><span class="sxs-lookup"><span data-stu-id="53962-151">CompensationSample.sln</span></span>|<span data-ttu-id="53962-152">サンプル ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="53962-152">Sample solution.</span></span>|  
|<span data-ttu-id="53962-153">CompensationSampleBinding.xml</span><span class="sxs-lookup"><span data-stu-id="53962-153">CompensationSampleBinding.xml</span></span>|<span data-ttu-id="53962-154">オーケストレーションのバインド データです。インストール中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="53962-154">Binding data for the orchestration (used during installation).</span></span>|  
|<span data-ttu-id="53962-155">ContactInfo.xsd</span><span class="sxs-lookup"><span data-stu-id="53962-155">ContactInfo.xsd</span></span>|<span data-ttu-id="53962-156">担当者情報のメッセージ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="53962-156">Contact information message schema.</span></span>|  
|<span data-ttu-id="53962-157">ContactInfo.xsx</span><span class="sxs-lookup"><span data-stu-id="53962-157">ContactInfo.xsx</span></span>|<span data-ttu-id="53962-158">オーケストレーション デザイナーのレイアウト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="53962-158">Orchestration Designer layout file.</span></span>|  
|<span data-ttu-id="53962-159">CreateSQLDataStore.sql</span><span class="sxs-lookup"><span data-stu-id="53962-159">CreateSQLDataStore.sql</span></span>|<span data-ttu-id="53962-160">サンプル データベースを作成してデータを取り込む SQL スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="53962-160">SQL script to create and populate the sample database.</span></span>|  
|<span data-ttu-id="53962-161">CrmSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="53962-161">CrmSchema.xsd</span></span>|<span data-ttu-id="53962-162">CRM の更新メッセージ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="53962-162">CRM update message schema.</span></span>|  
|<span data-ttu-id="53962-163">MailingListSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="53962-163">MailingListSchema.xsd</span></span>|<span data-ttu-id="53962-164">メーリング リストのメッセージの更新スキーマです。</span><span class="sxs-lookup"><span data-stu-id="53962-164">Mailing list message update schema.</span></span>|  
|<span data-ttu-id="53962-165">RemoveVirDir.vbs</span><span class="sxs-lookup"><span data-stu-id="53962-165">RemoveVirDir.vbs</span></span>|<span data-ttu-id="53962-166">Web サービスの仮想ディレクトリと物理ディレクトリを削除する、Microsoft Visual Basic Scripting Edition (VBScript) のスクリプトです。アンインストール中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="53962-166">Microsoft Visual Basic Scripting Edition (VBScript) script to remove Web service virtual and physical directories (used during uninstallation).</span></span>|  
|<span data-ttu-id="53962-167">Request2Crm.btm</span><span class="sxs-lookup"><span data-stu-id="53962-167">Request2Crm.btm</span></span>|<span data-ttu-id="53962-168">要求 (担当者情報) を CRM の更新メッセージに変換するメッセージ マップです。</span><span class="sxs-lookup"><span data-stu-id="53962-168">Message map to translate from request (contact info) to CRM update message.</span></span>|  
|<span data-ttu-id="53962-169">Request2MailingList.btm</span><span class="sxs-lookup"><span data-stu-id="53962-169">Request2MailingList.btm</span></span>|<span data-ttu-id="53962-170">要求 (担当者情報) をメーリング リストのメッセージに変換するメッセージ マップです。</span><span class="sxs-lookup"><span data-stu-id="53962-170">Message map to translate from request (contact info) to mailing list message.</span></span>|  
|<span data-ttu-id="53962-171">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="53962-171">Setup.bat</span></span>|<span data-ttu-id="53962-172">このサンプルをインストールするバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="53962-172">Batch file to install this sample.</span></span>|  
|<span data-ttu-id="53962-173">UpdateContact.odx</span><span class="sxs-lookup"><span data-stu-id="53962-173">UpdateContact.odx</span></span>|<span data-ttu-id="53962-174">オーケストレーション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="53962-174">Orchestration file.</span></span>|  
|<span data-ttu-id="53962-175">UpdateRequest2UpdateResponse.btm</span><span class="sxs-lookup"><span data-stu-id="53962-175">UpdateRequest2UpdateResponse.btm</span></span>|<span data-ttu-id="53962-176">要求 (担当者情報) を応答メッセージに変換するメッセージ マップです。</span><span class="sxs-lookup"><span data-stu-id="53962-176">Message map to translate from request (contact info) to a response message.</span></span>|  
|<span data-ttu-id="53962-177">UpdateResponse.xsd</span><span class="sxs-lookup"><span data-stu-id="53962-177">UpdateResponse.xsd</span></span>|<span data-ttu-id="53962-178">応答メッセージ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="53962-178">Response message schema.</span></span>|  
|<span data-ttu-id="53962-179">InfoPath\Contact Info Update.xsn</span><span class="sxs-lookup"><span data-stu-id="53962-179">InfoPath\Contact Info Update.xsn</span></span>|<span data-ttu-id="53962-180">Microsoft InfoPath ファイルが Web サービスのオーケストレーションにフォームを送信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="53962-180">Microsoft InfoPath file used to submit forms to the orchestration Web service.</span></span>|  
|<span data-ttu-id="53962-181">UpdateCrm\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="53962-181">UpdateCrm\AssemblyInfo.cs</span></span>|<span data-ttu-id="53962-182">UpdateCrm アセンブリ用のアセンブリ情報ソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="53962-182">Assembly information source file for the UpdateCrm assembly.</span></span> <span data-ttu-id="53962-183">UpdateCrm アセンブリでは、Northwind データベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="53962-183">(The UpdateCrm assembly updates the Northwind database.)</span></span>|  
|<span data-ttu-id="53962-184">UpdateCrm\UpdateCrm.cs</span><span class="sxs-lookup"><span data-stu-id="53962-184">UpdateCrm\UpdateCrm.cs</span></span>|<span data-ttu-id="53962-185">UpdateCrm アセンブリのメインのソース コードです。</span><span class="sxs-lookup"><span data-stu-id="53962-185">Main source code for the UpdateCrm assembly.</span></span>|  
|<span data-ttu-id="53962-186">UpdateCrm\UpdateCRM.csproj</span><span class="sxs-lookup"><span data-stu-id="53962-186">UpdateCrm\UpdateCRM.csproj</span></span>|<span data-ttu-id="53962-187">UpdateCrm プロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="53962-187">UpdateCrm project file.</span></span>|  
|<span data-ttu-id="53962-188">UpdateMailingList\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="53962-188">UpdateMailingList\AssemblyInfo.cs</span></span>|<span data-ttu-id="53962-189">UpdateMailingList アセンブリ用のアセンブリ情報ソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="53962-189">Assembly information source file for the UpdateMailingList assembly.</span></span> <span data-ttu-id="53962-190">UpdateMailingList アセンブリでは、サンプル データベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="53962-190">(The UpdateMailingList assembly updates the sample database.)</span></span>|  
|<span data-ttu-id="53962-191">UpdateMailingList\UpdateMailingList.cs</span><span class="sxs-lookup"><span data-stu-id="53962-191">UpdateMailingList\UpdateMailingList.cs</span></span>|<span data-ttu-id="53962-192">UpdateMailingList アセンブリのメインのソース コードです。</span><span class="sxs-lookup"><span data-stu-id="53962-192">Main source code for the UpdateMailingList assembly.</span></span>|  
|<span data-ttu-id="53962-193">UpdateMailingList\UpdateMailingList.csproj</span><span class="sxs-lookup"><span data-stu-id="53962-193">UpdateMailingList\UpdateMailingList.csproj</span></span>|<span data-ttu-id="53962-194">UpdateMailingList プロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="53962-194">UpdateMailingList project file.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="53962-195">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="53962-195">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-compensation-sample"></a><span data-ttu-id="53962-196">補正のサンプルをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="53962-196">To build and initialize the Compensation sample</span></span>  
  
1. <span data-ttu-id="53962-197">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="53962-197">In a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="53962-198">\<*パスのサンプル*\>\Orchestrations\Compensation\\</span><span class="sxs-lookup"><span data-stu-id="53962-198">\<*Samples Path*\>\Orchestrations\Compensation\\</span></span>  
  
2. <span data-ttu-id="53962-199">Setup.bat を実行します。処理内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53962-199">Run Setup.bat, which performs the following actions:</span></span>  
  
   -   <span data-ttu-id="53962-200">サンプル アセンブリをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="53962-200">Build and deploy the sample assembly.</span></span>  
  
   -   <span data-ttu-id="53962-201">BizTalk Web サービス公開ウィザードの起動時に、次の操作を手動で行います。</span><span class="sxs-lookup"><span data-stu-id="53962-201">When the BizTalk Web Services Publishing Wizard launches, do the following manually:</span></span>  
  
   1.  <span data-ttu-id="53962-202">**BizTalk Web サービス公開ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="53962-202">On the **Welcome to the BizTalk Web Services Publishing Wizard** page, click **Next**.</span></span>  
  
   2.  <span data-ttu-id="53962-203">**Web サービスの作成**] ページで、[ **web サービスとして公開する BizTalk オーケストレーション**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="53962-203">On the **Create Web Service** page, select **Publish BizTalk orchestration as web services**, and then click **Next**.</span></span>  
  
   3.  <span data-ttu-id="53962-204">**BizTalk アセンブリ**ページを参照して選択\<*サンプル パス*\>\Orchestrations\Compensation\bin\Release\CompensationOrchestration.dll と順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="53962-204">On the **BizTalk Assembly** page, browse and select \<*Samples Path*\>\Orchestrations\Compensation\bin\Release\CompensationOrchestration.dll, and then click **Next**.</span></span>  
  
   4.  <span data-ttu-id="53962-205">**オーケストレーションおよびポート**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="53962-205">On the **Orchestrations and Ports** page, click **Next**.</span></span>  
  
   5.  <span data-ttu-id="53962-206">**Web サービスのプロパティ**] ページの [ **web サービスのターゲット名前空間**、型`http://Microsoft.BizTalk.Samples.Compensation/`、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="53962-206">On the **Web Service Properties** page, in **Target namespace of web service**, type `http://Microsoft.BizTalk.Samples.Compensation/`, and then click **Next**.</span></span>  
  
   6.  <span data-ttu-id="53962-207">**Web サービス プロジェクト**] ページの [**場所**、型`http://localhost/CompensationOrchestrationWebServiceProxy`します。</span><span class="sxs-lookup"><span data-stu-id="53962-207">On the **Web Service Project** page, in **Location**, type `http://localhost/CompensationOrchestrationWebServiceProxy`.</span></span>  
  
   7.  <span data-ttu-id="53962-208">選択、 **web サービスへの匿名アクセスを許可する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="53962-208">Select the **Allow anonymous access to web service** check box.</span></span>  
  
   8.  <span data-ttu-id="53962-209">選択、**作成 BizTalk 受信場所を次のアプリケーションに**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="53962-209">Select the **Create BizTalk receive location in the following application** check box.</span></span>  
  
   9. <span data-ttu-id="53962-210">**作成 BizTalk 受信場所を次のアプリケーションに**ドロップダウン メニューで、 **BizTalk アプリケーション 1**クリックしてドロップダウン リストから**次**。</span><span class="sxs-lookup"><span data-stu-id="53962-210">In the **Create BizTalk receive location in the following application** drop-down menu, select **BizTalk Application 1** from the drop-down list, and then click **Next**.</span></span>  
  
   10. <span data-ttu-id="53962-211">**Web サービス プロジェクトの概要**] ページで [**作成**です。</span><span class="sxs-lookup"><span data-stu-id="53962-211">On the **Web Service Project Summary** page, click **Create**.</span></span>  
  
   11. <span data-ttu-id="53962-212">**BizTalk Web サービス公開ウィザードを完了**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="53962-212">On the **Completing the BizTalk Web Services Publishing Wizard** page, click **Finish**.</span></span>  
  
3. <span data-ttu-id="53962-213">セットアップによりポートが作成およびバインドされ、サンプル用のバックエンド データベースが作成されます。さらに、C# アセンブリがグローバル アセンブリ キャッシュに追加されます。</span><span class="sxs-lookup"><span data-stu-id="53962-213">Setup creates and binds ports, creates the back-end database for the sample, and adds C# assemblies to the global assembly cache.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="53962-214">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53962-214">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="53962-215">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="53962-215">Running This Sample</span></span>  
 <span data-ttu-id="53962-216">このサンプルをビルドおよび初期化したら、サンプルの実行前に次のことを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="53962-216">After you build and initialize this sample, consider the following before you run it:</span></span>  
  
- <span data-ttu-id="53962-217">このサンプルを実行している場合[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、IIS アプリケーション プールを作成し、BizTalk アプリケーション ユーザー Windows グループのメンバーであるアカウントにその id を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53962-217">If you are running this sample on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], you must create an IIS application pool and set its identity to an account that is a member of the BizTalk Application Users Windows group.</span></span> <span data-ttu-id="53962-218">また、オーケストレーションの Web サービスの仮想ディレクトリを更新し、このアプリケーション プール内で実行されるよう設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53962-218">You also need to update the orchestration Web service virtual directory to run within this application pool.</span></span>  
  
- <span data-ttu-id="53962-219">BizTalk 分離ホスト ユーザー グループに ASPNET アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="53962-219">Add the ASPNET account to the BizTalk Isolated Host Users group.</span></span>  
  
- <span data-ttu-id="53962-220">BizTalk Application Users グループの db_owner アクセス許可を与える、 **BTSCompensationSampleMailingList**と**Northwind**データベース。</span><span class="sxs-lookup"><span data-stu-id="53962-220">Give the BizTalk Application Users group db_owner permission to the **BTSCompensationSampleMailingList** and **Northwind** databases.</span></span>  
  
- <span data-ttu-id="53962-221">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が既定の場所にインストールされていない (BizTalk Server のドライブ: \Program Files\Microsoft\<バージョン\>\\) を使用する前に Contact Info Update.xsn フォームを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53962-221">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is not installed in the default location (drive:\Program Files\Microsoft BizTalk Server \<version\>\\), you must publish the Contact Info Update.xsn form before using it.</span></span> <span data-ttu-id="53962-222">これを行うには次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="53962-222">To do so, do the following.</span></span>  
  
  #### <a name="to-publish-the-infopath-form"></a><span data-ttu-id="53962-223">InfoPath フォームを公開するには</span><span class="sxs-lookup"><span data-stu-id="53962-223">To publish the InfoPath form</span></span>  
  
  1.  <span data-ttu-id="53962-224">Internet Explorer で、上、**ツール** メニューのをクリックして**インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="53962-224">In Internet Explorer, on the **Tools** menu, click **Internet Options**.</span></span>  
  
  2.  <span data-ttu-id="53962-225">**セキュリティ**] タブで [**インターネット**、順にクリックします**レベルのカスタマイズ**します。</span><span class="sxs-lookup"><span data-stu-id="53962-225">On the **Security** tab, click **Internet**, and then click **Custom Level**.</span></span>  
  
  3.  <span data-ttu-id="53962-226">**[その他]** セクションでは必ず、**ドメイン間でデータ ソースへのアクセス**設定が有効であり、クリックして **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="53962-226">In the **Miscellaneous** section, ensure that the **Access data sources across domains** setting is enabled, and then click **OK**.</span></span> <span data-ttu-id="53962-227">InfoPath ユーザー インターフェイス ソリューションのスクリプト コードを実行するには、この設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="53962-227">This setting is required for the InfoPath user interface solution scripting code to run.</span></span>  
  
  4.  <span data-ttu-id="53962-228">Windows エクスプ ローラーに移動します\<*サンプル パス*\>\Orchestrations\Compensation\InfoPath、右クリック**Contact Info Update.xsn**  をクリックし、  **。デザイン**します。</span><span class="sxs-lookup"><span data-stu-id="53962-228">In Windows Explorer, navigate to \<*Samples Path*\>\Orchestrations\Compensation\InfoPath, right-click **Contact Info Update.xsn** and then click **Design**.</span></span>  
  
  5.  <span data-ttu-id="53962-229">InfoPath Contact Info Update ソリューションがデザイン モードで開きます。</span><span class="sxs-lookup"><span data-stu-id="53962-229">The InfoPath Contact Info Update solution opens in design mode.</span></span>  
  
  6.  <span data-ttu-id="53962-230">InfoPath Contact Info Update アプリケーションでの**ファイル** メニューのをクリックして**発行**します。</span><span class="sxs-lookup"><span data-stu-id="53962-230">In the InfoPath Contact Info Update application, on the **File** menu, click **Publish**.</span></span>  
  
  7.  <span data-ttu-id="53962-231">公開ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53962-231">The Publish Wizard appears.</span></span>  
  
  8.  <span data-ttu-id="53962-232">選択**このコンピューターまたはネットワーク上の共有フォルダーに**パスにソリューションを発行および\<*サンプル パス*\>\Orchestrations\Compensation\InfoPath\Contact InfoUpdate.xsn します。</span><span class="sxs-lookup"><span data-stu-id="53962-232">Select **To a shared folder on this computer or on a network** and publish the solution to the path \<*Samples Path*\>\Orchestrations\Compensation\InfoPath\Contact Info Update.xsn.</span></span>  
  
  9. <span data-ttu-id="53962-233">デザイン モードの InfoPath を閉じます。</span><span class="sxs-lookup"><span data-stu-id="53962-233">Close the design mode InfoPath.</span></span>  
  
- <span data-ttu-id="53962-234">以上で、サンプルの実行準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="53962-234">You are ready to run this sample.</span></span>  
  
  #### <a name="to-run-the-compensation-sample"></a><span data-ttu-id="53962-235">補正のサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="53962-235">To run the Compensation sample</span></span>  
  
  1.  <span data-ttu-id="53962-236">ダブルクリック**Contact Info Update.xsn** InfoPath で開きます。</span><span class="sxs-lookup"><span data-stu-id="53962-236">Double-click **Contact Info Update.xsn** to open it in InfoPath.</span></span>  
  
  2.  <span data-ttu-id="53962-237">両方のデータベースに存在するアカウントのフォームに記入します。</span><span class="sxs-lookup"><span data-stu-id="53962-237">Fill out the form for an account that exists in both databases.</span></span> <span data-ttu-id="53962-238">たとえば、Northwind の Customers テーブルの既存のアカウント ID "ALFKI" を使用します。</span><span class="sxs-lookup"><span data-stu-id="53962-238">For example, use an existing account ID "ALFKI" from the Northwind Customers table.</span></span>  
  
  3.  <span data-ttu-id="53962-239">**ファイル**メニューの [**送信**、] をクリック**送信**します。</span><span class="sxs-lookup"><span data-stu-id="53962-239">On the **File** menu, select **Submit**, and click **Submit**.</span></span>  
  
  4.  <span data-ttu-id="53962-240">応答ドキュメントに表示されます、 \<*サンプル パス*\>\Orchestrations\Compensation\Out フォルダーと、Northwind と BTSCompensationSampleMailingList データベースの両方を更新する必要がありますInfoPath フォームから新しいデータです。</span><span class="sxs-lookup"><span data-stu-id="53962-240">The response document should appear in the \<*Samples Path*\>\Orchestrations\Compensation\Out folder, and both the Northwind and the BTSCompensationSampleMailingList databases should be updated with the new data from the InfoPath form.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="53962-241">BTSCompensationSampleMailingList データベースを接続解除するか、オフラインにして、オーケストレーションで実行される補正アクションをテストできます。</span><span class="sxs-lookup"><span data-stu-id="53962-241">You can detach the BTSCompensationSampleMailingList database or take it offline to test the compensation action that the orchestration performs.</span></span> <span data-ttu-id="53962-242">Northwind データベースで先にレコードが更新されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53962-242">Observe that the record is updated in the Northwind database first.</span></span> <span data-ttu-id="53962-243">その後、オーケストレーションが BTSCompensationSampleMailingList データベースを更新しようとすると、データベースが接続解除されているために、更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="53962-243">Then, when the orchestration tries to update the BTSCompensationSampleMailingList database, because that database is detached, the update fails.</span></span> <span data-ttu-id="53962-244">したがって、例外が発行され、10 秒が経過した後に補正アクションが実行されて、元の顧客データが Northwind データベースに再度書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="53962-244">Therefore, an exception is raised and there is a ten-second delay before the compensation action takes place to write the original customer data back to the Northwind database.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="53962-245">"ユーザー 'IIS APPPOOL\DefaultAppPool' はログインできませんでした。" というエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="53962-245">You may get a "Login failed for user 'IIS APPPOOL\DefaultAppPool' error.</span></span> <span data-ttu-id="53962-246">これは、トークンベースのサーバー アクセスの検証エラーが原因となっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53962-246">It might be because of the token-based server access validation failure.</span></span> <span data-ttu-id="53962-247">このエラーを解決するには、新しいアプリケーション プールを作成し、そのプールで管理アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="53962-247">To resolve this error, create a new application pool and use the administrator account in it.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="53962-248">このサンプルのアンインストール</span><span class="sxs-lookup"><span data-stu-id="53962-248">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-compensation-sample"></a><span data-ttu-id="53962-249">補正のサンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="53962-249">To uninstall the Compensation sample</span></span>  
  
1. <span data-ttu-id="53962-250">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="53962-250">In a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="53962-251">\<*パスのサンプル*\>\Orchestrations\Compensation\\</span><span class="sxs-lookup"><span data-stu-id="53962-251">\<*Samples Path*\>\Orchestrations\Compensation\\</span></span>  
  
2. <span data-ttu-id="53962-252">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="53962-252">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53962-253">参照</span><span class="sxs-lookup"><span data-stu-id="53962-253">See Also</span></span>  
 [<span data-ttu-id="53962-254">オーケストレーション (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="53962-254">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)

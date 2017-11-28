---
title: "逆アセンブリ ステージ (回復可能なインターチェンジ処理) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 552b1e90-f75d-4713-8c7b-155a52819308
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f36dd7a9d8bb10180d4af0562ba1e869957415d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="disassembly-stage-recoverable-interchange-processing"></a><span data-ttu-id="96522-102">逆アセンブリ ステージ (回復可能なインターチェンジ処理)</span><span class="sxs-lookup"><span data-stu-id="96522-102">Disassembly Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="96522-103">インターチェンジは、逆アセンブリ ステージにおいて 2 つのモードで処理されます。</span><span class="sxs-lookup"><span data-stu-id="96522-103">Interchanges are processed at the disassembly stage in two modes:</span></span>  
  
-   <span data-ttu-id="96522-104">**標準モードです。**</span><span class="sxs-lookup"><span data-stu-id="96522-104">**Standard mode.**</span></span> <span data-ttu-id="96522-105">受信パイプラインの逆アセンブラー コンポーネントが構成されて標準の逆アセンブリが行われる場合、インターチェンジに含まれるメッセージの抽出、受信パイプラインによるメッセージの処理、メッセージのマップ、およびトランザクションの作業単位としてのメッセージの公開が行われます。</span><span class="sxs-lookup"><span data-stu-id="96522-105">When the disassembler component of a receive pipeline is configured to perform standard disassembly, the messages contained in an interchange are extracted, processed by the receive pipeline, mapped, and published as a transactional unit of work.</span></span> <span data-ttu-id="96522-106">つまり、インターチェンジ全体と含まれるメッセージがすべて処理されて、メッセージ ボックス データベースに公開されます。または、保留キューにインターチェンジが配置されます。</span><span class="sxs-lookup"><span data-stu-id="96522-106">That is, either the entire interchange and its contained messages are fully processed and published into the MessageBox database, or the interchange is placed in the Suspended queue.</span></span>  
  
-   <span data-ttu-id="96522-107">**回復可能なモードです。**</span><span class="sxs-lookup"><span data-stu-id="96522-107">**Recoverable mode.**</span></span> <span data-ttu-id="96522-108">実行する、受信パイプラインの逆アセンブラー コンポーネントを構成するとき**回復可能なインターチェンジ処理**インターチェンジに含まれているメッセージは、それぞれ個別に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="96522-108">When the disassembler component of a receive pipeline is configured to perform **recoverable interchange processing**, the messages contained in an interchange are extracted independently of each other.</span></span> <span data-ttu-id="96522-109">抽出に成功したメッセージは、受信パイプラインの下に反映されます。</span><span class="sxs-lookup"><span data-stu-id="96522-109">Messages that are successfully extracted are propagated further down the receive pipeline.</span></span> <span data-ttu-id="96522-110">インターチェンジ内で確認されたメッセージの抽出に失敗した場合、そのメッセージは、保留キューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="96522-110">Messages that are identified within an interchange but are not successfully extracted are placed in the Suspended queue.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="96522-111">使用例</span><span class="sxs-lookup"><span data-stu-id="96522-111">Examples</span></span>  
 <span data-ttu-id="96522-112">次の例は、インターチェンジ処理のシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="96522-112">The following examples illustrate interchange processing scenarios.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="96522-113">例 1</span><span class="sxs-lookup"><span data-stu-id="96522-113">Example 1</span></span>  
 <span data-ttu-id="96522-114">この例では、標準のインターチェンジの受信場所で次の疑似インターチェンジが送信されます。</span><span class="sxs-lookup"><span data-stu-id="96522-114">In this example, the following pseudo-interchange is submitted on a standard interchange receive location.</span></span> <span data-ttu-id="96522-115">つまり、受信パイプラインの逆アセンブラー コンポーネントが構成されて、標準のインターチェンジ処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="96522-115">That is, the disassembler component in the receive pipeline is configured for standard interchange processing.</span></span>  
  
```  
<Interchange>  
<Document1>...</Document1>  
<Document2 failure=”routing”>...</Document2>  
<Document3>...</Document3>  
<Document4 failure=”pipeline” recoverableError=”true”>...</Document4>  
<Document5>...</Document5>  
</Interchange>  
```  
  
 <span data-ttu-id="96522-116">このインターチェンジには、5 つのメッセージが含まれます。これらのメッセージは、逆アセンブラーによるインターチェンジからの抽出が成功したメッセージです。</span><span class="sxs-lookup"><span data-stu-id="96522-116">This interchange contains five messages, all of which the disassembler successfully extracts from the interchange.</span></span> <span data-ttu-id="96522-117">これらのメッセージは、次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="96522-117">They are processed as follows:</span></span>  
  
-   <span data-ttu-id="96522-118">1 番目から 3 番目までのメッセージは、パイプラインを通じて伝達され、公開用のメッセージとなります。</span><span class="sxs-lookup"><span data-stu-id="96522-118">The first, second, and third messages propagate through the pipeline and are ready to be published.</span></span>  
  
-   <span data-ttu-id="96522-119">4 番目のメッセージは、パイプラインの逆アセンブリ ステージで処理に失敗します。</span><span class="sxs-lookup"><span data-stu-id="96522-119">The fourth message fails processing at the disassembling stage in the pipeline.</span></span> <span data-ttu-id="96522-120">このため、ロールバックされているすべてのメッセージと元のインターチェンジ メッセージが再開可能な状態で保留されます。</span><span class="sxs-lookup"><span data-stu-id="96522-120">This causes all the messages that have already been processed to roll back and the original interchange message to be suspended as resumable.</span></span>  
  
 <span data-ttu-id="96522-121">送信結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="96522-121">The result of submission is:</span></span>  
  
-   <span data-ttu-id="96522-122">何も公開されません。</span><span class="sxs-lookup"><span data-stu-id="96522-122">Nothing is published.</span></span> <span data-ttu-id="96522-123">標準のインターチェンジ処理で、抽出されたメッセージのインターチェンジ処理中 (または処理後) に障害が発生した場合、すべての抽出されたメッセージが破棄され、元のインターチェンジは再開可能な状態で保留キューに配置されます。このため、元のインターチェンジが保留されます。</span><span class="sxs-lookup"><span data-stu-id="96522-123">The original interchange is suspended because in standard interchange processing, any extracted message that fails at any point during or after interchange processing results in all extracted messages being discarded and the original interchange being placed on the Suspended queue as resumable.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="96522-124">例 2</span><span class="sxs-lookup"><span data-stu-id="96522-124">Example 2</span></span>  
 <span data-ttu-id="96522-125">この例では、前の例と同じインターチェンジ処理と伝達シナリオを使用します。逆アセンブリ ステージを構成して回復可能なインターチェンジ処理が行われる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="96522-125">The example uses the same interchange processing and propagation scenario as the previous example, except that the disassembly stage is configured to do recoverable interchange processing.</span></span>  
  
 <span data-ttu-id="96522-126">送信の結果、抽出された各メッセージがすべて処理され、元のインターチェンジが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="96522-126">The result of submission is that individual extracted messages are all processed and the original interchange is discarded.</span></span> <span data-ttu-id="96522-127">各メッセージは、次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="96522-127">The individual messages are processed as follows:</span></span>  
  
-   <span data-ttu-id="96522-128">1 番目から 3 番目までのメッセージは、パイプラインを通じて伝達され、公開用のメッセージとなります。</span><span class="sxs-lookup"><span data-stu-id="96522-128">The first, second, and third messages propagate through the pipeline and are ready to be published.</span></span>  
  
-   <span data-ttu-id="96522-129">4 番目のメッセージは、逆アセンブリ処理に失敗し (抽出後に不具合が発生する)、保留用のメッセージとなります。</span><span class="sxs-lookup"><span data-stu-id="96522-129">The fourth message fails disassembly processing (that is, something goes wrong after it is extracted) and is ready to be suspended.</span></span>  
  
-   <span data-ttu-id="96522-130">5 番目のメッセージは、パイプラインを通じて伝達され、公開用のメッセージとなります。</span><span class="sxs-lookup"><span data-stu-id="96522-130">The fifth message propagates through the pipeline and is ready to be published.</span></span>  
  
-   <span data-ttu-id="96522-131">すべてのメッセージがインターチェンジから抽出されると、メッセージ 1、メッセージ 2、メッセージ 3、およびメッセージ 5 は、メッセージ ボックス データベースに公開され、メッセージ 4 は、保留キューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="96522-131">After all messages are extracted from the interchange, messages 1, 2, 3, and 5 are published into the MessageBox database, and message 4 is placed on the Suspended queue.</span></span> <span data-ttu-id="96522-132">また、一致するサブスクライバーがないためにルーティング エラーが発生すると、メッセージ 2 が保留キューにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="96522-132">Message 2 is also redirected to the Suspended queue because of a routing failure due to no matching subscriber.</span></span>  
  
## <a name="configuring-recoverable-interchange-processing"></a><span data-ttu-id="96522-133">回復可能なインターチェンジ処理の構成</span><span class="sxs-lookup"><span data-stu-id="96522-133">Configuring Recoverable Interchange Processing</span></span>  
 <span data-ttu-id="96522-134">回復可能なインターチェンジ処理は、受信パイプラインの逆アセンブラー コンポーネントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="96522-134">Recoverable interchange processing is a property of the disassembler component of a receive pipeline.</span></span> <span data-ttu-id="96522-135">すべての逆アセンブラー コンポーネントで回復可能なインターチェンジ処理を指定できるとは限りません。たとえば、ネイティブの BizTalk Framework 逆アセンブラーでは、このような処理を指定できません。</span><span class="sxs-lookup"><span data-stu-id="96522-135">Not all disassembler components allow you to specify recoverable interchange processing; for example, the native BizTalk Framework disassembler does not.</span></span> <span data-ttu-id="96522-136">逆アセンブラーが回復可能なインターチェンジ処理をサポートしている場合、設計されているパイプラインの逆アセンブル ステージに逆アセンブラー コンポーネントを追加する際に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のパイプライン デザイナーでこの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="96522-136">If a disassembler supports recoverable interchange processing, then you specify this behavior in Pipeline Designer within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when you add the disassembler component to the Disassemble stage of the pipeline being designed.</span></span> <span data-ttu-id="96522-137">選択した逆アセンブラーをパイプラインの逆アセンブル ステージにドラッグした後、逆アセンブラー コンポーネントの回復可能なインターチェンジ処理のプロパティに `true` を設定します。</span><span class="sxs-lookup"><span data-stu-id="96522-137">After you drag the selected disassembler onto the Disassemble stage of the pipeline, you set the recoverable interchange processing property of that disassembler component to `true`.</span></span>  
  
### <a name="party-resolution"></a><span data-ttu-id="96522-138">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="96522-138">Party Resolution</span></span>  
 <span data-ttu-id="96522-139">回復可能なインターチェンジ処理での抽出に成功したメッセージは、親のインターチェンジが到着する受信ポートに対して構成されているパーティに応じて、送信するパーティを確認します。</span><span class="sxs-lookup"><span data-stu-id="96522-139">Messages that are successfully extracted in recoverable interchange processing have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="96522-140">特定のインターチェンジから抽出されたメッセージでパーティの解決が失敗した場合、パーティの解決は、インターチェンジ全体で失敗したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="96522-140">If party resolution fails for any message extracted from a given interchange, then party resolution is considered to have failed for the entire interchange.</span></span>  
  
### <a name="restrictions"></a><span data-ttu-id="96522-141">制限</span><span class="sxs-lookup"><span data-stu-id="96522-141">Restrictions</span></span>  
  
-   <span data-ttu-id="96522-142">インターチェンジが逆アセンブラーで失敗すると、インターチェンジは再開可能な状態で中断されます。</span><span class="sxs-lookup"><span data-stu-id="96522-142">When an interchange fails in the disassembler, the interchange is suspended as resumable.</span></span> <span data-ttu-id="96522-143">ただし、インターチェンジが管理の都合上再開されても、再度エラーが発生します。これは、逆アセンブリ エラーを引き起こす種類のエラーが、単にインターチェンジの内容 (インターチェンジが再開されても同じままになっている) による結果であるためです。</span><span class="sxs-lookup"><span data-stu-id="96522-143">However, if the interchange is administratively resumed, it will fail again because the kinds of errors that cause disassembly failure are solely a result of the interchange content, which stays the same when the interchange is resumed.</span></span> <span data-ttu-id="96522-144">このような失敗したインターチェンジは変更して、受信場所を通じて再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96522-144">Such a failed interchange must be modified and resubmitted through a receive location.</span></span>  
  
-   <span data-ttu-id="96522-145">サブスクライバーの不一致が原因で、インターチェンジからの抽出に成功したメッセージがメッセージの伝達に失敗した場合、メッセージが再開可能な状態で中断されます。</span><span class="sxs-lookup"><span data-stu-id="96522-145">If a message that was successfully extracted from an interchange subsequently fails to propagate through messaging due to an unmatched subscriber, the message is suspended as resumable.</span></span> <span data-ttu-id="96522-146">ルーティング エラーを解決すると、管理上の理由から、このメッセージを再開できます。</span><span class="sxs-lookup"><span data-stu-id="96522-146">This message can be administratively resumed if the cause of the routing failure is fixed.</span></span>  
  
-   <span data-ttu-id="96522-147">逆アセンブラー コンポーネントは、逆アセンブラー コンポーネントで次のエラーが発生しても、インターチェンジからのメッセージの抽出を続けます。</span><span class="sxs-lookup"><span data-stu-id="96522-147">The disassembler component continues to extract messages from an interchange despite the following errors in disassembler components:</span></span>  
  
    -   <span data-ttu-id="96522-148">スキーマが見つからない。</span><span class="sxs-lookup"><span data-stu-id="96522-148">Schema not found</span></span>  
  
    -   <span data-ttu-id="96522-149">スキーマのあいまいさが解決されない (同じメッセージの種類に複数のスキーマが存在する)。</span><span class="sxs-lookup"><span data-stu-id="96522-149">Schema ambiguity not resolved (that is, more than one schema exists for the same message type)</span></span>  
  
    -   <span data-ttu-id="96522-150">XML 検証が失敗した。</span><span class="sxs-lookup"><span data-stu-id="96522-150">XML validation failed</span></span>  
  
    -   <span data-ttu-id="96522-151">フラット ファイル解析が失敗した。</span><span class="sxs-lookup"><span data-stu-id="96522-151">Flat-file parsing failed</span></span>  
  
-   <span data-ttu-id="96522-152">逆アセンブラー コンポーネントは**いない**逆アセンブラー コンポーネントで、次のエラーが発生した場合、インターチェンジからのメッセージの抽出を続行します。</span><span class="sxs-lookup"><span data-stu-id="96522-152">The disassembler component does **not** continue to extract messages from an interchange if the following error occurs in disassembler components:</span></span>  
  
    -   <span data-ttu-id="96522-153">ドキュメントのデータが整形式 XML ではなく、System.Xml.XmlReader が失敗するドキュメント プロパティである。</span><span class="sxs-lookup"><span data-stu-id="96522-153">Document data is not well-formed XML—any document properties that would cause System.Xml.XmlReader to fail</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96522-154">参照</span><span class="sxs-lookup"><span data-stu-id="96522-154">See Also</span></span>  
 <span data-ttu-id="96522-155">[XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="96522-155">[How to Configure the XML Disassembler Pipeline Component](../core/how-to-configure-the-xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="96522-156">フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="96522-156">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)
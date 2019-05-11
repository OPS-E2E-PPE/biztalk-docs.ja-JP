---
title: 逆アセンブリ ステージ (回復可能なインターチェンジ処理) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 552b1e90-f75d-4713-8c7b-155a52819308
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81be8a4ca330c1ef48bbbb67a2de1b1c9d049f33
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530854"
---
# <a name="disassembly-stage-recoverable-interchange-processing"></a><span data-ttu-id="d128a-102">逆アセンブリ ステージ (回復可能なインターチェンジ処理)</span><span class="sxs-lookup"><span data-stu-id="d128a-102">Disassembly Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="d128a-103">インターチェンジは、2 つのモードでの逆アセンブリ ステージで処理されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-103">Interchanges are processed at the disassembly stage in two modes:</span></span>  
  
-   <span data-ttu-id="d128a-104">**標準モード。**</span><span class="sxs-lookup"><span data-stu-id="d128a-104">**Standard mode.**</span></span> <span data-ttu-id="d128a-105">受信パイプラインの逆アセンブラー コンポーネントは標準の逆アセンブルを実行するように構成、インターチェンジに含まれるメッセージは抽出、受信パイプラインによって処理される、マップ、およびトランザクション作業単位として公開します。</span><span class="sxs-lookup"><span data-stu-id="d128a-105">When the disassembler component of a receive pipeline is configured to perform standard disassembly, the messages contained in an interchange are extracted, processed by the receive pipeline, mapped, and published as a transactional unit of work.</span></span> <span data-ttu-id="d128a-106">つまり、インターチェンジ全体と含まれるメッセージが完全に処理され、メッセージ ボックス データベースに公開またはインターチェンジは保留キューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-106">That is, either the entire interchange and its contained messages are fully processed and published into the MessageBox database, or the interchange is placed in the Suspended queue.</span></span>  
  
-   <span data-ttu-id="d128a-107">**回復可能なモードです。**</span><span class="sxs-lookup"><span data-stu-id="d128a-107">**Recoverable mode.**</span></span> <span data-ttu-id="d128a-108">実行する、受信パイプラインの逆アセンブラー コンポーネントを構成するときに**回復可能なインターチェンジ処理**インターチェンジに含まれるメッセージは、それぞれ個別に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-108">When the disassembler component of a receive pipeline is configured to perform **recoverable interchange processing**, the messages contained in an interchange are extracted independently of each other.</span></span> <span data-ttu-id="d128a-109">正常に抽出されたメッセージが伝達される受信パイプラインの下します。</span><span class="sxs-lookup"><span data-stu-id="d128a-109">Messages that are successfully extracted are propagated further down the receive pipeline.</span></span> <span data-ttu-id="d128a-110">インターチェンジ内で識別されますが、正常に抽出されませんメッセージは保留キューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-110">Messages that are identified within an interchange but are not successfully extracted are placed in the Suspended queue.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d128a-111">使用例</span><span class="sxs-lookup"><span data-stu-id="d128a-111">Examples</span></span>  
 <span data-ttu-id="d128a-112">次の例では、インターチェンジ処理のシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="d128a-112">The following examples illustrate interchange processing scenarios.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="d128a-113">例 1</span><span class="sxs-lookup"><span data-stu-id="d128a-113">Example 1</span></span>  
 <span data-ttu-id="d128a-114">この例では、次の疑似インターチェンジが標準に送信されるインターチェンジの受信場所。</span><span class="sxs-lookup"><span data-stu-id="d128a-114">In this example, the following pseudo-interchange is submitted on a standard interchange receive location.</span></span> <span data-ttu-id="d128a-115">つまり、受信パイプラインの逆アセンブラー コンポーネントは、標準のインターチェンジ処理に対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-115">That is, the disassembler component in the receive pipeline is configured for standard interchange processing.</span></span>  
  
```  
<Interchange>  
<Document1>...</Document1>  
<Document2 failure=”routing”>...</Document2>  
<Document3>...</Document3>  
<Document4 failure=”pipeline” recoverableError=”true”>...</Document4>  
<Document5>...</Document5>  
</Interchange>  
```  
  
 <span data-ttu-id="d128a-116">このインターチェンジには、これらはすべて、逆アセンブラーが正常に抽出インターチェンジからの 5 つのメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d128a-116">This interchange contains five messages, all of which the disassembler successfully extracts from the interchange.</span></span> <span data-ttu-id="d128a-117">次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-117">They are processed as follows:</span></span>  
  
- <span data-ttu-id="d128a-118">1、2、および 3 番目のメッセージは、パイプラインを通じて伝達および発行する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="d128a-118">The first, second, and third messages propagate through the pipeline and are ready to be published.</span></span>  
  
- <span data-ttu-id="d128a-119">4 番目のメッセージでは、パイプラインの逆アセンブリ ステージで処理が失敗します。</span><span class="sxs-lookup"><span data-stu-id="d128a-119">The fourth message fails processing at the disassembling stage in the pipeline.</span></span> <span data-ttu-id="d128a-120">これにより、ロールバックを既に処理されたすべてのメッセージと、元のインターチェンジ メッセージを再開可能として中断されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-120">This causes all the messages that have already been processed to roll back and the original interchange message to be suspended as resumable.</span></span>  
  
  <span data-ttu-id="d128a-121">送信の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d128a-121">The result of submission is:</span></span>  
  
- <span data-ttu-id="d128a-122">何も発行されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-122">Nothing is published.</span></span> <span data-ttu-id="d128a-123">標準のインターチェンジの処理中またはインターチェンジ処理の後に任意の時点で失敗した抽出されたメッセージの抽出されたすべてのメッセージが破棄されると、元のインターチェンジの上に配置されている結果のため、元のインターチェンジが中断されます。再開可能な状態で保留キュー。</span><span class="sxs-lookup"><span data-stu-id="d128a-123">The original interchange is suspended because in standard interchange processing, any extracted message that fails at any point during or after interchange processing results in all extracted messages being discarded and the original interchange being placed on the Suspended queue as resumable.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="d128a-124">例 2</span><span class="sxs-lookup"><span data-stu-id="d128a-124">Example 2</span></span>  
 <span data-ttu-id="d128a-125">例では、前の例と同じインターチェンジ処理と伝達シナリオを使用して逆アセンブリ ステージが回復可能なインターチェンジ処理を実行するよう構成する点を除いて。</span><span class="sxs-lookup"><span data-stu-id="d128a-125">The example uses the same interchange processing and propagation scenario as the previous example, except that the disassembly stage is configured to do recoverable interchange processing.</span></span>  
  
 <span data-ttu-id="d128a-126">送信の結果は、個々 の抽出されたメッセージがすべて処理して、元のインターチェンジが破棄されるは。</span><span class="sxs-lookup"><span data-stu-id="d128a-126">The result of submission is that individual extracted messages are all processed and the original interchange is discarded.</span></span> <span data-ttu-id="d128a-127">個々 のメッセージは、次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-127">The individual messages are processed as follows:</span></span>  
  
-   <span data-ttu-id="d128a-128">1、2、および 3 番目のメッセージは、パイプラインを通じて伝達および発行する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="d128a-128">The first, second, and third messages propagate through the pipeline and are ready to be published.</span></span>  
  
-   <span data-ttu-id="d128a-129">4 番目のメッセージに逆アセンブリ処理が失敗した (つまり、何らかの問題が抽出後) を中断する準備ができているとします。</span><span class="sxs-lookup"><span data-stu-id="d128a-129">The fourth message fails disassembly processing (that is, something goes wrong after it is extracted) and is ready to be suspended.</span></span>  
  
-   <span data-ttu-id="d128a-130">5 番目のメッセージでは、パイプラインを通じて伝達され、発行する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="d128a-130">The fifth message propagates through the pipeline and is ready to be published.</span></span>  
  
-   <span data-ttu-id="d128a-131">インターチェンジからは、すべてのメッセージが抽出されたら、メッセージ 1、2、3、および 5 は、メッセージ ボックス データベースに公開され、メッセージ 4 は、保留キューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-131">After all messages are extracted from the interchange, messages 1, 2, 3, and 5 are published into the MessageBox database, and message 4 is placed on the Suspended queue.</span></span> <span data-ttu-id="d128a-132">メッセージ 2 は、一致するサブスクライバーがないため、ルーティング エラーにより保留キューにもリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="d128a-132">Message 2 is also redirected to the Suspended queue because of a routing failure due to no matching subscriber.</span></span>  
  
## <a name="configuring-recoverable-interchange-processing"></a><span data-ttu-id="d128a-133">回復可能なインターチェンジ処理の構成</span><span class="sxs-lookup"><span data-stu-id="d128a-133">Configuring Recoverable Interchange Processing</span></span>  
 <span data-ttu-id="d128a-134">回復可能なインターチェンジ処理は、受信パイプラインの逆アセンブラー コンポーネントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d128a-134">Recoverable interchange processing is a property of the disassembler component of a receive pipeline.</span></span> <span data-ttu-id="d128a-135">すべての逆アセンブラー コンポーネントでは、回復可能なインターチェンジ処理の; を指定できます。たとえば、BizTalk Framework 逆アセンブラーはネイティブです。</span><span class="sxs-lookup"><span data-stu-id="d128a-135">Not all disassembler components allow you to specify recoverable interchange processing; for example, the native BizTalk Framework disassembler does not.</span></span> <span data-ttu-id="d128a-136">逆アセンブラーは、回復可能なインターチェンジ処理をサポートしているかどうかは、パイプライン デザイナーでこの動作を指定する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]設計されているパイプラインの逆アセンブル ステージに逆アセンブラー コンポーネントを追加するとします。</span><span class="sxs-lookup"><span data-stu-id="d128a-136">If a disassembler supports recoverable interchange processing, then you specify this behavior in Pipeline Designer within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when you add the disassembler component to the Disassemble stage of the pipeline being designed.</span></span> <span data-ttu-id="d128a-137">選択した逆アセンブラーをパイプラインの逆アセンブル ステージにドラッグすると後、に、回復可能なインターチェンジを処理するには、その逆アセンブラー コンポーネントのプロパティを設定する`true`します。</span><span class="sxs-lookup"><span data-stu-id="d128a-137">After you drag the selected disassembler onto the Disassemble stage of the pipeline, you set the recoverable interchange processing property of that disassembler component to `true`.</span></span>  
  
### <a name="party-resolution"></a><span data-ttu-id="d128a-138">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="d128a-138">Party Resolution</span></span>  
 <span data-ttu-id="d128a-139">回復可能なインターチェンジ処理で正常に抽出されたメッセージがある、送信元パーティを親のインターチェンジが到着する受信ポート用に構成されたパーティに応じて確認します。</span><span class="sxs-lookup"><span data-stu-id="d128a-139">Messages that are successfully extracted in recoverable interchange processing have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="d128a-140">特定のインターチェンジから抽出されたメッセージのパーティの解決に失敗した場合は、インターチェンジ全体に対する失敗したパーティの解決が考慮します。</span><span class="sxs-lookup"><span data-stu-id="d128a-140">If party resolution fails for any message extracted from a given interchange, then party resolution is considered to have failed for the entire interchange.</span></span>  
  
### <a name="restrictions"></a><span data-ttu-id="d128a-141">制限</span><span class="sxs-lookup"><span data-stu-id="d128a-141">Restrictions</span></span>  
  
-   <span data-ttu-id="d128a-142">インターチェンジでは、逆アセンブラーで失敗した場合、インターチェンジは再開可能として中断されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-142">When an interchange fails in the disassembler, the interchange is suspended as resumable.</span></span> <span data-ttu-id="d128a-143">ただし場合は、インターチェンジが管理上再開され、失敗になりますもう一度 [逆アセンブル] エラーが発生したエラーの種類は、インターチェンジが再開されたときに同じままインターチェンジの内容の結果のみであるため。</span><span class="sxs-lookup"><span data-stu-id="d128a-143">However, if the interchange is administratively resumed, it will fail again because the kinds of errors that cause disassembly failure are solely a result of the interchange content, which stays the same when the interchange is resumed.</span></span> <span data-ttu-id="d128a-144">このような失敗したインターチェンジを変更して、受信場所を通じて再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d128a-144">Such a failed interchange must be modified and resubmitted through a receive location.</span></span>  
  
-   <span data-ttu-id="d128a-145">反映されるまで、サブスクライバーの不一致のためのメッセージング、その後、インターチェンジから抽出が正常にメッセージが失敗した場合、メッセージは再開可能として中断されます。</span><span class="sxs-lookup"><span data-stu-id="d128a-145">If a message that was successfully extracted from an interchange subsequently fails to propagate through messaging due to an unmatched subscriber, the message is suspended as resumable.</span></span> <span data-ttu-id="d128a-146">このメッセージは、ルーティング エラーの原因が固定の場合管理上再開できます。</span><span class="sxs-lookup"><span data-stu-id="d128a-146">This message can be administratively resumed if the cause of the routing failure is fixed.</span></span>  
  
-   <span data-ttu-id="d128a-147">逆アセンブラー コンポーネントは、メッセージの逆アセンブラー コンポーネントで次のエラーに関係なくインターチェンジから抽出を続行します。</span><span class="sxs-lookup"><span data-stu-id="d128a-147">The disassembler component continues to extract messages from an interchange despite the following errors in disassembler components:</span></span>  
  
    -   <span data-ttu-id="d128a-148">スキーマが見つかりません</span><span class="sxs-lookup"><span data-stu-id="d128a-148">Schema not found</span></span>  
  
    -   <span data-ttu-id="d128a-149">スキーマのあいまいさが解決されません (つまり、1 つ以上のスキーマが存在する同じメッセージの種類の)</span><span class="sxs-lookup"><span data-stu-id="d128a-149">Schema ambiguity not resolved (that is, more than one schema exists for the same message type)</span></span>  
  
    -   <span data-ttu-id="d128a-150">XML 検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="d128a-150">XML validation failed</span></span>  
  
    -   <span data-ttu-id="d128a-151">フラット ファイルの解析に失敗しました</span><span class="sxs-lookup"><span data-stu-id="d128a-151">Flat-file parsing failed</span></span>  
  
-   <span data-ttu-id="d128a-152">逆アセンブラー コンポーネントは**いない**逆アセンブラー コンポーネントで、次のエラーが発生した場合、インターチェンジからのメッセージの抽出を続行します。</span><span class="sxs-lookup"><span data-stu-id="d128a-152">The disassembler component does **not** continue to extract messages from an interchange if the following error occurs in disassembler components:</span></span>  
  
    -   <span data-ttu-id="d128a-153">ドキュメント データが整形式 XML-ドキュメント System.Xml.XmlReader が失敗する原因となるプロパティ</span><span class="sxs-lookup"><span data-stu-id="d128a-153">Document data is not well-formed XML—any document properties that would cause System.Xml.XmlReader to fail</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d128a-154">参照</span><span class="sxs-lookup"><span data-stu-id="d128a-154">See Also</span></span>  
 <span data-ttu-id="d128a-155">[XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d128a-155">[How to Configure the XML Disassembler Pipeline Component](../core/how-to-configure-the-xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="d128a-156">フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d128a-156">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)
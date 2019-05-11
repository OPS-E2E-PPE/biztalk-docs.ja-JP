---
title: メッセージ検証エンジン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message validation engine
- errors, validating
- XML validation
- parsing validation
- BRE policies, validating
- errors, messages
- messages, errors
- validating, messages
- validating, BRE policies
- validating, XML
- messages, validating
- validating, errors
- validating, parsing
ms.assetid: 4ba0b75e-665b-4771-b04f-5bc3e90d83f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd286de8a1f2b0d9947a87cedaafd2a0efbce976
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377193"
---
# <a name="message-validation-engine"></a><span data-ttu-id="e5d17-102">メッセージ検証エンジン</span><span class="sxs-lookup"><span data-stu-id="e5d17-102">Message Validation Engine</span></span>
<span data-ttu-id="e5d17-103">によって提供される最も重要な機能の 1 つ[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)](取引先によって送信されます)、SWIFT ネットワーク間で送受信を行う SWIFT ネットワーク宛てのバックエンド システムから受信した SWIFT のメッセージを完全に検証する機能です。</span><span class="sxs-lookup"><span data-stu-id="e5d17-103">One of the most important features provided by [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] is the ability to fully validate SWIFT messages received from back-end systems destined for the SWIFT network, or received from the SWIFT network (sent by trading partners).</span></span> <span data-ttu-id="e5d17-104">SWIFT メッセージの送信の検証、メッセージは、SWIFT 標準に準拠しているし、SWIFT ネットワークによって、メッセージは拒否されないことを保証します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-104">Validating outbound SWIFT messages guarantees that the messages conform to SWIFT standards and that the SWIFT network will not reject the messages.</span></span>  
  
 <span data-ttu-id="e5d17-105">他の金融機関から受信したメッセージが特定の契約 (ビジネス ルール) リレーションシップに固有に従うことにより、SWIFT メッセージの受信を検証しています。</span><span class="sxs-lookup"><span data-stu-id="e5d17-105">Validating inbound SWIFT messages ensures that messages received from other financial institutions obey particular agreements (business rules) specific to the relationship.</span></span> <span data-ttu-id="e5d17-106">両方のシナリオでは、検証し、メッセージをコミットする前にエラーをトラップする機能により、トランザクションの費用と総保有コスト (tco) 削減します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-106">In both scenarios, the ability to validate and trap errors before committing a message helps to reduce transaction costs and total cost of ownership (TCO).</span></span>  
  
 <span data-ttu-id="e5d17-107">A4SWIFT 検証エンジンを構成する 4 つの部分は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5d17-107">The following list describes the four parts that make up the A4SWIFT validation engine:</span></span>  
  
-   <span data-ttu-id="e5d17-108">フラット ファイル パーサーによって実行される構造の検証</span><span class="sxs-lookup"><span data-stu-id="e5d17-108">Structural validation performed by the flat file parser</span></span>  
  
-   <span data-ttu-id="e5d17-109">リーダーを検証する XML によって実行されるデータの検証</span><span class="sxs-lookup"><span data-stu-id="e5d17-109">Data validation performed by the XML validating reader</span></span>  
  
-   <span data-ttu-id="e5d17-110">ルールのビジネス ルール エンジン (BRE) で実行される検証を行う SWIFT ネットワークと使用状況</span><span class="sxs-lookup"><span data-stu-id="e5d17-110">SWIFT network and usage rule validation performed by the Business Rule Engine (BRE)</span></span>  
  
-   <span data-ttu-id="e5d17-111">メッセージのマーキングと「ベスト エフォート」のエラーの収集</span><span class="sxs-lookup"><span data-stu-id="e5d17-111">Message marking and "best effort" error collecting</span></span>  
  
## <a name="structural-validation-parsing"></a><span data-ttu-id="e5d17-112">(解析) 構造の検証</span><span class="sxs-lookup"><span data-stu-id="e5d17-112">Structural Validation (Parsing)</span></span>  
 <span data-ttu-id="e5d17-113">A4SWIFT SWIFT 標準に従って各 SWIFT メッセージの種類に対して定義されている XSD スキーマに対して SWIFT のフラット ファイル メッセージを解析します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-113">A4SWIFT parses SWIFT flat file messages against XSD schemas defined for each SWIFT message type in accordance with the SWIFT standard.</span></span> <span data-ttu-id="e5d17-114">XML を解析して、フラット ファイルは、フラット ファイルを構造的に正しいことを保証します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-114">Parsing a flat file into XML guarantees that the flat file is structurally correct.</span></span> <span data-ttu-id="e5d17-115">解析も、読み取り、操作、またはその他の形式またはメッセージの種類に変換を簡単に XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-115">Parsing also produces XML that is easier to read, manipulate, or transform into other formats or message types.</span></span> <span data-ttu-id="e5d17-116">データの有効性のスキーマに対して XML を検証しより複雑な評価のビジネス ルール エンジン (BRE) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5d17-116">You can also validate the XML against schema for data validity and use the Business Rule Engine (BRE) for more complex evaluations.</span></span>  
  
 <span data-ttu-id="e5d17-117">SWIFT 逆アセンブラーは、SWIFT 逆アセンブラーによって呼び出される SWIFT のフラット ファイル メッセージを解析する BizTalk フラット ファイル パーサーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-117">The SWIFT disassembler invokes the BizTalk flat file parser to parse SWIFT flat file messages invoked by the SWIFT disassembler.</span></span> <span data-ttu-id="e5d17-118">SWIFT 逆アセンブラーでは、エラーのコレクションで、解析時に発生したエラーの詳細を記録、常に最初のパスでできるだけ多くの構造化エラーを収集するために、データの解析を続行しようとします。</span><span class="sxs-lookup"><span data-stu-id="e5d17-118">The SWIFT disassembler records in an error collection the details of any errors encountered during parsing, and always attempts to continue parsing the data in an effort to collect as many structural errors as possible on the first pass.</span></span> <span data-ttu-id="e5d17-119">ただし、ほとんどの解析エラーは致命的なものし、最初のエラーでメッセージの処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-119">However, most parse errors are fatal and halt message processing at the first error.</span></span>  
  
 <span data-ttu-id="e5d17-120">構造の検証の詳細については、次を参照してください。[スキーマ操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-120">For more information about structural validation, see [Working with Schemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md).</span></span>  
  
## <a name="data-validation-xml-validation"></a><span data-ttu-id="e5d17-121">データ検証 (XML の検証)</span><span class="sxs-lookup"><span data-stu-id="e5d17-121">Data Validation (XML Validation)</span></span>  
 <span data-ttu-id="e5d17-122">整形式 XML として XSD スキーマの定義に準拠している構造の検証に合格した SWIFT のメッセージを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="e5d17-122">You can define SWIFT messages that pass structural validation as well-formed XML conforming to defined XSD schemas.</span></span> <span data-ttu-id="e5d17-123">A4SWIFT では、解析ステージ中に、SWIFT メッセージの構造上有効な XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-123">A4SWIFT produces XML for structurally valid SWIFT messages during the parsing stage.</span></span> <span data-ttu-id="e5d17-124">A4SWIFT の対応する XSD スキーマで定義された制約に対してデータの正確さには、この XML を検証できます。</span><span class="sxs-lookup"><span data-stu-id="e5d17-124">A4SWIFT can then validate this XML for data correctness against constraints defined in the corresponding XSD schema.</span></span>  
  
 <span data-ttu-id="e5d17-125">これらの制約には、データの型、長さ、および標準の SWIFT に従って定義されている値の範囲が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5d17-125">These constraints include data typing, length, and value ranges defined in accordance with the SWIFT standard.</span></span> <span data-ttu-id="e5d17-126">SWIFT 逆アセンブラーは、データ検証を実行するにはリーダーを検証する XML を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-126">The SWIFT disassembler invokes the XML validating reader to perform data validation.</span></span>  
  
 <span data-ttu-id="e5d17-127">SWIFT 逆アセンブラーは、XML の検証中に発生したエラーの詳細をエラー コレクションに記録し、最初のパスでできるだけ多くの XML 検証エラーを収集する残りのデータの検証を続行します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-127">The SWIFT disassembler records in an error collection the details of any errors encountered during XML validation, and continues validating the remaining data to collect as many XML validation errors as possible on the first pass.</span></span> <span data-ttu-id="e5d17-128">(解析とは異なり XML 検証の継続が保証されます。)</span><span class="sxs-lookup"><span data-stu-id="e5d17-128">(Unlike parsing, continuation of XML validation is guaranteed.)</span></span>  
  
 <span data-ttu-id="e5d17-129">データ検証の詳細については、次を参照してください。[スキーマ操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-129">For more information about data validation, see [Working with Schemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md).</span></span>  
  
## <a name="swift-network-and-usage-rule-validation-bre-validation"></a><span data-ttu-id="e5d17-130">SWIFT ネットワークと使用量ルールの検証 (BRE の検証)</span><span class="sxs-lookup"><span data-stu-id="e5d17-130">SWIFT Network and Usage Rule Validation (BRE Validation)</span></span>  
 <span data-ttu-id="e5d17-131">A4SWIFT のビジネス ルール エンジン (BRE) ポリシーに対するビジネス レベルの正確性の SWIFT メッセージの構造上有効な XML を検証します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-131">A4SWIFT validates XML for structurally valid SWIFT messages for business-level correctness against Business Rule Engine (BRE) policies.</span></span> <span data-ttu-id="e5d17-132">これらのポリシーには、SWIFT ネットワークと使用状況規則と SWIFT の標準に従って定義されているその他の複雑なクロス フィールド規則の適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5d17-132">These policies include enforcement of SWIFT network and usage rules and other complex cross-field rules defined in accordance with the SWIFT standard.</span></span> <span data-ttu-id="e5d17-133">SWIFT 逆アセンブラーは、ビジネス レベルの検証を実行する、BRE を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-133">The SWIFT disassembler invokes the BRE to perform business-level validation.</span></span>  
  
 <span data-ttu-id="e5d17-134">SWIFT 逆アセンブラーは、BRE の検証中に発生したエラーの詳細をエラー コレクションに記録し、最初のパスでできるだけ多くの BRE 検証エラーを収集する残りのデータの検証を続行します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-134">The SWIFT disassembler records in an error collection the details of any errors encountered during BRE validation, and continues validating the remaining data to collect as many BRE validation errors as possible on the first pass.</span></span> <span data-ttu-id="e5d17-135">(XML の検証などの BRE 検証の継続が保証されます。)</span><span class="sxs-lookup"><span data-stu-id="e5d17-135">(Like XML validation, continuation of BRE validation is guaranteed.)</span></span>  
  
 <span data-ttu-id="e5d17-136">SWIFT ネットワークと使用量ルールの検証の詳細については、次を参照してください。[の BRE ポリシーを操作](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-136">For more information about SWIFT network and usage rule validation, see [Working with BRE Policies](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md).</span></span>  
  
## <a name="validation-failures-and-message-marking"></a><span data-ttu-id="e5d17-137">検証エラーおよびメッセージのマーキング</span><span class="sxs-lookup"><span data-stu-id="e5d17-137">Validation Failures and Message Marking</span></span>  
 <span data-ttu-id="e5d17-138">A4SWIFT は検証エラーおよびメッセージの検証の各段階の詳細を収集します。 構造解析、XML の検証、および BRE 検証します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-138">A4SWIFT collects validation errors and details through each stage of message validation: structural parsing, XML validation, and BRE validation.</span></span> <span data-ttu-id="e5d17-139">A4SWIFT できるだけメッセージに関する多くのエラー情報を収集するために、「ベスト エフォート」ヒューリスティックを使用してこれらのエラーを収集します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-139">A4SWIFT collects these errors using a "best effort" heuristic to gather as much error information about a message as possible.</span></span> <span data-ttu-id="e5d17-140">この機能は、キャッチされたすべてのエラーが発生し、submit の複数のイテレーションを移動するのではなく、1 つのパスで報告される検証、失敗、修正、再送信に失敗したメッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-140">This functionality allows a failing message to have all errors caught and reported in one pass rather than having multiple iterations of submit, validate, fail, fix, resubmit.</span></span>  
  
 <span data-ttu-id="e5d17-141">エラーのコレクション内のいずれかの検証段階中に発生した 1 つ以上のエラー メッセージでは、無効と見なされが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="e5d17-141">Messages that have at least one error encountered during any validation stage in the error collection are considered invalid and are failed.</span></span> <span data-ttu-id="e5d17-142">A4SWIFT、MessageBox データベースにこれらのメッセージを発行するが、メッセージの検証が失敗したことを示すために昇格させたプロパティと各検証ステージのエラー数をレポートにマークされています。</span><span class="sxs-lookup"><span data-stu-id="e5d17-142">A4SWIFT publishes these messages to the MessageBox database, but they are marked with promoted properties to indicate that the message has failed validation and to report error counts for each validation stage.</span></span>  
  
 <span data-ttu-id="e5d17-143">だけでなく、昇格されたプロパティは、A4SWIFT は XML にエラーのコレクションをシリアル化し、マルチパート メッセージの「エラー一部」としてコレクションをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="e5d17-143">In addition to the promoted properties, A4SWIFT serializes the error collection into XML and attaches the collection as an "error part" of the multipart message.</span></span> <span data-ttu-id="e5d17-144">最後のメッセージ、失敗したメッセージのボディ部から成るとエラー コレクションの XML では、エラー、およびエラー状態を示す A4SWIFT 昇格させたプロパティを持つが強化されています。</span><span class="sxs-lookup"><span data-stu-id="e5d17-144">The final message consists of the failed message in the body part and error-collection XML in the error part, and is enhanced with A4SWIFT promoted properties that indicate a failure state.</span></span> <span data-ttu-id="e5d17-145">SWIFT 逆アセンブラーは、このマルチパート メッセージをメッセージ ボックス データベースに発行します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-145">The SWIFT disassembler publishes this multipart message to the MessageBox database.</span></span>  
  
 <span data-ttu-id="e5d17-146">BizTalk 送信ポートまたはオーケストレーションから取得できます失敗したメッセージ、メッセージ ボックス データベース、特別な昇格 A4SWIFT プロパティをサブスクライブしています。</span><span class="sxs-lookup"><span data-stu-id="e5d17-146">BizTalk send ports or orchestrations can retrieve failed messages from the MessageBox database by subscribing to the special A4SWIFT promoted properties.</span></span> <span data-ttu-id="e5d17-147">特定の検証段階からすべての失敗したメッセージまたはエラーの特定数のメッセージだけを取得するサブスクリプションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e5d17-147">You can make subscriptions to retrieve all failed messages or only messages with a particular number of errors from specific validation stages.</span></span>  
  
 <span data-ttu-id="e5d17-148">失敗したメッセージが取得された後は、レポート作成アプリケーション、修復アプリケーションまたはプロセス、またはエラーのリポジトリに送信することができます。 または破棄できます。</span><span class="sxs-lookup"><span data-stu-id="e5d17-148">After a failed message is retrieved, you can send it to a reporting application, a repair application or process, or a failure repository, or you can discard it.</span></span>  
  
 <span data-ttu-id="e5d17-149">この機能に失敗したメッセージ (および、サブスクリプションで失敗の種類を区別) を購読、情報豊富なエラーのコレクションと組み合わせると、失敗した各メッセージにアタッチされている XML フォームの単純なエラーを開発するための強力なフレームワークなど、メッセージの修復が提供する、アプリケーションと A4SWIFT セットアップによってインストールされている新しい送信機能を報告します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-149">This ability to subscribe to failed messages (and to differentiate between types of failures in the subscription), coupled with information-rich error collection XML attached to each failed message, forms a powerful framework for developing simple error reporting applications, such as provided by the message repair and new submission feature installed by A4SWIFT setup.</span></span>  
  
 <span data-ttu-id="e5d17-150">検証エラーとメッセージ的なマーキングの詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5d17-150">For more information about validation failures and message marking, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d17-151">参照</span><span class="sxs-lookup"><span data-stu-id="e5d17-151">See Also</span></span>  
 [<span data-ttu-id="e5d17-152">BizTalk Accelerator for SWIFT ランタイム</span><span class="sxs-lookup"><span data-stu-id="e5d17-152">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)
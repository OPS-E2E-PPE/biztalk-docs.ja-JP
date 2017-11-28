---
title: "メッセージの検証エンジン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbdcb375c04e4c9684b2a805c7a7a7315f46f83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-validation-engine"></a><span data-ttu-id="a76ce-102">メッセージ検証エンジン</span><span class="sxs-lookup"><span data-stu-id="a76ce-102">Message Validation Engine</span></span>
<span data-ttu-id="a76ce-103">によって提供される最も重要な機能の 1 つ[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]SWIFT ネットワーク、または (取引先によって送信された) SWIFT ネットワークから受信したバックエンド システムから受信した SWIFT のメッセージを完全に検証する機能です。</span><span class="sxs-lookup"><span data-stu-id="a76ce-103">One of the most important features provided by [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] is the ability to fully validate SWIFT messages received from back-end systems destined for the SWIFT network, or received from the SWIFT network (sent by trading partners).</span></span> <span data-ttu-id="a76ce-104">送信 SWIFT メッセージの検証メッセージが SWIFT 標準に準拠していることと、SWIFT ネットワークは、メッセージを拒否していないことを保証します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-104">Validating outbound SWIFT messages guarantees that the messages conform to SWIFT standards and that the SWIFT network will not reject the messages.</span></span>  
  
 <span data-ttu-id="a76ce-105">他の金融機関から受信したメッセージが特定の契約 (ビジネス ルールの場合)、リレーションシップに固有に従うことにより、SWIFT メッセージの受信を検証しています。</span><span class="sxs-lookup"><span data-stu-id="a76ce-105">Validating inbound SWIFT messages ensures that messages received from other financial institutions obey particular agreements (business rules) specific to the relationship.</span></span> <span data-ttu-id="a76ce-106">両方のシナリオでは、トランザクションのコストと総コスト (tco) を軽減する方法で検証し、メッセージをコミットする前にエラーをトラップする機能できます。</span><span class="sxs-lookup"><span data-stu-id="a76ce-106">In both scenarios, the ability to validate and trap errors before committing a message helps to reduce transaction costs and total cost of ownership (TCO).</span></span>  
  
 <span data-ttu-id="a76ce-107">次に、A4SWIFT 検証エンジンを構成する 4 つの部分を説明します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-107">The following list describes the four parts that make up the A4SWIFT validation engine:</span></span>  
  
-   <span data-ttu-id="a76ce-108">フラット ファイル パーサーによって実行される構造の検証</span><span class="sxs-lookup"><span data-stu-id="a76ce-108">Structural validation performed by the flat file parser</span></span>  
  
-   <span data-ttu-id="a76ce-109">リーダーを検証する XML によって実行されるデータ検証</span><span class="sxs-lookup"><span data-stu-id="a76ce-109">Data validation performed by the XML validating reader</span></span>  
  
-   <span data-ttu-id="a76ce-110">ルールの検証ビジネス ルール エンジン (BRE) での実行に SWIFT ネットワークとの使用</span><span class="sxs-lookup"><span data-stu-id="a76ce-110">SWIFT network and usage rule validation performed by the Business Rule Engine (BRE)</span></span>  
  
-   <span data-ttu-id="a76ce-111">メッセージのマーキングと「最適な」のエラーの収集</span><span class="sxs-lookup"><span data-stu-id="a76ce-111">Message marking and "best effort" error collecting</span></span>  
  
## <a name="structural-validation-parsing"></a><span data-ttu-id="a76ce-112">(解析) 構造の検証</span><span class="sxs-lookup"><span data-stu-id="a76ce-112">Structural Validation (Parsing)</span></span>  
 <span data-ttu-id="a76ce-113">A4SWIFT SWIFT 標準に従って各 SWIFT メッセージの種類に対して定義されている XSD スキーマに対して SWIFT のフラット ファイル メッセージを解析します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-113">A4SWIFT parses SWIFT flat file messages against XSD schemas defined for each SWIFT message type in accordance with the SWIFT standard.</span></span> <span data-ttu-id="a76ce-114">XML に、フラット ファイルの解析は、フラット ファイルが構造的に正しいことを保証します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-114">Parsing a flat file into XML guarantees that the flat file is structurally correct.</span></span> <span data-ttu-id="a76ce-115">解析は、XML を読み取り、操作、またはその他の形式またはメッセージの種類の変換を簡単にも生成します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-115">Parsing also produces XML that is easier to read, manipulate, or transform into other formats or message types.</span></span> <span data-ttu-id="a76ce-116">データの有効性のスキーマに対して XML を検証してより複雑な評価のビジネス ルール エンジン (BRE) を使用することができますも。</span><span class="sxs-lookup"><span data-stu-id="a76ce-116">You can also validate the XML against schema for data validity and use the Business Rule Engine (BRE) for more complex evaluations.</span></span>  
  
 <span data-ttu-id="a76ce-117">SWIFT の逆アセンブラーでは、SWIFT の逆アセンブラーによって呼び出された SWIFT のフラット ファイル メッセージを解析する、BizTalk フラット ファイル パーサーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-117">The SWIFT disassembler invokes the BizTalk flat file parser to parse SWIFT flat file messages invoked by the SWIFT disassembler.</span></span> <span data-ttu-id="a76ce-118">SWIFT の逆アセンブラーでは、エラーのコレクションで、解析時に発生したエラーの詳細を記録、常に最初のパスでできるだけ多くの構造エラーを収集するために、データの解析を続行しようとします。</span><span class="sxs-lookup"><span data-stu-id="a76ce-118">The SWIFT disassembler records in an error collection the details of any errors encountered during parsing, and always attempts to continue parsing the data in an effort to collect as many structural errors as possible on the first pass.</span></span> <span data-ttu-id="a76ce-119">ただし、ほとんどの解析エラーは致命的なものし、最初のエラーでメッセージの処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-119">However, most parse errors are fatal and halt message processing at the first error.</span></span>  
  
 <span data-ttu-id="a76ce-120">構造の検証の詳細については、次を参照してください。[スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="a76ce-120">For more information about structural validation, see [Working with Schemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md).</span></span>  
  
## <a name="data-validation-xml-validation"></a><span data-ttu-id="a76ce-121">データ検証 (XML の検証)</span><span class="sxs-lookup"><span data-stu-id="a76ce-121">Data Validation (XML Validation)</span></span>  
 <span data-ttu-id="a76ce-122">整形式 XML として定義された XSD スキーマに準拠している構造の検証に合格した SWIFT のメッセージを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="a76ce-122">You can define SWIFT messages that pass structural validation as well-formed XML conforming to defined XSD schemas.</span></span> <span data-ttu-id="a76ce-123">A4SWIFT には、解析ステージ中に SWIFT メッセージの構造上有効な XML が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a76ce-123">A4SWIFT produces XML for structurally valid SWIFT messages during the parsing stage.</span></span> <span data-ttu-id="a76ce-124">A4SWIFT の対応する XSD スキーマで定義された制約に対してデータの正確性は、この XML を検証できます。</span><span class="sxs-lookup"><span data-stu-id="a76ce-124">A4SWIFT can then validate this XML for data correctness against constraints defined in the corresponding XSD schema.</span></span>  
  
 <span data-ttu-id="a76ce-125">これらの制約には、入力データ、長さ、および値の範囲は標準の SWIFT に従って定義が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a76ce-125">These constraints include data typing, length, and value ranges defined in accordance with the SWIFT standard.</span></span> <span data-ttu-id="a76ce-126">SWIFT の逆アセンブラーでは、データの検証を実行するリーダーを検証する XML を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-126">The SWIFT disassembler invokes the XML validating reader to perform data validation.</span></span>  
  
 <span data-ttu-id="a76ce-127">SWIFT の逆アセンブラーは、XML の検証中に発生したエラーの詳細をエラー コレクションに記録し、最初のパスでできるだけ多くの XML 検証エラーを収集する残りのデータの検証を続行します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-127">The SWIFT disassembler records in an error collection the details of any errors encountered during XML validation, and continues validating the remaining data to collect as many XML validation errors as possible on the first pass.</span></span> <span data-ttu-id="a76ce-128">(解析とは異なり XML 検証の継続が保証されます。)</span><span class="sxs-lookup"><span data-stu-id="a76ce-128">(Unlike parsing, continuation of XML validation is guaranteed.)</span></span>  
  
 <span data-ttu-id="a76ce-129">データの検証の詳細については、次を参照してください。[スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="a76ce-129">For more information about data validation, see [Working with Schemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md).</span></span>  
  
## <a name="swift-network-and-usage-rule-validation-bre-validation"></a><span data-ttu-id="a76ce-130">SWIFT ネットワークと使用量ルールの検証 (BRE 検証)</span><span class="sxs-lookup"><span data-stu-id="a76ce-130">SWIFT Network and Usage Rule Validation (BRE Validation)</span></span>  
 <span data-ttu-id="a76ce-131">A4SWIFT は、ビジネス ルール エンジン (BRE) ポリシーと照らしてビジネス レベルの正確性の構造上有効な SWIFT メッセージの XML を検証します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-131">A4SWIFT validates XML for structurally valid SWIFT messages for business-level correctness against Business Rule Engine (BRE) policies.</span></span> <span data-ttu-id="a76ce-132">これらのポリシーには、SWIFT ネットワークと使用状況規則と、SWIFT 標準に従って定義されている他の複雑なクロス フィールド規則の適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a76ce-132">These policies include enforcement of SWIFT network and usage rules and other complex cross-field rules defined in accordance with the SWIFT standard.</span></span> <span data-ttu-id="a76ce-133">SWIFT の逆アセンブラーでは、ビジネス レベルの検証を実行する、BRE を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-133">The SWIFT disassembler invokes the BRE to perform business-level validation.</span></span>  
  
 <span data-ttu-id="a76ce-134">SWIFT の逆アセンブラーは、BRE の検証中に発生したエラーの詳細をエラー コレクションに記録し、最初のパスでできるだけ多くの BRE 検証エラーを収集する残りのデータの検証を続行します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-134">The SWIFT disassembler records in an error collection the details of any errors encountered during BRE validation, and continues validating the remaining data to collect as many BRE validation errors as possible on the first pass.</span></span> <span data-ttu-id="a76ce-135">(XML 検証のように BRE 検証の継続が保証されます。)</span><span class="sxs-lookup"><span data-stu-id="a76ce-135">(Like XML validation, continuation of BRE validation is guaranteed.)</span></span>  
  
 <span data-ttu-id="a76ce-136">SWIFT ネットワークと使用量ルールの検証の詳細については、次を参照してください。 [BRE ポリシーの扱い](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="a76ce-136">For more information about SWIFT network and usage rule validation, see [Working with BRE Policies](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md).</span></span>  
  
## <a name="validation-failures-and-message-marking"></a><span data-ttu-id="a76ce-137">検証エラーとメッセージのマーク付け</span><span class="sxs-lookup"><span data-stu-id="a76ce-137">Validation Failures and Message Marking</span></span>  
 <span data-ttu-id="a76ce-138">A4SWIFT が検証エラーとメッセージの検証の各段階の詳細情報を収集: 構造的な解析、XML の検証、および BRE です。</span><span class="sxs-lookup"><span data-stu-id="a76ce-138">A4SWIFT collects validation errors and details through each stage of message validation: structural parsing, XML validation, and BRE validation.</span></span> <span data-ttu-id="a76ce-139">A4SWIFT は、可能なメッセージについて多くのエラー情報を収集する「最適な」ヒューリスティックを使用してこれらのエラーを収集します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-139">A4SWIFT collects these errors using a "best effort" heuristic to gather as much error information about a message as possible.</span></span> <span data-ttu-id="a76ce-140">この機能は、キャッチされたすべてのエラーが発生し、submit の複数のイテレーションを必要するのではなく、1 つのパスで報告される検証、失敗、修正、再送信に失敗したメッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-140">This functionality allows a failing message to have all errors caught and reported in one pass rather than having multiple iterations of submit, validate, fail, fix, resubmit.</span></span>  
  
 <span data-ttu-id="a76ce-141">エラーのコレクション内のいずれかの検証段階中には、少なくとも 1 つのエラーがあるメッセージは、無効と見なされは失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a76ce-141">Messages that have at least one error encountered during any validation stage in the error collection are considered invalid and are failed.</span></span> <span data-ttu-id="a76ce-142">A4SWIFT がこれらのメッセージをメッセージ ボックス データベースに発行しますが、メッセージの検証が失敗したことを示すために昇格させたプロパティ、および各検証ステージのレポート エラー カウントにマークされています。</span><span class="sxs-lookup"><span data-stu-id="a76ce-142">A4SWIFT publishes these messages to the MessageBox database, but they are marked with promoted properties to indicate that the message has failed validation and to report error counts for each validation stage.</span></span>  
  
 <span data-ttu-id="a76ce-143">昇格させたプロパティに加えて、A4SWIFT は XML に、エラーのコレクションをシリアル化し、"エラー"、マルチパート メッセージの部分としてコレクションをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="a76ce-143">In addition to the promoted properties, A4SWIFT serializes the error collection into XML and attaches the collection as an "error part" of the multipart message.</span></span> <span data-ttu-id="a76ce-144">最後のメッセージから成る本文部分に失敗したメッセージとエラー コレクション XML エラーの部分でとエラー状態を示す A4SWIFT 昇格させたプロパティを持つ拡張します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-144">The final message consists of the failed message in the body part and error-collection XML in the error part, and is enhanced with A4SWIFT promoted properties that indicate a failure state.</span></span> <span data-ttu-id="a76ce-145">SWIFT の逆アセンブラーは、このマルチパート メッセージをメッセージ ボックス データベースに発行します。</span><span class="sxs-lookup"><span data-stu-id="a76ce-145">The SWIFT disassembler publishes this multipart message to the MessageBox database.</span></span>  
  
 <span data-ttu-id="a76ce-146">BizTalk 送信ポートまたはオーケストレーションから取得できます失敗したメッセージ、メッセージ ボックス データベース昇格 A4SWIFT の特殊なプロパティをサブスクライブすることで。</span><span class="sxs-lookup"><span data-stu-id="a76ce-146">BizTalk send ports or orchestrations can retrieve failed messages from the MessageBox database by subscribing to the special A4SWIFT promoted properties.</span></span> <span data-ttu-id="a76ce-147">特定の検証段階からすべての失敗したメッセージまたはエラーの特定の数のメッセージだけを取得するサブスクリプションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a76ce-147">You can make subscriptions to retrieve all failed messages or only messages with a particular number of errors from specific validation stages.</span></span>  
  
 <span data-ttu-id="a76ce-148">失敗したメッセージが取得された後は、レポート作成アプリケーション、修復アプリケーションまたはプロセス、または障害リポジトリに送信することができます。 または破棄できます。</span><span class="sxs-lookup"><span data-stu-id="a76ce-148">After a failed message is retrieved, you can send it to a reporting application, a repair application or process, or a failure repository, or you can discard it.</span></span>  
  
 <span data-ttu-id="a76ce-149">この機能に失敗したメッセージに、サブスクリプションでのエラーの種類を区別する) を購読、多くの情報がエラーのコレクションと組み合わせると、失敗した各メッセージにアタッチされている XML フォームの単純なエラーを開発するための強力なフレームワークレポートなど、メッセージの修復が提供する、アプリケーションと A4SWIFT セットアップによってインストールされている新しい送信機能。</span><span class="sxs-lookup"><span data-stu-id="a76ce-149">This ability to subscribe to failed messages (and to differentiate between types of failures in the subscription), coupled with information-rich error collection XML attached to each failed message, forms a powerful framework for developing simple error reporting applications, such as provided by the message repair and new submission feature installed by A4SWIFT setup.</span></span>  
  
 <span data-ttu-id="a76ce-150">検証の失敗とマーク付けはメッセージの詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)です。</span><span class="sxs-lookup"><span data-stu-id="a76ce-150">For more information about validation failures and message marking, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76ce-151">参照</span><span class="sxs-lookup"><span data-stu-id="a76ce-151">See Also</span></span>  
 [<span data-ttu-id="a76ce-152">BizTalk Accelerator for SWIFT のランタイム</span><span class="sxs-lookup"><span data-stu-id="a76ce-152">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)
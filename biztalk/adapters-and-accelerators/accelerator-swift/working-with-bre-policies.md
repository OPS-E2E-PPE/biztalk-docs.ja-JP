---
title: "BRE ポリシーの扱い |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BRE policies, about BRE policies
- BRE policies
ms.assetid: 4470f2b3-6891-46d7-9ba1-848f90d0767d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624af2a9c05e1a419acac66eeb6a1aea8d29d695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-bre-policies"></a><span data-ttu-id="3cf37-102">BRE ポリシーの扱い</span><span class="sxs-lookup"><span data-stu-id="3cf37-102">Working with BRE Policies</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="3cf37-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT の検証」の説明に従って、ビジネス ルール エンジン (BRE) を使用してメッセージのポリシー、 *SWIFT リファレンス ガイド*です。</span><span class="sxs-lookup"><span data-stu-id="3cf37-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] validates SWIFT messages by using Business Rule Engine (BRE) polices, as described in the *SWIFT Reference Guide*.</span></span> <span data-ttu-id="3cf37-104">これらのポリシーを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-104">These policies include the following:</span></span>  
  
-   <span data-ttu-id="3cf37-105">書式設定</span><span class="sxs-lookup"><span data-stu-id="3cf37-105">Formatting</span></span>  
  
-   <span data-ttu-id="3cf37-106">値の範囲</span><span class="sxs-lookup"><span data-stu-id="3cf37-106">Value range</span></span>  
  
-   <span data-ttu-id="3cf37-107">有効なリストのエントリ</span><span class="sxs-lookup"><span data-stu-id="3cf37-107">Valid list entries</span></span>  
  
-   <span data-ttu-id="3cf37-108">対応するエラー コードを持つネットワーク ルール</span><span class="sxs-lookup"><span data-stu-id="3cf37-108">Network rules with corresponding error codes</span></span>  
  
-   <span data-ttu-id="3cf37-109">メッセージ コンテンツから検証可能な使用に関する規則</span><span class="sxs-lookup"><span data-stu-id="3cf37-109">Usage rules that can be validated from the message content</span></span>  
  
 <span data-ttu-id="3cf37-110">これらのポリシーは、メッセージの内容、またはなメッセージのクロス検証に依存していない一般的なプラクティスを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="3cf37-110">These policies do not include general practices that are not dependent on the message content, or any cross-message validations.</span></span>  
  
 <span data-ttu-id="3cf37-111">メッセージ (とヘッダーとトレーラー) の XSD スキーマでは、基本的なフィールドの選択肢と書式設定の参照を SWIFT ベース Types.xsd スキーマを実装するメッセージ スキーマ中に、基数を実装します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-111">The XSD schema for the message (and header and trailer) implements basic field optionality and cardinality, while the message schema that implements formatting references the SWIFT Base Types.xsd schema.</span></span> <span data-ttu-id="3cf37-112">メッセージの種類ごとに 2 つの個別のポリシーは、各メッセージに関連付けられているルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-112">Two specific policies for each message type define the rules associated with each message:</span></span>  
  
-   <span data-ttu-id="3cf37-113">マスターのポリシー (MT*xxx*_Master_Policy.xml)</span><span class="sxs-lookup"><span data-stu-id="3cf37-113">Master policy (MT*xxx*_Master_Policy.xml)</span></span>  
  
-   <span data-ttu-id="3cf37-114">検証ポリシー (MT*xxx*_Validation_Policy.xml)</span><span class="sxs-lookup"><span data-stu-id="3cf37-114">Validation policy (MT*xxx*_Validation_Policy.xml)</span></span>  
  
 <span data-ttu-id="3cf37-115">メッセージの種類ごとに、マスター ポリシーでは、そのメッセージの種類に適用される特定のポリシーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-115">The master policy for each message type invokes the specific policies that apply to that message type.</span></span> <span data-ttu-id="3cf37-116">これらの特定のポリシーには、特別なフィールドは、その共通機能を実装、ネットワーク ルール、および使用状況規則を確認します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-116">These specific policies include special field checks that common functions implement, network rules, and usage rules.</span></span> <span data-ttu-id="3cf37-117">マスターのポリシー メッセージは、最初のポリシー メッセージに対して実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-117">The master policy for the message is the first policy run for that message.</span></span> <span data-ttu-id="3cf37-118">ポリシーの一覧には、メッセージの種類の検証ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cf37-118">The list of policies includes the validation policy for the message type.</span></span> <span data-ttu-id="3cf37-119">各マスターのポリシーには、コンストラクト「場合は、このメッセージを入力し、実行ポリシーの一覧」です。</span><span class="sxs-lookup"><span data-stu-id="3cf37-119">Each master policy has the construct "if this message type, then run the list of policies".</span></span>  
  
 <span data-ttu-id="3cf37-120">各メッセージの種類の検証ポリシーは、フィールド コードなど、他の外部の規則を実装する単一フィールドのチェックを一覧表示またはフィールドの特定のボキャブラリを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-120">The validation policy for each message type lists the single-field checks that other external rules implement, such as field codes, or uses a specific vocabulary for the field.</span></span> <span data-ttu-id="3cf37-121">これら個別のルールは、フィールドに固有であるため 2 つまたは複数のメッセージ全体で一般に共通です。</span><span class="sxs-lookup"><span data-stu-id="3cf37-121">These individual rules are generally common across two or more messages, because they are field-specific.</span></span> <span data-ttu-id="3cf37-122">いないプログラミング コード、BRE ボキャブラリに A4SWIFT_Codelists は許可されているフィールドの値を提供します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-122">The A4SWIFT_Codelists in the BRE vocabulary, not programming code, provide the allowed field values.</span></span>  
  
 <span data-ttu-id="3cf37-123">*SWIFT リファレンス ガイド*ネットワーク ルールの個別に実装します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-123">The *SWIFT Reference Guide* implements each of the network rules independently.</span></span> <span data-ttu-id="3cf37-124">各ネットワーク ルールのセットに対応するメッセージの種類、 *SWIFT リファレンス ガイド*を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-124">Each network rule addresses the set of message types that the *SWIFT Reference Guide* defines.</span></span>  
  
 <span data-ttu-id="3cf37-125">A4SWIFT セットアップでは、A4SWIFT インストールするときの規則はインストールされません。</span><span class="sxs-lookup"><span data-stu-id="3cf37-125">A4SWIFT Setup does not install rules when it installs A4SWIFT.</span></span> <span data-ttu-id="3cf37-126">した後、スキーマを選択し、ビルド アセンブリを展開することができますを使用して BRE 配置ユーティリティを選択し、スキーマ セットの適切なルールを展開します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-126">After you select the schemas, and build and deploy an assembly, you can use the BRE Deployment Utility to select and deploy the appropriate rules for the schema set.</span></span> <span data-ttu-id="3cf37-127">選択したメッセージの規則を展開するには、ユーティリティを実行し、関連するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-127">To deploy the rules for the selected messages, run the utility and select the relevant assemblies.</span></span> <span data-ttu-id="3cf37-128">このツールは、対応するマスター ポリシー、検証ポリシーと、参照先のネットワークまたはその他の規則を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-128">The tool selects the corresponding master policies, validation policies, and any referenced network or other rules.</span></span>  
  
 <span data-ttu-id="3cf37-129">A4SWIFT は、A4SWIFT ルールをボキャブラリの 2 種類に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3cf37-129">A4SWIFT associates two types of vocabularies with A4SWIFT rules.</span></span> <span data-ttu-id="3cf37-130">最初のボキャブラリは、さまざまなコード リストの値を含む A4SWIFT_Codelist です。</span><span class="sxs-lookup"><span data-stu-id="3cf37-130">The first vocabulary is A4SWIFT_Codelist, which contains the various code-list values.</span></span> <span data-ttu-id="3cf37-131">2 番目のボキャブラリは、A4SWIFT_Functions です。</span><span class="sxs-lookup"><span data-stu-id="3cf37-131">The second vocabulary is A4SWIFT_Functions.</span></span> <span data-ttu-id="3cf37-132">これらのボキャブラリは[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ロジックの検証と計算のためのクラスです。</span><span class="sxs-lookup"><span data-stu-id="3cf37-132">These vocabularies are [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] classes for logic validations and calculations.</span></span>  
  
 <span data-ttu-id="3cf37-133">受信パイプラインで A4SWIFT 逆アセンブラーがルールの呼び出しには、BRE の検証の構成パラメーターを true に設定できます。</span><span class="sxs-lookup"><span data-stu-id="3cf37-133">You can invoke the rules by the A4SWIFT disassembler in a receive pipeline, by setting the BRE validation configuration parameter to true.</span></span> <span data-ttu-id="3cf37-134">オーケストレーションからルールを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3cf37-134">You can also invoke the rules from an orchestration.</span></span> <span data-ttu-id="3cf37-135">A4SWIFT アセンブラー (ASM) でルールを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3cf37-135">You cannot invoke the rules by the A4SWIFT assembler (ASM).</span></span> <span data-ttu-id="3cf37-136">オーケストレーションを使用するか、受信パイプライン、スキーマに対してインスタンスを検証し、ルールを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf37-136">You must use an orchestration or receive pipeline to validate the instance against the schema and invoke the rules.</span></span>  
  
 <span data-ttu-id="3cf37-137">メッセージには、スキーマの検証またはビジネス ルールのいずれかが失敗すると、A4SWIFT は、検出されたエラーの説明を表すエラーの収集とエラーのフィールドまたはエラーが発生したメッセージ内の位置を示す値を準備します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-137">If a message fails either schema validation or a business rule, A4SWIFT prepares an error collection that contains a description of the errors found and an indication of the field in error or the position in the message where the error occurred.</span></span> <span data-ttu-id="3cf37-138">詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)です。</span><span class="sxs-lookup"><span data-stu-id="3cf37-138">For more information, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
 <span data-ttu-id="3cf37-139">A4SWIFT を提供するセットに追加の規則を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3cf37-139">You can add additional rules to the set that A4SWIFT provides.</span></span> <span data-ttu-id="3cf37-140">たとえば、一連のメッセージに影響を与える市場プラクティス グループの規則を採用している場合、マスターを含むポリシーを必要に応じて、1 つまたは複数の新しい検証の新しいバージョンを実装できます。</span><span class="sxs-lookup"><span data-stu-id="3cf37-140">For example, if you adopt a market practice group rule that affects a new set of messages, you can implement a new version of the master policy that includes one or more new validations, as required.</span></span> <span data-ttu-id="3cf37-141">同様に、単一フィールドの追加のチェックを適用する場合は、メッセージ検証ポリシーの新しいバージョンにこれらのチェックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3cf37-141">Similarly, if you impose additional single-field checks, you can add these checks to a new version of the message validation policy.</span></span> <span data-ttu-id="3cf37-142">新しいルール、またはボキャブラリ関数としては、新しい検証を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="3cf37-142">You can implement the new validation as a new rule or as a vocabulary function.</span></span>  
  
 <span data-ttu-id="3cf37-143">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cf37-143">This section contains:</span></span>  
  
-   [<span data-ttu-id="3cf37-144">銀行識別コードの検証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3cf37-144">Enabling Validation of Bank Identifier Codes</span></span>](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)  
  
-   [<span data-ttu-id="3cf37-145">A4SWIFT データベース内の Bicplus テーブルを管理します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-145">Managing the Bicplus Table in the A4SWIFT Database</span></span>](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)  
  
-   [<span data-ttu-id="3cf37-146">先行する量フィールドの検証時にゼロをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf37-146">Supporting Leading Zeros in Amount Field Validations</span></span>](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md)  
  
-   [<span data-ttu-id="3cf37-147">時間検証のためのオフセットを設定します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-147">Setting Offsets for Amount Validation</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-offsets-for-amount-validation.md)  
  
-   [<span data-ttu-id="3cf37-148">使用量ルールの検証を削除します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-148">Removing Usage Rule Validation</span></span>](../../adapters-and-accelerators/accelerator-swift/removing-usage-rule-validation.md)
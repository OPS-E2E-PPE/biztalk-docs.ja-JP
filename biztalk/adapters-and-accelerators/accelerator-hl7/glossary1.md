---
title: "BizTalk Server で HL7 アクセラレータの用語集 |Microsoft ドキュメント"
description: "共通の用語と定義を把握し、BizTalk Accelerator 用 HL7 の使い方について"
ms.custom: 
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffb9c18a-5fe5-448f-b115-0973e9d12952
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d90a98fd1c30aed5bb38cca99774f610a59dedaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="glossary"></a><span data-ttu-id="1a56e-103">用語集</span><span class="sxs-lookup"><span data-stu-id="1a56e-103">Glossary</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="1a56e-104">BizTalk Accelerator 用 HL7 は、次の用語と定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-104"> BizTalk Accelerator for HL7 uses the following terms and definitions.</span></span>

## <a name="a"></a><span data-ttu-id="1a56e-105">A</span><span class="sxs-lookup"><span data-stu-id="1a56e-105">A</span></span>    
 <span data-ttu-id="1a56e-106">**成果物**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-106">**artifact**  </span></span>  
 <span data-ttu-id="1a56e-107">HL7 V3.0 投票を構成する成果物は、検出、分析、およびメッセージ仕様の作成につながるデザイン アクティビティから結果として得られる成果物です。</span><span class="sxs-lookup"><span data-stu-id="1a56e-107">The artifacts that comprise the HL7 V3.0 ballot are the deliverables resulting from the discovery, analysis, and design activities leading to the creation of message specifications.</span></span>  
  
 <span data-ttu-id="1a56e-108">HL7 V3.0 標準内では、ドキュメントを構成するコンポーネントは、成果物が。</span><span class="sxs-lookup"><span data-stu-id="1a56e-108">Within the HL7 V3.0 standards, the components that make up the documentation are artifacts.</span></span> <span data-ttu-id="1a56e-109">これは、ストーリー ボード、アプリケーション ロール、イベントを発生させる、ドメイン メッセージ情報モデルの仕様 (D MIMs)、メッセージ情報モデルの調整の仕様 (R MIMs)、階層的なメッセージの説明 specificatins(HMDs)、メッセージの種類相互作用します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-109">This includes storyboards, application roles, trigger events, Domain Message Information Model specifications (D-MIMs), Refined Message Information Model specifications (R-MIMs), Hierarchical Message Description specificatins(HMDs), message types, and interactions.</span></span>  
  
 <span data-ttu-id="1a56e-110">**成果物識別子**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-110">**artifact identifier**  </span></span>  
 <span data-ttu-id="1a56e-111">技術委員会では、送信し、各成果物についてはのドメインと成果物のコード、6 桁、意味のない数、2 桁の数字レルム コード、および 2 桁のバージョン番号を連結することによって割り当てられている一意の識別子を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-111">A Technical Committee submits and gives each artifact a unique identifier that is assigned by concatenating the subsection, domain and artifact code, a 6-digit, non-meaningful number, a 2-digit Realm code, and a 2-digit version number.</span></span>  

## <a name="c"></a><span data-ttu-id="1a56e-112">C</span><span class="sxs-lookup"><span data-stu-id="1a56e-112">C</span></span>
  
 <span data-ttu-id="1a56e-113">**基数**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-113">**cardinality**  </span></span>  
 <span data-ttu-id="1a56e-114">データ要素 (回数データ要素は、オブジェクトのビューの個々 のオカレンス内で繰り返すことがあります) または階層的なメッセージの説明 (最小値と最大数のメッセージ要素の出現) 内の列のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="1a56e-114">The property of a data element (the number of times a data element may repeat within an individual occurrence of an object view) or column in the Hierarchical Message Description (the minimum and maximum number of occurrences of the message element).</span></span> <span data-ttu-id="1a56e-115">階層的なメッセージの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a56e-115">See Hierarchical Message Description.</span></span>  
  
## <a name="d"></a><span data-ttu-id="1a56e-116">D</span><span class="sxs-lookup"><span data-stu-id="1a56e-116">D</span></span>   
 <span data-ttu-id="1a56e-117">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="1a56e-117">**domain**</span></span>    
 1. <span data-ttu-id="1a56e-118">問題や、一連の HL7 メッセージ、またはシステム (「アプリケーション ドメイン」) に対応するサブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1a56e-118">The problem or subject to be addressed by a set of HL7 messages or by a system ("application domain").</span></span> <span data-ttu-id="1a56e-119">健康保険で関係のある特定の領域。</span><span class="sxs-lookup"><span data-stu-id="1a56e-119">A particular area of interest in health care.</span></span> 
 2. <span data-ttu-id="1a56e-120">データ型、属性、またはデータの種類のコンポーネントで使用できる値のセット。</span><span class="sxs-lookup"><span data-stu-id="1a56e-120">The set of possible values of a data type, attribute, or data type component.</span></span> <span data-ttu-id="1a56e-121">ボキャブラリのドメインを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a56e-121">See vocabulary domain.</span></span> 
 3. <span data-ttu-id="1a56e-122">薬局、研究、患者の管理など、HL7 内の対象グループです。</span><span class="sxs-lookup"><span data-stu-id="1a56e-122">An interest group within HL7, such as Pharmacy, Laboratory, Patient Administration.</span></span>  
  
## <a name="e"></a><span data-ttu-id="1a56e-123">E</span><span class="sxs-lookup"><span data-stu-id="1a56e-123">E</span></span> 
 <span data-ttu-id="1a56e-124">**イベント**</span><span class="sxs-lookup"><span data-stu-id="1a56e-124">**event**</span></span>    
 1. <span data-ttu-id="1a56e-125">オブジェクトの注目すべき状態変更の原因となる刺激です。</span><span class="sxs-lookup"><span data-stu-id="1a56e-125">A stimulus that causes a noteworthy state change of an object.</span></span> <span data-ttu-id="1a56e-126">オブジェクトの動作を起動する信号。</span><span class="sxs-lookup"><span data-stu-id="1a56e-126">A signal that invokes the behavior of an object.</span></span> <span data-ttu-id="1a56e-127">トリガー イベントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a56e-127">See trigger event.</span></span> 
 2. <span data-ttu-id="1a56e-128">ボキャブラリ ドメインには、気分の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a56e-128">A vocabulary domain value for Mood.</span></span>  
  
 
## <a name="h"></a><span data-ttu-id="1a56e-129">H</span><span class="sxs-lookup"><span data-stu-id="1a56e-129">H</span></span>
<span data-ttu-id="1a56e-130">**階層的なメッセージの説明 (ッドマウント)**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-130">**Hierarchical Message Description (HMD)**  </span></span>  
 <span data-ttu-id="1a56e-131">メッセージと、グループ化、シーケンス、省略可能性、および基数の正確なフィールドの仕様です。</span><span class="sxs-lookup"><span data-stu-id="1a56e-131">A specification of the exact fields of a message and their grouping, sequence, optionality, and cardinality.</span></span> <span data-ttu-id="1a56e-132">1 つまたは複数の相互作用のメッセージの種類を含む、または 1 つまたは複数の一般的なメッセージ要素型を表します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-132">Either contains message types for one or more interactions or represents one or more common message element types.</span></span> <span data-ttu-id="1a56e-133">これは、HL7 メッセージの主要な normative 構造です。</span><span class="sxs-lookup"><span data-stu-id="1a56e-133">This is the primary normative structure for HL7 messages.</span></span>  
  
## <a name="m"></a><span data-ttu-id="1a56e-134">M</span><span class="sxs-lookup"><span data-stu-id="1a56e-134">M</span></span>  
 <span data-ttu-id="1a56e-135">**必須**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-135">**mandatory**  </span></span>  
 <span data-ttu-id="1a56e-136">階層的なメッセージの説明 (ッドマウント) 内の列。</span><span class="sxs-lookup"><span data-stu-id="1a56e-136">A column in the Hierarchical Message Description (HMD).</span></span> <span data-ttu-id="1a56e-137">属性必須ですが、この属性に基づくすべてのメッセージ要素を含めることは、null 以外の値を含める必要がありますまたは場合、既定値は null でない必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a56e-137">If the inclusion for an attribute mandatory, all message elements based on this attribute must contain a non-null value, or they must have a default that is not null.</span></span>  
  
  
 <span data-ttu-id="1a56e-138">**メッセージ**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-138">**message**  </span></span>  
 <span data-ttu-id="1a56e-139">情報のパッケージは、別のアプリケーションにから通知されます。</span><span class="sxs-lookup"><span data-stu-id="1a56e-139">A package of information communicated from one application to another.</span></span> <span data-ttu-id="1a56e-140">メッセージの種類およびメッセージ インスタンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a56e-140">See message type and message instance.</span></span>  
  
 <span data-ttu-id="1a56e-141">**メッセージの開発フレームワーク (MDF)**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-141">**Message Development Framework (MDF)**  </span></span>  
 <span data-ttu-id="1a56e-142">モデル、メソッド、および HL7 V3.0 メッセージを指定するための方法を構成するツールのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1a56e-142">The collection of models, methods, and tools that comprise the methodology for specifying HL7 V3.0 messages.</span></span> <span data-ttu-id="1a56e-143">HL7 標準の開発者は、このフレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-143">Developers of the HL7 standards use this framework.</span></span> <span data-ttu-id="1a56e-144">V3.0 ガイドは、方法論の内容をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="1a56e-144">The V3.0 Guide summarizes the content of the methodology.</span></span>  
  
 <span data-ttu-id="1a56e-145">**メッセージ要素**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-145">**message element**  </span></span>  
 <span data-ttu-id="1a56e-146">メッセージの種類に構造体の単位。</span><span class="sxs-lookup"><span data-stu-id="1a56e-146">A unit of structure within a message type.</span></span>  
  
 <span data-ttu-id="1a56e-147">**メッセージの要素の型**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-147">**message element type**  </span></span>  
 <span data-ttu-id="1a56e-148">メッセージの要素のいずれかを説明するメッセージの種類の一部になります。</span><span class="sxs-lookup"><span data-stu-id="1a56e-148">A portion of a message type that describes one of the elements of the message.</span></span>  
  
 <span data-ttu-id="1a56e-149">**メッセージ インスタンス**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-149">**message instance**  </span></span>  
 <span data-ttu-id="1a56e-150">特定の伝送用にフォーマットされているメッセージです。</span><span class="sxs-lookup"><span data-stu-id="1a56e-150">A message that is formatted for a specific transmission.</span></span> <span data-ttu-id="1a56e-151">同じメッセージの種類できます 2 つのメッセージを記述同じ操作でと特定値、立ち会いの下、または送信されるデータが存在しない場合、およびコレクションの別の基数でのバリエーションのためのインスタンスでまだによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1a56e-151">The same message type can describe two messages  and identify with the same interaction and yet vary in the instance because of variations in values, presence, or absence of the data being sent and different cardinalities of collections.</span></span> <span data-ttu-id="1a56e-152">それ以外の場合と同じメッセージ可能性がありますの異なるインスタンスまたは別の送信者によって異なるタイミングで送信される場合。</span><span class="sxs-lookup"><span data-stu-id="1a56e-152">Otherwise, identical messages may be different instances if they are sent at different times or by a different sender.</span></span>  
  
 <span data-ttu-id="1a56e-153">**メッセージ ペイロード**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-153">**message payload**  </span></span>  
 <span data-ttu-id="1a56e-154">データは、メッセージで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1a56e-154">Data carried in a message.</span></span>  
  
 <span data-ttu-id="1a56e-155">**メッセージの種類**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-155">**message type**  </span></span>  
 <span data-ttu-id="1a56e-156">階層的なメッセージの説明 (ッドマウント) で指定されているメッセージの要素の組織。</span><span class="sxs-lookup"><span data-stu-id="1a56e-156">The organization of message elements that is specified in a Hierarchical Message Description (HMD).</span></span> <span data-ttu-id="1a56e-157">各メッセージの種類は相互作用モデルで 1 つまたは複数の相互作用の一部として伝達されます。</span><span class="sxs-lookup"><span data-stu-id="1a56e-157">Each message type is communicated as part of one or more interactions in the interaction model.</span></span> <span data-ttu-id="1a56e-158">メッセージの種類は、有効で、インスタンス データの特定のセットを指定したメッセージを構築するための規則のセットを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-158">A message type in effect constitutes a set of rules for constructing a message given a specific set of instance data.</span></span> <span data-ttu-id="1a56e-159">また、インスタンス データを回復するメッセージを解析するための規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-159">It also defines the rules for parsing a message to recover the instance data.</span></span> <span data-ttu-id="1a56e-160">メッセージの種類が設定されて実装技術仕様に依存しないメッセージ型ことができます、他のいずれかをするの (が音訳)、同じメッセージの種類と別の実装の技術仕様を使用して、同じデータを送信する場合。</span><span class="sxs-lookup"><span data-stu-id="1a56e-160">The message type is independent of the Implementation Technology Specification, so that if the same data is sent using the same message type and different implementation technology specifications, the message type can be transliterated from one to the other.</span></span>  

## <a name="p"></a><span data-ttu-id="1a56e-161">P</span><span class="sxs-lookup"><span data-stu-id="1a56e-161">P</span></span>  
 <span data-ttu-id="1a56e-162">**プロパティ**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-162">**property**  </span></span>  
 <span data-ttu-id="1a56e-163">属性、アソシエーション、メソッド、またはクラスまたはオブジェクトに対して定義されている状態モデル。</span><span class="sxs-lookup"><span data-stu-id="1a56e-163">Any attribute, association, method, or state model defined for a class or object.</span></span> <span data-ttu-id="1a56e-164">ッドマウントとして、クラス、属性、またはアソシエーションのロール名の名前を示す列で、参照情報モデル (rim へ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a56e-164">In an HMD, the column that states the name of the class, attribute, or association role name as it appears in the Reference Information Model (RIM).</span></span>  

## <a name="r"></a><span data-ttu-id="1a56e-165">R</span><span class="sxs-lookup"><span data-stu-id="1a56e-165">R</span></span>  
 <span data-ttu-id="1a56e-166">**参照情報モデル (rim へ)**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-166">**Reference Information Model (RIM)**  </span></span>  
 <span data-ttu-id="1a56e-167">その他のすべての情報モデル (たとえば、R-MIMs) およびメッセージの派生元と HL7 情報モデルです。</span><span class="sxs-lookup"><span data-stu-id="1a56e-167">The HL7 information model from which all other information models (for example, R-MIMs) and messages derive.</span></span>  
  
 <span data-ttu-id="1a56e-168">**洗練されたメッセージ情報モデル (R MIM)**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-168">**Refined Message Information Model (R-MIM)**  </span></span>  
 <span data-ttu-id="1a56e-169">メッセージの一連の要件を表す情報構造。</span><span class="sxs-lookup"><span data-stu-id="1a56e-169">An information structure that represents the requirements for a set of messages.</span></span> <span data-ttu-id="1a56e-170">Rim へのクラスからは、複製される他のクラスを含む可能性のある rim への制約付きのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="1a56e-170">A constrained subset of the RIM that may contain additional classes that are cloned from RIM classes.</span></span> <span data-ttu-id="1a56e-171">1 つまたは複数階層的なメッセージの説明 (HMDs) をサポートするために必要なそれらのクラス、属性、アソシエーション、およびデータ型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a56e-171">Contains those classes, attributes, associations, and data types that are needed to support one or more Hierarchical Message Description (HMDs).</span></span> <span data-ttu-id="1a56e-172">1 つのメッセージは、R MIM 内のクラスを介して特定のパスとして表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a56e-172">A single message can be shown as a particular pathway through the classes within an R-MIM.</span></span>  

## <a name="s"></a><span data-ttu-id="1a56e-173">S</span><span class="sxs-lookup"><span data-stu-id="1a56e-173">S</span></span>  
 <span data-ttu-id="1a56e-174">**シナリオ**  </span><span class="sxs-lookup"><span data-stu-id="1a56e-174">**scenario**  </span></span>  
 <span data-ttu-id="1a56e-175">UML Unified Modeling Language ()、「1 つのユース ケースでの実行の 1 つのパス」。</span><span class="sxs-lookup"><span data-stu-id="1a56e-175">In Unified Modeling Language (UML), "a single path of execution through a single use case".</span></span> <span data-ttu-id="1a56e-176">健康保険に関連する相互作用のシーケンスとして定義されているイベントのステートメント。</span><span class="sxs-lookup"><span data-stu-id="1a56e-176">A statement of events defined as a sequence of interactions relevant in health care.</span></span> <span data-ttu-id="1a56e-177">シナリオでは、通常は、ドメインで発生するが必要ですが、モデリング委員会の相互作用の 1 つのセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-177">The scenario provides one set of interactions that the modeling committee expects to typically occur in the domain.</span></span> <span data-ttu-id="1a56e-178">通常、1 つのシナリオの相互作用のグループを表示するシーケンス ダイアグラムが構築されます。</span><span class="sxs-lookup"><span data-stu-id="1a56e-178">Usually, a sequence diagram is constructed to show a group of interactions for a single scenario.</span></span> <span data-ttu-id="1a56e-179">各シナリオは、相互作用モデルのサブセットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a56e-179">Each scenario is displayed as a subset of the interaction model.</span></span>  
  
 <span data-ttu-id="1a56e-180">**スキーマ**</span><span class="sxs-lookup"><span data-stu-id="1a56e-180">**schema**</span></span>    
 1. <span data-ttu-id="1a56e-181">図表プレゼンテーション、構造化フレームワーク、または計画します。</span><span class="sxs-lookup"><span data-stu-id="1a56e-181">A diagrammatic presentation, a structured framework, or a plan.</span></span> 
 2. <span data-ttu-id="1a56e-182">ドキュメントまたはデータのセットの文法のコンテキスト内で有効な式を指定するために条件を満たす必要がある要件のセット。</span><span class="sxs-lookup"><span data-stu-id="1a56e-182">A set of requirements that need to be met in order for a document or set of data to be a valid expression within the context of that grammar.</span></span> <span data-ttu-id="1a56e-183">XML スキーマは、ドキュメントの構造またはデータのセットの仕様で標準一般化マークアップ言語 (SGML) です。</span><span class="sxs-lookup"><span data-stu-id="1a56e-183">An XML schema is a specification in Standard Generalized Markup Language (SGML) of the structure of a document or set of data.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1a56e-184">次の手順</span><span class="sxs-lookup"><span data-stu-id="1a56e-184">Next steps</span></span>
[<span data-ttu-id="1a56e-185">パーティの BTAHL7 構成エクスプ ローラー</span><span class="sxs-lookup"><span data-stu-id="1a56e-185">Parties - BTAHL7 Configuration Explorer</span></span>](parties-tab.md)  
[<span data-ttu-id="1a56e-186">グローバルの設定 - BTAHL7 構成エクスプ ローラー</span><span class="sxs-lookup"><span data-stu-id="1a56e-186">Global Settings - BTAHL7 Configuration Explorer</span></span>](global-settings-tab.md)  
[<span data-ttu-id="1a56e-187">MLLP トランスポートのプロパティ ダイアログ ボックスの UI ヘルプ</span><span class="sxs-lookup"><span data-stu-id="1a56e-187">MLLP Transport Properties Dialog Box UI Help</span></span>](mllp-transport-properties-dialog-box-ui-help.md)
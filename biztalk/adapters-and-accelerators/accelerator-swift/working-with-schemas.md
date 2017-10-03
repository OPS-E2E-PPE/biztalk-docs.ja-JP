---
title: "スキーマの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, schemas
- schemas, developing
ms.assetid: 123c4b43-34e4-41c7-980d-5d518b1479c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1c12936f2883bfdbcdcd80d300d2ab5a9ff58d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-schemas"></a><span data-ttu-id="27537-102">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="27537-102">Working with Schemas</span></span>
<span data-ttu-id="27537-103">指定されたスキーマ[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]は、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Worldwide 銀行間財務通信 (SWIFT) FIN メッセージの社会の XSD 表記します。</span><span class="sxs-lookup"><span data-stu-id="27537-103">The schemas provided in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] XSD representation of the Society for Worldwide Interbank Financial Telecommunication (SWIFT) FIN messages.</span></span> <span data-ttu-id="27537-104">各メッセージの種類は、SWIFT ヘッダーとトレーラーの SWIFT (インターチェンジの形式) を含む独自のスキーマがします。</span><span class="sxs-lookup"><span data-stu-id="27537-104">Each message type has its own schema, including the SWIFT header and SWIFT trailer (interchange format).</span></span> <span data-ttu-id="27537-105">このスキーマは、SWIFT メッセージの送受信に十分です。</span><span class="sxs-lookup"><span data-stu-id="27537-105">This schema is sufficient to send or receive a SWIFT message.</span></span> <span data-ttu-id="27537-106">これらのスキーマは、フラット ファイル FIN 構造体の詳細な XML 表現を提供する、区切り文字および位置指定レコードの一意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="27537-106">These schemas are a unique mixture of delimited and positional records, providing a detailed XML representation of the flat-file FIN structures.</span></span>  
  
 <span data-ttu-id="27537-107">SWIFT のほとんどのお客様は、SWIFT FIN メッセージの比較的小さなサブセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="27537-107">Most SWIFT customers use a relatively small subset of the SWIFT FIN messages.</span></span> <span data-ttu-id="27537-108">これらの顧客のソリューションを実装するには、BizTalk スキーマ プロジェクトを作成することができます (で示したように[第 2 章: 新しいスキーマ プロジェクトに追加する](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)A4SWIFT チュートリアルの)。</span><span class="sxs-lookup"><span data-stu-id="27537-108">To implement a solution for these customers, you can create a BizTalk schema project (as demonstrated in [Module 2: Adding a New Schemas Project](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md) of the A4SWIFT tutorial).</span></span> <span data-ttu-id="27537-109">関連するメッセージのスキーマを追加 (MT*xxx*.xsd) から\\\ files \microsoft BizTalk Accelerator for SWIFT\<バージョン > MessagePack\SWIFT Messages\A4SWIFT SRG\<バージョン > \X は xyy と FIN メッセージ型の最初の桁カテゴリ x\MT xyy ディレクトリは、メッセージの 3 桁のメッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="27537-109">Add the relevant message schemas (MT*xxx*.xsd) from \\\ Program Files\Microsoft BizTalk Accelerator for SWIFT \<version> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version>\Category x\MT xyy directory, where x is the first digit of the FIN message type and xyy is the three-digit message type for the message.</span></span>  
  
 <span data-ttu-id="27537-110">いくつかのスキーマは、同じプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="27537-110">You can add several schemas to the same project.</span></span> <span data-ttu-id="27537-111">管理の容易性を維持するためには、プロジェクトごとに 20 件以上のメッセージ スキーマを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="27537-111">To maintain manageability, you should not add more than 20 message schemas per project.</span></span> <span data-ttu-id="27537-112">また、基本クラスと共通のスキーマをプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27537-112">You also need to add the base and common schemas to the project.</span></span> <span data-ttu-id="27537-113">基本クラスと共通のスキーマが既にある場合は、それらを展開するのではなく、そのアセンブリへの参照を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27537-113">If you have already deployed the base and common schemas, you need to make a reference to their assembly, rather than deploy them.</span></span> <span data-ttu-id="27537-114">このセクションでは、これらのスキーマについて説明します。</span><span class="sxs-lookup"><span data-stu-id="27537-114">This section describes these schemas.</span></span> <span data-ttu-id="27537-115">メッセージ スキーマは、SWIFT ネットワークに送信されたメッセージと SWIFT から受信したメッセージの両方が使用する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="27537-115">The message schemas are ready to use as is for both messages sent to the SWIFT network and messages received from SWIFT.</span></span>  
  
 <span data-ttu-id="27537-116">内の各 SWIFT スキーマの内容を調べることができます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]スキーマ エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="27537-116">You can examine the contents of each SWIFT schema in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] using the Schema Editor.</span></span> <span data-ttu-id="27537-117">次の一般的な構造であるすべてのメッセージ交換スキーマ。</span><span class="sxs-lookup"><span data-stu-id="27537-117">All of the message interchange schemas have the following common structure:</span></span>  
  
-   <span data-ttu-id="27537-118">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="27537-118">Headers</span></span>  
  
-   <span data-ttu-id="27537-119">[メッセージ テキスト]</span><span class="sxs-lookup"><span data-stu-id="27537-119">Message text</span></span>  
  
-   <span data-ttu-id="27537-120">トレーラー</span><span class="sxs-lookup"><span data-stu-id="27537-120">Trailers</span></span>  
  
 <span data-ttu-id="27537-121">このセクションでは、ヘッダーとトレーラーのスキーマについて説明します。</span><span class="sxs-lookup"><span data-stu-id="27537-121">This section describes the header and trailer schemas.</span></span> <span data-ttu-id="27537-122">メッセージ テキストは、FIN メッセージのペイロードを構成および、送信者、受信者、およびメッセージの種類を含むフィールドを除くデータ フィールドのすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27537-122">The message text comprises the payload of the FIN message, and contains all of the data fields except the fields containing the sender, receiver, and message type.</span></span> <span data-ttu-id="27537-123">これら 3 つのフィールドは、ヘッダー部分に含まれます。</span><span class="sxs-lookup"><span data-stu-id="27537-123">These three fields are contained in the header portion.</span></span> <span data-ttu-id="27537-124">一部のメッセージには、処理情報も提供する、省略可能なユーザー ヘッダーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="27537-124">Some messages also contain an optional user header, which may also provide processing information.</span></span>  
  
 <span data-ttu-id="27537-125">各 FIN メッセージ ペイロードは、一連のフィールドに定義されたシーケンス内で構成されます。</span><span class="sxs-lookup"><span data-stu-id="27537-125">Each FIN message payload consists of a series of fields in a defined sequence.</span></span> <span data-ttu-id="27537-126">これらのフィールドは、次の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="27537-126">These fields conform to the following rules:</span></span>  
  
-   <span data-ttu-id="27537-127">フィールドには、必須または、シーケンス内でオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="27537-127">The fields may be required or optional within the sequence.</span></span>  
  
-   <span data-ttu-id="27537-128">シーケンスがサブ シーケンス、およびサブ シーケンスがシーケンス内で繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="27537-128">A sequence may contain sub-sequences, and a sub-sequence may repeat within a sequence.</span></span>  
  
-   <span data-ttu-id="27537-129">いくつかのメッセージ型のフィールドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="27537-129">You can use a field in several message types.</span></span>  
  
-   <span data-ttu-id="27537-130">フィールドの内部に、要素またはサブフィールドが可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27537-130">Within a field, there may be elements or subfields.</span></span> <span data-ttu-id="27537-131">要素またはサブフィールドをいくつかのフィールドに一般的な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27537-131">An element or subfield may be common to several fields.</span></span>  
  
-   <span data-ttu-id="27537-132">グループ ノードでは、各繰り返しのシーケンスを表します。</span><span class="sxs-lookup"><span data-stu-id="27537-132">A group node represents each repeating sequence.</span></span>  
  
-   <span data-ttu-id="27537-133">各フィールド自体があります、複数の節レベル レコードとして各説明します。</span><span class="sxs-lookup"><span data-stu-id="27537-133">Each field may itself have multiple nodal levels, each described as a record.</span></span>  
  
-   <span data-ttu-id="27537-134">スキーマ要素は、最下位レベルのサブフィールドのみを表します。</span><span class="sxs-lookup"><span data-stu-id="27537-134">Schema elements represent only the lowest level subfields.</span></span>  
  
-   <span data-ttu-id="27537-135">共通の基本とスキーマは、共通のレコードと要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="27537-135">The common and base schemas define common records and elements.</span></span>  
  
-   <span data-ttu-id="27537-136">スキーマは、いくつかの形式 (パーティ フィールドなど) の一部のフィールドを表します。</span><span class="sxs-lookup"><span data-stu-id="27537-136">Schemas represent some fields in several formats (such as party fields).</span></span> <span data-ttu-id="27537-137">スキーマは、選択フィールドとして、このようなフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="27537-137">Schemas define such fields as choice fields.</span></span>  
  
-   <span data-ttu-id="27537-138">一部のフィールドには、値のセットが制限されます。</span><span class="sxs-lookup"><span data-stu-id="27537-138">Some fields have limited sets of values.</span></span> <span data-ttu-id="27537-139">ほとんどの場合、スキーマには、これらの値が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="27537-139">For the most part, the schema lists these values.</span></span> <span data-ttu-id="27537-140">スキーマ定義には、文字セットの検証も含まれます。</span><span class="sxs-lookup"><span data-stu-id="27537-140">Schema definitions also include character set validation.</span></span>  
  
 <span data-ttu-id="27537-141">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="27537-141">This section contains:</span></span>  
  
-   [<span data-ttu-id="27537-142">ベースと一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="27537-142">Base and Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/base-and-common-schemas.md)  
  
-   [<span data-ttu-id="27537-143">SWIFT ヘッダーおよびトレーラ スキーマ</span><span class="sxs-lookup"><span data-stu-id="27537-143">SWIFT Header and Trailer Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
-   [<span data-ttu-id="27537-144">SWIFT スキーマの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="27537-144">SWIFT Schema Naming Conventions</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-schema-naming-conventions.md)
---
title: "名前付け規則に SWIFT のスキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb792fe66e5806a186b0ffb946aa99f86a6a10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-schema-naming-conventions"></a><span data-ttu-id="0430e-102">SWIFT スキーマの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="0430e-102">SWIFT Schema Naming Conventions</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="0430e-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Society の BizTalk エディターを使用して作成された世界銀行間財務通信 (SWIFT) FIN メッセージのスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0430e-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes schemas for Society for Worldwide Interbank Financial Telecommunication (SWIFT) FIN messages that were created using BizTalk Editor.</span></span> <span data-ttu-id="0430e-104">これらのスキーマは、全体で、次の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="0430e-104">These schemas conform to the following conventions throughout:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0430e-105">すべてのスキーマをバージョン管理します。</span><span class="sxs-lookup"><span data-stu-id="0430e-105">All schemas are versioned.</span></span> <span data-ttu-id="0430e-106">バージョンを表示、開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、ソリューション エクスプ ローラーでスキーマを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0430e-106">To see the version, open [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and right-click the schema in Solution Explorer.</span></span> <span data-ttu-id="0430e-107">\<スキーマ > ノードをプロパティ ウィンドウのスクロール標準バージョン プロパティの BizTalk エディターを選択します。</span><span class="sxs-lookup"><span data-stu-id="0430e-107">With the \<Schema> node selected in BizTalk Editor, in the Properties pane scroll down to the Standard Version property.</span></span>  
  
-   <span data-ttu-id="0430e-108">各インターチェンジのスキーマ ファイルの名前は **MT*xxx** *、.xsd、 *xxx* FIN メッセージ型です。</span><span class="sxs-lookup"><span data-stu-id="0430e-108">The name of each interchange schema file is **MT*xxx*.xsd**, where *xxx* is the FIN message type.</span></span>  
  
-   <span data-ttu-id="0430e-109">各メッセージに関連するマスター ポリシー ファイルの名前は **MT*xxx*_Master_Policy.xml**、ビジネス ルール エンジン (BRE) に対応する名前が、  **MT*xxx*_Master_Policy**の一覧の名前を持つ **MT*xxx*_PolicyList * *。</span><span class="sxs-lookup"><span data-stu-id="0430e-109">The name of the associated master policy file for each message is **MT*xxx*_Master_Policy.xml**, and the corresponding name in the Business Rule Engine (BRE) is **MT*xxx*_Master_Policy**, with a list name of **MT*xxx*_PolicyList**.</span></span>  
  
-   <span data-ttu-id="0430e-110">各メッセージに関連付けられている検証ポリシー ファイルの名前は **MT*xxx*_Validation_Policy.xml**、BRE に対応する名前が、  **MT*xxx*_Validation_Policy**です。</span><span class="sxs-lookup"><span data-stu-id="0430e-110">The name of the associated validation policy file for each message is **MT*xxx*_Validation_Policy.xml**, and the corresponding name in the BRE is **MT*xxx*_Validation_Policy**.</span></span>  
  
-   <span data-ttu-id="0430e-111">ルートの名前は、各メッセージ スキーマ内で **SWIFT_CATEGORY*z*_MT*zxx** *、_Interchange 場所*z*メッセージ カテゴリには(メッセージの種類の最初の数字) と*zxx*は、メッセージ型です。</span><span class="sxs-lookup"><span data-stu-id="0430e-111">Within each message schema, the name of the root is **SWIFT_CATEGORY*z*_MT*zxx*_Interchange**, where *z* is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="0430e-112">各メッセージ スキーマのターゲット名前空間は **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx** *、どこで*z*メッセージ カテゴリ (メッセージの種類の最初の桁) と*zxx*は、メッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="0430e-112">The target namespace for each message schema is **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx***, where *z* is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="0430e-113">ドキュメントの種類が **MT*zxx** *、どこで*zxx*は、メッセージ型です。</span><span class="sxs-lookup"><span data-stu-id="0430e-113">The document type is **MT*zxx***, where *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="0430e-114">番号付けされていないフィールドと下位のフィールドの名前には、ビジネスのわかりやすい名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0430e-114">The names of fields that are not numbered and sub-fields include descriptive business names.</span></span> <span data-ttu-id="0430e-115">各単語の最初の文字を大文字にすると、し、余分な空白や句読点単語間の名前が含まれません (たとえば、名前がなります**ServiceIdentifier**ではなく、**サービス識別子**).</span><span class="sxs-lookup"><span data-stu-id="0430e-115">The first letter of each word is capitalized, and the names do not include an intervening space or punctuation between words (for example, the name would be **ServiceIdentifier**, not **Service Identifier**).</span></span>  
  
-   <span data-ttu-id="0430e-116">準拠しているメッセージ内のシーケンスのラベル、 *SWIFT リファレンス ガイド*(たとえば、 **SequenceA**)。</span><span class="sxs-lookup"><span data-stu-id="0430e-116">The labels of sequences within messages conform to the *SWIFT Reference Guide* (for example, **SequenceA**).</span></span>  
  
-   <span data-ttu-id="0430e-117">番号付き SWIFT のフィールドのラベルの後に番号と省略可能な文字書式続くシーケンス (存在する場合)、わかりやすいタイトルを含める (たとえば、 **Reference_A_20C**)。</span><span class="sxs-lookup"><span data-stu-id="0430e-117">The labels of numbered SWIFT fields include a descriptive title followed by the sequence (if present), followed by the number code and optional letter format (for example, **Reference_A_20C**).</span></span>  
  
-   <span data-ttu-id="0430e-118">ノードのラベルは、フィールドの複数の形式の選択では、   **\<*選択肢*> * *、し、各オプションは、番号付きフィールドと (たとえば、 **Date_A_98A**と**DateTime_A_98C**)。</span><span class="sxs-lookup"><span data-stu-id="0430e-118">Where there is a choice of multiple formats for a field, the label of the node is **\<*Choice*>**, and then each option is a numbered field (for example, **Date_A_98A** and **DateTime_A_98C**).</span></span>  
  
-   <span data-ttu-id="0430e-119">サブ フィールドの最も低いレベルの要素の定義の名前は、続いてサブ フィールドの名前で構成されます**型**(たとえば、 **accountType**アカウント用)。</span><span class="sxs-lookup"><span data-stu-id="0430e-119">The name of the lowest level element definition of a sub-field consists of the name of the sub-field followed by **Type** (for example, **accountType** for Account).</span></span>  
  
 <span data-ttu-id="0430e-120">他の名前空間、メッセージ スキーマで、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0430e-120">Other namespaces in the message schema include the following:</span></span>  
  
-   <span data-ttu-id="0430e-121">xmlns:xs ="http://www.w3.org/2001/XMLSchema"です。</span><span class="sxs-lookup"><span data-stu-id="0430e-121">xmlns:xs="http://www.w3.org/2001/XMLSchema".</span></span> <span data-ttu-id="0430e-122">これは、既定の W3C XML スキーマ名前空間です。</span><span class="sxs-lookup"><span data-stu-id="0430e-122">This is the default W3C XML Schema namespace.</span></span>  
  
-   <span data-ttu-id="0430e-123">xmlns:b"http://schemas.microsoft.com/BizTalk/2003"を = です。</span><span class="sxs-lookup"><span data-stu-id="0430e-123">xmlns:b="http://schemas.microsoft.com/BizTalk/2003".</span></span> <span data-ttu-id="0430e-124">これは、既定の BizTalk 名前空間です。</span><span class="sxs-lookup"><span data-stu-id="0430e-124">This is the default BizTalk namespace.</span></span>  
  
 <span data-ttu-id="0430e-125">各メッセージ スキーマは、基本型と一般的なデータ型のスキーマを直接参照します。</span><span class="sxs-lookup"><span data-stu-id="0430e-125">Each message schema directly references the base type and common data type schemas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0430e-126">参照</span><span class="sxs-lookup"><span data-stu-id="0430e-126">See Also</span></span>  
 [<span data-ttu-id="0430e-127">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="0430e-127">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)
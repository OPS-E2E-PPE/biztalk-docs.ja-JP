---
title: SWIFT スキーマの名前付け規則 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f173b1d2e424a111e4657c0b0d943aee932ac21b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529743"
---
# <a name="swift-schema-naming-conventions"></a><span data-ttu-id="c9958-102">SWIFT スキーマの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="c9958-102">SWIFT Schema Naming Conventions</span></span>
<span data-ttu-id="c9958-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]社会の BizTalk エディターを使用して作成された世界銀行間金融電気通信 (SWIFT) FIN メッセージのスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9958-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes schemas for Society for Worldwide Interbank Financial Telecommunication (SWIFT) FIN messages that were created using BizTalk Editor.</span></span> <span data-ttu-id="c9958-104">これらのスキーマは、全体では、次の規則に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="c9958-104">These schemas conform to the following conventions throughout:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9958-105">すべてのスキーマは、バージョン管理されます。</span><span class="sxs-lookup"><span data-stu-id="c9958-105">All schemas are versioned.</span></span> <span data-ttu-id="c9958-106">バージョンを表示、開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーでスキーマを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c9958-106">To see the version, open [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and right-click the schema in Solution Explorer.</span></span> <span data-ttu-id="c9958-107">\<スキーマ\>標準バージョン プロパティまでのプロパティ ウィンドウのスクロールで BizTalk エディターを選択したノード。</span><span class="sxs-lookup"><span data-stu-id="c9958-107">With the \<Schema\> node selected in BizTalk Editor, in the Properties pane scroll down to the Standard Version property.</span></span>  
  
- <span data-ttu-id="c9958-108">各インターチェンジのスキーマ ファイルの名前は**MT*xxx*.xsd**ここで、 *xxx* FIN メッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="c9958-108">The name of each interchange schema file is **MT*xxx*.xsd**, where *xxx* is the FIN message type.</span></span>  
  
- <span data-ttu-id="c9958-109">各メッセージに関連するマスター ポリシー ファイルの名前は**MT*xxx*_Master_Policy.xml**、ビジネス ルール エンジン (BRE) に対応する名前が、 **MT*xxx*_Master_Policy**、リスト名を持つ**MT*xxx*_PolicyList**します。</span><span class="sxs-lookup"><span data-stu-id="c9958-109">The name of the associated master policy file for each message is **MT*xxx*_Master_Policy.xml**, and the corresponding name in the Business Rule Engine (BRE) is **MT*xxx*_Master_Policy**, with a list name of **MT*xxx*_PolicyList**.</span></span>  
  
- <span data-ttu-id="c9958-110">各メッセージに関連付けられている検証ポリシー ファイルの名前は**MT*xxx*_Validation_Policy.xml**、BRE に対応する名前が、 **MT*xxx*_Validation_Policy**します。</span><span class="sxs-lookup"><span data-stu-id="c9958-110">The name of the associated validation policy file for each message is **MT*xxx*_Validation_Policy.xml**, and the corresponding name in the BRE is **MT*xxx*_Validation_Policy**.</span></span>  
  
- <span data-ttu-id="c9958-111">ルートの名前は、各メッセージ スキーマ内で**SWIFT_CATEGORY*z*_MT*zxx*_Interchange**ここで、 *z*は、メッセージ カテゴリ (メッセージの種類の最初の桁) と*zxx*は、メッセージ型です。</span><span class="sxs-lookup"><span data-stu-id="c9958-111">Within each message schema, the name of the root is **SWIFT_CATEGORY*z*_MT*zxx*_Interchange**, where *z* is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
- <span data-ttu-id="c9958-112">各メッセージ スキーマのターゲット名前空間は**<http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx>**<em>ここで、\* z</em>メッセージ カテゴリ (メッセージの種類の最初の桁) と*zxx*はメッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="c9958-112">The target namespace for each message schema is **<http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx>**<em>, where \*z</em> is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
- <span data-ttu-id="c9958-113">ドキュメントの種類が**MT \* zxx**<em>ここで、\* zxx</em>は、メッセージ型です。</span><span class="sxs-lookup"><span data-stu-id="c9958-113">The document type is **MT\*zxx**<em>, where \*zxx</em> is the message type.</span></span>  
  
- <span data-ttu-id="c9958-114">番号付けされていないフィールドとサブ フィールドの名前には、ビジネスのわかりやすい名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9958-114">The names of fields that are not numbered and sub-fields include descriptive business names.</span></span> <span data-ttu-id="c9958-115">各単語の最初の文字が大文字になっているし、余分な空白または句読点の単語、名前が含まれません (たとえば、名前になります**ServiceIdentifier**ではなく、**サービス識別子**).</span><span class="sxs-lookup"><span data-stu-id="c9958-115">The first letter of each word is capitalized, and the names do not include an intervening space or punctuation between words (for example, the name would be **ServiceIdentifier**, not **Service Identifier**).</span></span>  
  
- <span data-ttu-id="c9958-116">準拠しているメッセージ内のシーケンスのラベル、 *SWIFT リファレンス ガイド*(たとえば、 **SequenceA**)。</span><span class="sxs-lookup"><span data-stu-id="c9958-116">The labels of sequences within messages conform to the *SWIFT Reference Guide* (for example, **SequenceA**).</span></span>  
  
- <span data-ttu-id="c9958-117">番号付き SWIFT フィールドのラベル、番号コードと省略可能な文字の書式設定後に続くシーケンス (ある場合)、わかりやすいタイトルを含める (たとえば、 **Reference_A_20C**)。</span><span class="sxs-lookup"><span data-stu-id="c9958-117">The labels of numbered SWIFT fields include a descriptive title followed by the sequence (if present), followed by the number code and optional letter format (for example, **Reference_A_20C**).</span></span>  
  
- <span data-ttu-id="c9958-118">ノードのラベルは、さまざまなフィールドの複数の形式では、  **\<*選択肢*\>**、し、各オプションは、番号付きフィールドと (たとえば、**日付_A_98A**と**DateTime_A_98C**)。</span><span class="sxs-lookup"><span data-stu-id="c9958-118">Where there is a choice of multiple formats for a field, the label of the node is **\<*Choice*\>**, and then each option is a numbered field (for example, **Date_A_98A** and **DateTime_A_98C**).</span></span>  
  
- <span data-ttu-id="c9958-119">サブ フィールドの最下位レベルの要素定義の名前が続くサブ フィールドの名前から成る**型**(たとえば、 **accountType**アカウントの)。</span><span class="sxs-lookup"><span data-stu-id="c9958-119">The name of the lowest level element definition of a sub-field consists of the name of the sub-field followed by **Type** (for example, **accountType** for Account).</span></span>  
  
  <span data-ttu-id="c9958-120">メッセージのスキーマで他の名前空間を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c9958-120">Other namespaces in the message schema include the following:</span></span>  
  
- <span data-ttu-id="c9958-121">xmlns:xs="<http://www.w3.org/2001/XMLSchema>".</span><span class="sxs-lookup"><span data-stu-id="c9958-121">xmlns:xs="<http://www.w3.org/2001/XMLSchema>".</span></span> <span data-ttu-id="c9958-122">これは、既定の W3C XML スキーマ名前空間です。</span><span class="sxs-lookup"><span data-stu-id="c9958-122">This is the default W3C XML Schema namespace.</span></span>  
  
- <span data-ttu-id="c9958-123">xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>".</span><span class="sxs-lookup"><span data-stu-id="c9958-123">xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>".</span></span> <span data-ttu-id="c9958-124">これは、既定の BizTalk 名前空間です。</span><span class="sxs-lookup"><span data-stu-id="c9958-124">This is the default BizTalk namespace.</span></span>  
  
  <span data-ttu-id="c9958-125">各メッセージ スキーマは、基本型と一般的なデータ型のスキーマを直接参照します。</span><span class="sxs-lookup"><span data-stu-id="c9958-125">Each message schema directly references the base type and common data type schemas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9958-126">参照</span><span class="sxs-lookup"><span data-stu-id="c9958-126">See Also</span></span>  
 [<span data-ttu-id="c9958-127">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="c9958-127">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)
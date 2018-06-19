---
title: ベースと一般的なスキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base schemas
- schemas, common schemas
- schemas, base schemas
- common schemas
ms.assetid: 60eb24f6-cc4f-4c6d-ab15-9e3a6b4ed376
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ca51abfcdbfe965bc3da8deeb97f72df736903
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209178"
---
# <a name="base-and-common-schemas"></a><span data-ttu-id="a5a4f-102">ベースと一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="a5a4f-102">Base and Common Schemas</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="a5a4f-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]レコードと別のスキーマ内の個々 のメッセージ スキーマを構成する要素を実装します。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] has implemented the records and elements that comprise individual message schemas in separate schemas.</span></span> <span data-ttu-id="a5a4f-104">この方法は、フィールドと形式の変更によってこのようなメッセージ スキーマを切り離すことの更新プログラムを提供する 1 つの場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-104">This approach provides a single location to provide updates for fields and formats, insulating the message schema from such changes.</span></span>  
  
 <span data-ttu-id="a5a4f-105">基本のスキーマ (**SWIFT 基本 Types.xsd**) メッセージ スキーマを参照する共通のレコードと、要素定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-105">The base schema (**SWIFT Base Types.xsd**) contains the common record and element definitions that the message schemas reference.</span></span> <span data-ttu-id="a5a4f-106">共通のレコードと、要素の定義は、SWIFT FIN メッセージ フィールドに対応します。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-106">The common record and element definitions correspond to the SWIFT FIN message fields.</span></span> <span data-ttu-id="a5a4f-107">このスキーマは、メッセージ スキーマを使用する他のプロジェクトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-107">You need to add this schema to any project that uses the message schema.</span></span> <span data-ttu-id="a5a4f-108">基本のスキーマは、共通の関数と規則について説明し、A4SWIFT が適切なメッセージ インスタンスの検証に使用する形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-108">The base schema covers the rules and common functions, and defines the formats that A4SWIFT uses to validate the appropriate message instances.</span></span> <span data-ttu-id="a5a4f-109">SWIFT ベース Types.xsd スキーマ XSD を定義する**simpleType**および SWIFT フィールドの複雑な要素です。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-109">The SWIFT Base Types.xsd schema defines XSD **simpleType** and complex elements for SWIFT fields.</span></span> <span data-ttu-id="a5a4f-110">SWIFT が定義されている**simpleType**量、レート、価格、およびに SWIFT をフィールドの多くで使用するなど、すべての基本フィールド用の要素。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-110">SWIFT has defined **simpleType** elements for all base fields, such as the Amount, Rate, Price, and so on, which SWIFT uses in many of the fields.</span></span> <span data-ttu-id="a5a4f-111">SWIFT ベース Types.xsd スキーマ フィールドを含む、カスタムの多くの複雑な要素を XSD でも定義**simpleTypes**スキーマで定義します。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-111">The SWIFT Base Types.xsd schema also defines XSD complex elements for fields that include many of the custom **simpleTypes** defined in the schema.</span></span> <span data-ttu-id="a5a4f-112">たとえば、 **BankIdentifierCode**複合型の要素は、銀行コード、国番号、市外局番、および分岐のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-112">For example, the **BankIdentifierCode** complex element uses Bank Code, Country Code, Area Code, and Branch Code.</span></span> <span data-ttu-id="a5a4f-113">ユーザーが新規に追加できる**simpleTypes**と複雑な要素であり、ミラー SWIFT フィールドと既存の型を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-113">Users can add new **simpleTypes** and complex elements that mirror SWIFT fields and can modify existing types.</span></span> <span data-ttu-id="a5a4f-114">注意してください、ただし、ビジネス ルール エンジン (BRE) の検証および XML の機能がこれらに定義された型に依存しているために、既存の型を変更するときにします。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-114">You should take care, however, when you modify existing types, because the Business Rule Engine (BRE) Validation and XML Validation features are dependent upon these defined types.</span></span>  
  
 <span data-ttu-id="a5a4f-115">共通のスキーマ (**SWIFT 共通データ Types.xsd**) ベースのスキーマのフィールドに適切な文字セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-115">The common schema (**SWIFT Common Data Types.xsd**) defines the character sets appropriate to the fields in the base schema.</span></span> <span data-ttu-id="a5a4f-116">SWIFT で参照しているこれらの文字セットを定義する、 *SWIFT ユーザー マニュアル*です。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-116">SWIFT defines these character sets, as referenced in the *SWIFT User Handbook*.</span></span> <span data-ttu-id="a5a4f-117">また、共通のスキーマをスキーマ プロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5a4f-117">You also need to add the common schema to your schema projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a4f-118">参照</span><span class="sxs-lookup"><span data-stu-id="a5a4f-118">See Also</span></span>  
 [<span data-ttu-id="a5a4f-119">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="a5a4f-119">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)
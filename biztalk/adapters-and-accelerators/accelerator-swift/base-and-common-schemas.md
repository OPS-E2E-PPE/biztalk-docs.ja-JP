---
title: ベースと一般的なスキーマ |Microsoft Docs
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
ms.openlocfilehash: 6b7f8f86e4b74b84cef556ae95bc6255d8575237
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012571"
---
# <a name="base-and-common-schemas"></a><span data-ttu-id="fc55e-102">ベースと一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="fc55e-102">Base and Common Schemas</span></span>
<span data-ttu-id="fc55e-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]レコードと別のスキーマ内の個々 のメッセージ スキーマを構成する要素を実装します。</span><span class="sxs-lookup"><span data-stu-id="fc55e-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] has implemented the records and elements that comprise individual message schemas in separate schemas.</span></span> <span data-ttu-id="fc55e-104">このアプローチでは、フィールドと形式のこのような変更からのメッセージ スキーマの保護の更新プログラムを提供する 1 つの場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc55e-104">This approach provides a single location to provide updates for fields and formats, insulating the message schema from such changes.</span></span>  
  
 <span data-ttu-id="fc55e-105">基本スキーマ (**SWIFT 基本 Types.xsd**) メッセージ スキーマを参照する共通のレコードと要素定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc55e-105">The base schema (**SWIFT Base Types.xsd**) contains the common record and element definitions that the message schemas reference.</span></span> <span data-ttu-id="fc55e-106">共通のレコードと要素の定義は、SWIFT FIN メッセージ フィールドに対応します。</span><span class="sxs-lookup"><span data-stu-id="fc55e-106">The common record and element definitions correspond to the SWIFT FIN message fields.</span></span> <span data-ttu-id="fc55e-107">このスキーマのメッセージ スキーマを使用するプロジェクトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc55e-107">You need to add this schema to any project that uses the message schema.</span></span> <span data-ttu-id="fc55e-108">基本スキーマは、規則と共通の関数について説明し、A4SWIFT を適切なメッセージ インスタンスの検証に使用する形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="fc55e-108">The base schema covers the rules and common functions, and defines the formats that A4SWIFT uses to validate the appropriate message instances.</span></span> <span data-ttu-id="fc55e-109">SWIFT ベース Types.xsd スキーマ XSD を定義する**simpleType**と SWIFT のフィールドの複雑な要素です。</span><span class="sxs-lookup"><span data-stu-id="fc55e-109">The SWIFT Base Types.xsd schema defines XSD **simpleType** and complex elements for SWIFT fields.</span></span> <span data-ttu-id="fc55e-110">SWIFT が定義されている**simpleType**量、速度、価格、およびフィールドの多くで SWIFT を使用して具合など、すべての基本フィールドの要素。</span><span class="sxs-lookup"><span data-stu-id="fc55e-110">SWIFT has defined **simpleType** elements for all base fields, such as the Amount, Rate, Price, and so on, which SWIFT uses in many of the fields.</span></span> <span data-ttu-id="fc55e-111">SWIFT ベース Types.xsd スキーマでは、カスタムの多くが含まれるフィールドの XSD の複雑な要素も定義します**simpleTypes**スキーマで定義されています。</span><span class="sxs-lookup"><span data-stu-id="fc55e-111">The SWIFT Base Types.xsd schema also defines XSD complex elements for fields that include many of the custom **simpleTypes** defined in the schema.</span></span> <span data-ttu-id="fc55e-112">たとえば、 **BankIdentifierCode**複雑な要素は、銀行コード、国コード、市外局番、およびブランチのコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc55e-112">For example, the **BankIdentifierCode** complex element uses Bank Code, Country Code, Area Code, and Branch Code.</span></span> <span data-ttu-id="fc55e-113">ユーザーが新規に追加できる**simpleTypes**と複雑な要素であり、ミラー SWIFT フィールドと、既存の型を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="fc55e-113">Users can add new **simpleTypes** and complex elements that mirror SWIFT fields and can modify existing types.</span></span> <span data-ttu-id="fc55e-114">注意が必要、ただし、ビジネス ルール エンジン (BRE) の検証および XML の検証機能は、これらの定義された型に依存するために既存の型を変更するとします。</span><span class="sxs-lookup"><span data-stu-id="fc55e-114">You should take care, however, when you modify existing types, because the Business Rule Engine (BRE) Validation and XML Validation features are dependent upon these defined types.</span></span>  
  
 <span data-ttu-id="fc55e-115">共通のスキーマ (**SWIFT 共通データ Types.xsd**) ベースのスキーマのフィールドに適切な文字セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="fc55e-115">The common schema (**SWIFT Common Data Types.xsd**) defines the character sets appropriate to the fields in the base schema.</span></span> <span data-ttu-id="fc55e-116">SWIFT で参照されるよう、これらの文字セットを定義する、 *SWIFT ユーザー向けハンドブック*します。</span><span class="sxs-lookup"><span data-stu-id="fc55e-116">SWIFT defines these character sets, as referenced in the *SWIFT User Handbook*.</span></span> <span data-ttu-id="fc55e-117">また、共通のスキーマをスキーマ プロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc55e-117">You also need to add the common schema to your schema projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc55e-118">参照</span><span class="sxs-lookup"><span data-stu-id="fc55e-118">See Also</span></span>  
 [<span data-ttu-id="fc55e-119">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="fc55e-119">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)
---
title: フラット ファイル スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8009fba7-85f0-4795-9284-5b4e94b3fc72
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ccb698a49df3edd6820cca5bb48a8045749bf89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387843"
---
# <a name="flat-file-schemas"></a><span data-ttu-id="5c8f0-102">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="5c8f0-102">Flat File Schemas</span></span>

## <a name="purpose-of-flat-file-schemas"></a><span data-ttu-id="5c8f0-103">フラット ファイル スキーマの目的</span><span class="sxs-lookup"><span data-stu-id="5c8f0-103">Purpose of flat file schemas</span></span>
<span data-ttu-id="5c8f0-104">フラット ファイル スキーマは、2 つの目的を果たします。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-104">Flat file schemas serve two purposes.</span></span> <span data-ttu-id="5c8f0-105">同じレコードおよびフィールドの特性 (構造体を含む) のすべての XML スキーマとして定義し、すべてのフラット ファイル インスタンス メッセージを同等の XML に変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供インスタンス メッセージ (またはその逆)。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-105">They define all of the same record and field characteristics (including structure) as XML schemas, and they provide a mechanism for defining all of the flat file characteristics that are required to translate a flat file instance message into an equivalent XML instance message (or vice versa).</span></span> <span data-ttu-id="5c8f0-106">前者の目的は、BizTalk マッパー内のフラット ファイル スキーマを使用して、異なる送信先構造に適合するフラット ファイル インスタンス メッセージの変換を定義するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-106">The former purpose is most useful when using the flat file schema within BizTalk Mapper to define a transformation of conforming flat file instance messages into a different, destination structure.</span></span> <span data-ttu-id="5c8f0-107">送信先構造は、BizTalk マッパーで、送信先スキーマで定義されている可能性がありますか、フラット ファイル メッセージ スキーマ (XML スキーマがある可能性があります) によって管理されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-107">The destination structure, defined by the destination schema in BizTalk Mapper, may or may not be governed by a flat file message schema (it could be an XML schema).</span></span>  
  
 <span data-ttu-id="5c8f0-108">ドキュメントのフラット ファイル形式と等価の XML の間の変換の書式を設定すると、後者の目的は、広範なセット、注釈構文を使用して XML スキーマ定義 (XSD) 言語スキーマに追加される情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-108">The latter purpose, that of translating between the flat file format of the document and its equivalent XML format, uses an extensive set of information that is added to the XML Schema definition (XSD) language schema using its annotation syntax.</span></span> <span data-ttu-id="5c8f0-109">この情報は、その構造を制御するスキーマに対して XML インスタンス メッセージを検証する際にその有用性の観点から、XSD の観点から余分なは。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-109">This information is superfluous from an XSD perspective, in terms of its usefulness in validating an XML instance message against the schema that governs its structure.</span></span> <span data-ttu-id="5c8f0-110">それにもかかわらず、XSD 注釈の構文は、さまざまなスキーマ全体については、内の注釈として格納されるまで、さまざまなスコープ内で、XSDスキーマ内のフラットファイル構造情報を格納する便利なメカニズムを提供します **。スキーマ**は特定のレコードまたはフィールドに固有の対応する内の注釈として格納されている情報への要素**要素**または**属性**要素。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-110">Nevertheless, the XSD annotation syntax provides a convenient mechanism for storing flat file structure information within the XSD schema within a variety of different scopes, ranging from schema-wide information stored as annotations within the **schema** element, to information that is specific to a particular record or field, stored as annotations within the corresponding **element** or **attribute** element.</span></span>  
  
 <span data-ttu-id="5c8f0-111">同等の XML とは異なるようにフラット ファイル スキーマのもう 1 つの特性は、インスタンス メッセージをコンテンツに基づいて、管理スキーマに一致することはできないことことです。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-111">Another characteristic of flat file schemas that make them different than their XML counterparts is the fact that instance messages cannot be matched to their governing schemas based on their content.</span></span> <span data-ttu-id="5c8f0-112">代わりに、実行時にフラット ファイル逆アセンブラーで使用するため、静的な一連のスキーマを指定してください。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-112">Instead, a static set of schemas must be specified for use by the flat file disassembler at runtime.</span></span>  
  
 <span data-ttu-id="5c8f0-113">フラット ファイルの特性に関連付けられているその他のノード プロパティを表示するには指定する必要があります、**フラット ファイル拡張子**を使用して、**スキーマ エディター拡張機能**プロパティ、の**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-113">To see the additional node properties associated with the characteristics of flat files, you need to specify the **Flat File Extension** by using the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="5c8f0-114">既定では表示されません。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-114">They do not appear by default.</span></span>  
  
 <span data-ttu-id="5c8f0-115">フラット ファイル スキーマに固有のノード プロパティの詳細については、次を参照してください。、**フラット ファイル スキーマの補足のノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5c8f0-115">For detailed information about the node properties that are specific to flat file schemas, see the **Supplemental Node Properties for Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5c8f0-116">参照</span><span class="sxs-lookup"><span data-stu-id="5c8f0-116">See Also</span></span>  
 [<span data-ttu-id="5c8f0-117">さまざまな種類の BizTalk スキーマ</span><span class="sxs-lookup"><span data-stu-id="5c8f0-117">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)
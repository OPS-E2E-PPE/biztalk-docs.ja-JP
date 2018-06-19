---
title: フラット ファイル スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 674a862b3966088bb1d75dd17ceacd47c30bdda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246050"
---
# <a name="flat-file-schemas"></a><span data-ttu-id="4d0ab-102">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="4d0ab-102">Flat File Schemas</span></span>

## <a name="purpose-of-flat-file-schemas"></a><span data-ttu-id="4d0ab-103">フラット ファイル スキーマの目的</span><span class="sxs-lookup"><span data-stu-id="4d0ab-103">Purpose of flat file schemas</span></span>
<span data-ttu-id="4d0ab-104">フラット ファイル スキーマには、2 つの機能があります。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-104">Flat file schemas serve two purposes.</span></span> <span data-ttu-id="4d0ab-105">その 1 つは、レコードおよびフィールドの同じ特性 (構造を含む) をすべて XML スキーマとして定義することです。もう 1 つの機能は、フラット ファイル インスタンス メッセージを等価の XML インスタンス メッセージに変換 (またはその逆の変換) する場合に必要となる、フラット ファイルのすべての特性を定義するメカニズムを提供することです。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-105">They define all of the same record and field characteristics (including structure) as XML schemas, and they provide a mechanism for defining all of the flat file characteristics that are required to translate a flat file instance message into an equivalent XML instance message (or vice versa).</span></span> <span data-ttu-id="4d0ab-106">最初の機能は、BizTalk マッパー内のフラット ファイル スキーマを使用して、準拠するフラット ファイル インスタンス メッセージを別の送信先構造に変換するための定義を行う場合に、利用できます。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-106">The former purpose is most useful when using the flat file schema within BizTalk Mapper to define a transformation of conforming flat file instance messages into a different, destination structure.</span></span> <span data-ttu-id="4d0ab-107">BizTalk マッパーの送信先スキーマで定義される送信先構造は、フラット ファイル メッセージ スキーマ (XML スキーマの可能性がある) によって管理される場合と、管理されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-107">The destination structure, defined by the destination schema in BizTalk Mapper, may or may not be governed by a flat file message schema (it could be an XML schema).</span></span>  
  
 <span data-ttu-id="4d0ab-108">2 つ目の機能 (ドキュメントのフラット ファイル形式と等価の XML 形式間の変換に関する機能) では、注釈構文を使用して XSD (XML Schema Definition) 言語のスキーマに追加される、さまざまな情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-108">The latter purpose, that of translating between the flat file format of the document and its equivalent XML format, uses an extensive set of information that is added to the XML Schema definition (XSD) language schema using its annotation syntax.</span></span> <span data-ttu-id="4d0ab-109">この情報は、XSD の観点 (構造を管理するスキーマを基にした XML インスタンス メッセージの検証で有用かどうかという概念) から考えると、余分な情報といえます。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-109">This information is superfluous from an XSD perspective, in terms of its usefulness in validating an XML instance message against the schema that governs its structure.</span></span> <span data-ttu-id="4d0ab-110">一方、XSD 注釈構文では、さまざまな異なるスコープ、スキーマ全体については、内の注釈として格納されている範囲内のXSDスキーマ内のフラットファイル構造情報を格納するための便利なメカニズム**スキーマ**固有情報を特定のレコードまたはフィールドに対応する内の注釈として格納する要素、**要素**または**属性**要素。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-110">Nevertheless, the XSD annotation syntax provides a convenient mechanism for storing flat file structure information within the XSD schema within a variety of different scopes, ranging from schema-wide information stored as annotations within the **schema** element, to information that is specific to a particular record or field, stored as annotations within the corresponding **element** or **attribute** element.</span></span>  
  
 <span data-ttu-id="4d0ab-111">フラット ファイル スキーマには、同等の XML スキーマには見られない独自の特性があります。それは、インスタンス メッセージと管理するスキーマを、内容に基づいて照合できないことです。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-111">Another characteristic of flat file schemas that make them different than their XML counterparts is the fact that instance messages cannot be matched to their governing schemas based on their content.</span></span> <span data-ttu-id="4d0ab-112">このため、静的なスキーマのセットを指定し、実行時にフラット ファイル逆アセンブラーが使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-112">Instead, a static set of schemas must be specified for use by the flat file disassembler at runtime.</span></span>  
  
 <span data-ttu-id="4d0ab-113">フラット ファイルの特性に関連付けられているその他のノード プロパティを表示するには指定する必要があります、**フラット ファイル拡張子**を使用して、**スキーマ エディター拡張機能**プロパティ、の**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-113">To see the additional node properties associated with the characteristics of flat files, you need to specify the **Flat File Extension** by using the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="4d0ab-114">これらのプロパティは、既定では表示されません。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-114">They do not appear by default.</span></span>  
  
 <span data-ttu-id="4d0ab-115">フラット ファイル スキーマに固有のノード プロパティの詳細については、次を参照してください。、**フラット ファイル スキーマの補足のノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4d0ab-115">For detailed information about the node properties that are specific to flat file schemas, see the **Supplemental Node Properties for Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d0ab-116">参照</span><span class="sxs-lookup"><span data-stu-id="4d0ab-116">See Also</span></span>  
 [<span data-ttu-id="4d0ab-117">BizTalk スキーマの種類</span><span class="sxs-lookup"><span data-stu-id="4d0ab-117">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)
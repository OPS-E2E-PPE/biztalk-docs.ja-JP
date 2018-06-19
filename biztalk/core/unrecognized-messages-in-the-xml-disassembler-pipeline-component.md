---
title: XML 逆アセンブラーで認識されないメッセージのパイプライン コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Allow Unrecognized Messages property
- XMLNorm.AllowUnrecognizedMessage property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], unrecognized messages
ms.assetid: 5a6be3a8-0bac-426a-bf0b-5091191091de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d82396002ff9d35484af5f0000dc3468c8ad37fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286746"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="be8de-102">XML 逆アセンブラー パイプライン コンポーネントで認識されないメッセージ</span><span class="sxs-lookup"><span data-stu-id="be8de-102">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="be8de-103">次のような場合、XML 逆アセンブラー コンポーネントで、メッセージが "認識されないメッセージ" として処理されます。</span><span class="sxs-lookup"><span data-stu-id="be8de-103">The XML Disassembler component may handle a message as "unrecognized" in the following cases:</span></span>  
  
-   <span data-ttu-id="be8de-104">受信した XML メッセージに本文が含まれていない、本文が空である、または、本文のデータが空である</span><span class="sxs-lookup"><span data-stu-id="be8de-104">An XML message is received with no body, an empty body, or empty data in the body.</span></span>  
  
-   <span data-ttu-id="be8de-105">XML メッセージを受信したが、そのメッセージに必要なスキーマが展開されていない</span><span class="sxs-lookup"><span data-stu-id="be8de-105">An XML message is received but no schema is deployed for it.</span></span>  
  
 <span data-ttu-id="be8de-106">に基づいて、認識されないメッセージが処理される、**認識されないメッセージを許可します**プロパティ (または、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキストのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="be8de-106">An unrecognized message is handled based on the **Allow Unrecognized Messages** property (or on the **XMLNorm.AllowUnrecognizedMessage** property on the message context).</span></span>  
  
 <span data-ttu-id="be8de-107">場合**認識されないメッセージを許可します**に設定されている**True**次のようにします。</span><span class="sxs-lookup"><span data-stu-id="be8de-107">If **Allow Unrecognized Messages** is set to **True**, the following occurs:</span></span>  
  
-   <span data-ttu-id="be8de-108">メッセージに本文が含まれていない、本文が空 (null) である、または本文のデータが空 (null) である場合、そのメッセージは変更されずに XML 逆アセンブラーを通過します。</span><span class="sxs-lookup"><span data-stu-id="be8de-108">A message with no body, an empty/null body, or with empty/null data in the body passes unchanged through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="be8de-109">XML ドキュメントに関連するスキーマが展開されていない場合、その XML ドキュメントは変更されずに XML 逆アセンブラーを通過します。</span><span class="sxs-lookup"><span data-stu-id="be8de-109">An XML document with no associated deployed schema passes unchanged through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="be8de-110">スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、XML ドキュメントのスキーマが展開されていた場合、その XML ドキュメントは XML 逆アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="be8de-110">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
 <span data-ttu-id="be8de-111">場合**認識されないメッセージを許可します**に設定されている**False**次のようにします。</span><span class="sxs-lookup"><span data-stu-id="be8de-111">If **Allow Unrecognized Messages** is set to **False**, the following occurs:</span></span>  
  
-   <span data-ttu-id="be8de-112">メッセージに本文が含まれていない、本文が空 (null) である、または本文のデータが空 (null) である場合、そのメッセージは XML 逆アセンブラーを通過できません。</span><span class="sxs-lookup"><span data-stu-id="be8de-112">A message with no body or an empty/null body or with empty/null data in the body is not passed through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="be8de-113">XML ドキュメントに関連するスキーマが展開されていない場合、その XML ドキュメントは XML 逆アセンブラーを通過できません。</span><span class="sxs-lookup"><span data-stu-id="be8de-113">An XML document that does not have a deployed schema associated with it is not passed through the disassembler.</span></span> <span data-ttu-id="be8de-114">エラーが報告され、可能な場合はメッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="be8de-114">An error is reported and the message is suspended, if possible.</span></span>  
  
-   <span data-ttu-id="be8de-115">スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、XML ドキュメントのスキーマが展開されていた場合、その XML ドキュメントは XML 逆アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="be8de-115">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
 <span data-ttu-id="be8de-116">既定では、XML 逆アセンブラーは、認識されないメッセージを許可しません。</span><span class="sxs-lookup"><span data-stu-id="be8de-116">By default, the XML Disassembler does not allow unrecognized messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be8de-117">XML 以外のメッセージに関係なく、XML 逆アセンブラーで処理されない、**認識されないメッセージを許可します**プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="be8de-117">Non-XML messages are not processed by the XML Disassembler regardless of the **Allow Unrecognized Messages** property setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be8de-118">参照</span><span class="sxs-lookup"><span data-stu-id="be8de-118">See Also</span></span>  
 <span data-ttu-id="be8de-119">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="be8de-119">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="be8de-120">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="be8de-120">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
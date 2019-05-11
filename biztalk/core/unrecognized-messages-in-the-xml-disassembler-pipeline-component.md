---
title: XML 逆アセンブラーで認識されないメッセージのパイプライン コンポーネント |Microsoft Docs
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
ms.openlocfilehash: c09d381a74b8f5083b600de73b72ac3c4d4da00d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400828"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="d18ed-102">XML 逆アセンブラー パイプライン コンポーネントで認識されないメッセージ</span><span class="sxs-lookup"><span data-stu-id="d18ed-102">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="d18ed-103">XML 逆アセンブラー コンポーネントは、次の場合に「認識されない」としてメッセージを処理可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d18ed-103">The XML Disassembler component may handle a message as "unrecognized" in the following cases:</span></span>  
  
- <span data-ttu-id="d18ed-104">XML メッセージには、本文のない、空の本文、または空の本文にデータを受け取りました。</span><span class="sxs-lookup"><span data-stu-id="d18ed-104">An XML message is received with no body, an empty body, or empty data in the body.</span></span>  
  
- <span data-ttu-id="d18ed-105">XML メッセージを受信したが、そのスキーマが展開されていません。</span><span class="sxs-lookup"><span data-stu-id="d18ed-105">An XML message is received but no schema is deployed for it.</span></span>  
  
  <span data-ttu-id="d18ed-106">に基づいて認識されないメッセージを処理、**認識されないメッセージを許可**プロパティ (または、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキストのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="d18ed-106">An unrecognized message is handled based on the **Allow Unrecognized Messages** property (or on the **XMLNorm.AllowUnrecognizedMessage** property on the message context).</span></span>  
  
  <span data-ttu-id="d18ed-107">場合**認識されないメッセージを許可**に設定されている**True**次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d18ed-107">If **Allow Unrecognized Messages** is set to **True**, the following occurs:</span></span>  
  
- <span data-ttu-id="d18ed-108">XML 逆アセンブラーでメッセージ本文のない、空や null 本文では、または本文のパスで空や null データが変更されていません。</span><span class="sxs-lookup"><span data-stu-id="d18ed-108">A message with no body, an empty/null body, or with empty/null data in the body passes unchanged through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="d18ed-109">展開されたスキーマが関連付けられていないパスを持つ XML ドキュメントでは、XML 逆アセンブラーで変更されていません。</span><span class="sxs-lookup"><span data-stu-id="d18ed-109">An XML document with no associated deployed schema passes unchanged through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="d18ed-110">関連付けられている展開済みスキーマを持つ XML ドキュメントは、スキーマが明示的にコンポーネントのプロパティで参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、XML 逆アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="d18ed-110">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
  <span data-ttu-id="d18ed-111">場合**認識されないメッセージを許可**に設定されている**False**次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d18ed-111">If **Allow Unrecognized Messages** is set to **False**, the following occurs:</span></span>  
  
- <span data-ttu-id="d18ed-112">メッセージ本文のないか、空や null 本体、または本文に空や null データは、XML 逆アセンブラーは渡されません。</span><span class="sxs-lookup"><span data-stu-id="d18ed-112">A message with no body or an empty/null body or with empty/null data in the body is not passed through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="d18ed-113">関連付けられている展開されたスキーマがない XML ドキュメントは、逆アセンブラーでは渡されません。</span><span class="sxs-lookup"><span data-stu-id="d18ed-113">An XML document that does not have a deployed schema associated with it is not passed through the disassembler.</span></span> <span data-ttu-id="d18ed-114">エラーが報告され、可能であれば、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="d18ed-114">An error is reported and the message is suspended, if possible.</span></span>  
  
- <span data-ttu-id="d18ed-115">関連付けられている展開済みスキーマを持つ XML ドキュメントは、スキーマが明示的にコンポーネントのプロパティで参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、XML 逆アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="d18ed-115">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
  <span data-ttu-id="d18ed-116">既定では、XML 逆アセンブラーは、認識されないメッセージを許可しません。</span><span class="sxs-lookup"><span data-stu-id="d18ed-116">By default, the XML Disassembler does not allow unrecognized messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d18ed-117">XML 以外のメッセージに関係なく、XML 逆アセンブラーによって処理されない、**認識されないメッセージを許可**プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="d18ed-117">Non-XML messages are not processed by the XML Disassembler regardless of the **Allow Unrecognized Messages** property setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d18ed-118">参照</span><span class="sxs-lookup"><span data-stu-id="d18ed-118">See Also</span></span>  
 <span data-ttu-id="d18ed-119">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d18ed-119">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="d18ed-120">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d18ed-120">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
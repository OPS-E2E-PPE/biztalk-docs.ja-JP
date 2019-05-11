---
title: XML 検証パイプライン コンポーネントを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Validator [pipeline component]
- send pipelines, validating
- pipeline components, XML Validator
- receive pipelines, validating
ms.assetid: 3b3becaf-703c-4399-a5ed-e7082e31e6e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89c136079a6283fe5e2eebd063718f97008029fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340223"
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a><span data-ttu-id="f2c07-102">XML 検証パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f2c07-102">How to Configure the XML Validator Pipeline Component</span></span>
<span data-ttu-id="f2c07-103">XML 検証パイプライン コンポーネントは、送信 (アセンブルとアセンブル) を除くいずれかの段階で使用できるまたは受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="f2c07-103">The XML Validator pipeline component can be used in any stage (except Disassemble or Assemble) in a send or receive pipeline.</span></span>  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a><span data-ttu-id="f2c07-104">XML 検証パイプライン コンポーネントのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="f2c07-104">To configure the properties for the XML Validator pipeline component</span></span>  
  
1.  <span data-ttu-id="f2c07-105">XML 検証パイプライン コンポーネントは、受信パイプラインの検証ステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f2c07-105">Drag the XML Validator pipeline component into the Validate stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="f2c07-106">[プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次を設定します。</span><span class="sxs-lookup"><span data-stu-id="f2c07-106">In the Properties window, in the **Pipeline Component Properties** section, set the following.</span></span>  
  
    |<span data-ttu-id="f2c07-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f2c07-107">Use this</span></span>|<span data-ttu-id="f2c07-108">目的</span><span class="sxs-lookup"><span data-stu-id="f2c07-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f2c07-109">**ドキュメント スキーマ**</span><span class="sxs-lookup"><span data-stu-id="f2c07-109">**Document schemas**</span></span>|<span data-ttu-id="f2c07-110">名前空間とスキーマまたはドキュメントに適用するスキーマの型名を示します。</span><span class="sxs-lookup"><span data-stu-id="f2c07-110">Indicates the namespace and typename of the schema or schemas to be applied to the document.</span></span> <span data-ttu-id="f2c07-111">詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)します。</span><span class="sxs-lookup"><span data-stu-id="f2c07-111">For more information, see [How to Use the Schema Collection Property Editor](../core/how-to-use-the-schema-collection-property-editor.md).</span></span> <span data-ttu-id="f2c07-112">スキーマが指定されていない場合、実行時にスキーマ検出は、メッセージのターゲットの名前空間とルート要素名の情報を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="f2c07-112">If no schemas are specified, the run-time schema discovery will be done by using the message's target namespace and root element name information.</span></span> <span data-ttu-id="f2c07-113">**注:** 2 つ以上のスキーマを指定する場合に、「2 つ以上の選択したスキーマは同じターゲット名前空間を共有」エラーが発生する可能性があります、**ドキュメント スキーマ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f2c07-113">**Note:**  You may receive a "Two or more of the selected schema share the same target namespace" error if you specify two or more schemas for the **Document schemas** property.</span></span> <br /><br /> <span data-ttu-id="f2c07-114">既定値:空のコレクション</span><span class="sxs-lookup"><span data-stu-id="f2c07-114">Default value: Empty collection</span></span>|  
    |<span data-ttu-id="f2c07-115">回復可能なインターチェンジ処理</span><span class="sxs-lookup"><span data-stu-id="f2c07-115">Recoverable Interchange Processing</span></span>|<span data-ttu-id="f2c07-116">"False"の場合は、(この場合、含まれるメッセージの失敗、インターチェンジ全体が中断されます)、ユニットとしてインターチェンジ全体を検証することを示します。</span><span class="sxs-lookup"><span data-stu-id="f2c07-116">When "false" - indicates that entire interchange is validated as a unit (if any contained message fails, entire interchange is suspended).</span></span><br /><br /> <span data-ttu-id="f2c07-117">"True"の場合は、インターチェンジ内のメッセージは個別に抽出される検証ツールによってメッセージの経路と中断されている他のユーザー メッセージやメッセージの可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="f2c07-117">When "true" - indicates that messages within interchange are extracted individually by validator with possibility of some propagating through messaging pathway and others being suspended.</span></span><br /><br /> <span data-ttu-id="f2c07-118">回復可能なインターチェンジ処理の詳細については、次を参照してください。[回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)します。</span><span class="sxs-lookup"><span data-stu-id="f2c07-118">For more information on recoverable interchange processing, see [Recoverable Interchange Processing](../core/recoverable-interchange-processing.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2c07-119">参照</span><span class="sxs-lookup"><span data-stu-id="f2c07-119">See Also</span></span>  
 <span data-ttu-id="f2c07-120">[XML 検証パイプライン コンポーネント](../core/xml-validator-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="f2c07-120">[XML Validator Pipeline Component](../core/xml-validator-pipeline-component.md) </span></span>  
 [<span data-ttu-id="f2c07-121">ネイティブ パイプライン コンポーネントの構成</span><span class="sxs-lookup"><span data-stu-id="f2c07-121">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)
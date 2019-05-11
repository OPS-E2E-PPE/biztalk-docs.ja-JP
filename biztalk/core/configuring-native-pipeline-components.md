---
title: ネイティブ パイプライン コンポーネントの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, pipeline components
- pipeline components, configuring
- Pipeline Designer, code sample
- IPersistPropertyBag interface
ms.assetid: a3332a60-8cd6-43fa-9ecf-e1e54e71fef7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9d60c963231f61684cc58187d40bc23141ff1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355299"
---
# <a name="configuring-native-pipeline-components"></a><span data-ttu-id="6ec63-102">ネイティブ パイプライン コンポーネントの構成</span><span class="sxs-lookup"><span data-stu-id="6ec63-102">Configuring Native Pipeline Components</span></span>
<span data-ttu-id="6ec63-103">パイプライン コンポーネントは、デザイン時に、独自のカスタム プロパティを公開することができます。</span><span class="sxs-lookup"><span data-stu-id="6ec63-103">Pipeline components can expose their own custom properties at design time.</span></span> <span data-ttu-id="6ec63-104">コンポーネントで定義されているパブリック プロパティは、読み取りし、書き込みのプロパティが実装されるアクセサーを提供するパイプライン デザイナーでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="6ec63-104">Any public property defined in the component will be rendered in Pipeline Designer providing that read and write accessors for that property are implemented.</span></span> <span data-ttu-id="6ec63-105">パイプライン デザイナーはそれらの宣言に従ってコンポーネントのプロパティを表示します。たとえば、プロパティは読み取り専用として宣言されている場合、それが表示されますようパイプライン デザイナーで。</span><span class="sxs-lookup"><span data-stu-id="6ec63-105">Pipeline Designer will display the component properties in accordance with their declaration; for example, if the property is declared as read-only, it will be displayed as such in Pipeline Designer.</span></span>  
  
 <span data-ttu-id="6ec63-106">カスタム パイプライン コンポーネントを実装する必要があります、 **IPersistPropertyBag**これらのカスタム プロパティの作成を有効にするインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6ec63-106">Custom pipeline components must implement the **IPersistPropertyBag** interface to enable the creation of these custom properties.</span></span> <span data-ttu-id="6ec63-107">プロパティで作成された、 **IPersistPropertyBag**インターフェイスは、Microsoft のプロパティ ウィンドウで設定できる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ネイティブ パイプライン コンポーネントのすべてのプロパティと同様、します。</span><span class="sxs-lookup"><span data-stu-id="6ec63-107">Properties created with the **IPersistPropertyBag** interface can be set in the Properties window of Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], just like all the properties of the native pipeline components.</span></span> <span data-ttu-id="6ec63-108">このセクションでは、各パイプラインが含まれるコンポーネントを構成するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="6ec63-108">This section contains procedures for configuring each of the included pipeline components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ec63-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ec63-109">In This Section</span></span>  
  
-   [<span data-ttu-id="6ec63-110">ネイティブ パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-110">How to Configure Native Pipeline Components</span></span>](../core/how-to-configure-native-pipeline-components.md)  
  
-   [<span data-ttu-id="6ec63-111">BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-111">How to Configure the BizTalk Framework Assembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-112">BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-112">How to Configure the BizTalk Framework Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-113">BizTalk Framework スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="6ec63-113">BizTalk Framework Schema and Properties</span></span>](../core/biztalk-framework-schema-and-properties.md)  
  
-   [<span data-ttu-id="6ec63-114">フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-114">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-115">フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-115">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-116">MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-116">How to Configure the MIME-SMIME Decoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-117">MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-117">How to Configure the MIME-SMIME Encoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-118">MIME-SMIME プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="6ec63-118">MIME-SMIME Property Schema and Properties</span></span>](../core/mime-smime-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="6ec63-119">パーティの解決パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-119">How to Configure the Party Resolution Pipeline Component</span></span>](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-120">XML アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-120">How to Configure the XML Assembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-121">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-121">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="6ec63-122">XML とフラット ファイル プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="6ec63-122">XML and Flat File Property Schema and Properties</span></span>](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="6ec63-123">XML 検証パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6ec63-123">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)
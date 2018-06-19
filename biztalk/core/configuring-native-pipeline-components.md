---
title: ネイティブ パイプライン コンポーネントの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 94475334395f8c360bbb636cfa9cbadcf3bf4fe3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233178"
---
# <a name="configuring-native-pipeline-components"></a><span data-ttu-id="a4f8d-102">ネイティブ パイプライン コンポーネントの構成</span><span class="sxs-lookup"><span data-stu-id="a4f8d-102">Configuring Native Pipeline Components</span></span>
<span data-ttu-id="a4f8d-103">パイプライン コンポーネントは、独自のカスタム プロパティをデザイン時に公開できます。</span><span class="sxs-lookup"><span data-stu-id="a4f8d-103">Pipeline components can expose their own custom properties at design time.</span></span> <span data-ttu-id="a4f8d-104">コンポーネントのパブリック プロパティに読み取りと書き込みのアクセサーが実装されていた場合、これらのすべてのプロパティがパイプライン デザイナーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4f8d-104">Any public property defined in the component will be rendered in Pipeline Designer providing that read and write accessors for that property are implemented.</span></span> <span data-ttu-id="a4f8d-105">パイプライン デザイナーは、対応する宣言に従ってコンポーネントのプロパティを表示します。たとえば、プロパティが読み取り専用として宣言されていた場合、パイプライン デザイナーでもそのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4f8d-105">Pipeline Designer will display the component properties in accordance with their declaration; for example, if the property is declared as read-only, it will be displayed as such in Pipeline Designer.</span></span>  
  
 <span data-ttu-id="a4f8d-106">カスタム パイプライン コンポーネントを実装する必要があります、 **IPersistPropertyBag**をこれらのカスタム プロパティの作成を有効にするインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a4f8d-106">Custom pipeline components must implement the **IPersistPropertyBag** interface to enable the creation of these custom properties.</span></span> <span data-ttu-id="a4f8d-107">作成されたプロパティ、 **IPersistPropertyBag**インターフェイスは、Microsoft のプロパティ ウィンドウで設定できます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ネイティブ パイプライン コンポーネントのすべてのプロパティと同様、します。</span><span class="sxs-lookup"><span data-stu-id="a4f8d-107">Properties created with the **IPersistPropertyBag** interface can be set in the Properties window of Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], just like all the properties of the native pipeline components.</span></span> <span data-ttu-id="a4f8d-108">このセクションでは、追加される各パイプライン コンポーネントを構成するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a4f8d-108">This section contains procedures for configuring each of the included pipeline components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4f8d-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a4f8d-109">In This Section</span></span>  
  
-   [<span data-ttu-id="a4f8d-110">ネイティブ パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-110">How to Configure Native Pipeline Components</span></span>](../core/how-to-configure-native-pipeline-components.md)  
  
-   [<span data-ttu-id="a4f8d-111">BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-111">How to Configure the BizTalk Framework Assembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-112">BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-112">How to Configure the BizTalk Framework Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-113">BizTalk Framework スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="a4f8d-113">BizTalk Framework Schema and Properties</span></span>](../core/biztalk-framework-schema-and-properties.md)  
  
-   [<span data-ttu-id="a4f8d-114">フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-114">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-115">フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-115">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-116">MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-116">How to Configure the MIME-SMIME Decoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-117">MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-117">How to Configure the MIME-SMIME Encoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-118">MIME/SMIME プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="a4f8d-118">MIME-SMIME Property Schema and Properties</span></span>](../core/mime-smime-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="a4f8d-119">パーティの解決パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-119">How to Configure the Party Resolution Pipeline Component</span></span>](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-120">XML アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-120">How to Configure the XML Assembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-121">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-121">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a4f8d-122">XML とフラット ファイル プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="a4f8d-122">XML and Flat File Property Schema and Properties</span></span>](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="a4f8d-123">XML 検証パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a4f8d-123">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)
---
title: "インライン XSLT および XSLT 呼び出しテンプレートを使用するスクリプト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3168417-3653-4c9e-a09c-184ffdc0ccb2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c4c1d8eff582d15f9ce022053b80f2dea2f856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a><span data-ttu-id="d765b-102">インライン XSLT および XSLT 呼び出しテンプレートを使用するスクリプト</span><span class="sxs-lookup"><span data-stu-id="d765b-102">Scripting Using Inline XSLT and XSLT Call Templates</span></span>
<span data-ttu-id="d765b-103">使用するための Extensible Stylesheet Language 変換 (XSLT) スタイル シートを直接書き込むことができます、**スクリプト**functoid です。</span><span class="sxs-lookup"><span data-stu-id="d765b-103">You can directly write Extensible Stylesheet Language Transformations (XSLT) stylesheets for use in the **Scripting** functoid.</span></span> <span data-ttu-id="d765b-104">これにより、変換を実行できます。ただし、リンクと組み込みの Functoid は、表現できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d765b-104">This enables you to perform transformations, that links and built-in functoids may not be able to represent.</span></span> <span data-ttu-id="d765b-105">XSLT スクリプトの 2 種類があります: インライン XSLT および XSLT 呼び出しテンプレート。</span><span class="sxs-lookup"><span data-stu-id="d765b-105">There are two kinds of XSLT scripts: inline XSLT and XSLT call templates.</span></span> <span data-ttu-id="d765b-106">いずれかを選択すると、**スクリプトの種類を選択して**ドロップダウン リストで、**スクリプト Functoid の構成**ダイアログ ボックスで、使用できる、サンプル コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d765b-106">When you select either in the **Select script type** dropdown in the **Configure Scripting Functoid** dialog box, sample code appears that you may use.</span></span>  
  
 <span data-ttu-id="d765b-107">インライン XSLT スクリプトおよびインライン XSLT 呼び出しテンプレートは、外部アセンブリの関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d765b-107">Inline XSLT scripts and inline XSLT call templates may call functions in external assemblies.</span></span> <span data-ttu-id="d765b-108">このような呼び出しを行うには、設定が必要です。、**カスタム拡張 XML**グリッドのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d765b-108">Making such calls requires setting the **Custom Extension XML** property of the grid.</span></span> <span data-ttu-id="d765b-109">詳細については、次を参照してください。**カスタム拡張 XML (グリッド プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d765b-109">For more information, see **Custom Extension XML (Grid Property)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="inline-xslt"></a><span data-ttu-id="d765b-110">インライン XSLT</span><span class="sxs-lookup"><span data-stu-id="d765b-110">Inline XSLT</span></span>  
 <span data-ttu-id="d765b-111">インライン XSLT スクリプトでは、出力を生成することのみが可能です。</span><span class="sxs-lookup"><span data-stu-id="d765b-111">An inline XSLT script may only produce output.</span></span> <span data-ttu-id="d765b-112">**スクリプト**functoid で、入力リンクがない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d765b-112">The **Scripting** functoid may not have any input links.</span></span> <span data-ttu-id="d765b-113">また、この Functoid は、送信先スキーマのレコードやフィールドに直接リンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d765b-113">The functoid must also directly link to a record or field in the destination schema.</span></span>  
  
 <span data-ttu-id="d765b-114">さらに、このスクリプトは、ターゲット ノードとそれに属する下部構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="d765b-114">In addition, the script is responsible for creating the target node and any structures underneath it.</span></span>  
  
 <span data-ttu-id="d765b-115">次の入力インスタンス メッセージには、連絡先に関する情報を示す 2 つの要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d765b-115">The following input instance message contains two elements representing contact information.</span></span>  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 <span data-ttu-id="d765b-116">スクリプト バッファーに入力された次のインライン XSLT スクリプトの変換、**連絡先**と**ContactType**フィールドの属性をします。</span><span class="sxs-lookup"><span data-stu-id="d765b-116">The following inline XSLT script, entered in the script buffer, converts the **Contact** and **ContactType** fields to attributes.</span></span>  
  
```  
<ContactInfo xmlns:p="http://SourceInstanceNamespace">  
     <xsl:variable name="var:var1" select="/p:SourceInstance/Address/ContactType" />  
     <xsl:attribute name="ContactType">  
          <xsl:value-of select="$var:var1" />  
     </xsl:attribute>  
     <xsl:variable name="var:var2" select="/p:SourceInstance/Address/Contact" />  
     <xsl:attribute name="Contact">  
          <xsl:value-of select="$var:var2" />  
     </xsl:attribute>  
</ContactInfo>  
```  
  
 <span data-ttu-id="d765b-117">このスクリプトは、前の入力インスタンス メッセージに対して実行される場合、出力スキーマが適切であると仮定して、次の出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="d765b-117">The script produces the following output, assuming an appropriate output schema, when run against the preceding input instance message.</span></span>  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 <span data-ttu-id="d765b-118">注意してへのリンクがない場合、**スクリプト**functoid は防止しません XSLT スクリプトの入力インスタンス メッセージからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="d765b-118">Notice that the absence of links to the **Scripting** functoid does not prevent the XSLT script from getting data from the input instance message.</span></span> <span data-ttu-id="d765b-119">このスクリプトでは、入力インスタンス値へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d765b-119">The script specifies paths to the input instance values.</span></span>  
  
 <span data-ttu-id="d765b-120">インライン XSLT スクリプトの別の例を参照してください。 [XML ツール (BizTalk Server Samples フォルダ)](../core/xml-tools-biztalk-server-samples-folder.md)です。</span><span class="sxs-lookup"><span data-stu-id="d765b-120">For another example of an inline XSLT script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="inline-xslt-call-templates"></a><span data-ttu-id="d765b-121">インライン XSLT 呼び出しテンプレート</span><span class="sxs-lookup"><span data-stu-id="d765b-121">Inline XSLT Call Templates</span></span>  
 <span data-ttu-id="d765b-122">インライン XSLT スクリプトのように、インライン XSLT 呼び出しテンプレートは、送信先ノードに直接接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d765b-122">Like an inline XSLT script, an inline XSLT call template must connect directly to a destination node.</span></span> <span data-ttu-id="d765b-123">ただし、インライン XSLT 呼び出しテンプレートでは、送信元スキーマおよび他の Functoid からのリンクを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d765b-123">However, an inline XSLT call template may use links from the source schema and from other functoids.</span></span>  
  
 <span data-ttu-id="d765b-124">呼び出しテンプレートは、送信先ノードおよびそのサブ構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="d765b-124">The call template is responsible for creating the destination node and any of its substructures.</span></span>  
  
 <span data-ttu-id="d765b-125">2 つの要素を連結するサンプルの XSLT 呼び出しテンプレートが表示されます、**スクリプトを入力**を選択すると、バッファー**インライン XSLT 呼び出しテンプレート**で、**スクリプトの種類を選択して**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="d765b-125">A sample XSLT call template that concatenates two elements appears in the **Input script** buffer when you select **Inline XSLT Call Template** in the **Select script type** dropdown.</span></span>  
  
 <span data-ttu-id="d765b-126">インライン XSLT 呼び出しテンプレートの別の例を参照してください。 [XML ツール (BizTalk Server Samples フォルダ)](../core/xml-tools-biztalk-server-samples-folder.md)です。</span><span class="sxs-lookup"><span data-stu-id="d765b-126">For another example of an inline XSLT call template, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d765b-127">参照</span><span class="sxs-lookup"><span data-stu-id="d765b-127">See Also</span></span>  
 <span data-ttu-id="d765b-128">[スクリプト Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="d765b-128">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="d765b-129">[外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="d765b-129">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="d765b-130">[インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="d765b-130">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="d765b-131">[スクリプト Functoid をマップに追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="d765b-131">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="d765b-132">スクリプト Functoid を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d765b-132">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)
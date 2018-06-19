---
title: BPEL4WS をインポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3626fcb9-8e7d-4812-a0c9-bde6e7954ec8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e82dd80e280eff39ff5c1678b5c9751e378ee1b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
ms.locfileid: "31008477"
---
# <a name="import-bpel4ws-in-biztalk-server"></a><span data-ttu-id="14fad-102">BizTalk Server での BPEL4WS をインポートします。</span><span class="sxs-lookup"><span data-stu-id="14fad-102">Import BPEL4WS in BizTalk Server</span></span>
<span data-ttu-id="14fad-103">既存の BPEL4WS をインポートすることによってオーケストレーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="14fad-103">You can import from existing BPEL4WS to create an orchestration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="14fad-104">このリリースの BizTalk Server では、BPEL4WS 1.1 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="14fad-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="14fad-105">BPEL4WS 1.0 をインポートまたはエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="14fad-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="14fad-106">BPEL4WS をインポートする方法の例は、次を参照してください。 [BPEL インポート (BizTalk Server サンプル)](../core/bpel-import-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="14fad-106">For an example of how to import BPEL4WS, see [BPEL Import (BizTalk Server Sample)](../core/bpel-import-biztalk-server-sample.md).</span></span>  
  
## <a name="import-bpel4ws-into-an-orchestration"></a><span data-ttu-id="14fad-107">オーケストレーションを BPEL4WS をインポート</span><span class="sxs-lookup"><span data-stu-id="14fad-107">Import BPEL4WS into an orchestration</span></span>  
  
1.  <span data-ttu-id="14fad-108">新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="14fad-108">Create a new project.</span></span>  
  
2.  <span data-ttu-id="14fad-109">BizTalk プロジェクトの種類から、[BizTalk Server BPEL インポート プロジェクト] をダブルクリックするか、[BizTalk Server BPEL インポート プロジェクト] を選択して [OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fad-109">From the BizTalk Project types, double-click BizTalk Server BPEL Import Project, or select BizTalk Server BPEL Import Project and press OK.</span></span>  
  
3.  <span data-ttu-id="14fad-110">ウィザードで、新しい BizTalk プロジェクトにインポートする BPEL ファイル、WSDL ファイル、および XSD ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="14fad-110">In the wizard, select the BPEL, WSDL and XSD files that should be imported to form the new BizTalk project.</span></span> <span data-ttu-id="14fad-111">import ステートメントと include ステートメントで参照するすべてのファイルを追加してください。</span><span class="sxs-lookup"><span data-stu-id="14fad-111">Include all files that are referenced via import and include statements.</span></span>  
  
4.  <span data-ttu-id="14fad-112">呼び出す Web サービスに対応した WSDL ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="14fad-112">Select WSDL files for invoked Web services.</span></span>  
  
     <span data-ttu-id="14fad-113">これで新しいオーケストレーションが作成されました。必要に応じて修正するか、そのまま展開できます。</span><span class="sxs-lookup"><span data-stu-id="14fad-113">You can now modify or deploy the new orchestration.</span></span>  
  
 <span data-ttu-id="14fad-114">**BPEL4WS のインポートに関する制限事項**</span><span class="sxs-lookup"><span data-stu-id="14fad-114">**Import restrictions on BPEL4WS**</span></span>  
  
-   <span data-ttu-id="14fad-115">BPEL および WSDL をインポートする際は、WSDL 定義ノードおよび BPEL プロセス ノードの Name プロパティが重複しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="14fad-115">When importing BPEL and WSDL, make sure that the Name property of the WSDL definition node and the BPEL process node do not match.</span></span>  
  
-   <span data-ttu-id="14fad-116">インポートする BPEL4WS に XLANG/s の予約語は使用できません。</span><span class="sxs-lookup"><span data-stu-id="14fad-116">Do not use XLANG/s reserved words in BPEL4WS that you import.</span></span> <span data-ttu-id="14fad-117">完全な一覧についてを参照してください。 [xlang/s の予約語](../core/xlang-s-reserved-words.md)です。</span><span class="sxs-lookup"><span data-stu-id="14fad-117">For a complete list, see [XLANG/s Reserved Words](../core/xlang-s-reserved-words.md).</span></span>  
  
-   <span data-ttu-id="14fad-118">XSD で定義された単純な型のみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="14fad-118">Only XSD predefined simple types are supported.</span></span>  
  
-   <span data-ttu-id="14fad-119">xsd:QName はサポートされません。System.String としてインポートされます。</span><span class="sxs-lookup"><span data-stu-id="14fad-119">xsd:QName is not supported; it is imported as System.String.</span></span> <span data-ttu-id="14fad-120">代わりに xsd:string を使用してください。</span><span class="sxs-lookup"><span data-stu-id="14fad-120">Use xsd:string instead.</span></span>  
  
-   <span data-ttu-id="14fad-121">BPEL4WS をインポートする際は、正規 (Canonical) XPaths を使用してください。</span><span class="sxs-lookup"><span data-stu-id="14fad-121">Consider using canonical XPaths when importing BPEL4WS.</span></span>  
  
     <span data-ttu-id="14fad-122">最適なパフォーマンスを得るため、正規 XPaths だけをインポートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14fad-122">It is good practice to import only canonical XPaths in order to achieve optimal performance.</span></span> <span data-ttu-id="14fad-123">'/\*[local-name()="someName" and namespace-uri()="someUri"]' のように、ルートを起点とする、昇格されたノードまでのパスを省略せずに記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14fad-123">The entire path from root to the promoted node must be spelled out by using '/\*[local-name()="someName" and namespace-uri()="someUri"]'.</span></span>  
  
     <span data-ttu-id="14fad-124">非正規 XPath をインポートする場合は、昇格を削除し、同じフィールドを再度昇格させることによって、正しい正規 XPath をスキーマ エディターに作成させることができます。</span><span class="sxs-lookup"><span data-stu-id="14fad-124">If you import a non-canonical XPath, you can remove a promotion and repromote the same field in order to have the Schema Editor create the correct canonical XPath.</span></span>  
  
     <span data-ttu-id="14fad-125">例: (targetNamespace = http://BizTalk_Server_Project3.Schema1)</span><span class="sxs-lookup"><span data-stu-id="14fad-125">Example: (targetNamespace = http://BizTalk_Server_Project3.Schema1)</span></span>  
  
    ```  
    <element name=Root type=complexType>  
                <sequence>  
                            <element name=promotedField/>  
                </sequence>  
    </element>  
    ```  
  
     `XPath - /*[local-name()='Root' and namespace-uri()='http://BizTalk_Server_Project3.Schema1']/\*[local-name()='promotedField' and namespace-uri()='']` 
  
    |<span data-ttu-id="14fad-126">正規 XPath</span><span class="sxs-lookup"><span data-stu-id="14fad-126">Canonical XPath</span></span>|<span data-ttu-id="14fad-127">非正規 XPath</span><span class="sxs-lookup"><span data-stu-id="14fad-127">Non-Canonical XPath</span></span>|  
    |---------------------|--------------------------|  
    |<span data-ttu-id="14fad-128">BizTalk エディターには、特別なアイコンが表示されます (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) フィールドを昇格されていることを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="14fad-128">BizTalk Editor displays a special icon (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) to denote that the field has been promoted.</span></span> <span data-ttu-id="14fad-129">正規 XPath 式を使用してフィールドを昇格させることにより、XML のトラバースを効率よく行うことができ、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="14fad-129">Usage of canonical XPath expressions to promote fields improves performance through more efficient traversal of the XML</span></span>|<span data-ttu-id="14fad-130">BizTalk エディターには、特殊なアイコンが表示されません。</span><span class="sxs-lookup"><span data-stu-id="14fad-130">BizTalk Editor does not display a special icon.</span></span> <span data-ttu-id="14fad-131">コンパイラおよび昇格ダイアログの両方で警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="14fad-131">Both the compiler and the promotion dialog give warnings.</span></span> <span data-ttu-id="14fad-132">メッセージ サイズが肥大化するなど、単純な影響が発生しますが、これはパフォーマンス上は無視できない影響です。</span><span class="sxs-lookup"><span data-stu-id="14fad-132">There is a linear but nontrivial effect on performance as the message size increases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14fad-133">参照</span><span class="sxs-lookup"><span data-stu-id="14fad-133">See Also</span></span>  
 <span data-ttu-id="14fad-134">[BPEL4WS にエクスポートする方法](../core/how-to-export-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="14fad-134">[How to Export BPEL4WS](../core/how-to-export-bpel4ws.md) </span></span>  
 [<span data-ttu-id="14fad-135">XLANG-s から BPEL4WS への種類の変換</span><span class="sxs-lookup"><span data-stu-id="14fad-135">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)

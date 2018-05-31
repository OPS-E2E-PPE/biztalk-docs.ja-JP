---
title: Namespace を追加する、ESB Namespace コンポーネントを削除および |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21df1b21-b73c-4e31-a234-49a1a6b53cc7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bcbe519cfd8c6796569da4de87f59fa6a16d8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296250"
---
# <a name="the-esb-add-namespace-and-remove-namespace-components"></a><span data-ttu-id="b6143-102">Namespace を追加する、ESB Namespace コンポーネントおよび削除</span><span class="sxs-lookup"><span data-stu-id="b6143-102">The ESB Add Namespace and Remove Namespace Components</span></span>
<span data-ttu-id="b6143-103">多くの企業早期導入の XML テクノロジの時点であったとき基準がまだに新たなドキュメントの共有なしで共通です。</span><span class="sxs-lookup"><span data-stu-id="b6143-103">Many companies were early adopters of XML technologies at the time when standards were still emerging and document sharing was uncommon.</span></span> <span data-ttu-id="b6143-104">したがってが厳密に実行しなかったこれは、通常、ケース今日、一意のルート名前空間を含めるための要件です。</span><span class="sxs-lookup"><span data-stu-id="b6143-104">Therefore, they did not strictly enforce the requirements for including unique root namespaces, which is usually the case today.</span></span>  
  
 <span data-ttu-id="b6143-105">ただし、Microsoft BizTalk Server には、ドキュメント ルート ノードの名前空間がないに対し肯定的な場合は、いくつかを識別するが困難なので、ルート ノードの名前空間とルート ノード名の組み合わせに基づいてドキュメントの識別を実行します別のドキュメント。種類は、同じルート ノードの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6143-105">However, Microsoft BizTalk Server performs document identification based on a combination of the root node namespace and the root node name, so documents that have no namespace for the root node are difficult to positively identify if several different document types use the same root node name.</span></span>  
  
 <span data-ttu-id="b6143-106">Namespace の追加と削除 Namespace コンポーネントでは、この問題を解決するために受信したときに、ドキュメントに名前空間を追加して、配信される前に、ドキュメントから名前空間を削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b6143-106">The Add Namespace and Remove Namespace components solve this problem by making it possible to add namespaces to documents when they are received and to remove the namespace from the documents before they are delivered.</span></span> <span data-ttu-id="b6143-107">ドキュメントできるため、既定の名前空間 (または複数の異なるドキュメントの種類に共通の名前空間) に、ESB と BizTalk 内での処理中に一時的な一意のルート名前空間に存在するが、する場合の送信し受信します。</span><span class="sxs-lookup"><span data-stu-id="b6143-107">Therefore, documents can reside in the default namespace (or in a namespace common to several different document types) when they are sent and received but reside in a transient unique root namespace during processing within the ESB and BizTalk.</span></span>  
  
 <span data-ttu-id="b6143-108">コンポーネントは、XML スキーマ定義ではなくドキュメント型定義 (DTD) を使用するか、ルート名前空間を含むドキュメントを作成できない従来の XML パーサーを使用するレガシ システムを統合している場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6143-108">The components are also useful when integrating legacy systems that use a Document Type Definition (DTD) instead of an XML Schema definition or that use legacy XML parsers that cannot create documents that contain a root namespace.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="b6143-109">インストール</span><span class="sxs-lookup"><span data-stu-id="b6143-109">Installation</span></span>  
 <span data-ttu-id="b6143-110">ESB コアを自動的にインストールするとインストール、**追加 Namespace**と**削除 Namespace** BizTalk Server パイプライン コンポーネント フォルダー内のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="b6143-110">Installing the ESB Core automatically installs the **Add Namespace** and **Remove Namespace** components in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="b6143-111">しくみ</span><span class="sxs-lookup"><span data-stu-id="b6143-111">How It Works</span></span>  
 <span data-ttu-id="b6143-112">Namespace の追加コンポーネントは、XML ドキュメントに指定された名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="b6143-112">The Add Namespace component adds a specified namespace to an XML document.</span></span> <span data-ttu-id="b6143-113">コンポーネントは、ドキュメントを単一の名前空間のみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b6143-113">The component can add only a single namespace to a document.</span></span> <span data-ttu-id="b6143-114">ルート ノードの名前空間が既にいる文書で Namespace の追加コンポーネントを使用してはいないシナリオはサポート 1 つの一意の名前空間が必要なものであるためです。</span><span class="sxs-lookup"><span data-stu-id="b6143-114">Using the Add Namespace component on a document that already has a root node namespace is not a supported scenario because a single unique namespace is all that is required.</span></span>  
  
 <span data-ttu-id="b6143-115">コンポーネントは、名前空間に対応していないし、名前空間の値のいずれかの保持されません。</span><span class="sxs-lookup"><span data-stu-id="b6143-115">The components are not namespace-aware and do not persist any of the namespace values.</span></span> <span data-ttu-id="b6143-116">ただし、追加の Namespace コンポーネントは、メッセージの既存の名前空間内の要求された名前空間を比較し、パイプラインに一致する場合、元のメッセージを単純に返します。</span><span class="sxs-lookup"><span data-stu-id="b6143-116">However, the Add Namespace component compares the requested namespace in the existing namespace of the message and simply returns the original message to the pipeline if they match.</span></span>  
  
 <span data-ttu-id="b6143-117">開発者は、受信パイプラインまたは送信パイプラインに追加の Namespace コンポーネントを含めるし、適切なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b6143-117">Developers include the Add Namespace component in a receive pipeline or a send pipeline and set the appropriate properties.</span></span> <span data-ttu-id="b6143-118">次の検証は実行時に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b6143-118">The following validation is performed at run time:</span></span>  
  
-   <span data-ttu-id="b6143-119">**Xpath**プロパティまたは**NamespaceBase**プロパティ値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6143-119">The **XPaths** property or the **NamespaceBase** property must contain a value.</span></span>  
  
-   <span data-ttu-id="b6143-120">**区切り**プロパティが有効な文字だけを含めることができます (など **/** または **\\** ) または空の文字列。</span><span class="sxs-lookup"><span data-stu-id="b6143-120">The **Separator** property can contain only valid characters (such as **/** or **\\**) or an empty string.</span></span>  
  
-   <span data-ttu-id="b6143-121">**NamespacePrefix**プロパティの値は予約済みの値のいずれかにすることはできません (**ns0**に**ns6**) と英数字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6143-121">The **NamespacePrefix** property value cannot be one of the reserved values (**ns0** to **ns6**) and must be alpha numeric.</span></span>  
  
 <span data-ttu-id="b6143-122">これらの規則からのすべてのバリエーションにより、メッセージを中断、実行時に例外がスローするコンポーネント (としてマークされている **– 中断された再開可能な**)、Windows アプリケーション イベント ログ エントリの書き込みとします。</span><span class="sxs-lookup"><span data-stu-id="b6143-122">Any variation from these rules causes the component to throw an exception at run time, suspend the message (marked as **Suspended – Resumable**), and write an entry in Windows Application Event Log.</span></span>  
  
 <span data-ttu-id="b6143-123">削除 Namespace コンポーネントは、XML ドキュメントからすべてのルート名前空間を削除します。</span><span class="sxs-lookup"><span data-stu-id="b6143-123">The Remove Namespace component removes all root namespaces from an XML document.</span></span> <span data-ttu-id="b6143-124">コンポーネントが 1 つのドキュメントから削除できる名前空間の数は、処理中に、現在のノードを保持するために使用できる物理メモリによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="b6143-124">The number of namespaces that the component can remove from a single document is constrained by the physical memory available to hold the current node during processing.</span></span> <span data-ttu-id="b6143-125">ただし、コンポーネントは、プロセスをストリーミング標準の BizTalk Server 2009 パイプラインのメッセージを使用し、ドキュメント内の現在のノードだけをドキュメント全体を読み込む代わりに、メモリに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b6143-125">However, the component uses standard BizTalk Server 2009 pipeline message streaming processes and loads only the current node in the document into memory instead of loading the entire document.</span></span>  
  
 <span data-ttu-id="b6143-126">削除 Namespace コンポーネントもの再エンコードを指定したエンコーディングのドキュメント (**ascii、unicode/utf16**または**utf8**) され場合に、ストリームの先頭からバイト オーダー マーク (BOM) を削除できます必須。</span><span class="sxs-lookup"><span data-stu-id="b6143-126">The Remove Namespace component also re-encodes the document to the specified encoding (**ascii, unicode/utf16,** or **utf8**) and can remove the Byte Order Mark (BOM) from the beginning of the stream, if required.</span></span>  
  
## <a name="using-the-add-namespace-and-remove-namespace-components"></a><span data-ttu-id="b6143-127">使用して、追加 Namespace Namespace コンポーネントおよび削除</span><span class="sxs-lookup"><span data-stu-id="b6143-127">Using the Add Namespace and Remove Namespace Components</span></span>  
 <span data-ttu-id="b6143-128">開発者は、次の状況のいずれかの追加 Namespace コンポーネントを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6143-128">Developers might use the Add Namespace component in any of the following circumstances:</span></span>  
  
-   <span data-ttu-id="b6143-129">受信メッセージには、ルート名前空間がありません。</span><span class="sxs-lookup"><span data-stu-id="b6143-129">The inbound message has no root namespace.</span></span>  
  
-   <span data-ttu-id="b6143-130">受信メッセージは、メッセージ型を記述するのに要素のデータまたは属性のデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6143-130">The inbound message uses element data or attribute data to describe the message type.</span></span>  
  
-   <span data-ttu-id="b6143-131">メッセージ型を記述するデータは、一貫性のあるおよび XPath クエリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6143-131">The data describing the message type is consistent and available using XPath queries.</span></span>  
  
 <span data-ttu-id="b6143-132">Namespace の追加と削除 Namespace コンポーネントは、受信パイプラインまたは送信パイプラインのいずれかの段階に配置できます。</span><span class="sxs-lookup"><span data-stu-id="b6143-132">The Add Namespace and Remove Namespace components can reside in any stage of a receive pipeline or a send pipeline.</span></span> <span data-ttu-id="b6143-133">必要な場合、このようなドキュメントのルート名前空間を変更する、追加の Namespace コンポーネント続けて削除 Namespace コンポーネントを使用している場合、コンポーネントのインスタンスを連結することができます。</span><span class="sxs-lookup"><span data-stu-id="b6143-133">You can chain instances of the component if required, such as if you are using the Remove Namespace component followed by the Add Namespace component to change the root namespace of a document.</span></span>  
  
 <span data-ttu-id="b6143-134">複数の受信場所のこれらのコンポーネントを使用する必要がある場合は場合、は、1 つのパイプラインを作成して、BizTalk Server を使用して、送信の各インスタンスのコンポーネント プロパティを設定したり、受信パイプラインのコンポーネントの構成"インスタンス"ごとです。</span><span class="sxs-lookup"><span data-stu-id="b6143-134">If you have multiple receive locations that require the use of these components, you can create a single pipeline and use the BizTalk Server "per instance" component configuration to set the component properties for each instance of the send or receive pipeline.</span></span> <span data-ttu-id="b6143-135">BizTalk Server 2009 を使用して、プロパティを設定するパイプラインのインスタンスごとに、複数、1 つのパイプラインを再利用できることを意味する受信場所、おそらくインスタンスごとに別のコンポーネント プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b6143-135">Using BizTalk Server 2009, you can set properties on a per-instance basis for pipelines, which means that you can reuse a single pipeline across multiple receive locations and perhaps have different component properties for each instance.</span></span> <span data-ttu-id="b6143-136">これは、コードまたは再配置を変更することがなく、BizTalk Server 管理コンソールを使用して変更を行う管理者を許可する実行時の設定です。</span><span class="sxs-lookup"><span data-stu-id="b6143-136">This is a run-time setting that allows administrators to make the change using the BizTalk Server Administration Console without requiring changes to the code or redeployment.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="b6143-137">コンポーネント プロパティ</span><span class="sxs-lookup"><span data-stu-id="b6143-137">Component Properties</span></span>  
 <span data-ttu-id="b6143-138">Namespace の追加コンポーネントは、5 つのパブリック プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="b6143-138">The Add Namespace component exposes five public properties:</span></span>  
  
-   <span data-ttu-id="b6143-139">**NamespacePrefix**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-139">**NamespacePrefix**.</span></span> <span data-ttu-id="b6143-140">これは、間に挿入される、名前空間のプレフィックス、 **xmlns:** 部分と、次の等号 (=) に署名します。</span><span class="sxs-lookup"><span data-stu-id="b6143-140">This is the prefix of the namespace, inserted between the **xmlns:** part and the following equals sign ( = ).</span></span> <span data-ttu-id="b6143-141">標準の BizTalk スキーマ名前空間プレフィックスとの競合を避けるためには、値は使用しないでください**ns0**を通じて**ns9**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-141">To avoid conflicts with standard BizTalk Schema namespace prefixes, avoid using the values **ns0** through **ns9**.</span></span>  
  
-   <span data-ttu-id="b6143-142">**NamespaceBase**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-142">**NamespaceBase**.</span></span> <span data-ttu-id="b6143-143">これは、名前空間内の値によって生成される結果をプレフィックスの静的なセクション、**区切り**と**Xpath**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b6143-143">This is the static section of the namespace that will prefix the result generated by the values in the **Separator** and **XPaths** properties.</span></span>  
  
-   <span data-ttu-id="b6143-144">**ExtractionNodeXPath**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-144">**ExtractionNodeXPath**.</span></span> <span data-ttu-id="b6143-145">これは、生成された名前空間の部分に使用する要素または属性の値を含むドキュメント内の単一要素に解決される XPath ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="b6143-145">This is an XPath statement that resolves to a single element in the document that contains the element or attribute values you want to use for the generated parts of the namespace.</span></span>  
  
-   <span data-ttu-id="b6143-146">**Xpath**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-146">**XPaths**.</span></span> <span data-ttu-id="b6143-147">これは、パイプ (**&#124;** ) が、名前空間を形成する結合されたコンポーネントのそれぞれを抽出するために使用する XPath クエリの区切られた一覧です。</span><span class="sxs-lookup"><span data-stu-id="b6143-147">This is a pipe (**&#124;** ) delimited list of XPath queries used to extract each of the components that will combine to form the namespace.</span></span>  
  
-   <span data-ttu-id="b6143-148">**区切り記号**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-148">**Separator**.</span></span> <span data-ttu-id="b6143-149">これは、セグメントの名前空間の間で使用する区切り記号です。</span><span class="sxs-lookup"><span data-stu-id="b6143-149">This is the separator to use between the namespace segments.</span></span> <span data-ttu-id="b6143-150">最も一般的な値はスラッシュ ( **/**  ) が必要な場合、空の文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6143-150">The most common value is a forward slash (**/** ), but it can be an empty string, if required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6143-151">要素と属性名など、すべての XML ノードは、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="b6143-151">All XML nodes, such as element and attribute names, are case sensitive.</span></span>  
  
 <span data-ttu-id="b6143-152">削除 Namespace コンポーネントは、2 つのパブリック プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="b6143-152">The Remove Namespace component exposes two public properties:</span></span>  
  
-   <span data-ttu-id="b6143-153">**エンコード**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-153">**Encoding**.</span></span> <span data-ttu-id="b6143-154">これは、次の値のいずれかの出力メッセージのエンコーディング: **ascii、unicode/utf16**または**utf8**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-154">This is the encoding for the output message, one of the following values: **ascii, unicode/utf16,** or **utf8**.</span></span>  
  
-   <span data-ttu-id="b6143-155">**RemoveByteOrderMark**です。</span><span class="sxs-lookup"><span data-stu-id="b6143-155">**RemoveByteOrderMark**.</span></span> <span data-ttu-id="b6143-156">これは、コンポーネントがバイト順マークを削除するかどうかを示すブール型プロパティ (通常**0xEFBB、0xBFFFFE、** または**0 xfeff**)、XML ドキュメント ストリームの先頭からです。</span><span class="sxs-lookup"><span data-stu-id="b6143-156">This is a Boolean property that indicates whether the component should remove the byte order mark (usually **0xEFBB, 0xBFFFFE,** or **0xFEFF**) from the beginning of the XML document stream.</span></span>  
  
 <span data-ttu-id="b6143-157">これらのコンポーネントを使用する方法の例は、次を参照してください。[をインストールすると、Namespace コンポーネント サンプルを実行している](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6143-157">For an example of how to use these components, see [Installing and Running the Namespace Component Sample](../esb-toolkit/installing-and-running-the-namespace-component-sample.md).</span></span>
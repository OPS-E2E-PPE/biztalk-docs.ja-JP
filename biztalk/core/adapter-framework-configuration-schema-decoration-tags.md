---
title: "アダプター フレームワーク構成スキーマの装飾タグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d5d7f6b-2273-45a6-ba9d-43201760cf22
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b834482b70e75d12bb6786dac2a5d9eb6f9fef40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a><span data-ttu-id="4b612-102">アダプター フレームワーク構成スキーマの装飾タグ</span><span class="sxs-lookup"><span data-stu-id="4b612-102">Adapter Framework Configuration Schema Decoration Tags</span></span>
<span data-ttu-id="4b612-103">このトピックで説明するタグを構成スキーマ ファイル内で使用して、アダプターのプロパティ ページでデータを表示および編成できます。</span><span class="sxs-lookup"><span data-stu-id="4b612-103">You can use the tags described in this topic within the configuration schema files to display and organize data on the adapter property pages.</span></span>  
  
 <span data-ttu-id="4b612-104">次の図は、FTP 受信場所のプロパティ ページでこれらのタグの一部を実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b612-104">The following figure shows how the FTP receive location property page implements some of these tags.</span></span>  
  
 ![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")  
<span data-ttu-id="4b612-105">\<説明 >、 \<displayname >、および\<カテゴリ > タグで FTP アダプターのプロパティ ページ</span><span class="sxs-lookup"><span data-stu-id="4b612-105">The \<description>, \<displayname>, and \<category> tags in the FTP adapter property page</span></span>  
  
## <a name="designer"></a><span data-ttu-id="4b612-106">\<デザイナー ></span><span class="sxs-lookup"><span data-stu-id="4b612-106">\<designer></span></span>  
 <span data-ttu-id="4b612-107">BizTalk アダプター フレームワークの装飾の間に表示、 \<baf:designer > タグと\</baf:designer > 終了タグ。</span><span class="sxs-lookup"><span data-stu-id="4b612-107">The BizTalk Adapter Framework decorations appear between a \<baf:designer> tag and \</baf:designer> end tag.</span></span> <span data-ttu-id="4b612-108">\<Baf:designer > タグでは、アダプター フレームワークを区別するのに役立ちます\<appinfo > とその他のアダプター指定\<appinfo > 情報。</span><span class="sxs-lookup"><span data-stu-id="4b612-108">The \<baf:designer> tag helps distinguish between Adapter Framework \<appinfo> and other adapter-supplied \<appinfo> information.</span></span>  
  
## <a name="category"></a><span data-ttu-id="4b612-109">\<カテゴリ ></span><span class="sxs-lookup"><span data-stu-id="4b612-109">\<category></span></span>  
 <span data-ttu-id="4b612-110">\<Category > 装飾には、グループに、プロパティ グリッド内のエントリを区切るために使用する文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b612-110">The \<category> decoration contains the string used to separate entries in the property grid into groups.</span></span> <span data-ttu-id="4b612-111">装飾には、カテゴリの下位エントリと同じカテゴリ文字列を使用するすべてのエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b612-111">The decoration displays all entries with the same category string as subordinate entries of the category.</span></span>  
  
 <span data-ttu-id="4b612-112">ローカライズできる\<category > エントリです。</span><span class="sxs-lookup"><span data-stu-id="4b612-112">You can localize \<category> entries.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4b612-113">\<説明 ></span><span class="sxs-lookup"><span data-stu-id="4b612-113">\<description></span></span>  
 <span data-ttu-id="4b612-114">\<説明 > 装飾には、プロパティ グリッドの下部にあるエントリの説明のテキストを提供するために使用する文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b612-114">The \<description> decoration contains the string used to provide descriptive text for entries at the bottom of the property grid.</span></span>  
  
 <span data-ttu-id="4b612-115">ローカライズできる\<説明 > エントリです。</span><span class="sxs-lookup"><span data-stu-id="4b612-115">You can localize \<description> entries.</span></span>  
  
## <a name="displayname"></a><span data-ttu-id="4b612-116">\<displayname ></span><span class="sxs-lookup"><span data-stu-id="4b612-116">\<displayname></span></span>  
 <span data-ttu-id="4b612-117">\<Displayname > 装飾には、エントリの名前を表示するための文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b612-117">The \<displayname> decoration contains the string used for displaying the name of an entry.</span></span> <span data-ttu-id="4b612-118">これにより、それらは許可されていないときに、スペース、句、およびを使用する、\<要素 > または\<属性 > の名前。</span><span class="sxs-lookup"><span data-stu-id="4b612-118">This enables you to use spaces, phrases, and so on, when they would not be allowed for an \<element> or \<attribute> name.</span></span>  
  
 <span data-ttu-id="4b612-119">ローカライズできる\<displayname > エントリです。</span><span class="sxs-lookup"><span data-stu-id="4b612-119">You can localize \<displayname> entries.</span></span>  
  
## <a name="readonly"></a><span data-ttu-id="4b612-120">\<読み取り専用 ></span><span class="sxs-lookup"><span data-stu-id="4b612-120">\<readonly></span></span>  
 <span data-ttu-id="4b612-121">\<固定 readonly =""> 装飾は、フィールドを変更することがあるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="4b612-121">The \<readonly fixed=""> decoration controls whether a field may be edited.</span></span> <span data-ttu-id="4b612-122">"fixed" 属性値が `true` (既定値) の場合、フィールドは読み取り専用になります。</span><span class="sxs-lookup"><span data-stu-id="4b612-122">A "fixed" attribute value of `true` (the default) makes a field read-only.</span></span>  
  
 <span data-ttu-id="4b612-123">外部エディターを実装する場合は、外部を実装する**TypeConverter**クラスし、オーバーライド、 **GetStandardValuesExclusive(ITypeDescriptorContext)**メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="4b612-123">When implementing an external editor, implement an external **TypeConverter** class and override the **GetStandardValuesExclusive(ITypeDescriptorContext)** method instead.</span></span> <span data-ttu-id="4b612-124">`true` を返すと、フィールドは読み取り専用になりますが、カスタム エディターへのアクセスは保持されます。</span><span class="sxs-lookup"><span data-stu-id="4b612-124">Returning `true` makes a field read-only but preserves access to the custom editor.</span></span>  
  
## <a name="browsable"></a><span data-ttu-id="4b612-125">\<ブラウズ ></span><span class="sxs-lookup"><span data-stu-id="4b612-125">\<browsable></span></span>  
 <span data-ttu-id="4b612-126">\<ブラウズ show =""> 装飾は、プロパティ グリッドでフィールドを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="4b612-126">The \<browsable show=""> decoration controls whether a field appears in the property grid.</span></span> <span data-ttu-id="4b612-127">"show" 属性値が `True` (既定値) の場合、フィールドはグリッドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b612-127">A "show" attribute value of `True` (the default) makes a field appear in the grid.</span></span>  
  
## <a name="converter"></a><span data-ttu-id="4b612-128">\<コンバーター ></span><span class="sxs-lookup"><span data-stu-id="4b612-128">\<converter></span></span>  
 <span data-ttu-id="4b612-129">\<コンバーター アセンブリ =""> 装飾は、必要な指定**TypeConverter**のクラス名、\<要素 > または\<属性 >。</span><span class="sxs-lookup"><span data-stu-id="4b612-129">The \<converter assembly=""> decoration specifies the desired **TypeConverter** class name for the \<element> or \<attribute>.</span></span> <span data-ttu-id="4b612-130">省略可能な"assembly"属性値を含む、必要なアセンブリへのパスを指定する**TypeConverter**です。</span><span class="sxs-lookup"><span data-stu-id="4b612-130">The optional "assembly" attribute value specifies the path to the assembly containing the desired **TypeConverter**.</span></span> <span data-ttu-id="4b612-131">"assembly" 値が指定されていない場合、クラス名には、グローバル アセンブリ キャッシュのアセンブリ名、キー、カルチャ、およびバージョンの値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b612-131">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="editor"></a><span data-ttu-id="4b612-132">\<エディター ></span><span class="sxs-lookup"><span data-stu-id="4b612-132">\<editor></span></span>  
 <span data-ttu-id="4b612-133">\<エディターのアセンブリ =""> 装飾は、必要な指定**UITypeEditor**のクラス名、\<要素 > または\<属性 >。</span><span class="sxs-lookup"><span data-stu-id="4b612-133">The \<editor assembly=""> decoration specifies the desired **UITypeEditor** class name for the \<element> or \<attribute>.</span></span> <span data-ttu-id="4b612-134">省略可能な"assembly"属性値を含む、必要なアセンブリへのパスを指定する**UITypeEditor**です。</span><span class="sxs-lookup"><span data-stu-id="4b612-134">The optional "assembly" attribute value specifies the path to the assembly containing the desired **UITypeEditor**.</span></span> <span data-ttu-id="4b612-135">"assembly" 値が指定されていない場合、クラス名には、グローバル アセンブリ キャッシュのアセンブリ名、キー、カルチャ、およびバージョンの値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b612-135">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="null-values-for-optional-enumerations"></a><span data-ttu-id="4b612-136">省略可能な列挙の Null 値</span><span class="sxs-lookup"><span data-stu-id="4b612-136">Null Values for Optional Enumerations</span></span>  
 <span data-ttu-id="4b612-137">省略可能な列挙体を使用する場合、値の 1 つがあります\<なし > を null 値を示すためにします。</span><span class="sxs-lookup"><span data-stu-id="4b612-137">When using an optional enumeration, one of the values should be \<none> to denote a null value.</span></span> <span data-ttu-id="4b612-138">これは組み込みのタグではありませんが、列挙が xsd:string から派生している場合は、none として処理される列挙値を指定して実現できます。</span><span class="sxs-lookup"><span data-stu-id="4b612-138">This is not a built-in tag, but may be achieved by providing an enumeration value that is treated as none if the enumeration is derived from xsd:string.</span></span> <span data-ttu-id="4b612-139">xsd:int から派生している列挙の場合、整数が値を保持する必要があるため無効です。</span><span class="sxs-lookup"><span data-stu-id="4b612-139">This is not possible for enumerations derived from xsd:int, because the integer must hold a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b612-140">参照</span><span class="sxs-lookup"><span data-stu-id="4b612-140">See Also</span></span>  
 [<span data-ttu-id="4b612-141">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="4b612-141">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)
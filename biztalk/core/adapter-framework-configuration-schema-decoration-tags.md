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
ms.openlocfilehash: d49aac9f11ef48bd0a66dcc9bda3a769cd6c34f4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a><span data-ttu-id="4b9bf-102">アダプター フレームワーク構成スキーマの装飾タグ</span><span class="sxs-lookup"><span data-stu-id="4b9bf-102">Adapter Framework Configuration Schema Decoration Tags</span></span>
<span data-ttu-id="4b9bf-103">このトピックで説明するタグを構成スキーマ ファイル内で使用して、アダプターのプロパティ ページでデータを表示および編成できます。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-103">You can use the tags described in this topic within the configuration schema files to display and organize data on the adapter property pages.</span></span>  
  
 <span data-ttu-id="4b9bf-104">次の図は、FTP 受信場所のプロパティ ページでこれらのタグの一部を実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-104">The following figure shows how the FTP receive location property page implements some of these tags.</span></span>  
  
 <span data-ttu-id="4b9bf-105">![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")</span><span class="sxs-lookup"><span data-stu-id="4b9bf-105">![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")</span></span>  
<span data-ttu-id="4b9bf-106">\<説明\>、 \<displayname\>、および\<カテゴリ\>FTP アダプター プロパティ ページ内のタグ</span><span class="sxs-lookup"><span data-stu-id="4b9bf-106">The \<description\>, \<displayname\>, and \<category\> tags in the FTP adapter property page</span></span>  
  
## <a name="designer"></a><span data-ttu-id="4b9bf-107">\<デザイナー\></span><span class="sxs-lookup"><span data-stu-id="4b9bf-107">\<designer\></span></span>  
 <span data-ttu-id="4b9bf-108">BizTalk アダプター フレームワークの装飾の間に表示、 \<baf:designer\>タグと\</baf:designer\>タグを終了します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-108">The BizTalk Adapter Framework decorations appear between a \<baf:designer\> tag and \</baf:designer\> end tag.</span></span> <span data-ttu-id="4b9bf-109">\<Baf:designer\>タグでは、アダプター フレームワークを区別するのに役立ちます\<appinfo\>し、その他のアダプター指定\<appinfo\>情報。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-109">The \<baf:designer\> tag helps distinguish between Adapter Framework \<appinfo\> and other adapter-supplied \<appinfo\> information.</span></span>  
  
## <a name="category"></a><span data-ttu-id="4b9bf-110">\<カテゴリ\></span><span class="sxs-lookup"><span data-stu-id="4b9bf-110">\<category\></span></span>  
 <span data-ttu-id="4b9bf-111">\<カテゴリ\>装飾には、グループに、プロパティ グリッド内のエントリを区切るために使用する文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-111">The \<category\> decoration contains the string used to separate entries in the property grid into groups.</span></span> <span data-ttu-id="4b9bf-112">装飾には、カテゴリの下位エントリと同じカテゴリ文字列を使用するすべてのエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-112">The decoration displays all entries with the same category string as subordinate entries of the category.</span></span>  
  
 <span data-ttu-id="4b9bf-113">ローカライズできる\<カテゴリ\>エントリです。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-113">You can localize \<category\> entries.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4b9bf-114">\<説明\></span><span class="sxs-lookup"><span data-stu-id="4b9bf-114">\<description\></span></span>  
 <span data-ttu-id="4b9bf-115">\<説明\>装飾には、プロパティ グリッドの下部にあるエントリの説明のテキストを提供するために使用する文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-115">The \<description\> decoration contains the string used to provide descriptive text for entries at the bottom of the property grid.</span></span>  
  
 <span data-ttu-id="4b9bf-116">ローカライズできる\<説明\>エントリです。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-116">You can localize \<description\> entries.</span></span>  
  
## <a name="displayname"></a><span data-ttu-id="4b9bf-117">\<表示名\></span><span class="sxs-lookup"><span data-stu-id="4b9bf-117">\<displayname\></span></span>  
 <span data-ttu-id="4b9bf-118">\<Displayname\>装飾には、エントリの名前を表示するための文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-118">The \<displayname\> decoration contains the string used for displaying the name of an entry.</span></span> <span data-ttu-id="4b9bf-119">これにより、それらは許可されていないときに、スペース、句、およびを使用する、\<要素\>または\<属性\>名。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-119">This enables you to use spaces, phrases, and so on, when they would not be allowed for an \<element\> or \<attribute\> name.</span></span>  
  
 <span data-ttu-id="4b9bf-120">ローカライズできる\<displayname\>エントリです。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-120">You can localize \<displayname\> entries.</span></span>  
  
## <a name="readonly"></a><span data-ttu-id="4b9bf-121">\<読み取り専用\></span><span class="sxs-lookup"><span data-stu-id="4b9bf-121">\<readonly\></span></span>  
 <span data-ttu-id="4b9bf-122">\<固定 readonly =""\>装飾は、フィールドを変更することがあるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-122">The \<readonly fixed=""\> decoration controls whether a field may be edited.</span></span> <span data-ttu-id="4b9bf-123">"fixed" 属性値が `true` (既定値) の場合、フィールドは読み取り専用になります。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-123">A "fixed" attribute value of `true` (the default) makes a field read-only.</span></span>  
  
 <span data-ttu-id="4b9bf-124">外部エディターを実装する場合は、外部を実装する**TypeConverter**クラスし、オーバーライド、 **GetStandardValuesExclusive(ITypeDescriptorContext)**メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-124">When implementing an external editor, implement an external **TypeConverter** class and override the **GetStandardValuesExclusive(ITypeDescriptorContext)** method instead.</span></span> <span data-ttu-id="4b9bf-125">`true` を返すと、フィールドは読み取り専用になりますが、カスタム エディターへのアクセスは保持されます。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-125">Returning `true` makes a field read-only but preserves access to the custom editor.</span></span>  
  
## <a name="browsable"></a><span data-ttu-id="4b9bf-126">\<ブラウズ\></span><span class="sxs-lookup"><span data-stu-id="4b9bf-126">\<browsable\></span></span>  
 <span data-ttu-id="4b9bf-127">\<ブラウズ show =""\>装飾は、プロパティ グリッドでフィールドを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-127">The \<browsable show=""\> decoration controls whether a field appears in the property grid.</span></span> <span data-ttu-id="4b9bf-128">"show" 属性値が `True` (既定値) の場合、フィールドはグリッドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-128">A "show" attribute value of `True` (the default) makes a field appear in the grid.</span></span>  
  
## <a name="converter"></a><span data-ttu-id="4b9bf-129">\<コンバーター\></span><span class="sxs-lookup"><span data-stu-id="4b9bf-129">\<converter\></span></span>  
 <span data-ttu-id="4b9bf-130">\<コンバーター アセンブリ =""\>装飾を指定、必要な**TypeConverter**のクラス名、\<要素\>または\<属性\>です。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-130">The \<converter assembly=""\> decoration specifies the desired **TypeConverter** class name for the \<element\> or \<attribute\>.</span></span> <span data-ttu-id="4b9bf-131">省略可能な"assembly"属性値を含む、必要なアセンブリへのパスを指定する**TypeConverter**です。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-131">The optional "assembly" attribute value specifies the path to the assembly containing the desired **TypeConverter**.</span></span> <span data-ttu-id="4b9bf-132">"assembly" 値が指定されていない場合、クラス名には、グローバル アセンブリ キャッシュのアセンブリ名、キー、カルチャ、およびバージョンの値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-132">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="editor"></a><span data-ttu-id="4b9bf-133">\<エディター\></span><span class="sxs-lookup"><span data-stu-id="4b9bf-133">\<editor\></span></span>  
 <span data-ttu-id="4b9bf-134">\<エディターのアセンブリ =""\>装飾を指定、必要な**UITypeEditor**のクラス名、\<要素\>または\<属性\>です。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-134">The \<editor assembly=""\> decoration specifies the desired **UITypeEditor** class name for the \<element\> or \<attribute\>.</span></span> <span data-ttu-id="4b9bf-135">省略可能な"assembly"属性値を含む、必要なアセンブリへのパスを指定する**UITypeEditor**です。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-135">The optional "assembly" attribute value specifies the path to the assembly containing the desired **UITypeEditor**.</span></span> <span data-ttu-id="4b9bf-136">"assembly" 値が指定されていない場合、クラス名には、グローバル アセンブリ キャッシュのアセンブリ名、キー、カルチャ、およびバージョンの値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-136">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="null-values-for-optional-enumerations"></a><span data-ttu-id="4b9bf-137">省略可能な列挙の Null 値</span><span class="sxs-lookup"><span data-stu-id="4b9bf-137">Null Values for Optional Enumerations</span></span>  
 <span data-ttu-id="4b9bf-138">省略可能な列挙体を使用する場合、値の 1 つがあります\<none\>を null 値を示すためにします。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-138">When using an optional enumeration, one of the values should be \<none\> to denote a null value.</span></span> <span data-ttu-id="4b9bf-139">これは組み込みのタグではありませんが、列挙が xsd:string から派生している場合は、none として処理される列挙値を指定して実現できます。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-139">This is not a built-in tag, but may be achieved by providing an enumeration value that is treated as none if the enumeration is derived from xsd:string.</span></span> <span data-ttu-id="4b9bf-140">xsd:int から派生している列挙の場合、整数が値を保持する必要があるため無効です。</span><span class="sxs-lookup"><span data-stu-id="4b9bf-140">This is not possible for enumerations derived from xsd:int, because the integer must hold a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9bf-141">参照</span><span class="sxs-lookup"><span data-stu-id="4b9bf-141">See Also</span></span>  
 [<span data-ttu-id="4b9bf-142">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="4b9bf-142">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)
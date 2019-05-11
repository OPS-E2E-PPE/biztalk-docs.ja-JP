---
title: アダプター フレームワーク構成スキーマの装飾タグ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d5d7f6b-2273-45a6-ba9d-43201760cf22
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdce504133ecb1de4763ce72b314fe39cea8fef3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361480"
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a><span data-ttu-id="7d3e9-102">アダプター フレームワーク構成スキーマの装飾タグ</span><span class="sxs-lookup"><span data-stu-id="7d3e9-102">Adapter Framework Configuration Schema Decoration Tags</span></span>
<span data-ttu-id="7d3e9-103">構成スキーマ ファイル内のこのトピックで説明されているタグを使用すると、データ アダプターのプロパティ ページを整理して表示できます。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-103">You can use the tags described in this topic within the configuration schema files to display and organize data on the adapter property pages.</span></span>  
  
 <span data-ttu-id="7d3e9-104">次の図は、FTP の受信場所のプロパティ ページでは、これらのタグの一部を実装します。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-104">The following figure shows how the FTP receive location property page implements some of these tags.</span></span>  
  
 <span data-ttu-id="7d3e9-105">![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")</span><span class="sxs-lookup"><span data-stu-id="7d3e9-105">![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")</span></span>  
<span data-ttu-id="7d3e9-106">\<説明\>、 \<displayname\>、および\<カテゴリ\>FTP アダプターのプロパティ ページでタグ</span><span class="sxs-lookup"><span data-stu-id="7d3e9-106">The \<description\>, \<displayname\>, and \<category\> tags in the FTP adapter property page</span></span>  
  
## <a name="designer"></a><span data-ttu-id="7d3e9-107">\<designer\></span><span class="sxs-lookup"><span data-stu-id="7d3e9-107">\<designer\></span></span>  
 <span data-ttu-id="7d3e9-108">BizTalk アダプター フレームワークの装飾の表示との間、 \<baf:designer\>タグと\</baf:designer\>終了タグ。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-108">The BizTalk Adapter Framework decorations appear between a \<baf:designer\> tag and \</baf:designer\> end tag.</span></span> <span data-ttu-id="7d3e9-109">\<Baf:designer\>タグでは、アダプター フレームワークを区別するのに役立ちます\<appinfo\> 、他のアダプター指定\<appinfo\>情報。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-109">The \<baf:designer\> tag helps distinguish between Adapter Framework \<appinfo\> and other adapter-supplied \<appinfo\> information.</span></span>  
  
## <a name="category"></a><span data-ttu-id="7d3e9-110">\<category\></span><span class="sxs-lookup"><span data-stu-id="7d3e9-110">\<category\></span></span>  
 <span data-ttu-id="7d3e9-111">\<カテゴリ\>装飾には、プロパティ グリッド内のエントリをグループに分割するために使用する文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-111">The \<category\> decoration contains the string used to separate entries in the property grid into groups.</span></span> <span data-ttu-id="7d3e9-112">装飾には、カテゴリの下位エントリと同じカテゴリ文字列のすべてのエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-112">The decoration displays all entries with the same category string as subordinate entries of the category.</span></span>  
  
 <span data-ttu-id="7d3e9-113">ローカライズできる\<カテゴリ\>エントリ。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-113">You can localize \<category\> entries.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7d3e9-114">\<description\></span><span class="sxs-lookup"><span data-stu-id="7d3e9-114">\<description\></span></span>  
 <span data-ttu-id="7d3e9-115">\<説明\>装飾には、プロパティ グリッドの下部にあるエントリの説明のテキストを提供するために使用する文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-115">The \<description\> decoration contains the string used to provide descriptive text for entries at the bottom of the property grid.</span></span>  
  
 <span data-ttu-id="7d3e9-116">ローカライズできる\<説明\>エントリ。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-116">You can localize \<description\> entries.</span></span>  
  
## <a name="displayname"></a><span data-ttu-id="7d3e9-117">\<displayname\></span><span class="sxs-lookup"><span data-stu-id="7d3e9-117">\<displayname\></span></span>  
 <span data-ttu-id="7d3e9-118">\<Displayname\>装飾にはエントリの名前を表示するための文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-118">The \<displayname\> decoration contains the string used for displaying the name of an entry.</span></span> <span data-ttu-id="7d3e9-119">許可はされていない場合に、スペース、句、およびを使用できます、\<要素\>または\<属性\>名。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-119">This enables you to use spaces, phrases, and so on, when they would not be allowed for an \<element\> or \<attribute\> name.</span></span>  
  
 <span data-ttu-id="7d3e9-120">ローカライズできる\<displayname\>エントリ。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-120">You can localize \<displayname\> entries.</span></span>  
  
## <a name="readonly"></a><span data-ttu-id="7d3e9-121">\<readonly\></span><span class="sxs-lookup"><span data-stu-id="7d3e9-121">\<readonly\></span></span>  
 <span data-ttu-id="7d3e9-122">\<固定読み取り専用 =""\>装飾は、フィールドを編集することがあるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-122">The \<readonly fixed=""\> decoration controls whether a field may be edited.</span></span> <span data-ttu-id="7d3e9-123">"Fixed"属性値`true`(既定値) は、読み取り専用フィールド。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-123">A "fixed" attribute value of `true` (the default) makes a field read-only.</span></span>  
  
 <span data-ttu-id="7d3e9-124">外部エディターを実装する場合、外部の実装**TypeConverter**クラスし、オーバーライド、 **GetStandardValuesExclusive(ITypeDescriptorContext)** メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-124">When implementing an external editor, implement an external **TypeConverter** class and override the **GetStandardValuesExclusive(ITypeDescriptorContext)** method instead.</span></span> <span data-ttu-id="7d3e9-125">返す`true`読み取り専用フィールドが、カスタム エディターへのアクセスは維持されます。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-125">Returning `true` makes a field read-only but preserves access to the custom editor.</span></span>  
  
## <a name="browsable"></a><span data-ttu-id="7d3e9-126">\<参照可能\></span><span class="sxs-lookup"><span data-stu-id="7d3e9-126">\<browsable\></span></span>  
 <span data-ttu-id="7d3e9-127">\<ブラウズ show =""\>装飾は、プロパティ グリッドでフィールドが表示されるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-127">The \<browsable show=""\> decoration controls whether a field appears in the property grid.</span></span> <span data-ttu-id="7d3e9-128">"Show"属性値の`True`(既定値) は、グリッドに表示するフィールド。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-128">A "show" attribute value of `True` (the default) makes a field appear in the grid.</span></span>  
  
## <a name="converter"></a><span data-ttu-id="7d3e9-129">\<コンバーター\></span><span class="sxs-lookup"><span data-stu-id="7d3e9-129">\<converter\></span></span>  
 <span data-ttu-id="7d3e9-130">\<コンバーター アセンブリ =""\>装飾は、必要な指定**TypeConverter**クラス名を\<要素\>または\<属性\>します。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-130">The \<converter assembly=""\> decoration specifies the desired **TypeConverter** class name for the \<element\> or \<attribute\>.</span></span> <span data-ttu-id="7d3e9-131">省略可能な"assembly"属性の値を含む、必要なアセンブリへのパスを指定します**TypeConverter**します。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-131">The optional "assembly" attribute value specifies the path to the assembly containing the desired **TypeConverter**.</span></span> <span data-ttu-id="7d3e9-132">"Assembly"値が指定されて、クラス名は、グローバル アセンブリ キャッシュのアセンブリの名前、キー、カルチャ、およびバージョンの値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-132">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="editor"></a><span data-ttu-id="7d3e9-133">\<editor\></span><span class="sxs-lookup"><span data-stu-id="7d3e9-133">\<editor\></span></span>  
 <span data-ttu-id="7d3e9-134">\<エディターのアセンブリ =""\>装飾は、必要な指定**UITypeEditor**クラス名を\<要素\>または\<属性\>します。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-134">The \<editor assembly=""\> decoration specifies the desired **UITypeEditor** class name for the \<element\> or \<attribute\>.</span></span> <span data-ttu-id="7d3e9-135">省略可能な"assembly"属性の値を含む、必要なアセンブリへのパスを指定します**UITypeEditor**します。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-135">The optional "assembly" attribute value specifies the path to the assembly containing the desired **UITypeEditor**.</span></span> <span data-ttu-id="7d3e9-136">"Assembly"値が指定されて、クラス名は、グローバル アセンブリ キャッシュのアセンブリの名前、キー、カルチャ、およびバージョンの値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-136">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="null-values-for-optional-enumerations"></a><span data-ttu-id="7d3e9-137">省略可能な列挙型の null 値</span><span class="sxs-lookup"><span data-stu-id="7d3e9-137">Null Values for Optional Enumerations</span></span>  
 <span data-ttu-id="7d3e9-138">省略可能な列挙体を使用する場合、値の 1 つは\<none\> null 値を示します。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-138">When using an optional enumeration, one of the values should be \<none\> to denote a null value.</span></span> <span data-ttu-id="7d3e9-139">これは、組み込みのタグではありませんが、列挙が xsd:string から派生している場合に none として処理する列挙値を提供することで実現できます。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-139">This is not a built-in tag, but may be achieved by providing an enumeration value that is treated as none if the enumeration is derived from xsd:string.</span></span> <span data-ttu-id="7d3e9-140">これはできません xsd:int から派生した列挙型の整数値を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3e9-140">This is not possible for enumerations derived from xsd:int, because the integer must hold a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d3e9-141">参照</span><span class="sxs-lookup"><span data-stu-id="7d3e9-141">See Also</span></span>  
 [<span data-ttu-id="7d3e9-142">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="7d3e9-142">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)
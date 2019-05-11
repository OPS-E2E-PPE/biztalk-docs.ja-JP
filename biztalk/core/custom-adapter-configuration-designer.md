---
title: カスタム アダプター構成デザイナー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9b231c3-3948-4db8-b4f0-d9c21c31b168
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d596d87e693dbcb0c8828087d4a3c56c00e104d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390092"
---
# <a name="custom-adapter-configuration-designer"></a><span data-ttu-id="71666-102">カスタム アダプター構成デザイナー</span><span class="sxs-lookup"><span data-stu-id="71666-102">Custom Adapter Configuration Designer</span></span>
<span data-ttu-id="71666-103">.NET クラス ライブラリにカスタム デザイナーを構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71666-103">You need to build the custom designers into a .NET class library.</span></span> <span data-ttu-id="71666-104">アダプターの DLL に組み込むことか、別の DLL をビルドできます。</span><span class="sxs-lookup"><span data-stu-id="71666-104">You may incorporate them into the DLL for the adapter or build a separate DLL.</span></span> <span data-ttu-id="71666-105">デザイナーのアセンブリをビルドした後は、説明やカテゴリと同様に、装飾を介して参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71666-105">After you build a designer assembly, you must reference it through decorations, just like a description or a category.</span></span> <span data-ttu-id="71666-106">参照には、使用するには、アセンブリと完全修飾クラス名の仕様が含まれています。</span><span class="sxs-lookup"><span data-stu-id="71666-106">The reference includes a specification of the assembly and a fully qualified class name to use.</span></span>  
  
 <span data-ttu-id="71666-107">これらの装飾は、特定のカスタム デザイナーを参照する 2 つの方法をサポートします。 または、ディスク上にある外部アセンブリとグローバル アセンブリ キャッシュ内のグローバル アセンブリとして。</span><span class="sxs-lookup"><span data-stu-id="71666-107">These decorations support two ways of referencing the specific custom designer: as a global assembly in the global assembly cache or as an external assembly located on the disk.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71666-108">これには 2 つの可能なデザイン時アセンブリ パスがあります。型エディターと構成 XSD 自体 (相対パスがサポートされていません)、XSD 内で使用するコンバーターの絶対パスを指定する、または型エディターと型コンバーターをグローバル アセンブリ キャッシュに格納でき、絶対パスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="71666-108">There are two possible design-time assembly paths: You can specify the absolute path to the type editors and converters used in the configuration XSD in the XSD itself (relative path is not supported), or you can store the type editors and converters in the global assembly cache and not need an absolute path.</span></span>  
  
## <a name="global-assembly-cache-designer-use"></a><span data-ttu-id="71666-109">グローバル アセンブリ キャッシュ デザイナーの使用</span><span class="sxs-lookup"><span data-stu-id="71666-109">Global Assembly Cache Designer Use</span></span>  
 <span data-ttu-id="71666-110">グローバル アセンブリ キャッシュには、アセンブリ名、公開キー、バージョン、およびカルチャによってアセンブリが格納されます。</span><span class="sxs-lookup"><span data-stu-id="71666-110">The global assembly cache stores assemblies by assembly name, public key, version, and culture.</span></span> <span data-ttu-id="71666-111">このため、推奨されること。</span><span class="sxs-lookup"><span data-stu-id="71666-111">Because of this, it is recommended that you:</span></span>  
  
1. <span data-ttu-id="71666-112">公開キー ファイルを生成し、AssemblyInfo.cs ファイルにこのファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="71666-112">Generate a public key file and add this file to the AssemblyInfo.cs file.</span></span>  
  
2. <span data-ttu-id="71666-113">AssemblyInfo.cs ファイルには、特定のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="71666-113">Specify a specific version in the AssemblyInfo.cs file.</span></span>  
  
   <span data-ttu-id="71666-114">グローバル アセンブリ キャッシュにアセンブリをドラッグするか、GACUTIL を使用して、グローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="71666-114">You can either drag the assembly into the global assembly cache or use GACUTIL to add it to the global assembly cache.</span></span>  
  
   <span data-ttu-id="71666-115">このデザイナーを使用するには、装飾の値として、完全修飾クラス名、コンマ、およびグローバル アセンブリ キャッシュのアセンブリ エントリ (アセンブリ名、バージョン、カルチャ、および公開キー トークン) を指定します。</span><span class="sxs-lookup"><span data-stu-id="71666-115">To use this designer, specify the fully qualified class name, a comma, and the global assembly cache assembly entry (assembly name, version, culture, and public key token) as the value of the decoration.</span></span> <span data-ttu-id="71666-116">使用\<エディター\>の装飾**UITypeEditor**実装と\<コンバーター\>の装飾**TypeConverter**の実装.</span><span class="sxs-lookup"><span data-stu-id="71666-116">Use \<editor\> decorations for **UITypeEditor** implementations and \<converter\> decorations for **TypeConverter** implementations.</span></span>  
  
   <span data-ttu-id="71666-117">次のコードでは、XSD ファイルでカスタム デザイナーを初期化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="71666-117">The following code shows how to initialize the custom designers in an XSD file:</span></span>  
  
```  
<xs:element name="Global" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>GAC Designer Component</baf:category>  
            <baf:editor>AdapterManagement.ComponentModel. PasswordUITypeEditor, AdapterManagement, Version=1.0.1.0, Culture=neutral, PublicKeyToken=f0db50abb0615c18</baf:editor>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
      </xs:sequence>  
```  
  
## <a name="external-assembly-installation-and-use"></a><span data-ttu-id="71666-118">外部アセンブリのインストールと使用</span><span class="sxs-lookup"><span data-stu-id="71666-118">External Assembly Installation and Use</span></span>  
 <span data-ttu-id="71666-119">外部アセンブリの場合は、装飾には、目的のデザイナーを含むアセンブリの名前と完全なパスを指定する省略可能な属性アセンブリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71666-119">For external assemblies, the decoration contains an optional attribute assembly that specifies the full path and name of the assembly containing the desired designer.</span></span>  
  
 <span data-ttu-id="71666-120">次のコードでは、外部アセンブリに含まれるカスタム デザイナーを初期化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="71666-120">The following code shows how to initialize the custom designers contained in external assemblies:</span></span>  
  
```  
<xs:element name="External" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>External Designer Component</baf:category>  
            <baf:converter assembly="C:\source\private\Adapter\Framework\Designer\bin\Debug\Designer.External.dll">Designer.External.DesignerTypeConverter</baf:converter>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
```  
  
## <a name="see-also"></a><span data-ttu-id="71666-121">参照</span><span class="sxs-lookup"><span data-stu-id="71666-121">See Also</span></span>  
 <span data-ttu-id="71666-122">[アダプター構成のカスタム ドロップダウン エディター](../core/custom-drop-down-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="71666-122">[Custom Drop-Down Editor for Adapter Configuration](../core/custom-drop-down-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="71666-123">[アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="71666-123">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="71666-124">[アダプターの構成のカスタム型コンバーター](../core/custom-type-converter-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="71666-124">[Custom Type Converter for Adapter Configuration](../core/custom-type-converter-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="71666-125">アダプターの詳細構成コンポーネント</span><span class="sxs-lookup"><span data-stu-id="71666-125">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)
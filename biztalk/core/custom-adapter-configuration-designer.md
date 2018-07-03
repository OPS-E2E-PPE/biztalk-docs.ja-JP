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
ms.openlocfilehash: 60754ea86e3c77534a15d00ff18b21705198d648
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014443"
---
# <a name="custom-adapter-configuration-designer"></a><span data-ttu-id="21e7c-102">カスタム アダプター構成デザイナー</span><span class="sxs-lookup"><span data-stu-id="21e7c-102">Custom Adapter Configuration Designer</span></span>
<span data-ttu-id="21e7c-103">.NET クラス ライブラリには、カスタム デザイナーを構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21e7c-103">You need to build the custom designers into a .NET class library.</span></span> <span data-ttu-id="21e7c-104">カスタム デザイナーは、アダプターの DLL に組み込むことも、個別の DLL として構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="21e7c-104">You may incorporate them into the DLL for the adapter or build a separate DLL.</span></span> <span data-ttu-id="21e7c-105">デザイナー アセンブリを構築した後は、説明やカテゴリと同様に、装飾を介して参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21e7c-105">After you build a designer assembly, you must reference it through decorations, just like a description or a category.</span></span> <span data-ttu-id="21e7c-106">参照は、使用するアセンブリの指定、および完全修飾されたクラス名の指定によって実行します。</span><span class="sxs-lookup"><span data-stu-id="21e7c-106">The reference includes a specification of the assembly and a fully qualified class name to use.</span></span>  
  
 <span data-ttu-id="21e7c-107">これらの装飾は、特定のカスタム デザイナーを参照する 2 つの方法をサポートします。 または、ディスク上にある外部アセンブリとグローバル アセンブリ キャッシュ内のグローバル アセンブリとして。</span><span class="sxs-lookup"><span data-stu-id="21e7c-107">These decorations support two ways of referencing the specific custom designer: as a global assembly in the global assembly cache or as an external assembly located on the disk.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21e7c-108">2 つの可能なデザイン時アセンブリ パスがあります型エディターと構成 XSD 自体 (相対パスがサポートされていません)、XSD 内で使用するコンバーターの絶対パスを指定するか、グローバル型のエディターと型コンバーターを格納することができます。アセンブリ キャッシュと絶対パスが必要です。</span><span class="sxs-lookup"><span data-stu-id="21e7c-108">There are two possible design-time assembly paths: You can specify the absolute path to the type editors and converters used in the configuration XSD in the XSD itself (relative path is not supported), or you can store the type editors and converters in the global assembly cache and not need an absolute path.</span></span>  
  
## <a name="global-assembly-cache-designer-use"></a><span data-ttu-id="21e7c-109">グローバル アセンブリ キャッシュ デザイナーの使用</span><span class="sxs-lookup"><span data-stu-id="21e7c-109">Global Assembly Cache Designer Use</span></span>  
 <span data-ttu-id="21e7c-110">グローバル アセンブリ キャッシュには、アセンブリの名前、公開キー、バージョン、カルチャの内容でアセンブリが格納されます。</span><span class="sxs-lookup"><span data-stu-id="21e7c-110">The global assembly cache stores assemblies by assembly name, public key, version, and culture.</span></span> <span data-ttu-id="21e7c-111">そのため、以下のようにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="21e7c-111">Because of this, it is recommended that you:</span></span>  
  
1. <span data-ttu-id="21e7c-112">公開キー ファイルを生成して、AssemblyInfo.cs ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="21e7c-112">Generate a public key file and add this file to the AssemblyInfo.cs file.</span></span>  
  
2. <span data-ttu-id="21e7c-113">AssemblyInfo.cs ファイルに、特定のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="21e7c-113">Specify a specific version in the AssemblyInfo.cs file.</span></span>  
  
   <span data-ttu-id="21e7c-114">アセンブリをグローバル アセンブリ キャッシュに追加するには、そのアセンブリをグローバル アセンブリ キャッシュにドラッグするか、GACUTIL を使用します。</span><span class="sxs-lookup"><span data-stu-id="21e7c-114">You can either drag the assembly into the global assembly cache or use GACUTIL to add it to the global assembly cache.</span></span>  
  
   <span data-ttu-id="21e7c-115">このデザイナーを使用するには、装飾の値として、完全修飾されたクラス名、コンマ、グローバル アセンブリ キャッシュのアセンブリ エントリ (アセンブリ名、バージョン、カルチャ、公開キー トークン) を指定します。</span><span class="sxs-lookup"><span data-stu-id="21e7c-115">To use this designer, specify the fully qualified class name, a comma, and the global assembly cache assembly entry (assembly name, version, culture, and public key token) as the value of the decoration.</span></span> <span data-ttu-id="21e7c-116">使用\<エディター\>の装飾**UITypeEditor**実装と\<コンバーター\>の装飾**TypeConverter**の実装.</span><span class="sxs-lookup"><span data-stu-id="21e7c-116">Use \<editor\> decorations for **UITypeEditor** implementations and \<converter\> decorations for **TypeConverter** implementations.</span></span>  
  
   <span data-ttu-id="21e7c-117">XSD ファイルでカスタム デザイナーを初期化する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="21e7c-117">The following code shows how to initialize the custom designers in an XSD file:</span></span>  
  
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
  
## <a name="external-assembly-installation-and-use"></a><span data-ttu-id="21e7c-118">外部アセンブリのインストールおよび使用</span><span class="sxs-lookup"><span data-stu-id="21e7c-118">External Assembly Installation and Use</span></span>  
 <span data-ttu-id="21e7c-119">外部アセンブリの場合は、目的のデザイナーを含むアセンブリの完全パスと名前を指定する属性アセンブリを、オプションで装飾に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="21e7c-119">For external assemblies, the decoration contains an optional attribute assembly that specifies the full path and name of the assembly containing the desired designer.</span></span>  
  
 <span data-ttu-id="21e7c-120">次のコードは、外部アセンブリに含まれるカスタム デザイナーを初期化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="21e7c-120">The following code shows how to initialize the custom designers contained in external assemblies:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21e7c-121">参照</span><span class="sxs-lookup"><span data-stu-id="21e7c-121">See Also</span></span>  
 <span data-ttu-id="21e7c-122">[アダプター構成のカスタム ドロップダウン エディター](../core/custom-drop-down-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="21e7c-122">[Custom Drop-Down Editor for Adapter Configuration](../core/custom-drop-down-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="21e7c-123">[アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="21e7c-123">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="21e7c-124">[アダプターの構成のカスタム型コンバーター](../core/custom-type-converter-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="21e7c-124">[Custom Type Converter for Adapter Configuration](../core/custom-type-converter-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="21e7c-125">アダプターの詳細構成コンポーネント</span><span class="sxs-lookup"><span data-stu-id="21e7c-125">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)
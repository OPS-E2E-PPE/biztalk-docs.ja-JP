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
# <a name="custom-adapter-configuration-designer"></a>カスタム アダプター構成デザイナー
.NET クラス ライブラリにカスタム デザイナーを構築する必要があります。 アダプターの DLL に組み込むことか、別の DLL をビルドできます。 デザイナーのアセンブリをビルドした後は、説明やカテゴリと同様に、装飾を介して参照する必要があります。 参照には、使用するには、アセンブリと完全修飾クラス名の仕様が含まれています。  
  
 これらの装飾は、特定のカスタム デザイナーを参照する 2 つの方法をサポートします。 または、ディスク上にある外部アセンブリとグローバル アセンブリ キャッシュ内のグローバル アセンブリとして。  
  
> [!NOTE]
>  これには 2 つの可能なデザイン時アセンブリ パスがあります。型エディターと構成 XSD 自体 (相対パスがサポートされていません)、XSD 内で使用するコンバーターの絶対パスを指定する、または型エディターと型コンバーターをグローバル アセンブリ キャッシュに格納でき、絶対パスは必要ありません。  
  
## <a name="global-assembly-cache-designer-use"></a>グローバル アセンブリ キャッシュ デザイナーの使用  
 グローバル アセンブリ キャッシュには、アセンブリ名、公開キー、バージョン、およびカルチャによってアセンブリが格納されます。 このため、推奨されること。  
  
1. 公開キー ファイルを生成し、AssemblyInfo.cs ファイルにこのファイルを追加します。  
  
2. AssemblyInfo.cs ファイルには、特定のバージョンを指定します。  
  
   グローバル アセンブリ キャッシュにアセンブリをドラッグするか、GACUTIL を使用して、グローバル アセンブリ キャッシュに追加します。  
  
   このデザイナーを使用するには、装飾の値として、完全修飾クラス名、コンマ、およびグローバル アセンブリ キャッシュのアセンブリ エントリ (アセンブリ名、バージョン、カルチャ、および公開キー トークン) を指定します。 使用\<エディター\>の装飾**UITypeEditor**実装と\<コンバーター\>の装飾**TypeConverter**の実装.  
  
   次のコードでは、XSD ファイルでカスタム デザイナーを初期化する方法を示します。  
  
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
  
## <a name="external-assembly-installation-and-use"></a>外部アセンブリのインストールと使用  
 外部アセンブリの場合は、装飾には、目的のデザイナーを含むアセンブリの名前と完全なパスを指定する省略可能な属性アセンブリが含まれています。  
  
 次のコードでは、外部アセンブリに含まれるカスタム デザイナーを初期化する方法を示します。  
  
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
  
## <a name="see-also"></a>参照  
 [アダプター構成のカスタム ドロップダウン エディター](../core/custom-drop-down-editor-for-adapter-configuration.md)   
 [アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [アダプターの構成のカスタム型コンバーター](../core/custom-type-converter-for-adapter-configuration.md)   
 [アダプターの詳細構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)
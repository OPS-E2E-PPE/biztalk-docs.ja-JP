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
# <a name="custom-adapter-configuration-designer"></a>カスタム アダプター構成デザイナー
.NET クラス ライブラリには、カスタム デザイナーを構築する必要があります。 カスタム デザイナーは、アダプターの DLL に組み込むことも、個別の DLL として構築することもできます。 デザイナー アセンブリを構築した後は、説明やカテゴリと同様に、装飾を介して参照する必要があります。 参照は、使用するアセンブリの指定、および完全修飾されたクラス名の指定によって実行します。  
  
 これらの装飾は、特定のカスタム デザイナーを参照する 2 つの方法をサポートします。 または、ディスク上にある外部アセンブリとグローバル アセンブリ キャッシュ内のグローバル アセンブリとして。  
  
> [!NOTE]
>  2 つの可能なデザイン時アセンブリ パスがあります型エディターと構成 XSD 自体 (相対パスがサポートされていません)、XSD 内で使用するコンバーターの絶対パスを指定するか、グローバル型のエディターと型コンバーターを格納することができます。アセンブリ キャッシュと絶対パスが必要です。  
  
## <a name="global-assembly-cache-designer-use"></a>グローバル アセンブリ キャッシュ デザイナーの使用  
 グローバル アセンブリ キャッシュには、アセンブリの名前、公開キー、バージョン、カルチャの内容でアセンブリが格納されます。 そのため、以下のようにしておくことをお勧めします。  
  
1. 公開キー ファイルを生成して、AssemblyInfo.cs ファイルに追加します。  
  
2. AssemblyInfo.cs ファイルに、特定のバージョンを指定します。  
  
   アセンブリをグローバル アセンブリ キャッシュに追加するには、そのアセンブリをグローバル アセンブリ キャッシュにドラッグするか、GACUTIL を使用します。  
  
   このデザイナーを使用するには、装飾の値として、完全修飾されたクラス名、コンマ、グローバル アセンブリ キャッシュのアセンブリ エントリ (アセンブリ名、バージョン、カルチャ、公開キー トークン) を指定します。 使用\<エディター\>の装飾**UITypeEditor**実装と\<コンバーター\>の装飾**TypeConverter**の実装.  
  
   XSD ファイルでカスタム デザイナーを初期化する方法を次のコード例に示します。  
  
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
  
## <a name="external-assembly-installation-and-use"></a>外部アセンブリのインストールおよび使用  
 外部アセンブリの場合は、目的のデザイナーを含むアセンブリの完全パスと名前を指定する属性アセンブリを、オプションで装飾に含めることができます。  
  
 次のコードは、外部アセンブリに含まれるカスタム デザイナーを初期化する方法を示しています。  
  
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
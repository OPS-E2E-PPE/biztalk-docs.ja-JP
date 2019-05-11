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
# <a name="adapter-framework-configuration-schema-decoration-tags"></a>アダプター フレームワーク構成スキーマの装飾タグ
構成スキーマ ファイル内のこのトピックで説明されているタグを使用すると、データ アダプターのプロパティ ページを整理して表示できます。  
  
 次の図は、FTP の受信場所のプロパティ ページでは、これらのタグの一部を実装します。  
  
 ![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")  
\<説明\>、 \<displayname\>、および\<カテゴリ\>FTP アダプターのプロパティ ページでタグ  
  
## <a name="designer"></a>\<designer\>  
 BizTalk アダプター フレームワークの装飾の表示との間、 \<baf:designer\>タグと\</baf:designer\>終了タグ。 \<Baf:designer\>タグでは、アダプター フレームワークを区別するのに役立ちます\<appinfo\> 、他のアダプター指定\<appinfo\>情報。  
  
## <a name="category"></a>\<category\>  
 \<カテゴリ\>装飾には、プロパティ グリッド内のエントリをグループに分割するために使用する文字列が含まれています。 装飾には、カテゴリの下位エントリと同じカテゴリ文字列のすべてのエントリが表示されます。  
  
 ローカライズできる\<カテゴリ\>エントリ。  
  
## <a name="description"></a>\<description\>  
 \<説明\>装飾には、プロパティ グリッドの下部にあるエントリの説明のテキストを提供するために使用する文字列が含まれています。  
  
 ローカライズできる\<説明\>エントリ。  
  
## <a name="displayname"></a>\<displayname\>  
 \<Displayname\>装飾にはエントリの名前を表示するための文字列が含まれています。 許可はされていない場合に、スペース、句、およびを使用できます、\<要素\>または\<属性\>名。  
  
 ローカライズできる\<displayname\>エントリ。  
  
## <a name="readonly"></a>\<readonly\>  
 \<固定読み取り専用 =""\>装飾は、フィールドを編集することがあるかどうかを制御します。 "Fixed"属性値`true`(既定値) は、読み取り専用フィールド。  
  
 外部エディターを実装する場合、外部の実装**TypeConverter**クラスし、オーバーライド、 **GetStandardValuesExclusive(ITypeDescriptorContext)** メソッド代わりにします。 返す`true`読み取り専用フィールドが、カスタム エディターへのアクセスは維持されます。  
  
## <a name="browsable"></a>\<参照可能\>  
 \<ブラウズ show =""\>装飾は、プロパティ グリッドでフィールドが表示されるかどうかを制御します。 "Show"属性値の`True`(既定値) は、グリッドに表示するフィールド。  
  
## <a name="converter"></a>\<コンバーター\>  
 \<コンバーター アセンブリ =""\>装飾は、必要な指定**TypeConverter**クラス名を\<要素\>または\<属性\>します。 省略可能な"assembly"属性の値を含む、必要なアセンブリへのパスを指定します**TypeConverter**します。 "Assembly"値が指定されて、クラス名は、グローバル アセンブリ キャッシュのアセンブリの名前、キー、カルチャ、およびバージョンの値を含める必要があります。  
  
## <a name="editor"></a>\<editor\>  
 \<エディターのアセンブリ =""\>装飾は、必要な指定**UITypeEditor**クラス名を\<要素\>または\<属性\>します。 省略可能な"assembly"属性の値を含む、必要なアセンブリへのパスを指定します**UITypeEditor**します。 "Assembly"値が指定されて、クラス名は、グローバル アセンブリ キャッシュのアセンブリの名前、キー、カルチャ、およびバージョンの値を含める必要があります。  
  
## <a name="null-values-for-optional-enumerations"></a>省略可能な列挙型の null 値  
 省略可能な列挙体を使用する場合、値の 1 つは\<none\> null 値を示します。 これは、組み込みのタグではありませんが、列挙が xsd:string から派生している場合に none として処理する列挙値を提供することで実現できます。 これはできません xsd:int から派生した列挙型の整数値を保持する必要があります。  
  
## <a name="see-also"></a>参照  
 [アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)
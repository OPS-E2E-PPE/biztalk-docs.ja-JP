---
title: アダプター フレームワーク構成スキーマの装飾タグ |Microsoft ドキュメント
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
ms.openlocfilehash: d49aac9f11ef48bd0a66dcc9bda3a769cd6c34f4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965376"
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a>アダプター フレームワーク構成スキーマの装飾タグ
このトピックで説明するタグを構成スキーマ ファイル内で使用して、アダプターのプロパティ ページでデータを表示および編成できます。  
  
 次の図は、FTP 受信場所のプロパティ ページでこれらのタグの一部を実装する方法を示しています。  
  
 ![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")  
\<説明\>、 \<displayname\>、および\<カテゴリ\>FTP アダプター プロパティ ページ内のタグ  
  
## <a name="designer"></a>\<デザイナー\>  
 BizTalk アダプター フレームワークの装飾の間に表示、 \<baf:designer\>タグと\</baf:designer\>タグを終了します。 \<Baf:designer\>タグでは、アダプター フレームワークを区別するのに役立ちます\<appinfo\>し、その他のアダプター指定\<appinfo\>情報。  
  
## <a name="category"></a>\<カテゴリ\>  
 \<カテゴリ\>装飾には、グループに、プロパティ グリッド内のエントリを区切るために使用する文字列が含まれています。 装飾には、カテゴリの下位エントリと同じカテゴリ文字列を使用するすべてのエントリが表示されます。  
  
 ローカライズできる\<カテゴリ\>エントリです。  
  
## <a name="description"></a>\<説明\>  
 \<説明\>装飾には、プロパティ グリッドの下部にあるエントリの説明のテキストを提供するために使用する文字列が含まれています。  
  
 ローカライズできる\<説明\>エントリです。  
  
## <a name="displayname"></a>\<表示名\>  
 \<Displayname\>装飾には、エントリの名前を表示するための文字列が含まれています。 これにより、それらは許可されていないときに、スペース、句、およびを使用する、\<要素\>または\<属性\>名。  
  
 ローカライズできる\<displayname\>エントリです。  
  
## <a name="readonly"></a>\<読み取り専用\>  
 \<固定 readonly =""\>装飾は、フィールドを変更することがあるかどうかを制御します。 "fixed" 属性値が `true` (既定値) の場合、フィールドは読み取り専用になります。  
  
 外部エディターを実装する場合は、外部を実装する**TypeConverter**クラスし、オーバーライド、 **GetStandardValuesExclusive(ITypeDescriptorContext)** メソッド代わりにします。 `true` を返すと、フィールドは読み取り専用になりますが、カスタム エディターへのアクセスは保持されます。  
  
## <a name="browsable"></a>\<ブラウズ\>  
 \<ブラウズ show =""\>装飾は、プロパティ グリッドでフィールドを表示するかどうかを制御します。 "show" 属性値が `True` (既定値) の場合、フィールドはグリッドに表示されます。  
  
## <a name="converter"></a>\<コンバーター\>  
 \<コンバーター アセンブリ =""\>装飾を指定、必要な**TypeConverter**のクラス名、\<要素\>または\<属性\>です。 省略可能な"assembly"属性値を含む、必要なアセンブリへのパスを指定する**TypeConverter**です。 "assembly" 値が指定されていない場合、クラス名には、グローバル アセンブリ キャッシュのアセンブリ名、キー、カルチャ、およびバージョンの値を含める必要があります。  
  
## <a name="editor"></a>\<エディター\>  
 \<エディターのアセンブリ =""\>装飾を指定、必要な**UITypeEditor**のクラス名、\<要素\>または\<属性\>です。 省略可能な"assembly"属性値を含む、必要なアセンブリへのパスを指定する**UITypeEditor**です。 "assembly" 値が指定されていない場合、クラス名には、グローバル アセンブリ キャッシュのアセンブリ名、キー、カルチャ、およびバージョンの値を含める必要があります。  
  
## <a name="null-values-for-optional-enumerations"></a>省略可能な列挙の Null 値  
 省略可能な列挙体を使用する場合、値の 1 つがあります\<none\>を null 値を示すためにします。 これは組み込みのタグではありませんが、列挙が xsd:string から派生している場合は、none として処理される列挙値を指定して実現できます。 xsd:int から派生している列挙の場合、整数が値を保持する必要があるため無効です。  
  
## <a name="see-also"></a>参照  
 [アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)
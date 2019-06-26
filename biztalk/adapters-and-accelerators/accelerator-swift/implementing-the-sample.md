---
title: サンプルの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd788fd3-b070-40d5-a3d3-ac8e5208cc47
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca5f7a6d3561e8217a3eebca16b48644a56238da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377354"
---
# <a name="implementing-the-sample"></a>サンプルの実装
サンプルを実装するには、ように進めます。  
  
1.  SWIFT スキーマの新しいフォルダーを作成 (\<DocumentSchemaLocation\>ユーティリティの構文で)。 InfoPath フォームの作成/変更する予定のすべてのスキーマは、ユーティリティを実行するときに、このフォルダーに配置する必要があります。  
  
2.  MT メッセージの InfoPath フォームを生成している場合、コピー **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**から **\<ドライブ:\> \Program Files\Microsoft BizTalk Accelerator for SWIFT\<メッセージ パック バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<メッセージ パック バージョン\>\Base スキーマ**フォルダーにします。SWIFT スキーマ用に作成します。  
  
3.  手順 1. で SWIFT スキーマ用に作成したフォルダーに InfoPath フォームを作成する予定のすべてのスキーマをコピーします。  
  
4.  作成または作成した InfoPath フォーム テンプレート ソリューション ファイルを保存するフォルダーを指定 (\<DestinationFolderPath\>ユーティリティの構文で)。 出力フォルダーを作成しない場合、ユーティリティで作成されます、同じパスと名前、コマンドラインで渡すこと。  
  
5.  [オプション]-テキスト ファイルを作成\<NameOfFileContainingSchemaList\> InfoPath フォームを生成するメッセージのメッセージの種類を一覧表示します。 例: メッセージの種類には、MT103、MT102 などを指定できます。メッセージ名は、このテキスト ファイルを作成する代わりにコマンドラインを使用して直接渡されることができます。  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a>FormGenerator.exe のコマンドの使用法の構文  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 各要素の説明は次のとおりです。  
  
-   -b: です。指定した場合は、作成後にフォームがコンパイルされます。  
  
-   InfoPath ソリューションを作成するために使用するテンプレート ファイルを含むフォルダーの TemplateFolderPath:  
  
-   -#:場合は、指定されたテンプレートを検索する複数のテンプレートのパス (多くの整数として # の番号を指定します) と指定された順序で。  
  
-   フォームを作成するフォルダーの DestinationFolderPath:  
  
-   スキーマ (MT メッセージの基本クラスと共通のスキーマを含む) の DocumentSchemaLocation: の場所  
  
-   SpaceSeparatedDocumentSchemaList: MT103 MT300 などのスキーマのスペースで区切られた一覧。  
  
-   -f: を割り当てます。指定した場合、スキーマの一覧をファイルから読み取る必要があります。  
  
-   リストを含むファイルの名前を NameOfFileContainingSchemaList: です。  
  
    > [!NOTE]
    >  上記のコマンドは、MT、MX、およびカテゴリ 0 の汎用コマンド メッセージ。 この種類のフォームを生成する特定のコマンドがで指定された、以下のセクションでします。
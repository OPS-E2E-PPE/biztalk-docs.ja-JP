---
title: このサンプルを実装する |Microsoft ドキュメント
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
ms.openlocfilehash: d6622d201c6f7b7d94694a77198d0eb562482489
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966704"
---
# <a name="implementing-the-sample"></a>このサンプルを実装します。
サンプルを実装するには、手順に従います。  
  
1.  SWIFT スキーマの新しいフォルダーを作成 (\<DocumentSchemaLocation\>ユーティリティの構文で)。 対象の InfoPath フォームの作成または変更することは、すべてのスキーマは、ユーティリティを実行するときに、このフォルダーに配置する必要があります。  
  
2.  InfoPath フォーム MT メッセージを生成する場合、コピー **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**から**\<ドライブ:\> \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<メッセージ パック バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<メッセージ パック バージョン\>\Base スキーマ**フォルダーにします。SWIFT スキーマ用に作成します。  
  
3.  しようとする InfoPath フォームを作成し、手順 1. で SWIFT スキーマ用に作成したフォルダーをすべてのスキーマをコピーします。  
  
4.  作成または作成した InfoPath フォーム テンプレート ソリューション ファイルを保存するフォルダーを指定 (\<DestinationFolderPath\>ユーティリティの構文で)。 出力フォルダーを作成しない場合、ユーティリティは作成同じパスと、コマンドラインで渡された名前を使用します。  
  
5.  [オプション]-テキスト ファイルを作成\<NameOfFileContainingSchemaList\> InfoPath フォームを生成するメッセージのメッセージの種類を一覧表示します。 例: メッセージの種類は MT103、MT102 などを指定できます。メッセージの名前は、このテキスト ファイルを作成する代わりにコマンドラインを使用して直接渡されます。  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a>FormGenerator.exe のコマンドの使用法の構文  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 各要素の説明は次のとおりです。  
  
-   フォームを作成後にコンパイルする b: 指定した場合。  
  
-   InfoPath ソリューションを作成するために使用するテンプレート ファイルを含むフォルダーの TemplateFolderPath:  
  
-   -#: 場合は、指定されたテンプレートがルックアップする複数のテンプレート パスに (できるだけ番号 # 整数として指定) と指定された順序で。  
  
-   フォームを作成するフォルダーの DestinationFolderPath:  
  
-   スキーマ (MT メッセージの基本クラスと共通のスキーマを含む) の DocumentSchemaLocation: の場所  
  
-   SpaceSeparatedDocumentSchemaList: MT103 MT300 と同様にスキーマのスペースで区切られた一覧です。  
  
-   -f: 場合、指定されたスキーマの一覧がファイルから読み取られる必要があります。  
  
-   リストを含むファイルの名前を NameOfFileContainingSchemaList: です。  
  
    > [!NOTE]
    >  上記のコマンドは、MT、MX、およびカテゴリ 0 ジェネリック コマンドのメッセージ。 この種類のフォームを生成する特定のコマンドがで指定された、以下のセクションでします。
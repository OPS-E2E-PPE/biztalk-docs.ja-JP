---
title: Namespace コンポーネントのテストを実行している |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13768608-ade6-44c0-897f-d417c3408302
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae865e91fd6ff796cb870c71840bde8a95831e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294938"
---
# <a name="running-the-namespace-component-tests"></a>Namespace コンポーネントのテストを実行しています。
次の手順は 4 つのテスト シナリオのすべてを実行する方法を示しています、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Namespace コンポーネント サンプルです。  
  
 **Namespace コンポーネント サンプルのテストのシナリオを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所と送信ポートの URL を指しているソース配布ファイルに適切なサブフォルダーを確認します。 受信場所のサブフォルダー \Source\Samples\Namespace\Test\Filedrop\In とサブフォルダー \Source\Samples\Namespace\Test\Filedrop\Out 送信ポートの URL を指定します。  
  
2.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。  
  
3.  (ESB インストール フォルダーの \Source\Samples\Namespace\Test\Data\ サブフォルダーにあります)、TEST_Add_to_PassThrough.0000.ns.xml をという名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで、コピーの名前を変更します。  
  
4.  \Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。  
  
5.  ESB は、メッセージを取得、名前空間を追加し、\Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに、更新されたメッセージをドロップします。 入力を開き、このテストの結果を確認するためのテキスト エディターでファイルを出力します。  
  
6.  2 つ目のテストを実行します。 TEST_Add_to_Remove.0000.ns.xml をという名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで名前を変更します。  
  
7.  \Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。  
  
8.  ESB は、メッセージを取得、名前空間を追加、新しい名前空間を削除、および \Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに、更新されたメッセージをドロップをします。 入力を開き、このテストの結果を確認するためのテキスト エディターでファイルを出力します。  
  
9. 3 番目のテストを実行します。 TEST_PassThrough_to_Remove.0000.ns.xml をという名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで名前を変更します。  
  
10. \Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。  
  
11. ESB は、メッセージを取得、既存の名前空間を削除し、\Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに、更新されたメッセージをドロップします。 入力を開き、このテストの結果を確認するためのテキスト エディターでファイルを出力します。  
  
12. 最後に、4 つ目のテストを実行します。 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml をという名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで名前を変更します。  
  
13. \Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。  
  
14. ESB は、メッセージを取得で指定された要素を抽出し、 **ExtractionNodeXPath**プロパティがこの要素で指定された名前空間の値からメッセージを作成し、\Source\Samples\ に更新されたメッセージをドロップします。Namespace\Test\Filedrop\Out サブフォルダーです。 入力を開き、このテストの結果を確認するためのテキスト エディターでファイルを出力します。